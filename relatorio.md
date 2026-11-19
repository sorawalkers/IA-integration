# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 320 --out /tmp/claude-0/-home-user/9c313045-93b3-5e24-94e7-7b32312bf85f/scratchpad/f34.md` em 2026-11-19T18:24:47.337Z · commit `80d7634`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

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
| Guerreiro | Vanguarda 37% (25%) | Vanguarda 41% (30%) | Vanguarda 40% (34%) |
| Paladino | Vanguarda 39% (26%) | Vanguarda 40% (32%) | Vanguarda 42% (35%) |
| Bárbaro | Vanguarda 39% (30%) | Vanguarda 47% (36%) | Vanguarda 50% (41%) |
| Bardo | Meio 31% (26%) | Meio 41% (36%) | Meio 42% (39%) |
| Ladino | Meio 48% (35%) | Meio 57% (46%) | Meio 43% (40%) |
| Patrulheiro | Retaguarda 34% (26%) | Retaguarda 29% (24%) | Retaguarda 30% (26%) |
| Mago | Retaguarda 29% (22%) | Retaguarda 38% (31%) | Meio 54% (46%) |
| Alquimista | Retaguarda 33% (28%) | Retaguarda 45% (41%) | Retaguarda 50% (47%) |
| **Diferença** | **20 pp** | **28 pp** | **24 pp** |
| **Duração média da luta** | 19.3s | 17.1s | 11.4s |

### Painel de metas (critério Q-37)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% (melhor posição) | ❌ 1/8 | ❌ 6/8 | ❌ 7/8 |
| Melhor composição ≤ 68% | ❌ 85% | ❌ 90% | ❌ 91% |
| Nenhuma classe em mais de 6 das 10 melhores composições | ❌ Ladino 10/10 | ❌ Ladino 9/10 | ❌ Alquimista 9/10 |
| Duração média 14–18s | ❌ 19.3s | ✅ 17.1s | ❌ 11.4s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ✅ nenhum | ✅ nenhum | ✅ nenhum |

### Top 10 composições — sala 3

80 lutas por composição (erro ≈ ±5pp; o top 10 tende a sair um pouco acima do real por sorte).

| # | Retaguarda | Meio | Vanguarda | Vitória |
|---|---|---|---|---|
| 1 | Alquimista | Ladino | Bárbaro | 85% |
| 2 | Alquimista | Ladino | Paladino | 84% |
| 3 | Alquimista | Ladino | Guerreiro | 80% |
| 4 | Paladino | Ladino | Paladino | 76% |
| 5 | Bardo | Ladino | Guerreiro | 76% |
| 6 | Alquimista | Ladino | Alquimista | 75% |
| 7 | Paladino | Ladino | Guerreiro | 71% |
| 8 | Bárbaro | Ladino | Paladino | 71% |
| 9 | Patrulheiro | Ladino | Paladino | 71% |
| 10 | Patrulheiro | Ladino | Bárbaro | 71% |

### Top 10 composições — sala 9

80 lutas por composição (erro ≈ ±5pp; o top 10 tende a sair um pouco acima do real por sorte).

| # | Retaguarda | Meio | Vanguarda | Vitória |
|---|---|---|---|---|
| 1 | Alquimista | Ladino | Bárbaro | 90% |
| 2 | Alquimista | Ladino | Guerreiro | 88% |
| 3 | Alquimista | Ladino | Paladino | 86% |
| 4 | Alquimista | Ladino | Alquimista | 86% |
| 5 | Alquimista | Ladino | Ladino | 83% |
| 6 | Paladino | Ladino | Guerreiro | 78% |
| 7 | Paladino | Ladino | Alquimista | 78% |
| 8 | Alquimista | Mago | Bárbaro | 78% |
| 9 | Paladino | Ladino | Paladino | 76% |
| 10 | Bárbaro | Ladino | Guerreiro | 76% |

### Top 10 composições — sala 18

80 lutas por composição (erro ≈ ±5pp; o top 10 tende a sair um pouco acima do real por sorte).

| # | Retaguarda | Meio | Vanguarda | Vitória |
|---|---|---|---|---|
| 1 | Alquimista | Mago | Bárbaro | 91% |
| 2 | Alquimista | Mago | Paladino | 86% |
| 3 | Bardo | Bardo | Bardo | 84% |
| 4 | Mago | Bardo | Alquimista | 81% |
| 5 | Alquimista | Mago | Bardo | 81% |
| 6 | Mago | Mago | Alquimista | 79% |
| 7 | Mago | Alquimista | Guerreiro | 79% |
| 8 | Alquimista | Ladino | Bárbaro | 79% |
| 9 | Bardo | Mago | Alquimista | 76% |
| 10 | Mago | Ladino | Alquimista | 76% |

_Tempo de simulação: 238.9s._
