# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 500 --out relatorio-solo.md` em 2026-11-19T20:35:35.900Z · commit `7cb3220`
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
| Guerreiro | 49% | 60% | 56% |
| Ladino | 57% | 48% | 40% |
| Patrulheiro | 51% | 48% | 49% |
| Mago | 40% | 44% | 50% |
| **Diferença** | **17 pp** | **15 pp** | **17 pp** |
| **Duração média da luta** | 18.3s | 16.7s | 22.3s |

### Painel de metas (modo solo)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% | ✅ 4/4 | ✅ 4/4 | ❌ 3/4 |
| Confrontos extremos (um lado vence > 80%), de 6 | ❌ 0.5 | ❌ 1 | ✅ 0 |
| Espelhos entre 45% e 55% | ❌ 3/4 (48 / 47 / 49 / 45) | ❌ 3/4 (45 / 52 / 48 / 51) | ❌ 3/4 (44 / 50 / 50 / 50) |
| Duração média 14–24s | ✅ 18.3s | ✅ 16.7s | ✅ 22.3s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ✅ nenhum | ✅ nenhum | ✅ nenhum |

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 48 | 65 | 42 | 40 |
| **Ladino** | 36 | 47 | 65 | 81 |
| **Patrulheiro** | 58 | 33 | 49 | 65 |
| **Mago** | 57 | 22 | 38 | 45 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 45 | 85 | 56 | 52 |
| **Ladino** | 18 | 52 | 51 | 69 |
| **Patrulheiro** | 38 | 52 | 48 | 55 |
| **Mago** | 46 | 34 | 45 | 51 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 44 | 75 | 46 | 61 |
| **Ladino** | 25 | 50 | 37 | 47 |
| **Patrulheiro** | 52 | 58 | 50 | 37 |
| **Mago** | 41 | 48 | 59 | 50 |

_Tempo de simulação: 163.4s._
