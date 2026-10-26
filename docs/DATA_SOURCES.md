# Catálogo e proveniência dos dados
## TSE — resultados e eleitorado
https://dadosabertos.tse.jus.br/
Dataset 2026: https://dadosabertos.tse.jus.br/dataset/resultados-2026
Pesquisar recursos específicos e testar schema dos anos 2002–2026; disponibilidade, granularidade e campos variam por eleição. Preferir votos por seção quando houver cobertura, com totalizações municipais/UF para auditoria independente. Não assumir arquivos de 2026 definitivamente homologados; registrar momento da extração e atualizações.

## IBGE — PIB e geografia
PIB dos Municípios: https://www.ibge.gov.br/estatisticas/economicas/contas-nacionais/9088-produto-interno-bruto-dos-municipios.html
Malhas territoriais e estimativas de população: consultar catálogo oficial e fixar versão/ano.
PIB e VAB têm cobertura/séries distintas: registrar por indicador; não extrapolar até 2026 sem regra explícita.

## Tesouro — FINBRA / Siconfi
https://siconfi.tesouro.gov.br/
Identificar rubricas por plano de contas, exercício fiscal, regime e classificação; receitas totais e próprias são diferentes. Tratar cobertura faltante e revisões.

## IBGE — REGIC
https://www.ibge.gov.br/geociencias/organizacao-do-territorio/redes-e-fluxos-geograficos/15798-regioes-de-influencia-das-cidades.html
A centralidade é medida em edições discretas, não uma série anual contínua.

## Manifesto obrigatório
```yaml
source: TSE|IBGE|TESOURO
resource_url: https://...
downloaded_at_utc: ...
sha256: ...
license_or_terms: ...
year: ...
coverage: ...
schema_version: ...
transformation_git_sha: ...
reconciliation_status: pending|passed|failed
```
Nenhuma URL dinâmica de arquivo deve ser inventada. Criar inventário de recursos com links reais confirmados e snapshots dos metadados do catálogo.
