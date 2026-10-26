# Instruções aos agentes de programação — Codex, Claude Code, Antigravity
Leia README.md e docs/{ARCHITECTURE,METHODOLOGY,MODELS,DATA_SOURCES,ROADMAP}.md antes da tarefa.

## Contrato de trabalho
1. Escolha uma issue e cite `Refs #N` na PR. Uma tarefa coerente por branch; `feat/NN-descricao`, `fix/NN-descricao`, `docs/NN-descricao`.
2. Não altere `main` diretamente nem faça merge sem revisão humana. Não altere metodologias ou modelos silenciosamente: abra ADR e documente impactos.
3. PR deve conter: propósito, arquivos modificados, resultados de testes, limites, riscos científicos, evidências de reconciliação (quando aplicável), comandos de reprodução, referência à issue.
4. Dados de produção são **somente das fontes oficiais**, nunca dados sintéticos apresentados como resultados reais. Fixtures pequenas e sintéticas devem estar claramente rotuladas.
5. Nunca invente URLs de recursos, nomes de colunas, totais de votos, cobertura histórica ou resultados. Descubra fontes, registre versões e valide schemas reais antes da ingestão.
6. M0 precisa reproduzir os totais oficiais TSE (por eleição/turno/cargo/UF e agregação verificável) antes de liberar resultados. Se falhar, interrompa a campanha; não corrija a divergência descartando linhas sem justificativa.
7. Compare primeiro/segundo turno separadamente. Cenários mudam *agregação de votos observados*, não comportamento do eleitor, candidaturas ou regra constitucional real.
8. Seja neutro sobre partidos/candidatos e evite conclusões causais não sustentadas. Separe voto observado, resultados calculados e contrafactuais.
9. Preserve imutabilidade de raw; produza manifestos com origem, licença, timestamp UTC, SHA-256, algoritmo, parâmetros, git SHA e avisos de cobertura.
10. Requisitos: tipos explícitos em API pública, Python 3.12+, pytest + ruff; testes de casos-limite (empate, zero válidos, candidatos ausentes, agregação, período, municípios alterados, precisão).
11. Evite arquivos grandes no Git. Sem segredos, tokens, dados pessoais de eleitor ou acesso externo desnecessário. Não exponha dashboard à internet da universidade por padrão.
12. Prefira DuckDB/SQL e Parquet particionado; processe batch por eleição/turno/UF. A primeira execução deve caber em 12 GiB RAM com limite configurável.

## Definição de pronto
Critérios de aceite da issue cumpridos; testes automatizados verdes; documentação e changelog quando relevantes; evidência de testes sobre fixtures e/ou dados oficiais; PR pronta para revisão. Não declarar etapas concluídas só por ter criado esqueleto.
