# SYN.POLIS 2026 · PRÉ-REGISTRO DO 2º TURNO
**synBe the lab · escrito e selado em 12/10/2026, ANTES de qualquer rodada do 2º turno.**
Este documento fixa como o número final será calculado. Ele é selado no Bitcoin antes das rodadas; o relatório do 2º turno, selado depois, só pode usar a regra abaixo.

## 1. O que mudou depois do 1º turno (lição registrada)
No 1º turno (selo de 20/09), o motor calibrado partia das pesquisas como se fossem a preferência real e herdou o erro delas (Flávio subestimado em 3,6pp). O motor orgânico, lido contra controle, acertou o líder. Para o 2º turno:
- **Âncora = voto REAL do 1º turno** (TSE, 100% apurado, por região), não pesquisa.
- Pesquisas de 2º turno entram só como cenário alternativo declarado, não como âncora.

## 2. As rodadas (definidas antes de rodar)
- **(A) Motor numérico:** 50 rodadas (seeds 1–50), população de 4.000 iniciada no resultado oficial do 1º turno por região; 13 dias simulados (13/10 → urna 25/10); urna restrita a Flávio × Lula.
- **(B) Motor orgânico:** 800 eleitores-espelho estratificados (seed 1), cada um começando com o próprio voto do 1º turno e pensando via LLM os 13 dias de campanha; eventos datados da campanha real até 12/10 e agenda conhecida (debates 15, 18 e 23/10).
- **(C) Controle do orgânico:** mesma população, mesmos 13 dias, sem eventos.

## 2.1 Reprodutibilidade
Corrigido em 12/10, antes das rodadas: a rejeição individual usava `hash()` do Python, que muda a cada execução. Agora usa CRC32 (determinístico): mesma seed, mesmo resultado no motor numérico. O orgânico depende da LLM e não é determinístico; por isso tem rodada de controle.

## 2.2 Calibração antes das rodadas oficiais
A população reproduz o 1º turno real (checagem em `rodadas/2026-t2-numerico.json`). A rejeição das pesquisas (Lula 46 / Flávio 43) mandava 37% da terceira via para branco/nulo, contra 15% medidos (Datafolha 06–08/10). A rejeição foi calibrada contra essa transferência observada (grade em `motor/calibrar_t2.py`): Lula 0,35 / Flávio 0,22 → transferência simulada 49,7 / 34,4 / 15,9 contra 49,5 / 34,4 / 16,1 observada.

## 2.3 Modelos de IA
O `mistral-nemotron` (usado no 1º turno) foi desligado pela NVIDIA em 28/09/2026. No 2º turno o orgânico usa Nemotron Super 120B (julgamentos), Gemma 4 31B e Nemotron Lightning 30B (volume). A troca de modelo muda a deriva própria da IA; por isso a leitura é sempre contra a rodada de controle, que usa os mesmos modelos.

## 3. REGRA DE CONSOLIDAÇÃO (o número que vale)
1. **Orgânico corrigido** = ponto de partida + **lift**, onde ponto de partida = média do `dia0` das 50 rodadas de (A) (votos válidos do 2º turno implicados pela população iniciada no 1º turno real, antes de qualquer dia de campanha) e lift = urna de (B) − urna de (C).
2. **Número consolidado do 2º turno = média simples, pesos iguais, de (A) média das 50 rodadas e (B) orgânico corrigido**, em % dos votos válidos de Flávio e de Lula.
3. O relatório selado traz: o consolidado, (A), (B) bruto, (C), o lift, os números por região, e o cenário alternativo ancorado nas pesquisas — com as contas.
4. **Nenhuma outra combinação** (outra média, outro peso, um motor só) será apresentada como "nossa previsão" depois de 25/10.

## 3.1 Adendo de 13/10/2026 (escrito DEPOIS da 1ª rodada orgânica e ANTES da 2ª)
A 1ª rodada orgânica (seed 1) terminou em 13/10: oficial Flávio 49,1; controle Flávio 59,6; lift −10,5; consolidado pela regra Flávio 47,1 × Lula 52,9 (`rodadas/t2-consolidacao.json`). Dois sinais de instabilidade foram vistos: no controle, 20% dos eleitores de Lula no 1º turno migraram para Flávio sem nenhum evento; na oficial, a terceira via foi 51% Lula / 42% Flávio, contra 46% Flávio / 32% Lula medidos pelo Datafolha.
Decisão: rodar uma 2ª seed (oficial + controle, seed 2), mesmas configs e código. Regra, fixada antes de rodar:
- **lift final = média simples dos lifts das seeds 1 e 2**; o orgânico corrigido e o consolidado seguem a seção 3 com esse lift.
- As duas seeds são publicadas integralmente, inclusive a 1ª e o consolidado que ela daria sozinha.
- Nenhuma 3ª seed será rodada.

## 4. Registro das leituras derivadas do 1º turno (publicadas em 04/10, fora do selo de 20/09)
Publicadas no dia da eleição, com a apuração já em andamento. Não estavam no selo de 20/09; são médias dos números selados.
- 1º turno: "Flávio 43,4% × Lula 42,1%" (urna: 47,03 × 45,16; líder certo; erro de margem −0,6pp).
- 2º turno: "se Flávio vencer o 1º turno, Flávio 51,7% × Lula 48,3%; se Lula vencer, Lula 52,4% × Flávio 47,6%". O cenário Flávio usou uma suposição feita em 04/10 (efeito-manchete simétrico), não selada.

## 5. Arquivos congelados junto com este pré-registro
Configs e código das rodadas, com hash em `docs/MANIFESTO-PRE-REGISTRO-T2.sha256` (selado junto): `rodadas/2026-t2.json`, `rodadas/2026-t2-controle.json`, `motor/t2.py`, `motor/organico.py`, `motor/motor.py`, `motor/llm.py`, `dados/2026/resultado-t1-oficial.json`, `dados/2026/segundo-turno-pesquisas-fatos.md`.

*synBe the lab · 12/10/2026*
