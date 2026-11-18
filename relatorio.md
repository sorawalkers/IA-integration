# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 320` em 2026-11-18T18:39:10.226Z · commit `7f1f05d`
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
| Guerreiro | Vanguarda 41% (25%) | Vanguarda 47% (34%) | Vanguarda 53% (44%) |
| Paladino | Vanguarda 38% (22%) | Vanguarda 40% (25%) | Vanguarda 41% (31%) |
| Bárbaro | Vanguarda 42% (31%) | Vanguarda 43% (34%) | Vanguarda 51% (45%) |
| Bardo | Meio 28% (23%) | Meio 43% (38%) | Meio 58% (52%) |
| Ladino | Meio 42% (29%) | Meio 37% (30%) | Meio 37% (34%) |
| Patrulheiro | Retaguarda 31% (23%) | Retaguarda 36% (30%) | Retaguarda 43% (39%) |
| Mago | Retaguarda 40% (29%) | Retaguarda 52% (42%) | Meio 57% (48%) |
| Alquimista | Retaguarda 43% (37%) | Retaguarda 50% (46%) | Retaguarda 49% (45%) |
| **Diferença** | **14 pp** | **16 pp** | **21 pp** |
| **Duração média da luta** | 26.1s | 15.8s | 7.5s |

_Tempo de simulação: 109.9s._
