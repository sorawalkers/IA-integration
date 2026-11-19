# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 500 --out relatorio-solo.md` em 2026-11-19T19:38:42.760Z · commit `5ad6d43`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

## Escalonamento das classes (sala 3, sala 9, sala 18)

**Modo solo** (branch `feat/solo-class`, SPEC-SOLO): 4 classes x 4 classes = 16 confrontos por sala, 500 lutas por confronto, **iniciativa alternada** (metade das lutas com os lados trocados). Os dois lados evoluem igual:

| Sala | Itens extras | Fusão | Encantamentos |
|---|---|---|---|
| 3 | 2 | +0 | 0 |
| 9 | 4 | +1 | 1 |
| 18 | 8 | +1 (20% +2) | 3 |

Vitória média de cada classe contra as 4 classes (inclui o espelho, que deve ficar perto de 50%)

| Classe | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 45% | 52% | 42% |
| Ladino | 71% | 67% | 61% |
| Patrulheiro | 47% | 40% | 45% |
| Mago | 40% | 41% | 55% |
| **Diferença** | **31 pp** | **27 pp** | **19 pp** |
| **Duração média da luta** | 17.9s | 14.7s | 20.3s |

### Painel de metas (modo solo)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% | ❌ 2/4 | ❌ 3/4 | ❌ 3/4 |
| Confrontos extremos (um lado vence > 80%), de 6 | ❌ 1 | ❌ 1 | ✅ 0 |
| Espelhos entre 45% e 55% | ✅ 4/4 (55 / 50 / 47 / 50) | ✅ 4/4 (49 / 51 / 51 / 51) | ✅ 4/4 (50 / 52 / 51 / 49) |
| Duração média 14–18s | ✅ 17.9s | ✅ 14.7s | ❌ 20.3s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ⚠ Ladino | ✅ nenhum | ✅ nenhum |

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 55 | 26 | 48 | 52 |
| **Ladino** | 76 | 50 | 83 | 76 |
| **Patrulheiro** | 54 | 20 | 47 | 66 |
| **Mago** | 50 | 23 | 35 | 50 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 49 | 46 | 57 | 57 |
| **Ladino** | 58 | 51 | 83 | 77 |
| **Patrulheiro** | 41 | 15 | 51 | 53 |
| **Mago** | 44 | 24 | 45 | 51 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 50 | 36 | 38 | 43 |
| **Ladino** | 66 | 52 | 66 | 60 |
| **Patrulheiro** | 66 | 32 | 51 | 30 |
| **Mago** | 57 | 41 | 72 | 49 |

_Tempo de simulação: 44.4s._
