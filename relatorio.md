# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --fights 300 --out relatorio.md` em 2026-11-18T20:42:29.617Z · commit `8121dc4`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

Linha de base **[Mago, Bardo, Guerreiro]** contra ghosts da **sala 3**: 18.0% de vitória, 17.4s por luta (300 lutas por variante).

## Classes (média nas 512 composições; delta = diferença para a média geral)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Ladino | sug. Meio | 34.5% | +6.6pp | 0.7 | ▲ forte | melhor: Meio · Retaguarda 34% · Meio 48% · Vanguarda 22% |
| Bárbaro | sug. Vanguarda | 30.7% | +2.8pp | 0.7 |  | melhor: Vanguarda · Retaguarda 26% · Meio 28% · Vanguarda 39% |
| Alquimista | sug. Retaguarda | 30.4% | +2.5pp | 0.7 |  | melhor: Retaguarda · Retaguarda 35% · Meio 27% · Vanguarda 30% |
| Patrulheiro | sug. Retaguarda | 27.1% | -0.8pp | 0.6 |  | melhor: Retaguarda · Retaguarda 37% · Meio 26% · Vanguarda 19% |
| Bardo | sug. Meio | 25.9% | -2.0pp | 0.6 |  | melhor: Meio · Retaguarda 26% · Meio 31% · Vanguarda 21% |
| Guerreiro | sug. Vanguarda | 25.4% | -2.5pp | 0.6 |  | melhor: Vanguarda · Retaguarda 17% · Meio 19% · Vanguarda 40% |
| Paladino | sug. Vanguarda | 24.6% | -3.3pp | 0.6 | ▼ fraco | melhor: Vanguarda · Retaguarda 17% · Meio 17% · Vanguarda 39% |
| Mago | sug. Retaguarda | 24.5% | -3.4pp | 0.6 | ▼ fraco | melhor: Retaguarda · Retaguarda 32% · Meio 28% · Vanguarda 13% |

## Itens (+1 cópia na party, no melhor herói e posição)

"Com Ladino" / "Sem Ladino": melhor delta nas parties de referência com e sem Ladino. O Combo do Ladino
(+8% de crítico por item diferente encostado na adaga) valoriza qualquer item pequeno; "Sem Ladino" mostra
a utilidade própria do item.

| Variante | Grupo | Vitória | Delta | ± | Com Ladino | Sem Ladino | pp/PO | Veredito | Nota |
|---|---|---|---|---|---|---|---|---|---|
| Cajado do Arquimago | advanced | 98.0% | +57.0pp | 2.9 | +43.3pp | +57.0pp | 4.1 (14 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Égide do Cruzado | advanced | 95.3% | +54.3pp | 2.9 | +33.0pp | +54.3pp | 3.6 (15 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Lobo Alfa Espiritual | advanced | 82.0% | +41.0pp | 2.9 | +25.7pp | +41.0pp | 3.4 (12 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Machado Trovejante | advanced | 80.7% | +39.7pp | 2.9 | +28.7pp | +39.7pp | 3.1 (13 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Língua de Fogo | advanced | 76.3% | +35.3pp | 2.8 | +23.7pp | +35.3pp | 2.7 (13 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Adaga | basic | 70.3% | +32.7pp | 2.7 | +7.7pp | +32.7pp | 10.9 (3 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Maça | basic | 70.3% | +32.7pp | 2.7 | +12.3pp | +32.7pp | 8.2 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Espada Curta | basic | 69.7% | +32.0pp | 2.7 | +12.7pp | +32.0pp | 8.0 (4 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Bomba Alquímica | basic | 51.0% | +31.0pp | 2.7 | +14.7pp | +31.0pp | 10.3 (3 PO) | ▲ forte | com Alquimista · party Alquimista/Bardo/Guerreiro · sala 3 · melhor em: Alquimista |
| Rubi Ígneo | advanced | 90.7% | +31.0pp | 2.7 | +0.0pp | +31.0pp | 6.2 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Presa de Víbora | advanced | 71.3% | +30.3pp | 2.7 | +14.3pp | +30.3pp | 6.1 (5 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Escudo Torre | advanced | 89.7% | +30.0pp | 2.8 | — | +30.0pp | 3.3 (9 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Guerreiro |
| Grimório | advanced | 83.0% | +29.3pp | 2.7 | +16.3pp | +29.3pp | 2.7 (11 PO) | ▲ forte | com Mago · party Mago/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Cajado Runado | advanced | 69.7% | +28.7pp | 2.6 | +20.3pp | +28.7pp | 3.2 (9 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Cajado de Aprendiz | basic | 51.0% | +28.3pp | 2.7 | +21.7pp | +28.3pp | 7.1 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Bardo |
| Ração de Viagem | basic | 65.0% | +27.3pp | 2.6 | +12.7pp | +27.3pp | 13.7 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Patrulheiro |
| Poção de Vida Menor | basic | 49.3% | +26.7pp | 2.6 | +16.0pp | +26.7pp | 8.9 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Arco Longo | advanced | 67.3% | +26.3pp | 2.7 | +16.3pp | +26.3pp | 3.8 (7 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Pergaminho de Fogo | advanced | 65.7% | +24.7pp | 2.6 | +14.7pp | +24.7pp | 6.2 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Tomo Menor | basic | 42.3% | +24.3pp | 2.7 | +18.3pp | +24.3pp | 6.1 (4 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Mago |
| Símbolo Sagrado | advanced | 65.3% | +24.3pp | 2.5 | +18.7pp | +24.3pp | 4.1 (6 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Paladino |
| Elixir da Restauração | advanced | 84.0% | +24.3pp | 2.5 | +13.3pp | +24.3pp | 3.0 (8 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Arco Curto | basic | 46.7% | +24.0pp | 2.5 | +12.3pp | +24.0pp | 6.0 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Harpa da Fortuna | advanced | 64.7% | +23.7pp | 2.6 | +19.7pp | +23.7pp | 1.6 (15 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Tambor de Guerra | basic | 44.3% | +21.7pp | 2.5 | +19.0pp | +21.7pp | 5.4 (4 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Alquimista |
| Machado Grande | advanced | 59.3% | +20.7pp | 2.6 | +14.3pp | +20.7pp | 2.1 (10 PO) | ▲ forte | com Bárbaro · party Patrulheiro/Bardo/Bárbaro · sala 9 (item +1, party evoluída) · melhor em: Bárbaro (no lugar de Adaga) |
| Poção de Vida Maior | advanced | 80.0% | +20.3pp | 2.3 | +17.0pp | +20.3pp | 4.1 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |
| Espada Longa | advanced | 60.7% | +19.7pp | 2.5 | +12.3pp | +19.7pp | 2.5 (8 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Alquimista |
| Pedra de Amolar | basic | 86.0% | +16.3pp | 2.1 | +16.3pp | +8.7pp | 5.4 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Elmo de Ferro | advanced | 56.7% | +15.7pp | 2.2 | +6.0pp | +15.7pp | 3.1 (5 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Amuleto de Madeira | basic | 36.7% | +14.0pp | 2.1 | +10.0pp | +14.0pp | 4.7 (3 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 3 · melhor em: Paladino |
| Gazuas | basic | 81.7% | +12.0pp | 1.9 | +12.0pp | — | 4.0 (3 PO) | ▲ forte | com Ladino · party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Lobo Cinzento | advanced | 48.7% | +10.7pp | 2.1 | +6.0pp | +10.7pp | 1.1 (10 PO) | ▲ forte | com Patrulheiro · party Patrulheiro/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Patrulheiro |
| Broquel | basic | 80.0% | +10.3pp | 1.9 | +10.3pp | +7.3pp | 3.4 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Poção de Mana Menor | basic | 80.0% | +10.3pp | 1.9 | +10.3pp | +0.0pp | 3.4 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Gema Bruta | basic | 28.3% | +10.3pp | 1.8 | +10.3pp | +10.3pp | 3.4 (3 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 3 · melhor em: Mago |
| Aljava | basic | 80.0% | +10.3pp | 1.9 | +10.3pp | +0.0pp | 3.4 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Erva Curativa | basic | 46.0% | +8.3pp | 1.6 | +6.0pp | +8.3pp | 4.2 (2 PO) | ▲ forte | party Patrulheiro/Bardo/Guerreiro · sala 3 · melhor em: Guerreiro |
| Gibão de Couro | basic | 76.0% | +6.3pp | 1.6 | +6.3pp | +4.7pp | 2.1 (3 PO) | ▲ forte | party Alquimista/Ladino/Paladino · sala 3 · melhor em: Ladino |
| Rato de Cripta | basic | 67.0% | +6.0pp | 2.4 | +6.0pp | +0.7pp | 2.0 (3 PO) | ▲ forte | com Patrulheiro · party Patrulheiro/Ladino/Paladino · sala 3 · melhor em: Patrulheiro |
| Alaúde dos Ventos | advanced | 45.7% | +4.7pp | 2.1 | — | +4.7pp | 0.4 (12 PO) | ▲ forte | party Alquimista/Bardo/Paladino · sala 9 (item +1, party evoluída) · melhor em: Bardo |
| Gema de Mana | advanced | 64.0% | +4.3pp | 1.4 | +0.7pp | +4.3pp | 0.9 (5 PO) | ▲ forte | party Mago/Bardo/Guerreiro · sala 9 (item +1, party evoluída) · melhor em: Mago |

## Encantamentos (em todas as armas)

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Flamejante | encantamento | 60.3% | +42.3pp | 2.9 | ▲ forte | em todas as armas |
| Gélido | encantamento | 58.7% | +40.7pp | 2.9 | ▲ forte | em todas as armas |
| Armazenador | encantamento | 54.3% | +36.3pp | 2.8 | ▲ forte | em todas as armas |
| Trovejante | encantamento | 53.3% | +35.3pp | 2.8 | ▲ forte | em todas as armas |
| Mortal | encantamento | 47.7% | +29.7pp | 2.6 | ▲ forte | em todas as armas |
| Veloz | encantamento | 45.0% | +27.0pp | 2.7 | ▲ forte | em todas as armas |
| Defensor | encantamento | 44.3% | +26.3pp | 2.5 | ▲ forte | em todas as armas |
| Afiado | encantamento | 43.7% | +25.7pp | 2.6 | ▲ forte | em todas as armas |
| Vorpal | encantamento | 41.7% | +23.7pp | 2.6 | ▲ forte | em todas as armas |
| Vampírico | encantamento | 32.3% | +14.3pp | 2.0 | ▲ forte | em todas as armas |

## Fusão: item +1 contra 2 cópias +0

| Variante | Grupo | Vitória | Delta | ± | Veredito | Nota |
|---|---|---|---|---|---|---|
| Tambor de Guerra +1 | Arma/Instrumento | 45.7% | +11.0pp | 1.9 | ▲ forte | vs 2x Tambor de Guerra: 35% · no Guerreiro |
| Arco Curto +1 | Arma/Instrumento | 66.0% | +7.3pp | 2.1 | ▲ forte | vs 2x Arco Curto: 59% · no Guerreiro |
| Espada Curta +1 | Arma/Instrumento | 59.7% | +5.7pp | 2.2 | ▲ forte | vs 2x Espada Curta: 54% · no Guerreiro |
| Poção de Vida Menor +1 | Consumível | 40.3% | +2.7pp | 1.0 |  | vs 2x Poção de Vida Menor: 38% · no Mago |
| Adaga +1 | Arma/Instrumento | 53.3% | +1.3pp | 1.9 |  | vs 2x Adaga: 52% · no Guerreiro |
| Broquel +1 | Armadura | 25.7% | +1.3pp | 0.7 |  | vs 2x Broquel: 24% · no Mago |
| Gibão de Couro +1 | Armadura | 28.3% | +1.3pp | 0.8 |  | vs 2x Gibão de Couro: 27% · no Mago |
| Maça +1 | Arma/Instrumento | 57.0% | +1.0pp | 2.2 |  | vs 2x Maça: 56% · no Guerreiro |
| Cajado de Aprendiz +1 | Arma/Instrumento | 53.7% | -2.0pp | 1.9 |  | vs 2x Cajado de Aprendiz: 56% · no Bardo |
| Gema Bruta +1 | Catalisador | 41.0% | -6.0pp | 1.4 | ▼ fraco | vs 2x Gema Bruta: 47% · no Mago |
| Poção de Mana Menor +1 | Consumível | 18.0% | +0.0pp | 0.0 |  | vs 2x Poção de Mana Menor: 18% · no Mago |
| Pedra de Amolar +1 | Catalisador | 22.3% | +0.0pp | 0.0 |  | vs 2x Pedra de Amolar: 22% · no Bardo |
| Erva Curativa +1 | Catalisador | 24.0% | +0.0pp | 0.0 |  | vs 2x Erva Curativa: 24% · no Mago |
| Amuleto de Madeira +1 | Catalisador | 21.0% | +0.0pp | 0.0 |  | vs 2x Amuleto de Madeira: 21% · no Mago |

_Tempo de simulação: 129.1s._

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
| Guerreiro | Vanguarda 40% (25%) | Vanguarda 45% (32%) | Vanguarda 54% (44%) |
| Paladino | Vanguarda 39% (24%) | Vanguarda 43% (30%) | Vanguarda 52% (42%) |
| Bárbaro | Vanguarda 38% (30%) | Vanguarda 41% (33%) | Vanguarda 50% (43%) |
| Bardo | Meio 31% (26%) | Meio 39% (35%) | Meio 48% (46%) |
| Ladino | Meio 48% (34%) | Meio 42% (34%) | Meio 40% (38%) |
| Patrulheiro | Retaguarda 36% (27%) | Retaguarda 31% (25%) | Retaguarda 43% (39%) |
| Mago | Retaguarda 33% (25%) | Meio 49% (40%) | Meio 70% (58%) |
| Alquimista | Retaguarda 35% (30%) | Retaguarda 43% (39%) | Retaguarda 55% (51%) |
| **Diferença** | **17 pp** | **18 pp** | **29 pp** |
| **Duração média da luta** | 20.9s | 13.6s | 7.8s |

### Painel de metas (critério Q-27)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 44% e 56% (melhor posição) | ❌ 1/8 | ❌ 2/8 | ❌ 5/8 |
| Diferença melhor − pior ≤ 12pp | ❌ 17pp | ❌ 18pp | ❌ 29pp |
| Duração média 14–18s | ❌ 20.9s | ❌ 13.6s | ❌ 7.8s |
| Absurdos da Fase 1 (classe > 70% ou < 25%, luta < 8s) | ✅ nenhum | ✅ nenhum | ⚠ luta < 8s |

_Tempo de simulação: 218.6s._
