# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --fights 300` em 2026-11-18T18:43:45.619Z · commit `7f1f05d`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

Linha de base **[Mago, Bardo, Guerreiro]** contra ghosts da **sala 3**: 27.3% de vitória, 21.8s por luta (300 lutas por variante).

## Classes (média nas 512 composições; delta = diferença para a média geral)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Alquimista | sug. Retaguarda | 37.7% | +10.0pp | 0.7 | ▲ forte | melhor: Retaguarda · Retaguarda 43% · Meio 35% · Vanguarda 35% |
| Bárbaro | sug. Vanguarda | 31.3% | +3.5pp | 0.7 | ▲ forte | melhor: Vanguarda · Retaguarda 25% · Meio 26% · Vanguarda 42% |
| Ladino | sug. Meio | 29.2% | +1.4pp | 0.7 |  | melhor: Meio · Retaguarda 27% · Meio 42% · Vanguarda 18% |
| Mago | sug. Retaguarda | 29.0% | +1.3pp | 0.7 |  | melhor: Retaguarda · Retaguarda 40% · Meio 33% · Vanguarda 15% |
| Guerreiro | sug. Vanguarda | 25.7% | -2.1pp | 0.6 |  | melhor: Vanguarda · Retaguarda 17% · Meio 19% · Vanguarda 41% |
| Patrulheiro | sug. Retaguarda | 23.5% | -4.2pp | 0.6 | ▼ fraco | melhor: Retaguarda · Retaguarda 32% · Meio 24% · Vanguarda 15% |
| Bardo | sug. Meio | 23.4% | -4.4pp | 0.6 | ▼ fraco | melhor: Meio · Retaguarda 24% · Meio 29% · Vanguarda 18% |
| Paladino | sug. Vanguarda | 22.1% | -5.6pp | 0.6 | ▼ fraco | melhor: Vanguarda · Retaguarda 15% · Meio 13% · Vanguarda 38% |

## Itens (+1 cópia na party, no melhor herói e posição)

"Com Ladino" / "Sem Ladino": melhor delta nas parties de referência com e sem Ladino. O Combo do Ladino
(+8% de crítico por item diferente encostado na adaga) valoriza qualquer item pequeno; "Sem Ladino" mostra
a utilidade própria do item.

| Variante | Grupo | Vitória | Delta | ± | Com Ladino | Sem Ladino | pp/PO | Veredito | Nota |
|---|---|---|---|---|---|---|---|---|---|
| Bomba Alquímica | basic | 65.3% | +41.3pp | 2.8 | +16.7pp | +41.3pp | 13.8 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Arco Longo | advanced | 78.3% | +37.3pp | 2.8 | +2.3pp | +37.3pp | 5.3 (7 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Machado Grande | advanced | 75.7% | +36.7pp | 2.8 | +17.0pp | +36.7pp | 3.7 (10 PO) | ▲ forte | com Bárbaro · party Patrulheiro/Bardo/Bárbaro · sala 9 (item +1, party evoluída) · melhor em: Bárbaro (no lugar de Rubi Ígneo) |
| Maça | basic | 60.0% | +36.0pp | 2.8 | +10.3pp | +36.0pp | 9.0 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Cajado de Aprendiz | basic | 60.0% | +36.0pp | 2.8 | +20.7pp | +36.0pp | 9.0 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Poção de Vida Menor | basic | 58.0% | +34.0pp | 2.7 | +18.0pp | +34.0pp | 11.3 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Espada Longa | advanced | 75.0% | +34.0pp | 2.7 | -0.3pp | +34.0pp | 4.3 (8 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Cajado Runado | advanced | 74.3% | +33.3pp | 2.8 | +11.3pp | +33.3pp | 3.7 (9 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Adaga | basic | 56.7% | +32.7pp | 2.7 | +7.0pp | +32.7pp | 10.9 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Espada Curta | basic | 55.3% | +31.3pp | 2.7 | +13.3pp | +31.3pp | 7.8 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Arco Curto | basic | 54.7% | +30.7pp | 2.7 | +13.7pp | +30.7pp | 7.7 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Ração de Viagem | basic | 49.3% | +25.3pp | 2.5 | +15.7pp | +25.3pp | 12.7 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Pergaminho de Fogo | advanced | 63.7% | +22.7pp | 2.6 | +8.0pp | +22.7pp | 5.7 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Poção de Vida Maior | advanced | 61.7% | +20.7pp | 2.3 | +8.7pp | +20.7pp | 4.1 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Escudo Torre | advanced | 98.7% | +20.3pp | 2.4 | — | +20.3pp | 2.3 (9 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Alaúde dos Ventos | advanced | 79.7% | +19.7pp | 2.6 | — | +19.7pp | 1.6 (12 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Tomo Menor | basic | 43.3% | +19.3pp | 2.3 | +19.0pp | +19.3pp | 4.8 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Pedra de Amolar | basic | 87.0% | +16.7pp | 2.2 | +16.7pp | +6.3pp | 5.6 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Tambor de Guerra | basic | 40.0% | +16.0pp | 2.2 | +14.3pp | +16.0pp | 4.0 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Grimório | advanced | 92.7% | +14.3pp | 2.1 | +7.7pp | +14.3pp | 1.3 (11 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago (no lugar de Cajado Runado) |
| Elmo de Ferro | advanced | 55.0% | +14.0pp | 2.2 | +1.0pp | +14.0pp | 2.8 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Gazuas | basic | 57.0% | +11.3pp | 1.8 | +11.3pp | — | 3.8 (3 PO) | ▲ forte | com Ladino · party Mago/Ladino/Guerreiro · sala 3 · melhor em: Ladino |
| Broquel | basic | 80.3% | +10.0pp | 1.8 | +10.0pp | +6.3pp | 3.3 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Rubi Ígneo | advanced | 88.3% | +10.0pp | 1.7 | +0.0pp | +10.0pp | 2.0 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Amuleto de Madeira | basic | 79.7% | +9.3pp | 1.7 | +9.3pp | +9.0pp | 3.1 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Poção de Mana Menor | basic | 79.0% | +8.7pp | 1.7 | +8.7pp | +4.0pp | 2.9 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gema Bruta | basic | 79.0% | +8.7pp | 1.7 | +8.7pp | +3.3pp | 2.9 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Aljava | basic | 79.0% | +8.7pp | 1.7 | +8.7pp | +0.0pp | 2.9 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Erva Curativa | basic | 32.3% | +8.3pp | 1.6 | +5.0pp | +8.3pp | 4.2 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Gibão de Couro | basic | 76.7% | +6.3pp | 1.6 | +6.3pp | +4.7pp | 2.1 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Símbolo Sagrado | advanced | 48.0% | +5.3pp | 1.5 | +4.0pp | +5.3pp | 0.9 (6 PO) | ▲ forte | com Paladino · party Patrulheiro/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Rato de Cripta | basic | 52.7% | +4.0pp | 2.2 | +4.0pp | +1.7pp | 1.3 (3 PO) |  | com Patrulheiro · party Patrulheiro/Ladino/Paladino · sala 3 · melhor em: Patrulheiro |
| Gema de Mana | advanced | 81.0% | +2.7pp | 1.6 | +0.0pp | +2.7pp | 0.5 (5 PO) |  | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Lobo Cinzento | advanced | 44.7% | +2.0pp | 2.3 | -4.3pp | +2.0pp | 0.2 (10 PO) |  | com Patrulheiro · party Patrulheiro/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Patrulheiro (no lugar de Arco Longo) |

## Encantamentos (em todas as armas)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Gélido | encantamento | 66.7% | +39.3pp | 2.9 | ▲ forte | em todas as armas |
| Flamejante | encantamento | 61.0% | +33.7pp | 2.7 | ▲ forte | em todas as armas |
| Defensor | encantamento | 52.7% | +25.3pp | 2.5 | ▲ forte | em todas as armas |
| Vorpal | encantamento | 46.7% | +19.3pp | 2.3 | ▲ forte | em todas as armas |
| Armazenador | encantamento | 45.3% | +18.0pp | 2.5 | ▲ forte | em todas as armas |
| Trovejante | encantamento | 44.3% | +17.0pp | 2.3 | ▲ forte | em todas as armas |
| Veloz | encantamento | 44.0% | +16.7pp | 2.3 | ▲ forte | em todas as armas |
| Vampírico | encantamento | 42.0% | +14.7pp | 2.0 | ▲ forte | em todas as armas |
| Afiado | encantamento | 41.0% | +13.7pp | 2.0 | ▲ forte | em todas as armas |
| Mortal | encantamento | 35.0% | +7.7pp | 1.5 | ▲ forte | em todas as armas |

## Fusão: item +1 contra 2 cópias +0

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Cajado de Aprendiz +1 | Arma/Instrumento | 74.0% | +7.3pp | 2.1 | ▲ forte | vs 2x Cajado de Aprendiz: 67% |
| Poção de Vida Menor +1 | Consumível | 58.7% | +5.0pp | 1.4 | ▲ forte | vs 2x Poção de Vida Menor: 54% |
| Pedra de Amolar +1 | Catalisador | 34.3% | +1.3pp | 0.9 |  | vs 2x Pedra de Amolar: 33% |
| Maça +1 | Arma/Instrumento | 73.7% | +1.0pp | 2.0 |  | vs 2x Maça: 73% |
| Amuleto de Madeira +1 | Catalisador | 32.0% | +1.0pp | 0.6 |  | vs 2x Amuleto de Madeira: 31% |
| Broquel +1 | Armadura | 34.7% | +0.7pp | 0.5 |  | vs 2x Broquel: 34% |
| Poção de Mana Menor +1 | Consumível | 33.0% | +0.7pp | 0.5 |  | vs 2x Poção de Mana Menor: 32% |
| Erva Curativa +1 | Catalisador | 37.7% | +0.3pp | 0.3 |  | vs 2x Erva Curativa: 37% |
| Arco Curto +1 | Arma/Instrumento | 73.3% | -0.3pp | 2.0 |  | vs 2x Arco Curto: 74% |
| Espada Curta +1 | Arma/Instrumento | 67.0% | -1.3pp | 2.0 |  | vs 2x Espada Curta: 68% |
| Adaga +1 | Arma/Instrumento | 67.7% | -2.0pp | 2.1 |  | vs 2x Adaga: 70% |
| Gema Bruta +1 | Catalisador | 45.7% | -3.0pp | 1.1 |  | vs 2x Gema Bruta: 49% |
| Tambor de Guerra +1 | Arma/Instrumento | 43.3% | -14.0pp | 2.1 | ▼ fraco | vs 2x Tambor de Guerra: 57% |
| Gibão de Couro +1 | Armadura | 34.3% | +0.0pp | 0.5 |  | vs 2x Gibão de Couro: 34% |

_Tempo de simulação: 73.2s._
