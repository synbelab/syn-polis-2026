# SYN.POLIS 2026 · ANTECIPAÇÃO SELADA DA ELEIÇÃO PRESIDENCIAL
**synBe the lab · Documento fechado em 20/09/2026 — 14 dias antes do 1º turno (04/10) e 35 dias antes do 2º (25/10).**
**Este documento foi registrado por hash em blockchain antes da eleição e revelado depois dela. Nenhum número foi alterado após o registro.**

---

## O que afirmamos — em ordem de confiança

### 1. O segundo turno será LULA × FLÁVIO BOLSONARO — confiança alta
Em 100% das 50 rodadas do motor calibrado, na rodada orgânica oficial e na rodada de controle, os mesmos dois nomes foram ao 2º turno. A terceira via (Caiado, Renan, Zema, Cury) é esmagada pelo voto útil na reta final em todos os futuros simulados.

### 2. A liderança do 1º turno está genuinamente em disputa — e a crise do STF é o motivo
Os dois motores independentes divergem exatamente aqui, e a divergência é a informação:
- **Motor calibrado** (validado na eleição de 2022): **Lula 45,9% × Flávio 43,4%** dos válidos (dp 0,5pp em 50 rodadas).
- **Motor orgânico** (800 eleitores sintéticos pensando via IA, lido contra controle): **Flávio 43,4% × Lula 38,3%** — o efeito medido da crise STF×Moraes×Banco Master foi **+4,1pp para Flávio e −4,3pp para Lula** sobre a âncora das pesquisas.
- Leitura consolidada: **1º turno entre empate técnico e vantagem Flávio**, com Cury em ~4–6% herdando parte da terceira via.

### 3. O 2º turno está no fio — e o momentum do 1º turno vale ~4 pontos
- Motor calibrado: **Lula 50,9% × Flávio 49,1%** (Lula vence 47 de 50 futuros; Flávio vence 3).
- Motor orgânico: o experimento oficial×controle isolou um **efeito-manchete de +4,0pp para quem vence o 1º turno** (bandwagon do resultado).
- Leitura consolidada: **~50×50, com o vencedor do 1º turno levando vantagem de ~4pp para 25/10.** Nenhum método honesto crava vencedor com essa margem — quem cravar está chutando.

### 4. O mapa regional (motor calibrado, média de 50 rodadas do 2º turno)
| Região | Resultado |
|---|---|
| Nordeste | Lula 67,8% |
| Norte | Flávio 51,1% |
| Sudeste | Flávio 53,9% |
| Centro-Oeste | Flávio 59,7% |
| Sul | Flávio 60,1% |

A eleição de Lula depende de UMA região compensar quatro. Abstenção projetada: ~21%.

### 5. Condicionais registradas (o que muda o quadro)
- STF decidir **investigar Moraes** antes de 01/10 → amplifica o efeito pró-Flávio do item 2.
- Julgamento **arquivado/esfriado** → devolve o 1º turno ao empate da âncora.
- Escândalo do financiamento da campanha de Flávio (caso Vorcaro/“Dark Horse”/Vance) virar caso criminal → reverte parte do lift.
- Ausência de Lula nos debates de 27/09 e 01/10 → soma ao lift de Flávio.

---

## Como foi feito (resumo auditável)

**População.** 4.000 eleitores sintéticos nas cotas oficiais do eleitorado (TSE jul/2026: região, sexo, idade; IBGE/Censo 2022: religião×região×idade, raça, urbano/rural; PNAD: renda), cada um com história de vida, tensão íntima, dieta de mídia e voto 2022 calibrado ao resultado oficial por região. Nenhum dado pessoal real: microdados públicos agregados.

**Motor calibrado (numérico).** Dinâmica diária de conversas com homofilia regional, espiral do silêncio (Noelle-Neumann), voto útil (Granovetter), momentum pós-urna. **Validação: backtest cego da eleição de 2022** — acertou vencedor, par do 2º turno e vencedor final em 50 de 50 rodadas virgens; erro médio de 2,6pp no 1º turno, 1,9pp no 2º; reproduziu o erro-das-pesquisas de 2022 (subestimação do declarado) pelo mecanismo. Paridade 90–96% por candidato.

**Motor orgânico (IA).** 800 eleitores-espelho estratificados pensando individualmente via LLM (NVIDIA Nemotron/Mistral): julgam cada fato da campanha em persona, conversam, refletem e votam em urna secreta simulada — nenhuma fórmula escreve opinião. Lido **contra rodada de controle** (mesma população, zero eventos) para descontar a deriva do modelo, protocolo validado pelo lab no backtest Domino's 2009/2010. Registro de honestidade: sem o controle, o modelo deriva sozinho +9pp pró-Lula em 37 dias; medimos e descontamos.

**Âncoras.** Mediana de 8 institutos com campo em 09–16/09/2026 (pivô Datafolha 15–16/09, BR: Lula 39×36; 2º turno ~empate). Fatos injetados com fonte: crise do STF (linha do tempo 27/08–15/09), indeferimento de Marçal (TSE, 11/09), agenda de debates, deflação de agosto, comício de Sobral (24/09).

**Limitações declaradas.** (a) Método validado contra uma única eleição real (2022); (b) as intensidades dos eventos da reta final são estimativas do lab, mitigadas pela leitura em cenários; (c) âncoras regionais derivadas de 2022+swing por ausência de crosstab regional publicado em setembro; (d) resultados dentro de margem de erro não permitem cravar vencedor — este documento não crava.

**Custo de execução das rodadas: R$ 0** (motor local + API gratuita NVIDIA Inception). O investimento foi feito na construção: personas e calibração.

---

## Arquivos que compõem esta antecipação (hasheados junto)
`rodadas/2026-retafinal.json` · `rodadas/2026-retafinal-distribuicao.json` · `rodadas/organico-2026-retafinal-n800-s1/` · `rodadas/organico-2026-controle-n800-s1/` · `rodadas/organico-leitura-final.json` · `rodadas/backtest2022-validacao.json` · `dados/2026/pesquisas-setembro.md` · `dados/2026/fatos-setembro.md` · `dados/amostra-4000.json`

*syn.Polis: reduzir a incerteza sobre o futuro, não prever. — synBe the lab, 20/09/2026*
