# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --fights 300 --out relatorio.md` em 2026-11-18T19:05:00.951Z · commit `44c443e`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

Linha de base **[Mago, Bardo, Guerreiro]** contra ghosts da **sala 3**: 38.0% de vitória, 15.9s por luta (300 lutas por variante).

## Classes (média nas 512 composições; delta = diferença para a média geral)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Alquimista | sug. Retaguarda | 34.7% | +5.7pp | 0.7 | ▲ forte | melhor: Retaguarda · Retaguarda 39% · Meio 32% · Vanguarda 33% |
| Mago | sug. Retaguarda | 31.5% | +2.6pp | 0.7 |  | melhor: Retaguarda · Retaguarda 43% · Meio 36% · Vanguarda 16% |
| Bardo | sug. Meio | 31.5% | +2.6pp | 0.7 |  | melhor: Meio · Retaguarda 32% · Meio 38% · Vanguarda 25% |
| Bárbaro | sug. Vanguarda | 29.6% | +0.7pp | 0.7 |  | melhor: Vanguarda · Retaguarda 25% · Meio 24% · Vanguarda 40% |
| Ladino | sug. Meio | 29.1% | +0.2pp | 0.7 |  | melhor: Meio · Retaguarda 26% · Meio 43% · Vanguarda 19% |
| Guerreiro | sug. Vanguarda | 27.1% | -1.8pp | 0.6 |  | melhor: Vanguarda · Retaguarda 18% · Meio 19% · Vanguarda 44% |
| Patrulheiro | sug. Retaguarda | 24.3% | -4.6pp | 0.6 | ▼ fraco | melhor: Retaguarda · Retaguarda 32% · Meio 26% · Vanguarda 15% |
| Paladino | sug. Vanguarda | 23.5% | -5.4pp | 0.6 | ▼ fraco | melhor: Vanguarda · Retaguarda 17% · Meio 14% · Vanguarda 40% |

## Itens (+1 cópia na party, no melhor herói e posição)

"Com Ladino" / "Sem Ladino": melhor delta nas parties de referência com e sem Ladino. O Combo do Ladino
(+8% de crítico por item diferente encostado na adaga) valoriza qualquer item pequeno; "Sem Ladino" mostra
a utilidade própria do item.

| Variante | Grupo | Vitória | Delta | ± | Com Ladino | Sem Ladino | pp/PO | Veredito | Nota |
|---|---|---|---|---|---|---|---|---|---|
| Bomba Alquímica | basic | 66.3% | +36.7pp | 2.9 | +17.7pp | +36.7pp | 12.2 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Maça | basic | 68.0% | +34.3pp | 2.7 | +11.7pp | +34.3pp | 8.6 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Machado Grande | advanced | 78.0% | +33.7pp | 2.8 | +19.0pp | +33.7pp | 3.4 (10 PO) | ▲ forte | com Bárbaro · party Patrulheiro/Bardo/Bárbaro · sala 9 (item +1, party evoluída) · melhor em: Bárbaro (no lugar de Rubi Ígneo) |
| Adaga | basic | 67.0% | +33.3pp | 2.7 | +5.0pp | +33.3pp | 11.1 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Cajado de Aprendiz | basic | 62.3% | +32.7pp | 2.7 | +24.7pp | +32.7pp | 8.2 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Espada Curta | basic | 63.0% | +29.3pp | 2.6 | +13.7pp | +29.3pp | 7.3 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Poção de Vida Menor | basic | 59.0% | +29.3pp | 2.6 | +18.7pp | +29.3pp | 9.8 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Arco Curto | basic | 57.7% | +28.0pp | 2.7 | +13.3pp | +28.0pp | 7.0 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Arco Longo | advanced | 81.7% | +28.0pp | 2.6 | +4.3pp | +28.0pp | 4.0 (7 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Cajado Runado | advanced | 81.0% | +27.3pp | 2.6 | +12.3pp | +27.3pp | 3.0 (9 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Espada Longa | advanced | 80.3% | +26.7pp | 2.6 | -1.7pp | +26.7pp | 3.3 (8 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Tomo Menor | basic | 88.3% | +21.7pp | 2.5 | +21.7pp | +20.7pp | 5.4 (4 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Tambor de Guerra | basic | 50.7% | +21.0pp | 2.4 | +18.3pp | +21.0pp | 5.3 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Ração de Viagem | basic | 52.3% | +18.7pp | 2.2 | +10.3pp | +18.7pp | 9.3 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Poção de Vida Maior | advanced | 70.7% | +17.0pp | 2.2 | +10.0pp | +17.0pp | 3.4 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Elmo de Ferro | advanced | 70.3% | +16.7pp | 2.2 | +1.0pp | +16.7pp | 3.3 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Escudo Torre | advanced | 97.3% | +16.3pp | 2.4 | — | +16.3pp | 1.8 (9 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Alaúde dos Ventos | advanced | 84.0% | +15.3pp | 2.1 | — | +15.3pp | 1.3 (12 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Pergaminho de Fogo | advanced | 68.0% | +14.3pp | 2.2 | +9.0pp | +14.3pp | 3.6 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Pedra de Amolar | basic | 81.0% | +14.3pp | 2.2 | +14.3pp | +5.7pp | 4.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Grimório | advanced | 93.0% | +12.0pp | 2.1 | +2.3pp | +12.0pp | 1.1 (11 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago (no lugar de Cajado Runado) |
| Broquel | basic | 78.0% | +11.3pp | 1.9 | +11.3pp | +4.7pp | 3.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gazuas | basic | 77.0% | +10.3pp | 1.9 | +10.3pp | — | 3.4 (3 PO) | ▲ forte | com Ladino · party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Amuleto de Madeira | basic | 76.7% | +10.0pp | 1.8 | +10.0pp | +9.0pp | 3.3 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Rubi Ígneo | advanced | 91.0% | +10.0pp | 1.9 | +0.0pp | +10.0pp | 2.0 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Poção de Mana Menor | basic | 75.0% | +8.3pp | 1.7 | +8.3pp | +1.3pp | 2.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gema Bruta | basic | 75.0% | +8.3pp | 1.7 | +8.3pp | +2.3pp | 2.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Aljava | basic | 75.0% | +8.3pp | 1.7 | +8.3pp | +0.0pp | 2.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Erva Curativa | basic | 40.3% | +6.7pp | 1.4 | +3.0pp | +6.7pp | 3.3 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Gibão de Couro | basic | 44.3% | +6.3pp | 1.6 | +5.3pp | +6.3pp | 2.1 (3 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Mago |
| Rato de Cripta | basic | 37.3% | +3.7pp | 1.6 | +1.3pp | +3.7pp | 1.2 (3 PO) | ▲ forte | com Patrulheiro · party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Símbolo Sagrado | advanced | 78.3% | +3.7pp | 1.2 | +3.7pp | +1.7pp | 0.6 (6 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Gema de Mana | advanced | 82.7% | +1.7pp | 1.5 | +0.0pp | +1.7pp | 0.3 (5 PO) |  | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Lobo Cinzento | advanced | 54.3% | +0.7pp | 2.0 | -1.7pp | +0.7pp | 0.1 (10 PO) |  | com Patrulheiro · party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Patrulheiro (no lugar de Arco Longo) |

## Encantamentos (em todas as armas)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Gélido | encantamento | 73.3% | +35.3pp | 2.9 | ▲ forte | em todas as armas |
| Armazenador | encantamento | 70.7% | +32.7pp | 2.9 | ▲ forte | em todas as armas |
| Trovejante | encantamento | 70.3% | +32.3pp | 3.0 | ▲ forte | em todas as armas |
| Flamejante | encantamento | 68.0% | +30.0pp | 2.8 | ▲ forte | em todas as armas |
| Defensor | encantamento | 62.3% | +24.3pp | 2.5 | ▲ forte | em todas as armas |
| Vampírico | encantamento | 59.3% | +21.3pp | 2.4 | ▲ forte | em todas as armas |
| Mortal | encantamento | 59.0% | +21.0pp | 2.4 | ▲ forte | em todas as armas |
| Vorpal | encantamento | 58.7% | +20.7pp | 2.8 | ▲ forte | em todas as armas |
| Veloz | encantamento | 57.7% | +19.7pp | 2.5 | ▲ forte | em todas as armas |
| Afiado | encantamento | 51.7% | +13.7pp | 2.4 | ▲ forte | em todas as armas |

## Fusão: item +1 contra 2 cópias +0

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Poção de Vida Menor +1 | Consumível | 73.0% | +5.0pp | 1.3 | ▲ forte | vs 2x Poção de Vida Menor: 68% |
| Pedra de Amolar +1 | Catalisador | 46.0% | +4.0pp | 1.1 | ▲ forte | vs 2x Pedra de Amolar: 42% |
| Espada Curta +1 | Arma/Instrumento | 74.7% | +2.3pp | 2.2 |  | vs 2x Espada Curta: 72% |
| Arco Curto +1 | Arma/Instrumento | 78.7% | +1.7pp | 2.0 |  | vs 2x Arco Curto: 77% |
| Cajado de Aprendiz +1 | Arma/Instrumento | 75.0% | +1.3pp | 2.0 |  | vs 2x Cajado de Aprendiz: 74% |
| Broquel +1 | Armadura | 50.3% | +1.0pp | 0.7 |  | vs 2x Broquel: 49% |
| Amuleto de Madeira +1 | Catalisador | 40.7% | +0.3pp | 0.6 |  | vs 2x Amuleto de Madeira: 40% |
| Gibão de Couro +1 | Armadura | 51.0% | -0.3pp | 0.3 |  | vs 2x Gibão de Couro: 51% |
| Maça +1 | Arma/Instrumento | 73.7% | -1.7pp | 2.2 |  | vs 2x Maça: 75% |
| Gema Bruta +1 | Catalisador | 52.7% | -2.3pp | 1.0 |  | vs 2x Gema Bruta: 55% |
| Adaga +1 | Arma/Instrumento | 67.7% | -5.7pp | 2.2 | ▼ fraco | vs 2x Adaga: 73% |
| Tambor de Guerra +1 | Arma/Instrumento | 57.7% | -13.0pp | 2.4 | ▼ fraco | vs 2x Tambor de Guerra: 71% |
| Poção de Mana Menor +1 | Consumível | 39.7% | +0.0pp | 0.0 |  | vs 2x Poção de Mana Menor: 40% |
| Erva Curativa +1 | Catalisador | 43.0% | +0.0pp | 0.0 |  | vs 2x Erva Curativa: 43% |

_Tempo de simulação: 70.6s._

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
| Guerreiro | Vanguarda 44% (27%) | Vanguarda 47% (34%) | Vanguarda 53% (44%) |
| Paladino | Vanguarda 40% (23%) | Vanguarda 40% (25%) | Vanguarda 41% (30%) |
| Bárbaro | Vanguarda 40% (29%) | Vanguarda 42% (34%) | Vanguarda 50% (45%) |
| Bardo | Meio 38% (31%) | Meio 47% (40%) | Meio 55% (51%) |
| Ladino | Meio 42% (29%) | Meio 37% (29%) | Meio 35% (33%) |
| Patrulheiro | Retaguarda 32% (24%) | Retaguarda 34% (28%) | Retaguarda 39% (35%) |
| Mago | Retaguarda 43% (32%) | Retaguarda 51% (42%) | Meio 61% (52%) |
| Alquimista | Retaguarda 39% (35%) | Retaguarda 50% (46%) | Retaguarda 56% (53%) |
| **Diferença** | **12 pp** | **17 pp** | **26 pp** |
| **Duração média da luta** | 19.5s | 15.7s | 13.6s |

_Tempo de simulação: 111.8s._
