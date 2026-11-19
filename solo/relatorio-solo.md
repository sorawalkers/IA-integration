# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 500 --out relatorio-solo.md` em 2026-11-19T19:22:43.678Z · commit `535ed49`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

## Escalonamento das classes (sala 3, sala 9, sala 18)

**Modo solo** (branch `feat/solo-class`, SPEC-SOLO): 4 classes x 4 classes = 16 confrontos por sala, 500 lutas por confronto, **iniciativa alternada** (metade das lutas com os lados trocados). Os dois lados evoluem igual:

| Sala | Itens extras | Fusão | Encantamentos |
|---|---|---|---|
| 3 | 2 | +0 | 0 |
| 9 | 4 | +1 | 1 |
| 18 | 8 | +2 (10% +3) | 3 |

Vitória média de cada classe contra as 4 classes (inclui o espelho, que deve ficar perto de 50%)

| Classe | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 41% | 42% | 41% |
| Ladino | 76% | 83% | 70% |
| Patrulheiro | 45% | 37% | 38% |
| Mago | 39% | 38% | 50% |
| **Diferença** | **37 pp** | **45 pp** | **31 pp** |
| **Duração média da luta** | 17.4s | 13.0s | 8.2s |

### Painel de metas (modo solo)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% | ❌ 2/4 | ❌ 1/4 | ❌ 2/4 |
| Confrontos extremos (um lado vence > 80%), de 6 | ❌ 2 | ❌ 3 | ❌ 2 |
| Espelhos entre 45% e 55% | ✅ 4/4 (55 / 51 / 47 / 50) | ✅ 4/4 (49 / 54 / 50 / 51) | ✅ 4/4 (48 / 52 / 47 / 47) |
| Duração média 14–18s | ✅ 17.4s | ❌ 13.0s | ❌ 8.2s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ⚠ Ladino | ⚠ Ladino | ✅ nenhum |

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 55 | 11 | 48 | 51 |
| **Ladino** | 87 | 51 | 89 | 78 |
| **Patrulheiro** | 54 | 13 | 47 | 65 |
| **Mago** | 51 | 21 | 36 | 50 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 49 | 7 | 56 | 55 |
| **Ladino** | 93 | 54 | 96 | 89 |
| **Patrulheiro** | 44 | 3 | 50 | 52 |
| **Mago** | 46 | 12 | 45 | 51 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 48 | 16 | 53 | 47 |
| **Ladino** | 84 | 52 | 85 | 58 |
| **Patrulheiro** | 46 | 14 | 47 | 46 |
| **Mago** | 54 | 46 | 53 | 47 |

_Tempo de simulação: 39.5s._
