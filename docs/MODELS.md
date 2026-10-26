# Catálogo de modelos (especificações preliminares)
Todos os modelos são **hipóteses**, não leis vigentes; antes da implementação de cada um registrar (a) unidade, (b) função peso, (c) distribuição, (d) decisão, (e) empate, (f) casos sem dados.

| ID | Modelo | Unidade | Peso/distribuição proposta |
|---|---|---|---|
| M0 | Oficial | voto | soma dos votos válidos nominais |
| M1 | Municípios | município | 1 ponto integral ao mais votado |
| M2 | Zonas | zona eleitoral | 1 ponto integral |
| M3 | Seções | seção eleitoral | 1 ponto integral |
| M4 | Estados | UF | 1 ponto integral |
| M5 | Colégio estadual | UF | delegados predefinidos, integral |
| M6 | Delegados proporcionais | UF | delegados predefinidos, proporcional |
| M7 | Município ponderado | município | peso por eleitorado/população, declarar escolha |
| M8 | Faixas municipais | município | faixas de tamanho declaradas |
| M9 | Híbrido territorial-popular | múltipla | combinação parametrizada |
| M10 | PIB total | município | PIB total |
| M11 | PIB per capita | município | PIB / população |
| M12 | Receita orçamentária | município | receita orçamentária |
| M13 | Receita tributária própria | município | arrecadação própria |
| M14 | Receita própria per capita | município | arrecadação própria / população |
| M15 | Agropecuária | município | VAB agropecuário (se disponível) |
| M16 | Indústria | município | VAB industrial (se disponível) |
| M17 | Serviços | município | VAB serviços (se disponível) |
| M18 | Influência urbana | cidade/município | indicador REGIC mapeado |
| M19 | Índice econômico composto | município | pesos compostos auditáveis |
| M20 | PIB × população | município | função explícita de PIB e população |
| M21 | PIB × representação territorial | município | vencedor integral com peso econômico |
| M22 | Ponderação econômica limitada | município | pesos econômicos com teto parametrizado |
| M23 | Ponderação logarítmica | município | log(1 + PIB na unidade especificada) |

## Matriz de experimentos
Cada modelo deve declarar versões **proporcional** e/ou **winner-take-all** quando matematicamente compatíveis. Não assumir que M10–M20 usam automaticamente winner-take-all: a dimensão `allocation` é independente de `weight`.

Configuração mínima de um run: election_year, round, office, unit, allocation, weight_model, indicators_year, missing_policy, tie_policy, parameters, dataset_version, code_sha.

## Casos de teste
Empate, votos zero, candidato ausente, voto branco/nulo, seção agregada, UF com poucos municípios, peso zero, outliers de PIB, receita inexistente, códigos municipais alterados, números grandes, reprodutibilidade. Nunca somar seções duplicadas.
