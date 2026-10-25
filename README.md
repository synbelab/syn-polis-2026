# syn.Polis 2026 · antecipação selada da eleição presidencial

**synBe the lab.** Dois documentos registrados no Bitcoin antes de cada turno e abertos depois da eleição. Este repositório guarda os documentos, as provas e os dados das rodadas, para qualquer pessoa conferir.

Não prevemos o futuro, antecipamos os futuros possíveis.

## Os selos

| | 1º turno | 2º turno |
|---|---|---|
| Documento | [`docs/RELATORIO-SELADO-2026.md`](docs/RELATORIO-SELADO-2026.md) | [`docs/RELATORIO-SELADO-T2-2026.md`](docs/RELATORIO-SELADO-T2-2026.md) |
| SHA-256 | `fa13d160a7f3cac99a5047671f4a66e693d848e061a7dc8fe3286e228b314f07` | `e30138adf67769776099396225b6e866ce6ba8ad2d30c05821ada96aff76d34c` |
| Primeiro bloco Bitcoin | 967825 · 20/09/2026, 09h19 (Brasília) | 971279 · 13/10/2026, 14h34 (Brasília) |
| Prova OpenTimestamps | `docs/RELATORIO-SELADO-2026.md.ots` | `docs/RELATORIO-SELADO-T2-2026.md.ots` |

## Como conferir em 1 minuto, sem instalar nada
1. Baixe o documento (`.md`) e a prova (`.ots`) da pasta `docs/`.
2. Abra **https://opentimestamps.org** e arraste os dois arquivos.
3. O site confirma o bloco do Bitcoin em que o documento foi registrado. Se o documento tivesse uma vírgula diferente, a verificação falharia.

## Como conferir pelo terminal
```bash
shasum -a 256 -c docs/RELATORIO-SELADO-2026.sha256
shasum -a 256 -c docs/RELATORIO-SELADO-T2-2026.sha256
shasum -a 256 -c docs/MANIFESTO-SELADO-2026.sha256
shasum -a 256 -c docs/MANIFESTO-SELADO-T2-2026.sha256
pip install opentimestamps-client && ots verify docs/RELATORIO-SELADO-T2-2026.md.ots
```
Os dois manifestos listam o hash de cada arquivo de dados e de código das rodadas, e também estão selados (`.ots` ao lado). Assim, os dados de cada rodada ficam amarrados ao mesmo registro no Bitcoin.

## O que há aqui
- `docs/`: os relatórios selados, as provas `.ots`, os hashes e os manifestos.
- `dados/`: a população de 4.000 eleitores sintéticos (sem nenhum dado pessoal real), as fontes de cada turno e o resultado oficial do 1º turno.
- `rodadas/`: as saídas de todas as rodadas, inclusive as descartadas, declaradas na seção 6 do relatório do 2º turno.
- `RETIDOS.md`: os dois arquivos de código retidos por propriedade intelectual, com o hash de cada um.

## Nota sobre os arquivos
Os arquivos de `docs/`, `dados/` e `rodadas/` estão exatamente como foram selados. Nenhum foi editado depois do registro, nem para corrigir digitação, porque qualquer mudança quebraria a verificação. O `.gitattributes` impede o Git de converter fim de linha nessas pastas.

O motor de IA do lab é o **syn.Mind 1.6**: a base de linguagem, o protocolo syn.Opsis, a população com fatos reais e a medida por semelhança de sentido, versionados juntos.
