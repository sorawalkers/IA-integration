# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 500 --out relatorio-solo.md` em 2026-11-19T20:28:09.182Z · commit `0dae980`
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
| Guerreiro | 48% | 59% | 56% |
| Ladino | 61% | 48% | 40% |
| Patrulheiro | 49% | 48% | 49% |
| Mago | 39% | 44% | 50% |
| **Diferença** | **23 pp** | **15 pp** | **16 pp** |
| **Duração média da luta** | 18.1s | 16.6s | 22.3s |

### Painel de metas (modo solo)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% | ❌ 2/4 | ✅ 4/4 | ✅ 4/4 |
| Confrontos extremos (um lado vence > 80%), de 6 | ❌ 1 | ❌ 1 | ✅ 0 |
| Espelhos entre 45% e 55% | ❌ 3/4 (48 / 49 / 49 / 45) | ❌ 3/4 (45 / 53 / 48 / 51) | ❌ 3/4 (44 / 47 / 50 / 50) |
| Duração média 14–18s | ❌ 18.1s | ✅ 16.6s | ❌ 22.3s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ✅ nenhum | ✅ nenhum | ✅ nenhum |

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 48 | 63 | 42 | 40 |
| **Ladino** | 37 | 49 | 74 | 85 |
| **Patrulheiro** | 58 | 24 | 49 | 65 |
| **Mago** | 57 | 16 | 38 | 45 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 45 | 84 | 56 | 52 |
| **Ladino** | 19 | 53 | 52 | 68 |
| **Patrulheiro** | 38 | 51 | 48 | 55 |
| **Mago** | 46 | 33 | 45 | 51 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 44 | 74 | 46 | 61 |
| **Ladino** | 24 | 47 | 39 | 50 |
| **Patrulheiro** | 52 | 58 | 50 | 37 |
| **Mago** | 41 | 51 | 59 | 50 |

_Tempo de simulação: 171.9s._
