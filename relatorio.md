# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --fights 300 --out relatorio.md` em 2026-11-18T19:25:13.550Z · commit `94aae1c`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

Linha de base **[Mago, Bardo, Guerreiro]** contra ghosts da **sala 3**: 29.7% de vitória, 15.9s por luta (300 lutas por variante).

## Classes (média nas 512 composições; delta = diferença para a média geral)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Ladino | sug. Meio | 31.7% | +4.3pp | 0.7 | ▲ forte | melhor: Meio · Retaguarda 29% · Meio 47% · Vanguarda 19% |
| Alquimista | sug. Retaguarda | 31.1% | +3.8pp | 0.7 | ▲ forte | melhor: Retaguarda · Retaguarda 35% · Meio 28% · Vanguarda 30% |
| Bardo | sug. Meio | 28.7% | +1.4pp | 0.7 |  | melhor: Meio · Retaguarda 30% · Meio 34% · Vanguarda 23% |
| Mago | sug. Retaguarda | 27.7% | +0.4pp | 0.6 |  | melhor: Retaguarda · Retaguarda 37% · Meio 32% · Vanguarda 14% |
| Bárbaro | sug. Vanguarda | 27.6% | +0.3pp | 0.6 |  | melhor: Vanguarda · Retaguarda 23% · Meio 22% · Vanguarda 38% |
| Guerreiro | sug. Vanguarda | 25.7% | -1.6pp | 0.6 |  | melhor: Vanguarda · Retaguarda 18% · Meio 18% · Vanguarda 42% |
| Patrulheiro | sug. Retaguarda | 23.3% | -4.0pp | 0.6 | ▼ fraco | melhor: Retaguarda · Retaguarda 31% · Meio 25% · Vanguarda 14% |
| Paladino | sug. Vanguarda | 22.8% | -4.6pp | 0.6 | ▼ fraco | melhor: Vanguarda · Retaguarda 16% · Meio 14% · Vanguarda 38% |

## Itens (+1 cópia na party, no melhor herói e posição)

"Com Ladino" / "Sem Ladino": melhor delta nas parties de referência com e sem Ladino. O Combo do Ladino
(+8% de crítico por item diferente encostado na adaga) valoriza qualquer item pequeno; "Sem Ladino" mostra
a utilidade própria do item.

| Variante | Grupo | Vitória | Delta | ± | Com Ladino | Sem Ladino | pp/PO | Veredito | Nota |
|---|---|---|---|---|---|---|---|---|---|
| Machado Grande | advanced | 78.3% | +36.0pp | 2.8 | +17.7pp | +36.0pp | 3.6 (10 PO) | ▲ forte | com Bárbaro · party Patrulheiro/Bardo/Bárbaro · sala 9 (item +1, party evoluída) · melhor em: Bárbaro (no lugar de Rubi Ígneo) |
| Adaga | basic | 68.3% | +34.3pp | 2.8 | +3.7pp | +34.3pp | 11.4 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Maça | basic | 66.3% | +32.3pp | 2.7 | +14.3pp | +32.3pp | 8.1 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Bomba Alquímica | basic | 55.7% | +31.3pp | 2.8 | +14.3pp | +31.3pp | 10.4 (3 PO) | ▲ forte | com Alquimista · party Alquimista/Bardo/Guerreiro · sala 3 · melhor em: Alquimista |
| Espada Curta | basic | 64.0% | +30.0pp | 2.7 | +13.3pp | +30.0pp | 7.5 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Cajado Runado | advanced | 77.0% | +28.7pp | 2.7 | +9.7pp | +28.7pp | 3.2 (9 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Espada Longa | advanced | 74.7% | +26.3pp | 2.6 | -3.3pp | +26.3pp | 3.3 (8 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Arco Longo | advanced | 74.7% | +26.3pp | 2.6 | +2.0pp | +26.3pp | 3.8 (7 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Cajado de Aprendiz | basic | 55.3% | +25.3pp | 2.6 | +20.0pp | +25.3pp | 6.3 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Poção de Vida Menor | basic | 54.3% | +24.3pp | 2.5 | +15.0pp | +24.3pp | 8.1 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Arco Curto | basic | 52.7% | +23.0pp | 2.8 | +12.3pp | +23.0pp | 5.8 (4 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Ração de Viagem | basic | 54.7% | +20.7pp | 2.3 | +8.0pp | +20.7pp | 10.3 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Tambor de Guerra | basic | 54.0% | +20.0pp | 2.4 | +17.7pp | +20.0pp | 5.0 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Poção de Vida Maior | advanced | 67.7% | +19.3pp | 2.3 | +7.0pp | +19.3pp | 3.9 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Tomo Menor | basic | 48.0% | +18.3pp | 2.8 | +17.7pp | +18.3pp | 4.6 (4 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Mago |
| Pergaminho de Fogo | advanced | 66.0% | +17.7pp | 2.3 | +5.7pp | +17.7pp | 4.4 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Escudo Torre | advanced | 96.0% | +17.7pp | 2.3 | — | +17.7pp | 2.0 (9 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Pedra de Amolar | basic | 88.0% | +15.7pp | 2.1 | +15.7pp | +7.0pp | 5.2 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Elmo de Ferro | advanced | 62.7% | +14.3pp | 2.1 | +1.3pp | +14.3pp | 2.9 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Grimório | advanced | 90.3% | +12.0pp | 2.1 | -2.0pp | +12.0pp | 1.1 (11 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago (no lugar de Cajado Runado) |
| Rubi Ígneo | advanced | 90.3% | +12.0pp | 2.0 | +0.0pp | +12.0pp | 2.4 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Gazuas | basic | 58.3% | +10.0pp | 1.7 | +10.0pp | — | 3.3 (3 PO) | ▲ forte | com Ladino · party Patrulheiro/Ladino/Guerreiro · sala 3 · melhor em: Ladino |
| Gema Bruta | basic | 39.0% | +9.3pp | 1.9 | +6.0pp | +9.3pp | 3.1 (3 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Mago |
| Amuleto de Madeira | basic | 81.0% | +8.7pp | 1.6 | +8.7pp | +8.3pp | 2.9 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Paladino |
| Broquel | basic | 80.3% | +8.0pp | 1.7 | +8.0pp | +4.7pp | 2.7 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Erva Curativa | basic | 41.7% | +7.7pp | 1.5 | +3.3pp | +7.7pp | 3.8 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Gibão de Couro | basic | 40.3% | +6.3pp | 1.6 | +6.0pp | +6.3pp | 2.1 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Poção de Mana Menor | basic | 78.3% | +6.0pp | 1.5 | +6.0pp | +0.0pp | 2.0 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Aljava | basic | 78.3% | +6.0pp | 1.5 | +6.0pp | +0.0pp | 2.0 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Rato de Cripta | basic | 39.7% | +5.7pp | 2.1 | +3.0pp | +5.7pp | 1.9 (3 PO) | ▲ forte | com Patrulheiro · party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Gema de Mana | advanced | 83.3% | +5.0pp | 2.0 | +0.0pp | +5.0pp | 1.0 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Alaúde dos Ventos | advanced | 82.7% | +4.3pp | 1.8 | — | +4.3pp | 0.4 (12 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Símbolo Sagrado | advanced | 69.7% | +4.3pp | 1.2 | +2.0pp | +4.3pp | 0.7 (6 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Lobo Cinzento | advanced | 50.7% | +2.3pp | 2.0 | -4.0pp | +2.3pp | 0.2 (10 PO) |  | com Patrulheiro · party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Patrulheiro (no lugar de Arco Longo) |

## Encantamentos (em todas as armas)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Armazenador | encantamento | 68.3% | +38.7pp | 2.9 | ▲ forte | em todas as armas |
| Flamejante | encantamento | 62.7% | +33.0pp | 3.0 | ▲ forte | em todas as armas |
| Gélido | encantamento | 62.3% | +32.7pp | 3.0 | ▲ forte | em todas as armas |
| Trovejante | encantamento | 62.3% | +32.7pp | 3.0 | ▲ forte | em todas as armas |
| Afiado | encantamento | 55.3% | +25.7pp | 2.8 | ▲ forte | em todas as armas |
| Defensor | encantamento | 54.3% | +24.7pp | 2.5 | ▲ forte | em todas as armas |
| Vorpal | encantamento | 52.3% | +22.7pp | 2.8 | ▲ forte | em todas as armas |
| Veloz | encantamento | 51.7% | +22.0pp | 2.7 | ▲ forte | em todas as armas |
| Mortal | encantamento | 50.3% | +20.7pp | 2.4 | ▲ forte | em todas as armas |
| Vampírico | encantamento | 49.3% | +19.7pp | 2.3 | ▲ forte | em todas as armas |

## Fusão: item +1 contra 2 cópias +0

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Tambor de Guerra +1 | Arma/Instrumento | 55.3% | +9.0pp | 2.0 | ▲ forte | vs 2x Tambor de Guerra: 46% · no Guerreiro |
| Poção de Vida Menor +1 | Consumível | 57.7% | +4.7pp | 1.2 | ▲ forte | vs 2x Poção de Vida Menor: 53% · no Mago |
| Cajado de Aprendiz +1 | Arma/Instrumento | 69.7% | +4.0pp | 1.9 | ▲ forte | vs 2x Cajado de Aprendiz: 66% · no Guerreiro |
| Arco Curto +1 | Arma/Instrumento | 75.7% | +3.7pp | 2.0 |  | vs 2x Arco Curto: 72% · no Guerreiro |
| Espada Curta +1 | Arma/Instrumento | 69.3% | +2.7pp | 2.4 |  | vs 2x Espada Curta: 67% · no Guerreiro |
| Amuleto de Madeira +1 | Catalisador | 33.7% | +1.3pp | 0.7 |  | vs 2x Amuleto de Madeira: 32% · no Guerreiro |
| Pedra de Amolar +1 | Catalisador | 34.0% | +0.7pp | 0.5 |  | vs 2x Pedra de Amolar: 33% · no Bardo |
| Adaga +1 | Arma/Instrumento | 63.7% | -0.3pp | 2.6 |  | vs 2x Adaga: 64% · no Guerreiro |
| Gema Bruta +1 | Catalisador | 50.0% | -2.0pp | 0.9 |  | vs 2x Gema Bruta: 52% · no Mago |
| Maça +1 | Arma/Instrumento | 66.7% | -2.7pp | 2.4 |  | vs 2x Maça: 69% · no Guerreiro |
| Broquel +1 | Armadura | 38.7% | +0.0pp | 0.5 |  | vs 2x Broquel: 39% · no Mago |
| Gibão de Couro +1 | Armadura | 41.0% | +0.0pp | 0.5 |  | vs 2x Gibão de Couro: 41% · no Mago |
| Poção de Mana Menor +1 | Consumível | 29.7% | +0.0pp | 0.0 |  | vs 2x Poção de Mana Menor: 30% · no Mago |
| Erva Curativa +1 | Catalisador | 35.0% | +0.0pp | 0.0 |  | vs 2x Erva Curativa: 35% · no Mago |

_Tempo de simulação: 67.4s._

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
| Guerreiro | Vanguarda 41% (26%) | Vanguarda 45% (33%) | Vanguarda 52% (44%) |
| Paladino | Vanguarda 38% (23%) | Vanguarda 38% (24%) | Vanguarda 40% (31%) |
| Bárbaro | Vanguarda 38% (27%) | Vanguarda 41% (32%) | Vanguarda 50% (45%) |
| Bardo | Meio 34% (28%) | Meio 44% (37%) | Meio 49% (47%) |
| Ladino | Meio 46% (32%) | Meio 38% (30%) | Meio 35% (33%) |
| Patrulheiro | Retaguarda 31% (23%) | Retaguarda 32% (26%) | Retaguarda 39% (34%) |
| Mago | Retaguarda 37% (28%) | Retaguarda 47% (39%) | Meio 59% (52%) |
| Alquimista | Retaguarda 35% (31%) | Retaguarda 49% (45%) | Retaguarda 56% (53%) |
| **Diferença** | **16 pp** | **17 pp** | **24 pp** |
| **Duração média da luta** | 18.6s | 15.3s | 13.3s |

_Tempo de simulação: 111.5s._

---

## Diagnóstico das classes — sala 18

300 lutas por classe, na melhor posição; os outros 2 heróis são sorteados entre as 8 classes.

### Desempenho do herói da classe

Dano = dano direto dos golpes (sem Veneno/Queimadura, que não têm dono no registro). "Golpes com DOT" = golpes que aplicaram Veneno ou Queimadura. Escudo e cura = gerados pelos itens do herói (para qualquer aliado).

| Classe | Posição | Vitória | Tempo vivo | Morre primeiro | Dano/luta | % do dano da party | Dano/s vivo | Golpes/luta | Golpes com DOT | Escudo/luta | Cura/luta |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Guerreiro | Vanguarda | 45% | 10.4s de 14.5s (72%) | 34% | 1010 | 30% | 97.1 | 19.4 | 1.0 | 13 | 941 |
| Paladino | Vanguarda | 42% | 11.4s de 15.7s (73%) | 33% | 599 | 19% | 52.6 | 9.3 | 0.5 | 222 | 849 |
| Bárbaro | Vanguarda | 48% | 7.7s de 12.1s (64%) | 39% | 1381 | 41% | 179.0 | 25.7 | 1.0 | 10 | 242 |
| Bardo | Meio | 42% | 9.3s de 11.6s (80%) | 3% | 816 | 25% | 87.6 | 28.1 | 1.3 | 12 | 414 |
| Ladino | Meio | 31% | 12.2s de 15.6s (78%) | 4% | 916 | 33% | 75.2 | 29.8 | 18.7 | 12 | 581 |
| Patrulheiro | Retaguarda | 34% | 8.3s de 10.9s (76%) | 21% | 1364 | 44% | 164.5 | 33.6 | 1.2 | 16 | 163 |
| Mago | Meio | 60% | 4.9s de 7.3s (67%) | 21% | 1580 | 58% | 325.6 | 15.7 | 0.5 | 6 | 42 |
| Alquimista | Retaguarda | 50% | 12.7s de 15.3s (83%) | 26% | 740 | 21% | 58.1 | 20.8 | 1.1 | 16 | 1796 |

### Mochila montada pelo gerador (média de itens por tipo)

| Classe | arma corpo a corpo | arma à distância | arma mágica | mascote | instrumento | armadura | poção | catalisador/outro | Corpo a corpo na Retaguarda (-20%) |
|---|---|---|---|---|---|---|---|---|---|
| Guerreiro | 1.5 | 0.2 | 0.6 | 0.0 | 0.2 | 2.5 | 1.4 | 2.2 | — |
| Paladino | 1.0 | 0.0 | 0.1 | 0.0 | 0.0 | 2.1 | 1.4 | 3.2 | — |
| Bárbaro | 2.6 | 0.2 | 0.6 | 0.0 | 0.2 | 0.4 | 0.4 | 3.2 | — |
| Bardo | 1.6 | 0.3 | 0.6 | 0.0 | 1.2 | 0.4 | 1.4 | 1.2 | — |
| Ladino | 2.6 | 0.3 | 0.6 | 0.0 | 0.1 | 0.4 | 1.4 | 2.3 | — |
| Patrulheiro | 0.5 | 1.2 | 0.5 | 2.2 | 0.1 | 0.4 | 0.5 | 4.2 | 0.5 |
| Mago | 0.6 | 0.2 | 2.6 | 0.0 | 0.1 | 0.4 | 1.4 | 3.1 | — |
| Alquimista | 0.5 | 1.3 | 0.5 | 0.0 | 0.1 | 1.5 | 2.4 | 2.3 | 0.5 |

### Fusão no mesmo herói (sala 3, linha de base Mago/Bardo/Guerreiro, 300 lutas)

| Item | Herói | 2 cópias +0 | 1 cópia +1 | Delta (pp) |
|---|---|---|---|---|
| Adaga | Mago | 41.3% | 41.3% | +0.0 |
| Adaga | Bardo | 46.3% | 51.3% | +5.0 |
| Adaga | Guerreiro | 64.0% | 63.7% | -0.3 |
| Gema Bruta | Mago | 52.0% | 50.0% | -2.0 |
| Gema Bruta | Bardo | 29.7% | 29.7% | +0.0 |
| Gema Bruta | Guerreiro | 29.7% | 29.7% | +0.0 |
| Tambor de Guerra | Mago | 40.3% | 45.0% | +4.7 |
| Tambor de Guerra | Bardo | 29.7% | 34.3% | +4.7 |
| Tambor de Guerra | Guerreiro | 46.3% | 55.3% | +9.0 |
