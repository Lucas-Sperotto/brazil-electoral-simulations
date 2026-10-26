# Brazilian Electoral Counterfactuals
**Simulações Contrafactuais de Sistemas Eleitorais Brasileiros**

Projeto científico, aberto e apartidário de análise reprodutível de resultados das eleições presidenciais brasileiras sob regras hipotéticas de agregação e ponderação territorial, demográfica, econômica e fiscal.

> **Status:** planejamento e arquitetura (não há resultados empíricos validados nem pipelines de produção nesta versão). Resultados simulados **não** são resultados oficiais nem preveem como pessoas votariam sob outras regras.

## Questões de pesquisa
- A classificação dos candidatos mudaria se cada seção, zona, município ou estado tivesse o mesmo peso?
- Qual o efeito de delegados estaduais, PIB, PIB per capita, receitas, arrecadação própria e centralidade urbana?
- Quais modelos ampliam ou reduzem a desigualdade de peso por eleitor?
- Quão robustas são as diferenças ao variar parâmetros, ano-base econômico e regra de desempate?

## Escopo
Eleições presidenciais de 2002, 2006, 2010, 2014, 2018, 2022 e 2026, por turno, observando cobertura e consolidação de cada fonte. Prioridade da primeira execução: **2022 (1º e 2º turnos)**; 2026 entra após validação dos artefatos disponíveis.

## Arquitetura proposta
Python 3.12+ · DuckDB · Parquet · Polars · Pytest · Ruff · GeoPandas · Plotly/Streamlit. Execução batch no Stargate, inicialmente mononó no stargate-console; sem Kubernetes/Spark na fase inicial.

[Arquitetura](docs/ARCHITECTURE.md) · [Metodologia](docs/METHODOLOGY.md) · [Modelos M0–M23](docs/MODELS.md) · [Fontes de dados](docs/DATA_SOURCES.md) · [Roadmap](docs/ROADMAP.md) · [Stargate](docs/STARGATE.md) · [Política para agentes](AGENTS.md)

## Ciclo de trabalho
1. Descobrir/registrar dataset oficial, ano e versão; baixar para `data/raw` fora do Git.
2. Verificar hash, schema e granularidade; harmonizar códigos; construir Parquet por eleição/turno/UF.
3. **Reconciliar M0** com a totalização do TSE antes de publicar simulações.
4. Executar modelos versionados com configurações fixas e sementes quando necessárias.
5. Exportar tabelas, gráficos e relatórios com manifesto de proveniência.

## Fontes oficiais
- TSE: https://dadosabertos.tse.jus.br/
- IBGE PIB municipal: https://www.ibge.gov.br/estatisticas/economicas/contas-nacionais/9088-produto-interno-bruto-dos-municipios.html
- Tesouro FINBRA/Siconfi: https://siconfi.tesouro.gov.br/
- IBGE REGIC: https://www.ibge.gov.br/geociencias/organizacao-do-territorio/redes-e-fluxos-geograficos/15798-regioes-de-influencia-das-cidades.html

## Colaboração
Consulte [CONTRIBUTING.md](CONTRIBUTING.md), escolha uma issue com critérios de aceite e abra PR pequena. Codex, Claude Code e Antigravity devem ler [AGENTS.md](AGENTS.md) antes de alterar código. Não envie dados brutos, credenciais ou resultados sem validação ao Git.

## Licença
Código MIT (arquivo LICENSE). Dados oficiais mantêm atribuições e condições próprias. Citações acadêmicas serão descritas em CITATION.cff.
