# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 320 --out /tmp/claude-0/-home-user/9c313045-93b3-5e24-94e7-7b32312bf85f/scratchpad/f32.md` em 2026-11-19T17:53:53.323Z · commit `efef274`
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
| Guerreiro | Vanguarda 37% (24%) | Vanguarda 43% (31%) | Vanguarda 44% (36%) |
| Paladino | Vanguarda 39% (26%) | Vanguarda 43% (32%) | Vanguarda 43% (36%) |
| Bárbaro | Vanguarda 41% (32%) | Vanguarda 52% (39%) | Vanguarda 57% (47%) |
| Bardo | Meio 32% (26%) | Meio 42% (37%) | Meio 42% (40%) |
| Ladino | Meio 47% (35%) | Meio 51% (41%) | Meio 38% (35%) |
| Patrulheiro | Retaguarda 35% (26%) | Retaguarda 30% (25%) | Retaguarda 34% (30%) |
| Mago | Retaguarda 30% (22%) | Retaguarda 44% (36%) | Meio 58% (48%) |
| Alquimista | Retaguarda 35% (30%) | Retaguarda 49% (43%) | Retaguarda 49% (46%) |
| **Diferença** | **17 pp** | **21 pp** | **24 pp** |
| **Duração média da luta** | 21.7s | 16.7s | 9.1s |

### Painel de metas (critério Q-27)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 44% e 56% (melhor posição) | ❌ 1/8 | ❌ 4/8 | ❌ 1/8 |
| Diferença melhor − pior ≤ 12pp | ❌ 17pp | ❌ 21pp | ❌ 24pp |
| Duração média 14–18s | ❌ 21.7s | ✅ 16.7s | ❌ 9.1s |
| Absurdos da Fase 1 (classe > 70% ou < 25%, luta < 8s) | ✅ nenhum | ✅ nenhum | ✅ nenhum |

_Tempo de simulação: 250.9s._
