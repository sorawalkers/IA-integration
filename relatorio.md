# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --fights 300` em 2026-11-18T18:42:13.246Z · commit `7f1f05d`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

Linha de base **[Mago, Bardo, Guerreiro]** contra ghosts da **sala 3**: 16.3% de vitória, 18.6s por luta (300 lutas por variante).

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
| Arco Longo | advanced | 78.3% | +37.3pp | 2.8 | +2.3pp | +37.3pp | 5.3 (7 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Machado Grande | advanced | 75.7% | +36.7pp | 2.8 | +17.0pp | +36.7pp | 3.7 (10 PO) | ▲ forte | com Bárbaro · party Patrulheiro/Bardo/Bárbaro · sala 9 (item +1, party evoluída) · melhor em: Bárbaro (no lugar de Rubi Ígneo) |
| Bomba Alquímica | basic | 44.3% | +34.7pp | 2.7 | +26.3pp | +34.7pp | 11.6 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Espada Longa | advanced | 75.0% | +34.0pp | 2.7 | -0.3pp | +34.0pp | 4.3 (8 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Cajado de Aprendiz | basic | 80.7% | +33.7pp | 2.8 | +33.7pp | +23.7pp | 8.4 (4 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Cajado Runado | advanced | 74.3% | +33.3pp | 2.8 | +11.3pp | +33.3pp | 3.7 (9 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Tomo Menor | basic | 75.3% | +28.3pp | 2.7 | +28.3pp | +16.3pp | 7.1 (4 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Poção de Vida Menor | basic | 74.0% | +27.0pp | 2.6 | +27.0pp | +21.7pp | 9.0 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Alquimista |
| Maça | basic | 38.7% | +26.7pp | 2.6 | +18.7pp | +26.7pp | 6.7 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Espada Curta | basic | 38.0% | +26.0pp | 2.5 | +19.3pp | +26.0pp | 6.5 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Adaga | basic | 37.0% | +25.0pp | 2.5 | +9.7pp | +25.0pp | 8.3 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Arco Curto | basic | 33.0% | +23.3pp | 2.4 | +20.7pp | +23.3pp | 5.8 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Pergaminho de Fogo | advanced | 63.7% | +22.7pp | 2.6 | +8.0pp | +22.7pp | 5.7 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Pedra de Amolar | basic | 68.0% | +21.0pp | 2.4 | +21.0pp | +4.3pp | 7.0 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Poção de Vida Maior | advanced | 61.7% | +20.7pp | 2.3 | +8.7pp | +20.7pp | 4.1 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Escudo Torre | advanced | 98.7% | +20.3pp | 2.4 | — | +20.3pp | 2.3 (9 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Tambor de Guerra | basic | 66.7% | +19.7pp | 2.4 | +19.7pp | +12.3pp | 4.9 (4 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Alaúde dos Ventos | advanced | 79.7% | +19.7pp | 2.6 | — | +19.7pp | 1.6 (12 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Ração de Viagem | basic | 65.0% | +18.0pp | 2.2 | +18.0pp | +17.0pp | 9.0 (2 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Grimório | advanced | 92.7% | +14.3pp | 2.1 | +7.7pp | +14.3pp | 1.3 (11 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago (no lugar de Cajado Runado) |
| Elmo de Ferro | advanced | 55.0% | +14.0pp | 2.2 | +1.0pp | +14.0pp | 2.8 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Broquel | basic | 60.0% | +13.0pp | 1.9 | +13.0pp | +5.3pp | 4.3 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Amuleto de Madeira | basic | 59.7% | +12.7pp | 1.9 | +12.7pp | +8.0pp | 4.2 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Poção de Mana Menor | basic | 58.3% | +11.3pp | 1.9 | +11.3pp | +4.3pp | 3.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gema Bruta | basic | 58.3% | +11.3pp | 1.9 | +11.3pp | +3.7pp | 3.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Aljava | basic | 58.3% | +11.3pp | 1.9 | +11.3pp | +0.0pp | 3.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gazuas | basic | 57.7% | +10.7pp | 1.8 | +10.7pp | — | 3.6 (3 PO) | ▲ forte | com Ladino · party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Rubi Ígneo | advanced | 88.3% | +10.0pp | 1.7 | +0.0pp | +10.0pp | 2.0 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Gibão de Couro | basic | 54.7% | +7.7pp | 1.6 | +7.7pp | +4.3pp | 2.6 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Erva Curativa | basic | 54.0% | +7.0pp | 1.5 | +7.0pp | +6.0pp | 3.5 (2 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Paladino |
| Símbolo Sagrado | advanced | 48.0% | +5.3pp | 1.5 | +4.0pp | +5.3pp | 0.9 (6 PO) | ▲ forte | com Paladino · party Patrulheiro/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Rato de Cripta | basic | 33.7% | +3.7pp | 2.2 | +3.7pp | +1.7pp | 1.2 (3 PO) |  | com Patrulheiro · party Patrulheiro/Ladino/Paladino · sala 3 · melhor em: Patrulheiro |
| Gema de Mana | advanced | 81.0% | +2.7pp | 1.6 | +0.0pp | +2.7pp | 0.5 (5 PO) |  | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Lobo Cinzento | advanced | 44.7% | +2.0pp | 2.3 | -4.3pp | +2.0pp | 0.2 (10 PO) |  | com Patrulheiro · party Patrulheiro/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Patrulheiro (no lugar de Arco Longo) |

## Encantamentos (em todas as armas)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Gélido | encantamento | 51.3% | +35.0pp | 2.8 | ▲ forte | em todas as armas |
| Flamejante | encantamento | 42.3% | +26.0pp | 2.5 | ▲ forte | em todas as armas |
| Defensor | encantamento | 40.7% | +24.3pp | 2.5 | ▲ forte | em todas as armas |
| Trovejante | encantamento | 33.7% | +17.3pp | 2.2 | ▲ forte | em todas as armas |
| Vorpal | encantamento | 32.3% | +16.0pp | 2.1 | ▲ forte | em todas as armas |
| Vampírico | encantamento | 30.3% | +14.0pp | 2.0 | ▲ forte | em todas as armas |
| Veloz | encantamento | 28.3% | +12.0pp | 1.9 | ▲ forte | em todas as armas |
| Armazenador | encantamento | 28.3% | +12.0pp | 2.4 | ▲ forte | em todas as armas |
| Afiado | encantamento | 25.0% | +8.7pp | 1.6 | ▲ forte | em todas as armas |
| Mortal | encantamento | 22.3% | +6.0pp | 1.4 | ▲ forte | em todas as armas |

## Fusão: item +1 contra 2 cópias +0

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Cajado de Aprendiz +1 | Arma/Instrumento | 51.7% | +5.3pp | 2.5 | ▲ forte | vs 2x Cajado de Aprendiz: 46% |
| Poção de Vida Menor +1 | Consumível | 39.0% | +3.3pp | 1.2 | ▲ forte | vs 2x Poção de Vida Menor: 36% |
| Pedra de Amolar +1 | Catalisador | 22.3% | +2.3pp | 1.3 |  | vs 2x Pedra de Amolar: 20% |
| Maça +1 | Arma/Instrumento | 49.3% | +1.3pp | 1.5 |  | vs 2x Maça: 48% |
| Gibão de Couro +1 | Armadura | 23.7% | +0.7pp | 0.5 |  | vs 2x Gibão de Couro: 23% |
| Amuleto de Madeira +1 | Catalisador | 20.7% | +0.7pp | 1.3 |  | vs 2x Amuleto de Madeira: 20% |
| Arco Curto +1 | Arma/Instrumento | 50.7% | -0.7pp | 2.4 |  | vs 2x Arco Curto: 51% |
| Broquel +1 | Armadura | 21.0% | -0.7pp | 0.5 |  | vs 2x Broquel: 22% |
| Poção de Mana Menor +1 | Consumível | 22.0% | -1.0pp | 0.7 |  | vs 2x Poção de Mana Menor: 23% |
| Espada Curta +1 | Arma/Instrumento | 47.0% | -1.7pp | 1.6 |  | vs 2x Espada Curta: 49% |
| Adaga +1 | Arma/Instrumento | 45.3% | -2.0pp | 1.8 |  | vs 2x Adaga: 47% |
| Gema Bruta +1 | Catalisador | 33.3% | -3.7pp | 1.1 | ▼ fraco | vs 2x Gema Bruta: 37% |
| Tambor de Guerra +1 | Arma/Instrumento | 30.7% | -11.0pp | 1.9 | ▼ fraco | vs 2x Tambor de Guerra: 42% |
| Erva Curativa +1 | Catalisador | 22.7% | +0.0pp | 0.0 |  | vs 2x Erva Curativa: 23% |

_Tempo de simulação: 73.0s._
