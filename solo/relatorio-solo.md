# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 500 --out relatorio-solo.md` em 2026-11-19T19:28:33.856Z · commit `1b56a97`
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
| Guerreiro | 44% | 46% | 36% |
| Ladino | 71% | 75% | 74% |
| Patrulheiro | 48% | 39% | 41% |
| Mago | 41% | 41% | 52% |
| **Diferença** | **30 pp** | **37 pp** | **38 pp** |
| **Duração média da luta** | 18.0s | 14.4s | 19.0s |

### Painel de metas (modo solo)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% | ❌ 3/4 | ❌ 2/4 | ❌ 2/4 |
| Confrontos extremos (um lado vence > 80%), de 6 | ❌ 1 | ❌ 1 | ❌ 2 |
| Espelhos entre 45% e 55% | ✅ 4/4 (55 / 51 / 47 / 50) | ✅ 4/4 (49 / 53 / 51 / 51) | ✅ 4/4 (50 / 53 / 50 / 49) |
| Duração média 14–18s | ✅ 18.0s | ✅ 14.4s | ❌ 19.0s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ⚠ Ladino | ⚠ Ladino | ⚠ Ladino |

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 55 | 20 | 48 | 52 |
| **Ladino** | 80 | 51 | 80 | 72 |
| **Patrulheiro** | 54 | 23 | 47 | 66 |
| **Mago** | 50 | 28 | 35 | 50 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 49 | 23 | 57 | 57 |
| **Ladino** | 80 | 53 | 91 | 78 |
| **Patrulheiro** | 42 | 9 | 51 | 53 |
| **Mago** | 44 | 24 | 45 | 51 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 50 | 15 | 37 | 43 |
| **Ladino** | 85 | 53 | 84 | 72 |
| **Patrulheiro** | 67 | 14 | 50 | 32 |
| **Mago** | 57 | 31 | 70 | 49 |

_Tempo de simulação: 41.6s._
