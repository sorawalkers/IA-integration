# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --fights 300 --out relatorio.md` em 2026-11-19T11:52:08.203Z · commit `072b6c3`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

Linha de base **[Mago, Bardo, Guerreiro]** contra ghosts da **sala 3**: 20.0% de vitória, 17.0s por luta (300 lutas por variante).

## Classes (média nas 512 composições; delta = diferença para a média geral)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Ladino | sug. Meio | 34.9% | +6.2pp | 0.7 | ▲ forte | melhor: Meio · Retaguarda 34% · Meio 47% · Vanguarda 23% |
| Bárbaro | sug. Vanguarda | 32.3% | +3.6pp | 0.7 | ▲ forte | melhor: Vanguarda · Retaguarda 26% · Meio 28% · Vanguarda 43% |
| Alquimista | sug. Retaguarda | 31.2% | +2.5pp | 0.7 |  | melhor: Retaguarda · Retaguarda 36% · Meio 28% · Vanguarda 29% |
| Bardo | sug. Meio | 27.7% | -1.0pp | 0.6 |  | melhor: Meio · Retaguarda 27% · Meio 33% · Vanguarda 23% |
| Patrulheiro | sug. Retaguarda | 27.4% | -1.3pp | 0.6 |  | melhor: Retaguarda · Retaguarda 36% · Meio 26% · Vanguarda 20% |
| Paladino | sug. Vanguarda | 26.3% | -2.4pp | 0.6 |  | melhor: Vanguarda · Retaguarda 20% · Meio 19% · Vanguarda 39% |
| Mago | sug. Retaguarda | 25.1% | -3.6pp | 0.6 | ▼ fraco | melhor: Retaguarda · Retaguarda 32% · Meio 30% · Vanguarda 14% |
| Guerreiro | sug. Vanguarda | 24.7% | -4.0pp | 0.6 | ▼ fraco | melhor: Vanguarda · Retaguarda 17% · Meio 19% · Vanguarda 38% |

## Itens (+1 cópia na party, no melhor herói e posição)

"Com Ladino" / "Sem Ladino": melhor delta nas parties de referência com e sem Ladino. O Combo do Ladino
(+8% de crítico por item diferente encostado na adaga) valoriza qualquer item pequeno; "Sem Ladino" mostra
a utilidade própria do item.

| Variante | Grupo | Vitória | Delta | ± | Com Ladino | Sem Ladino | pp/PO | Veredito | Nota |
|---|---|---|---|---|---|---|---|---|---|
| Cajado do Arquimago | advanced | 87.0% | +58.7pp | 2.8 | +43.3pp | +58.7pp | 4.2 (14 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Égide do Cruzado | advanced | 86.0% | +57.7pp | 2.9 | +43.3pp | +57.7pp | 3.8 (15 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Machado Trovejante | advanced | 78.7% | +50.3pp | 2.9 | +21.7pp | +50.3pp | 3.9 (13 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo (no lugar de Adaga) |
| Grimório | advanced | 75.0% | +49.0pp | 2.9 | +31.0pp | +49.0pp | 4.5 (11 PO) | ▲ forte | com Mago · party Mago/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Escudo Torre | advanced | 79.7% | +44.7pp | 3.2 | — | +44.7pp | 5.0 (9 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro (no lugar de Espada Curta) |
| Rubi Ígneo | advanced | 74.0% | +39.0pp | 2.9 | +5.0pp | +39.0pp | 7.8 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Lobo Alfa Espiritual | advanced | 62.7% | +34.3pp | 2.8 | +31.7pp | +34.3pp | 2.9 (12 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Harpa da Fortuna | advanced | 67.7% | +29.7pp | 2.6 | +29.7pp | +20.0pp | 2.0 (15 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 9 (item +1, party evoluída) · melhor em: Ladino |
| Espada Curta | basic | 57.3% | +28.0pp | 2.7 | +9.0pp | +28.0pp | 7.0 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Adaga | basic | 56.7% | +27.3pp | 2.6 | +1.0pp | +27.3pp | 9.1 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Maça | basic | 56.7% | +27.3pp | 2.6 | +8.3pp | +27.3pp | 6.8 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Língua de Fogo | advanced | 55.7% | +27.3pp | 2.7 | +17.7pp | +27.3pp | 2.1 (13 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Cajado de Aprendiz | basic | 50.3% | +27.0pp | 2.6 | +22.3pp | +27.0pp | 6.8 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Bomba Alquímica | basic | 43.3% | +26.3pp | 2.6 | +9.7pp | +26.3pp | 8.8 (3 PO) | ▲ forte | com Alquimista · party Alquimista/Bardo/Guerreiro · sala 3 · melhor em: Alquimista |
| Poção de Vida Maior | advanced | 60.3% | +25.3pp | 2.5 | +23.3pp | +25.3pp | 5.1 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Ração de Viagem | basic | 53.3% | +24.0pp | 2.5 | +12.3pp | +24.0pp | 12.0 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Cajado Runado | advanced | 58.7% | +23.7pp | 3.0 | +16.0pp | +23.7pp | 2.6 (9 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Poção de Vida Menor | basic | 46.3% | +23.0pp | 2.4 | +17.3pp | +23.0pp | 7.7 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Presa de Víbora | advanced | 63.0% | +22.3pp | 2.5 | +17.0pp | +22.3pp | 4.5 (5 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Tambor de Guerra | basic | 44.0% | +20.7pp | 2.4 | +17.0pp | +20.7pp | 5.2 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Arco Curto | basic | 42.7% | +19.3pp | 2.5 | +6.7pp | +19.3pp | 4.8 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Tomo Menor | basic | 82.7% | +19.0pp | 2.5 | +19.0pp | +13.7pp | 4.8 (4 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gema de Mana | advanced | 53.0% | +18.0pp | 2.8 | +5.0pp | +18.0pp | 3.6 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Elixir da Restauração | advanced | 52.3% | +17.3pp | 2.4 | +16.3pp | +17.3pp | 2.2 (8 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Pedra de Amolar | basic | 80.0% | +16.3pp | 2.4 | +16.3pp | +6.7pp | 5.4 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Elmo de Ferro | advanced | 46.7% | +11.7pp | 1.9 | +6.7pp | +11.7pp | 2.3 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Espada Longa | advanced | 39.7% | +11.3pp | 2.1 | +4.7pp | +11.3pp | 1.4 (8 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Arco Longo | advanced | 46.0% | +11.0pp | 2.8 | +6.7pp | +11.0pp | 1.6 (7 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Amuleto de Madeira | basic | 33.3% | +10.0pp | 1.8 | +8.7pp | +10.0pp | 3.3 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Paladino |
| Broquel | basic | 73.3% | +9.7pp | 2.0 | +9.7pp | +4.0pp | 3.2 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gazuas | basic | 73.3% | +9.7pp | 1.9 | +9.7pp | — | 3.2 (3 PO) | ▲ forte | com Ladino · party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Pergaminho de Fogo | advanced | 37.7% | +9.3pp | 1.8 | +9.0pp | +9.3pp | 2.3 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Poção de Mana Menor | basic | 72.3% | +8.7pp | 1.9 | +8.7pp | +1.0pp | 2.9 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gema Bruta | basic | 72.3% | +8.7pp | 1.9 | +8.7pp | +0.0pp | 2.9 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Aljava | basic | 72.3% | +8.7pp | 1.9 | +8.7pp | +0.0pp | 2.9 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Lobo Cinzento | advanced | 26.0% | +7.7pp | 2.2 | +7.7pp | +1.0pp | 0.8 (10 PO) | ▲ forte | com Patrulheiro · party Patrulheiro/Ladino/Paladino · sala 9 (item +1, party evoluída) · melhor em: Patrulheiro |
| Erva Curativa | basic | 36.7% | +7.3pp | 1.5 | +1.7pp | +7.3pp | 3.7 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Rato de Cripta | basic | 57.3% | +6.0pp | 2.4 | +6.0pp | +4.0pp | 2.0 (3 PO) | ▲ forte | com Patrulheiro · party Patrulheiro/Ladino/Paladino · sala 3 · melhor em: Patrulheiro |
| Gibão de Couro | basic | 69.0% | +5.3pp | 1.7 | +5.3pp | +2.3pp | 1.8 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Símbolo Sagrado | advanced | 31.0% | +5.0pp | 1.4 | +4.7pp | +5.0pp | 0.8 (6 PO) | ▲ forte | com Paladino · party Mago/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Alaúde dos Ventos | advanced | 32.7% | -2.3pp | 2.4 | — | -2.3pp | -0.2 (12 PO) |  | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Machado Grande | advanced | — | — | — | — | — | — |  | sem espaço |

## Encantamentos (em todas as armas)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Gélido | encantamento | 54.3% | +34.3pp | 2.8 | ▲ forte | em todas as armas |
| Trovejante | encantamento | 50.7% | +30.7pp | 2.7 | ▲ forte | em todas as armas |
| Flamejante | encantamento | 49.0% | +29.0pp | 2.7 | ▲ forte | em todas as armas |
| Armazenador | encantamento | 47.3% | +27.3pp | 2.7 | ▲ forte | em todas as armas |
| Mortal | encantamento | 46.0% | +26.0pp | 2.6 | ▲ forte | em todas as armas |
| Vorpal | encantamento | 44.0% | +24.0pp | 2.6 | ▲ forte | em todas as armas |
| Afiado | encantamento | 37.0% | +17.0pp | 2.3 | ▲ forte | em todas as armas |
| Veloz | encantamento | 36.7% | +16.7pp | 2.3 | ▲ forte | em todas as armas |
| Defensor | encantamento | 32.7% | +12.7pp | 1.9 | ▲ forte | em todas as armas |
| Vampírico | encantamento | 29.0% | +9.0pp | 1.7 | ▲ forte | em todas as armas |

## Fusão: item +1 contra 2 cópias +0

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Tambor de Guerra +1 | Arma/Instrumento | 30.0% | +4.3pp | 1.8 | ▲ forte | vs 2x Tambor de Guerra: 26% · no Guerreiro |
| Maça +1 | Arma/Instrumento | 47.7% | +2.0pp | 2.0 |  | vs 2x Maça: 46% · no Guerreiro |
| Poção de Vida Menor +1 | Consumível | 38.0% | +2.0pp | 1.1 |  | vs 2x Poção de Vida Menor: 36% · no Mago |
| Adaga +1 | Arma/Instrumento | 45.0% | +1.3pp | 2.2 |  | vs 2x Adaga: 44% · no Guerreiro |
| Pedra de Amolar +1 | Catalisador | 23.0% | +0.7pp | 0.5 |  | vs 2x Pedra de Amolar: 22% · no Bardo |
| Broquel +1 | Armadura | 24.3% | +0.3pp | 0.3 |  | vs 2x Broquel: 24% · no Mago |
| Amuleto de Madeira +1 | Catalisador | 22.0% | +0.3pp | 0.3 |  | vs 2x Amuleto de Madeira: 22% · no Guerreiro |
| Gibão de Couro +1 | Armadura | 24.3% | -0.3pp | 0.6 |  | vs 2x Gibão de Couro: 25% · no Mago |
| Poção de Mana Menor +1 | Consumível | 21.0% | -0.7pp | 0.5 |  | vs 2x Poção de Mana Menor: 22% · no Mago |
| Espada Curta +1 | Arma/Instrumento | 44.0% | -3.3pp | 2.0 |  | vs 2x Espada Curta: 47% · no Guerreiro |
| Gema Bruta +1 | Catalisador | 36.0% | -3.3pp | 1.1 | ▼ fraco | vs 2x Gema Bruta: 39% · no Mago |
| Cajado de Aprendiz +1 | Arma/Instrumento | 48.7% | -4.0pp | 1.9 | ▼ fraco | vs 2x Cajado de Aprendiz: 53% · no Bardo |
| Arco Curto +1 | Arma/Instrumento | 55.0% | +0.0pp | 1.8 |  | vs 2x Arco Curto: 55% · no Guerreiro |
| Erva Curativa +1 | Catalisador | 23.7% | +0.0pp | 0.0 |  | vs 2x Erva Curativa: 24% · no Guerreiro |

_Tempo de simulação: 133.5s._

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
| Guerreiro | Vanguarda 37% (24%) | Vanguarda 43% (31%) | Vanguarda 44% (36%) |
| Paladino | Vanguarda 39% (26%) | Vanguarda 42% (32%) | Vanguarda 42% (34%) |
| Bárbaro | Vanguarda 42% (32%) | Vanguarda 51% (39%) | Vanguarda 58% (47%) |
| Bardo | Meio 32% (27%) | Meio 42% (38%) | Meio 42% (39%) |
| Ladino | Meio 47% (34%) | Meio 49% (39%) | Meio 37% (35%) |
| Patrulheiro | Retaguarda 36% (27%) | Retaguarda 30% (25%) | Retaguarda 35% (31%) |
| Mago | Retaguarda 32% (25%) | Meio 53% (43%) | Meio 58% (49%) |
| Alquimista | Retaguarda 36% (31%) | Retaguarda 47% (42%) | Retaguarda 48% (44%) |
| **Diferença** | **15 pp** | **22 pp** | **23 pp** |
| **Duração média da luta** | 20.9s | 14.7s | 7.4s |

### Painel de metas (critério Q-27)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 44% e 56% (melhor posição) | ❌ 1/8 | ❌ 4/8 | ❌ 2/8 |
| Diferença melhor − pior ≤ 12pp | ❌ 15pp | ❌ 22pp | ❌ 23pp |
| Duração média 14–18s | ❌ 20.9s | ✅ 14.7s | ❌ 7.4s |
| Absurdos da Fase 1 (classe > 70% ou < 25%, luta < 8s) | ✅ nenhum | ✅ nenhum | ⚠ luta < 8s |

_Tempo de simulação: 217.7s._

---

## Emboscada PvE: vitória da party (300 lutas, composições sorteadas, party do gerador)

| Encontro | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Horda de Goblins | 100% (6.9s) | 100% (3.6s) | 100% (1.8s) |
| Elite: Horda de Goblins | 99% (10.1s) | 100% (5.0s) | 100% (2.2s) |
| Câmara dos Esqueletos | 100% (11.5s) | 100% (5.7s) | 100% (2.5s) |
| Elite: Câmara dos Esqueletos | 99% (17.7s) | 100% (8.5s) | 100% (3.4s) |
| Ninho de Cubos Gelatinosos | 100% (13.9s) | 100% (7.0s) | 100% (2.9s) |
| Elite: Ninho de Cubos Gelatinosos | 74% (29.6s) | 96% (16.7s) | 100% (5.0s) |
