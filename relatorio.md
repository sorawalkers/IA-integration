# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --fights 300 --out relatorio.md` em 2026-11-18T19:46:55.296Z · commit `45a9c11`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

Linha de base **[Mago, Bardo, Guerreiro]** contra ghosts da **sala 3**: 25.0% de vitória, 16.0s por luta (300 lutas por variante).

## Classes (média nas 512 composições; delta = diferença para a média geral)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Ladino | sug. Meio | 34.4% | +5.5pp | 0.7 | ▲ forte | melhor: Meio · Retaguarda 33% · Meio 49% · Vanguarda 22% |
| Alquimista | sug. Retaguarda | 31.2% | +2.2pp | 0.7 |  | melhor: Retaguarda · Retaguarda 35% · Meio 28% · Vanguarda 30% |
| Bárbaro | sug. Vanguarda | 30.1% | +1.2pp | 0.7 |  | melhor: Vanguarda · Retaguarda 25% · Meio 26% · Vanguarda 40% |
| Mago | sug. Retaguarda | 28.7% | -0.2pp | 0.7 |  | melhor: Retaguarda · Retaguarda 38% · Meio 33% · Vanguarda 15% |
| Patrulheiro | sug. Retaguarda | 28.7% | -0.3pp | 0.7 |  | melhor: Retaguarda · Retaguarda 39% · Meio 29% · Vanguarda 18% |
| Guerreiro | sug. Vanguarda | 27.9% | -1.1pp | 0.6 |  | melhor: Vanguarda · Retaguarda 18% · Meio 21% · Vanguarda 45% |
| Bardo | sug. Meio | 27.6% | -1.4pp | 0.6 |  | melhor: Meio · Retaguarda 28% · Meio 32% · Vanguarda 23% |
| Paladino | sug. Vanguarda | 22.9% | -6.0pp | 0.6 | ▼ fraco | melhor: Vanguarda · Retaguarda 15% · Meio 15% · Vanguarda 39% |

## Itens (+1 cópia na party, no melhor herói e posição)

"Com Ladino" / "Sem Ladino": melhor delta nas parties de referência com e sem Ladino. O Combo do Ladino
(+8% de crítico por item diferente encostado na adaga) valoriza qualquer item pequeno; "Sem Ladino" mostra
a utilidade própria do item.

| Variante | Grupo | Vitória | Delta | ± | Com Ladino | Sem Ladino | pp/PO | Veredito | Nota |
|---|---|---|---|---|---|---|---|---|---|
| Machado Grande | advanced | 65.3% | +42.0pp | 2.9 | +5.7pp | +42.0pp | 4.2 (10 PO) | ▲ forte | com Bárbaro · party Patrulheiro/Bardo/Bárbaro · sala 9 (item +1, party evoluída) · melhor em: Bárbaro |
| Bomba Alquímica | basic | 58.0% | +37.7pp | 2.9 | +11.0pp | +37.7pp | 12.6 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Maça | basic | 77.0% | +34.0pp | 2.8 | +7.7pp | +34.0pp | 8.5 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Espada Curta | basic | 74.7% | +31.7pp | 2.7 | +10.0pp | +31.7pp | 7.9 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Adaga | basic | 72.7% | +29.7pp | 2.6 | +4.3pp | +29.7pp | 9.9 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Poção de Vida Menor | basic | 49.0% | +28.7pp | 2.6 | +12.7pp | +28.7pp | 9.6 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Cajado Runado | advanced | 79.7% | +28.0pp | 2.7 | +7.7pp | +28.0pp | 3.1 (9 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Cajado de Aprendiz | basic | 47.7% | +27.3pp | 2.6 | +15.3pp | +27.3pp | 6.8 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Arco Curto | basic | 47.3% | +27.0pp | 2.6 | +9.0pp | +27.0pp | 6.8 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Espada Longa | advanced | 40.0% | +25.7pp | 2.6 | +1.7pp | +25.7pp | 3.2 (8 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Tomo Menor | basic | 50.0% | +25.0pp | 2.7 | +13.3pp | +25.0pp | 6.3 (4 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Mago |
| Ração de Viagem | basic | 66.3% | +23.3pp | 2.5 | +7.7pp | +23.3pp | 11.7 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Tambor de Guerra | basic | 42.7% | +22.3pp | 2.5 | +15.3pp | +22.3pp | 5.6 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Arco Longo | advanced | 34.0% | +19.7pp | 2.4 | +3.0pp | +19.7pp | 2.8 (7 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Pergaminho de Fogo | advanced | 67.7% | +16.0pp | 2.4 | +3.0pp | +16.0pp | 4.0 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Poção de Vida Maior | advanced | 67.3% | +15.7pp | 2.1 | +5.3pp | +15.7pp | 3.1 (5 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Escudo Torre | advanced | 100.0% | +13.0pp | 1.9 | — | +13.0pp | 1.4 (9 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Gema Bruta | basic | 37.7% | +12.7pp | 2.0 | +6.0pp | +12.7pp | 4.2 (3 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Mago |
| Amuleto de Madeira | basic | 32.3% | +12.0pp | 1.9 | +6.7pp | +12.0pp | 4.0 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Paladino |
| Pedra de Amolar | basic | 85.0% | +11.0pp | 1.8 | +11.0pp | +8.0pp | 3.7 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Símbolo Sagrado | advanced | 62.0% | +10.3pp | 1.8 | +4.0pp | +10.3pp | 1.7 (6 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Erva Curativa | basic | 52.7% | +9.7pp | 1.7 | +1.7pp | +9.7pp | 4.8 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Rato de Cripta | basic | 66.7% | +9.3pp | 2.5 | +9.3pp | +6.0pp | 3.1 (3 PO) | ▲ forte | com Patrulheiro · party Patrulheiro/Ladino/Paladino · sala 3 · melhor em: Patrulheiro |
| Gazuas | basic | 63.0% | +9.0pp | 1.8 | +9.0pp | — | 3.0 (3 PO) | ▲ forte | com Ladino · party Mago/Ladino/Guerreiro · sala 3 · melhor em: Ladino |
| Broquel | basic | 82.3% | +8.3pp | 1.7 | +8.3pp | +7.0pp | 2.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Elmo de Ferro | advanced | 59.3% | +7.7pp | 1.9 | +5.7pp | +7.7pp | 1.5 (5 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Rubi Ígneo | advanced | 94.0% | +7.0pp | 1.5 | +0.0pp | +7.0pp | 1.4 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Gibão de Couro | basic | 49.0% | +6.0pp | 1.4 | +6.0pp | +6.0pp | 2.0 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Poção de Mana Menor | basic | 80.0% | +6.0pp | 1.4 | +6.0pp | +0.3pp | 2.0 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Aljava | basic | 80.0% | +6.0pp | 1.4 | +6.0pp | +0.0pp | 2.0 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gema de Mana | advanced | 83.3% | +1.3pp | 0.7 | +1.3pp | +0.3pp | 0.3 (5 PO) |  | party Alquimista/Ladino/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Lobo Cinzento | advanced | 21.0% | -1.0pp | 1.2 | -3.3pp | -1.0pp | -0.1 (10 PO) |  | com Patrulheiro · party Patrulheiro/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Patrulheiro (no lugar de Erva Curativa) |
| Grimório | advanced | — | — | — | — | — | — |  | sem espaço |
| Alaúde dos Ventos | advanced | 87.0% | +0.0pp | 0.0 | — | +0.0pp | 0.0 (12 PO) |  | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo (no lugar de Tambor de Guerra) |

## Encantamentos (em todas as armas)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Flamejante | encantamento | 65.7% | +40.7pp | 2.8 | ▲ forte | em todas as armas |
| Armazenador | encantamento | 65.7% | +40.7pp | 2.9 | ▲ forte | em todas as armas |
| Gélido | encantamento | 63.7% | +38.7pp | 3.0 | ▲ forte | em todas as armas |
| Trovejante | encantamento | 62.7% | +37.7pp | 2.8 | ▲ forte | em todas as armas |
| Afiado | encantamento | 56.0% | +31.0pp | 2.7 | ▲ forte | em todas as armas |
| Mortal | encantamento | 52.7% | +27.7pp | 2.6 | ▲ forte | em todas as armas |
| Defensor | encantamento | 52.0% | +27.0pp | 2.6 | ▲ forte | em todas as armas |
| Veloz | encantamento | 50.0% | +25.0pp | 2.8 | ▲ forte | em todas as armas |
| Vorpal | encantamento | 44.3% | +19.3pp | 2.8 | ▲ forte | em todas as armas |
| Vampírico | encantamento | 42.7% | +17.7pp | 2.2 | ▲ forte | em todas as armas |

## Fusão: item +1 contra 2 cópias +0

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Tambor de Guerra +1 | Arma/Instrumento | 57.0% | +13.3pp | 2.1 | ▲ forte | vs 2x Tambor de Guerra: 44% · no Guerreiro |
| Arco Curto +1 | Arma/Instrumento | 76.3% | +8.7pp | 2.3 | ▲ forte | vs 2x Arco Curto: 68% · no Guerreiro |
| Poção de Vida Menor +1 | Consumível | 49.7% | +2.3pp | 1.0 |  | vs 2x Poção de Vida Menor: 47% · no Mago |
| Gibão de Couro +1 | Armadura | 38.0% | +2.0pp | 0.9 |  | vs 2x Gibão de Couro: 36% · no Mago |
| Broquel +1 | Armadura | 35.0% | +1.7pp | 0.7 |  | vs 2x Broquel: 33% · no Mago |
| Espada Curta +1 | Arma/Instrumento | 69.0% | +1.3pp | 2.6 |  | vs 2x Espada Curta: 68% · no Guerreiro |
| Amuleto de Madeira +1 | Catalisador | 29.7% | +1.3pp | 0.7 |  | vs 2x Amuleto de Madeira: 28% · no Guerreiro |
| Pedra de Amolar +1 | Catalisador | 32.3% | +0.7pp | 0.7 |  | vs 2x Pedra de Amolar: 32% · no Bardo |
| Adaga +1 | Arma/Instrumento | 65.0% | -0.3pp | 2.7 |  | vs 2x Adaga: 65% · no Guerreiro |
| Gema Bruta +1 | Catalisador | 53.0% | -3.7pp | 1.1 | ▼ fraco | vs 2x Gema Bruta: 57% · no Mago |
| Maça +1 | Arma/Instrumento | 65.0% | -6.0pp | 2.6 | ▼ fraco | vs 2x Maça: 71% · no Guerreiro |
| Cajado de Aprendiz +1 | Arma/Instrumento | 54.3% | -7.7pp | 2.2 | ▼ fraco | vs 2x Cajado de Aprendiz: 62% · no Bardo |
| Poção de Mana Menor +1 | Consumível | 25.3% | +0.0pp | 0.0 |  | vs 2x Poção de Mana Menor: 25% · no Mago |
| Erva Curativa +1 | Catalisador | 32.7% | +0.0pp | 0.0 |  | vs 2x Erva Curativa: 33% · no Guerreiro |

_Tempo de simulação: 69.3s._

---

## Escalonamento das classes (sala 3, sala 9, sala 18)

512 composições por sala, 80 lutas por composição. Jogador e ghost evoluem igual:

| Sala | Itens extras | Fusão | Encantamentos |
|---|---|---|---|
| 3 | 2 | +0 | 0 |
| 9 | 6 | +1 | 1 |
| 18 | 12 | +2 (25% +3) | 3 |

Melhor posição de cada classe · vitória nela · (média geral nas 512 composições)

| Classe | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | Vanguarda 44% (28%) | Vanguarda 44% (30%) | Vanguarda 45% (37%) |
| Paladino | Vanguarda 38% (23%) | Vanguarda 35% (22%) | Vanguarda 41% (30%) |
| Bárbaro | Vanguarda 39% (30%) | Vanguarda 37% (28%) | Vanguarda 43% (37%) |
| Bardo | Meio 31% (27%) | Meio 34% (31%) | Vanguarda 41% (40%) |
| Ladino | Meio 48% (34%) | Meio 46% (35%) | Meio 41% (38%) |
| Patrulheiro | Retaguarda 39% (28%) | Retaguarda 33% (26%) | Retaguarda 38% (33%) |
| Mago | Retaguarda 38% (29%) | Meio 52% (42%) | Meio 68% (57%) |
| Alquimista | Retaguarda 35% (31%) | Retaguarda 42% (38%) | Retaguarda 51% (48%) |
| **Diferença** | **17 pp** | **19 pp** | **31 pp** |
| **Duração média da luta** | 18.8s | 14.9s | 13.0s |

_Tempo de simulação: 119.6s._

---

## Diagnóstico das classes — sala 18

300 lutas por classe, na melhor posição; os outros 2 heróis são sorteados entre as 8 classes.

### Desempenho do herói da classe

Dano = dano direto dos golpes (sem Veneno/Queimadura, que não têm dono no registro). "Golpes com DOT" = golpes que aplicaram Veneno ou Queimadura. Escudo e cura = gerados pelos itens do herói (para qualquer aliado).

| Classe | Posição | Vitória | Tempo vivo | Morre primeiro | Dano/luta | % do dano da party | Dano/s vivo | Golpes/luta | Golpes com DOT | Escudo/luta | Cura/luta |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Guerreiro | Vanguarda | 46% | 10.4s de 15.3s (68%) | 36% | 1116 | 31% | 107.6 | 20.5 | 1.0 | 14 | 814 |
| Paladino | Vanguarda | 43% | 11.7s de 15.6s (75%) | 28% | 639 | 20% | 54.4 | 9.3 | 0.7 | 1003 | 763 |
| Bárbaro | Vanguarda | 41% | 6.8s de 12.1s (56%) | 47% | 1301 | 39% | 191.8 | 23.5 | 0.6 | 15 | 93 |
| Bardo | Meio | 37% | 10.5s de 12.7s (83%) | 5% | 608 | 19% | 58.0 | 24.9 | 0.8 | 27 | 676 |
| Ladino | Meio | 37% | 9.9s de 13.1s (76%) | 5% | 848 | 33% | 85.3 | 26.7 | 17.6 | 22 | 552 |
| Patrulheiro | Retaguarda | 32% | 8.2s de 10.6s (78%) | 20% | 1564 | 50% | 190.4 | 34.7 | 1.2 | 14 | 74 |
| Mago | Meio | 63% | 4.1s de 6.5s (63%) | 14% | 1767 | 64% | 434.1 | 14.6 | 0.6 | 6 | 16 |
| Alquimista | Retaguarda | 49% | 13.9s de 16.6s (84%) | 28% | 648 | 18% | 46.6 | 19.5 | 0.7 | 8 | 2251 |

### Mochila montada pelo gerador (média de itens por tipo)

| Classe | arma corpo a corpo | arma à distância | arma mágica | mascote | instrumento | armadura | poção | catalisador/outro | Corpo a corpo na Retaguarda (-20%) |
|---|---|---|---|---|---|---|---|---|---|
| Guerreiro | 2.0 | 0.1 | 0.2 | 0.0 | 0.0 | 2.9 | 1.1 | 1.8 | — |
| Paladino | 1.0 | 0.0 | 0.0 | 0.0 | 0.0 | 2.3 | 1.1 | 3.0 | — |
| Bárbaro | 3.5 | 0.1 | 0.2 | 0.0 | 0.0 | 0.2 | 0.1 | 3.2 | — |
| Bardo | 1.3 | 0.1 | 0.2 | 0.0 | 1.7 | 0.1 | 2.2 | 1.3 | — |
| Ladino | 2.6 | 0.2 | 0.7 | 0.0 | 0.1 | 0.2 | 1.6 | 2.6 | — |
| Patrulheiro | 0.2 | 1.5 | 0.2 | 2.6 | 0.1 | 0.2 | 0.2 | 4.5 | 0.2 |
| Mago | 0.2 | 0.1 | 3.6 | 0.0 | 0.1 | 0.1 | 1.1 | 3.3 | — |
| Alquimista | 0.2 | 1.6 | 0.2 | 0.0 | 0.1 | 1.2 | 3.2 | 2.3 | 0.2 |

### Fusão no mesmo herói (sala 3, linha de base Mago/Bardo/Guerreiro, 300 lutas)

| Item | Herói | 2 cópias +0 | 1 cópia +1 | Delta (pp) |
|---|---|---|---|---|
| Adaga | Mago | 40.3% | 35.7% | -4.7 |
| Adaga | Bardo | 45.7% | 50.7% | +5.0 |
| Adaga | Guerreiro | 65.3% | 65.0% | -0.3 |
| Gema Bruta | Mago | 56.7% | 53.0% | -3.7 |
| Gema Bruta | Bardo | 25.0% | 25.0% | +0.0 |
| Gema Bruta | Guerreiro | 25.0% | 25.0% | +0.0 |
| Tambor de Guerra | Mago | 40.3% | 50.7% | +10.3 |
| Tambor de Guerra | Bardo | 25.0% | 32.0% | +7.0 |
| Tambor de Guerra | Guerreiro | 43.7% | 57.0% | +13.3 |
