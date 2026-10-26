# Roadmap por dependências (não por datas presumidas)
| Fase | Objetivo | Gate de conclusão |
|---|---|---|
| F0 | Governança, decisões e bootstrap | README, AGENTS, CI, pacote instalável, fixtures e testes |
| F1 | TSE 2022 | Inventário, download, normalização e M0 **reconciliado** em dois turnos |
| F2 | Modelos territoriais M1–M9 | Resultados determinísticos, empates e métricas testados |
| F3 | 2026 e séries 2002–2018 | Schemas por eleição validados, lacunas documentadas |
| F4 | PIB, finanças e REGIC | Crosswalks e ano-base com cobertura/qualidade publicados |
| F5 | M10–M23 e sensibilidade | Fórmulas/testes, missingness e métricas de equidade |
| F6 | Mapas, dashboard e Stargate | Docker Compose funcional em intranet, batch benchmark |
| F7 | Auditoria/publicação científica | Manifestos, relatório reproduzível e revisão externa |

## Política de PR
Uma issue por PR, dependências explícitas. `main` deve permanecer estável; não mergear trabalhos só porque compilaram. CI sem dados externos por padrão; smoke e campanhas reais são jobs manuais controlados. Toda simulação depende de gate M0.

## Primeira entrega útil
CLI capaz de ingerir TSE 2022, processar 1º/2º turno, reconciliar M0 e calcular M1/M2/M3/M4 sobre fixtures e dados reais, com exportação CSV/Parquet + manifesto.
