# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 500 --out relatorio-solo.md` em 2026-11-19T20:04:49.399Z · commit `b0ed055`
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
| Guerreiro | 62% | 69% | 63% |
| Ladino | 38% | 41% | 38% |
| Patrulheiro | 57% | 50% | 51% |
| Mago | 43% | 40% | 48% |
| **Diferença** | **24 pp** | **29 pp** | **25 pp** |
| **Duração média da luta** | 18.8s | 16.3s | 22.7s |

### Painel de metas (modo solo)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% | ❌ 2/4 | ❌ 2/4 | ❌ 2/4 |
| Confrontos extremos (um lado vence > 80%), de 6 | ❌ 1 | ❌ 1 | ❌ 0.5 |
| Espelhos entre 45% e 55% | ❌ 3/4 (50 / 52 / 45 / 56) | ✅ 4/4 (51 / 52 / 51 / 51) | ✅ 4/4 (49 / 49 / 51 / 49) |
| Duração média 14–18s | ❌ 18.8s | ✅ 16.3s | ❌ 22.7s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ✅ nenhum | ✅ nenhum | ✅ nenhum |

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 50 | 85 | 56 | 57 |
| **Ladino** | 15 | 52 | 32 | 52 |
| **Patrulheiro** | 49 | 63 | 45 | 72 |
| **Mago** | 38 | 47 | 30 | 56 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 51 | 90 | 69 | 65 |
| **Ladino** | 10 | 52 | 41 | 62 |
| **Patrulheiro** | 38 | 50 | 51 | 59 |
| **Mago** | 31 | 39 | 38 | 51 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 49 | 80 | 52 | 69 |
| **Ladino** | 22 | 49 | 37 | 45 |
| **Patrulheiro** | 45 | 63 | 51 | 45 |
| **Mago** | 32 | 52 | 57 | 49 |

_Tempo de simulação: 207.3s._
