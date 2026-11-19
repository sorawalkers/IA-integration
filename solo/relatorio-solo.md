# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 500 --out relatorio-solo.md` em 2026-11-19T20:17:28.092Z · commit `f122c01`
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
| Guerreiro | 60% | 68% | 62% |
| Ladino | 36% | 40% | 38% |
| Patrulheiro | 55% | 49% | 51% |
| Mago | 48% | 43% | 49% |
| **Diferença** | **24 pp** | **28 pp** | **24 pp** |
| **Duração média da luta** | 18.6s | 16.2s | 21.1s |

### Painel de metas (modo solo)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% | ❌ 2/4 | ❌ 2/4 | ❌ 2/4 |
| Confrontos extremos (um lado vence > 80%), de 6 | ❌ 1 | ❌ 1 | ❌ 0.5 |
| Espelhos entre 45% e 55% | ❌ 3/4 (50 / 52 / 45 / 57) | ✅ 4/4 (51 / 52 / 51 / 50) | ✅ 4/4 (50 / 50 / 51 / 49) |
| Duração média 14–18s | ❌ 18.6s | ✅ 16.2s | ❌ 21.1s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ✅ nenhum | ✅ nenhum | ✅ nenhum |

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 50 | 85 | 56 | 49 |
| **Ladino** | 16 | 52 | 32 | 45 |
| **Patrulheiro** | 49 | 63 | 45 | 64 |
| **Mago** | 46 | 53 | 37 | 57 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 51 | 90 | 69 | 62 |
| **Ladino** | 10 | 52 | 41 | 56 |
| **Patrulheiro** | 38 | 50 | 51 | 56 |
| **Mago** | 35 | 43 | 43 | 50 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 50 | 81 | 52 | 67 |
| **Ladino** | 21 | 50 | 38 | 43 |
| **Patrulheiro** | 44 | 63 | 51 | 45 |
| **Mago** | 32 | 55 | 58 | 49 |

_Tempo de simulação: 212.7s._
