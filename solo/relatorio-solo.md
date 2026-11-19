# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 500 --out relatorio-solo.md` em 2026-11-19T19:11:31.637Z · commit `aa39227`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

## Escalonamento das classes (sala 3, sala 9, sala 18)

**Modo solo** (branch `feat/solo-class`, SPEC-SOLO): 4 classes x 4 classes = 16 confrontos por sala, 500 lutas por confronto, **iniciativa alternada** (metade das lutas com os lados trocados). Os dois lados evoluem igual:

| Sala | Itens extras | Fusão | Encantamentos |
|---|---|---|---|
| 3 | 2 | +0 | 0 |
| 9 | 6 | +1 | 1 |
| 18 | 12 | +2 (25% +3) | 3 |

Vitória média de cada classe contra as 4 classes (inclui o espelho, que deve ficar perto de 50%)

| Classe | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 41% | 51% | 48% |
| Ladino | 83% | 77% | 64% |
| Patrulheiro | 45% | 33% | 43% |
| Mago | 33% | 37% | 44% |
| **Diferença** | **50 pp** | **44 pp** | **21 pp** |
| **Duração média da luta** | 12.4s | 8.3s | 4.7s |

### Painel de metas (modo solo)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% | ❌ 2/4 | ❌ 1/4 | ❌ 3/4 |
| Confrontos extremos (um lado vence > 80%), de 6 | ❌ 3 | ❌ 3 | ✅ 0 |
| Espelhos entre 45% e 55% | ✅ 4/4 (54 / 48 / 50 / 50) | ✅ 4/4 (51 / 50 / 50 / 47) | ✅ 4/4 (52 / 52 / 49 / 46) |
| Duração média 14–18s | ❌ 12.4s | ❌ 8.3s | ❌ 4.7s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ⚠ Ladino | ⚠ Ladino | ⚠ luta < 8s |

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 54 | 3 | 47 | 58 |
| **Ladino** | 95 | 48 | 96 | 92 |
| **Patrulheiro** | 53 | 3 | 50 | 73 |
| **Mago** | 46 | 7 | 31 | 50 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 51 | 14 | 74 | 65 |
| **Ladino** | 83 | 50 | 96 | 80 |
| **Patrulheiro** | 26 | 4 | 50 | 54 |
| **Mago** | 32 | 20 | 48 | 47 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 52 | 23 | 61 | 55 |
| **Ladino** | 72 | 52 | 77 | 57 |
| **Patrulheiro** | 38 | 21 | 49 | 63 |
| **Mago** | 46 | 47 | 35 | 46 |

_Tempo de simulação: 57.9s._
