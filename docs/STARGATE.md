# Operação no Stargate (planejada, não implantada)
## Topologia inicial
Usar `stargate-console` (aprox. 12 GiB RAM) para batch e armazenamento persistente em `/data/projects/brazil-electoral-simulations`. `stargate-master` coordena serviços leves; nós de processamento só após benchmark justificar distribuição. Confirme CPU, discos, Docker, permissões e conectividade local antes de implantar.

## Configurações iniciais
DuckDB: `memory_limit=6GB`, `threads=4`, diretório temporário em volume persistente com espaço disponível. Parquet por `year/round/uf`. Preferir execução offline após baixar fontes; não depender de acesso externo da rede institucional.

## Segurança
Sem portas abertas para internet; interface Streamlit restrita à intranet e com autenticação/proxy se for exposta; containers sem privilégios, volumes raw somente leitura quando possível, limites de memória, backups e logs. Não comprometer outros serviços do cluster.

## Plano de implantação (issue dedicada)
1. Preparar ambiente e `compose.yaml` com limites/volumes e healthcheck.
2. Rodar fixtures e smoke test local, checar saída e uso de recursos.
3. Download controlado dos recursos oficiais para raw.
4. Executar reconciliação, campanha e benchmark.
5. Gerar relatório de reprodução e plano de recuperação.
