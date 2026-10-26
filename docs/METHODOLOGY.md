# Protocolo científico
## Natureza do experimento
Retrospectivo e **contrafactual mecânico**: votos observados permanecem fixos; apenas a regra de agregação/ponderação muda. Não estimar preferência individual, causalidade ou resultado de eleição efetiva sob novas regras. Não confundir maioria de seções com maioria de eleitores.

## Unidade, distribuição e decisão
Para unidade territorial i e candidato c, votos v_ic e total válido V_i = sum_c v_ic; p_ic=v_ic/V_i quando V_i>0.
- Proporcional: S_c = sum_i w_i p_ic.
- Vencedor integral: S_c = sum_i w_i 1[c = argmax_k(v_ik)] com política explícita de empate.
- Oficial M0: S_c = sum_i v_ic, sem normalização territorial.
Pesos não podem ser negativos nem não finitos; documentar denominadores, desempates e exclusões.

## Pesos econômicos
Avaliar w_i = P_i^alpha * G_i^beta * R_i^gamma * I_i^delta após padronização apropriada e registro das unidades. Para comparar escalas, normalizar pesos entre municípios (a normalização comum não altera a ordem). Para PIB per capita, usar indicador separado, não interpretar PIB total como riqueza domiciliar.
- Idealmente usar ano-base *anterior ao pleito* e disponível então; análises com indicador posterior explicitadas como retrospectivas e analisadas separadamente.
- Deflacionar valores monetários quando a comparação temporal necessitar e especificar índice/base.
- Receitas de transferência e receita própria são categorias distintas; população e eleitorado também.
- Dados REGIC observados em anos específicos não representam uma série anual.

## Qualidade
1. Baixar e registrar artefatos/fontes/data/hash.
2. Inferir/validar schema real de cada eleição e cobertura por nível.
3. Somar e reconciliar M0 contra total oficial por recortes verificáveis, documentando diferenças/causas.
4. Definir pré-registro dos modelos, combinações de parâmetros e política de empate antes de analisar inversões.
5. Executar estudos de sensibilidade a missingness, proxies, ano-base, amostras e unidade; não preencher dados ausentes silenciosamente.
6. Comparar eleições separadamente por turno; no primeiro turno, liderança não equivale a eleição sem verificar condições legais.
7. Publicar tabelas de inversão de ordenação, margens, cobertura, razão de peso efetivo por eleitor, concentração e estabilidade.
8. Relatar limitações e evitar linguagem de defesa normativa de voto baseado em riqueza.

## Empates e seções agregadas
A regra de tratamento de empate é versionada por cenário: dividir pontos igualmente, empates não decididos ou regra secundária explicitamente escolhida. A política padrão será definida por ADR; não usar sorteio implícito. Boletins/seções agregadas devem ser associados sem duplicação.

## Ética
Nenhum modelo alternativo pretende substituir apuração constitucional. Evitar inferências sobre eleitores individuais, voto secreto ou suposta fraude a partir de divergência entre modelos.
