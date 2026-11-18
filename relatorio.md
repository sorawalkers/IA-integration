# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --fights 300 --out relatorio.md` em 2026-11-18T19:15:06.676Z · commit `f6a0423`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

Linha de base **[Mago, Bardo, Guerreiro]** contra ghosts da **sala 3**: 28.0% de vitória, 16.2s por luta (300 lutas por variante).

## Classes (média nas 512 composições; delta = diferença para a média geral)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Ladino | sug. Meio | 32.4% | +5.5pp | 0.7 | ▲ forte | melhor: Meio · Retaguarda 30% · Meio 47% · Vanguarda 20% |
| Alquimista | sug. Retaguarda | 31.3% | +4.4pp | 0.7 | ▲ forte | melhor: Retaguarda · Retaguarda 36% · Meio 28% · Vanguarda 30% |
| Bardo | sug. Meio | 28.2% | +1.2pp | 0.6 |  | melhor: Meio · Retaguarda 28% · Meio 35% · Vanguarda 21% |
| Bárbaro | sug. Vanguarda | 27.8% | +0.9pp | 0.6 |  | melhor: Vanguarda · Retaguarda 23% · Meio 22% · Vanguarda 38% |
| Guerreiro | sug. Vanguarda | 25.4% | -1.6pp | 0.6 |  | melhor: Vanguarda · Retaguarda 17% · Meio 18% · Vanguarda 41% |
| Mago | sug. Retaguarda | 24.5% | -2.5pp | 0.6 |  | melhor: Retaguarda · Retaguarda 34% · Meio 26% · Vanguarda 13% |
| Patrulheiro | sug. Retaguarda | 23.5% | -3.4pp | 0.6 | ▼ fraco | melhor: Retaguarda · Retaguarda 32% · Meio 25% · Vanguarda 14% |
| Paladino | sug. Vanguarda | 22.4% | -4.5pp | 0.6 | ▼ fraco | melhor: Vanguarda · Retaguarda 16% · Meio 13% · Vanguarda 38% |

## Itens (+1 cópia na party, no melhor herói e posição)

"Com Ladino" / "Sem Ladino": melhor delta nas parties de referência com e sem Ladino. O Combo do Ladino
(+8% de crítico por item diferente encostado na adaga) valoriza qualquer item pequeno; "Sem Ladino" mostra
a utilidade própria do item.

| Variante | Grupo | Vitória | Delta | ± | Com Ladino | Sem Ladino | pp/PO | Veredito | Nota |
|---|---|---|---|---|---|---|---|---|---|
| Machado Grande | advanced | 78.3% | +36.0pp | 2.8 | +17.3pp | +36.0pp | 3.6 (10 PO) | ▲ forte | com Bárbaro · party Patrulheiro/Bardo/Bárbaro · sala 9 (item +1, party evoluída) · melhor em: Bárbaro (no lugar de Rubi Ígneo) |
| Maça | basic | 67.7% | +33.7pp | 2.7 | +11.7pp | +33.7pp | 8.4 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Espada Curta | basic | 66.3% | +32.3pp | 2.7 | +12.7pp | +32.3pp | 8.1 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Adaga | basic | 65.3% | +31.3pp | 2.7 | +7.0pp | +31.3pp | 10.4 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Bomba Alquímica | basic | 57.3% | +30.7pp | 2.8 | +13.7pp | +30.7pp | 10.2 (3 PO) | ▲ forte | com Alquimista · party Alquimista/Bardo/Guerreiro · sala 3 · melhor em: Alquimista |
| Cajado de Aprendiz | basic | 57.7% | +27.3pp | 2.7 | +19.3pp | +27.3pp | 6.8 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Cajado Runado | advanced | 77.7% | +26.7pp | 2.7 | +9.7pp | +26.7pp | 3.0 (9 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Arco Longo | advanced | 76.7% | +25.7pp | 2.7 | +2.3pp | +25.7pp | 3.7 (7 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Poção de Vida Menor | basic | 55.7% | +25.3pp | 2.5 | +16.3pp | +25.3pp | 8.4 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Espada Longa | advanced | 75.0% | +24.0pp | 2.6 | -1.7pp | +24.0pp | 3.0 (8 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Arco Curto | basic | 51.7% | +23.7pp | 2.9 | +10.0pp | +23.7pp | 5.9 (4 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Alaúde dos Ventos | advanced | 90.0% | +23.0pp | 2.5 | — | +23.0pp | 1.9 (12 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Tambor de Guerra | basic | 52.0% | +21.7pp | 2.5 | +16.7pp | +21.7pp | 5.4 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Ração de Viagem | basic | 54.3% | +20.3pp | 2.3 | +8.3pp | +20.3pp | 10.2 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Poção de Vida Maior | advanced | 71.0% | +20.0pp | 2.3 | +8.0pp | +20.0pp | 4.0 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Tomo Menor | basic | 91.3% | +18.0pp | 2.3 | +18.0pp | +15.7pp | 4.5 (4 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Pergaminho de Fogo | advanced | 67.7% | +16.7pp | 2.5 | +6.7pp | +16.7pp | 4.2 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Escudo Torre | advanced | 96.7% | +16.7pp | 2.3 | — | +16.7pp | 1.9 (9 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Pedra de Amolar | basic | 89.0% | +15.7pp | 2.2 | +15.7pp | +5.7pp | 5.2 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Elmo de Ferro | advanced | 64.0% | +13.0pp | 2.1 | +2.0pp | +13.0pp | 2.6 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Rubi Ígneo | advanced | 91.7% | +11.7pp | 1.9 | +0.0pp | +11.7pp | 2.3 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Amuleto de Madeira | basic | 40.0% | +9.7pp | 1.7 | +8.0pp | +9.7pp | 3.2 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Paladino |
| Gazuas | basic | 60.0% | +9.3pp | 1.9 | +9.3pp | — | 3.1 (3 PO) | ▲ forte | com Ladino · party Patrulheiro/Ladino/Guerreiro · sala 3 · melhor em: Ladino |
| Broquel | basic | 82.0% | +8.7pp | 1.7 | +8.7pp | +5.3pp | 2.9 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Erva Curativa | basic | 41.7% | +7.7pp | 1.5 | +4.0pp | +7.7pp | 3.8 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Rato de Cripta | basic | 59.3% | +7.0pp | 2.5 | +7.0pp | +5.0pp | 2.3 (3 PO) | ▲ forte | com Patrulheiro · party Patrulheiro/Ladino/Paladino · sala 3 · melhor em: Patrulheiro |
| Poção de Mana Menor | basic | 79.7% | +6.3pp | 1.5 | +6.3pp | +0.0pp | 2.1 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gema Bruta | basic | 79.7% | +6.3pp | 1.5 | +6.3pp | +0.0pp | 2.1 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Aljava | basic | 79.7% | +6.3pp | 1.5 | +6.3pp | +0.0pp | 2.1 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gibão de Couro | basic | 33.7% | +5.7pp | 1.5 | +5.3pp | +5.7pp | 1.9 (3 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Mago |
| Símbolo Sagrado | advanced | 59.7% | +4.3pp | 1.2 | +3.3pp | +4.3pp | 0.7 (6 PO) | ▲ forte | com Paladino · party Patrulheiro/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Grimório | advanced | 85.7% | +4.0pp | 2.0 | -2.7pp | +4.0pp | 0.4 (11 PO) | ▲ forte | com Mago · party Mago/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Mago (no lugar de Cajado Runado) |
| Gema de Mana | advanced | 81.3% | +1.3pp | 1.7 | +0.0pp | +1.3pp | 0.3 (5 PO) |  | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Lobo Cinzento | advanced | 54.7% | -0.7pp | 2.1 | -4.0pp | -0.7pp | -0.1 (10 PO) |  | com Patrulheiro · party Patrulheiro/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Patrulheiro (no lugar de Arco Longo) |

## Encantamentos (em todas as armas)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Armazenador | encantamento | 66.7% | +38.7pp | 2.9 | ▲ forte | em todas as armas |
| Gélido | encantamento | 63.7% | +35.7pp | 2.8 | ▲ forte | em todas as armas |
| Trovejante | encantamento | 63.3% | +35.3pp | 3.0 | ▲ forte | em todas as armas |
| Flamejante | encantamento | 59.7% | +31.7pp | 2.9 | ▲ forte | em todas as armas |
| Veloz | encantamento | 53.3% | +25.3pp | 2.6 | ▲ forte | em todas as armas |
| Defensor | encantamento | 53.0% | +25.0pp | 2.5 | ▲ forte | em todas as armas |
| Afiado | encantamento | 51.3% | +23.3pp | 2.8 | ▲ forte | em todas as armas |
| Vorpal | encantamento | 51.0% | +23.0pp | 2.6 | ▲ forte | em todas as armas |
| Mortal | encantamento | 50.0% | +22.0pp | 2.6 | ▲ forte | em todas as armas |
| Vampírico | encantamento | 45.7% | +17.7pp | 2.2 | ▲ forte | em todas as armas |

## Fusão: item +1 contra 2 cópias +0

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Poção de Vida Menor +1 | Consumível | 56.7% | +4.7pp | 1.2 | ▲ forte | vs 2x Poção de Vida Menor: 52% |
| Arco Curto +1 | Arma/Instrumento | 74.7% | +4.0pp | 2.1 |  | vs 2x Arco Curto: 71% |
| Espada Curta +1 | Arma/Instrumento | 69.0% | +2.7pp | 2.4 |  | vs 2x Espada Curta: 66% |
| Cajado de Aprendiz +1 | Arma/Instrumento | 66.0% | +2.3pp | 2.3 |  | vs 2x Cajado de Aprendiz: 64% |
| Pedra de Amolar +1 | Catalisador | 34.3% | +1.7pp | 1.0 |  | vs 2x Pedra de Amolar: 33% |
| Broquel +1 | Armadura | 38.0% | +1.0pp | 0.6 |  | vs 2x Broquel: 37% |
| Gibão de Couro +1 | Armadura | 39.0% | +1.0pp | 0.6 |  | vs 2x Gibão de Couro: 38% |
| Amuleto de Madeira +1 | Catalisador | 31.0% | +1.0pp | 0.6 |  | vs 2x Amuleto de Madeira: 30% |
| Maça +1 | Arma/Instrumento | 67.3% | -1.0pp | 2.4 |  | vs 2x Maça: 68% |
| Adaga +1 | Arma/Instrumento | 61.7% | -5.3pp | 2.5 | ▼ fraco | vs 2x Adaga: 67% |
| Gema Bruta +1 | Catalisador | 42.7% | -7.0pp | 1.5 | ▼ fraco | vs 2x Gema Bruta: 50% |
| Tambor de Guerra +1 | Arma/Instrumento | 54.7% | -14.7pp | 2.4 | ▼ fraco | vs 2x Tambor de Guerra: 69% |
| Poção de Mana Menor +1 | Consumível | 28.0% | +0.0pp | 0.0 |  | vs 2x Poção de Mana Menor: 28% |
| Erva Curativa +1 | Catalisador | 33.3% | +0.0pp | 0.0 |  | vs 2x Erva Curativa: 33% |

_Tempo de simulação: 73.0s._

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
| Guerreiro | Vanguarda 41% (25%) | Vanguarda 46% (34%) | Vanguarda 53% (45%) |
| Paladino | Vanguarda 38% (22%) | Vanguarda 38% (24%) | Vanguarda 41% (31%) |
| Bárbaro | Vanguarda 38% (28%) | Vanguarda 41% (33%) | Vanguarda 50% (45%) |
| Bardo | Meio 34% (28%) | Meio 47% (40%) | Meio 54% (51%) |
| Ladino | Meio 47% (32%) | Meio 38% (30%) | Meio 35% (33%) |
| Patrulheiro | Retaguarda 31% (23%) | Retaguarda 33% (27%) | Retaguarda 39% (35%) |
| Mago | Retaguarda 35% (25%) | Retaguarda 45% (37%) | Meio 59% (51%) |
| Alquimista | Retaguarda 36% (31%) | Retaguarda 49% (45%) | Retaguarda 56% (53%) |
| **Diferença** | **16 pp** | **16 pp** | **23 pp** |
| **Duração média da luta** | 19.4s | 14.9s | 11.6s |

_Tempo de simulação: 119.8s._
