# Arquitetura — decisão inicial
## Objetivo
Motor batch reprodutível, baixo consumo de RAM, desacoplado da UI e executável no Stargate e em PCs comuns.

## Camadas
- `ingestion`: inventário/download com licença, URL, timestamp, hash e formato; arquivos raw imutáveis.
- `validation`: checagem de schema, totais, cobertura, duplicatas e reconciliador M0/TSE.
- `harmonization`: ano/turno/cargo/candidato/município/zona/seção; chaves canônicas, mudanças históricas, tipos.
- `indicators`: tabelas econômicas e demográficas versionadas, deflator/ano-base quando aplicável, flags de dados ausentes.
- `models`: registro de M0–M23, fórmulas explícitas e desempates.
- `simulation`: execução determinística por campanha/modelo, batch e cache.
- `metrics`: inversão, margens, representação por eleitor, sensibilidade e cobertura.
- `reporting`: Parquet/CSV, gráficos/relatórios, manifesto; `dashboard` lê apenas curated/results.

## Layout-alvo
```text
configs/{sources,models,elections}.yaml
src/electoral_simulations/{ingestion,validation,harmonization,indicators,models,simulation,metrics,geography,reporting,cli.py}
dashboard/
tests/{unit,integration,scientific}/
data/{raw,staging,curated,results}/    # dados ignorados pelo Git
docs/
```
## Regras
- Dataset canônico de votos por ano, turno, cargo, UF, código municipal TSE/IBGE mapeado, zona, seção, candidato e votos válidos.
- Guarde sempre identificadores originais e versão de tabela de correspondência IBGE/TSE; não suponha identidade entre códigos.
- Unidades sem eleitores/votos válidos e votos não nominais têm regra explícita; candidatos não encontrados não são zero presumido.
- DuckDB lê Parquet particionado `year=YYYY/round=N/uf=XX/`, com `memory_limit` e `threads` configuráveis.
- Sem API online na fase MVP; UI Streamlit lê artefatos imutáveis.
- Motor puro sem dependência de Streamlit, facilitando testes e execução CLI.
## Decisões pendentes
ADR para pesos de delegados, empate e limites constitucionais de cada simulação; ver docs/METHODOLOGY.md.
