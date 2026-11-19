# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 300 --out relatorio-solo.md` em 2026-11-19T18:50:05.829Z · commit `9dfb6f6`
> Resumo e histórico das rodadas: `docs/BALANCO.md` (https://osr.valiran.party).

## Escalonamento das classes (sala 3, sala 9, sala 18)

**Modo solo** (branch `feat/solo-class`): 8 classes x 8 classes = 64 confrontos por sala, 300 lutas por confronto. Os dois lados evoluem igual:

| Sala | Itens extras | Fusão | Encantamentos |
|---|---|---|---|
| 3 | 2 | +0 | 0 |
| 9 | 6 | +1 | 1 |
| 18 | 12 | +2 (25% +3) | 3 |

Vitória média de cada classe contra as 8 classes (inclui o espelho, que fica perto de 50%)

| Classe | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 56% | 58% | 59% |
| Paladino | 76% | 72% | 55% |
| Bárbaro | 82% | 74% | 67% |
| Bardo | 20% | 24% | 30% |
| Ladino | 56% | 56% | 52% |
| Patrulheiro | 52% | 35% | 39% |
| Mago | 32% | 48% | 55% |
| Alquimista | 25% | 38% | 46% |
| **Diferença** | **62 pp** | **50 pp** | **37 pp** |
| **Duração média da luta** | 17.6s | 14.0s | 12.2s |

### Painel de metas (modo solo)

| Meta | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Classes entre 40% e 60% | ❌ 3/8 | ❌ 3/8 | ❌ 5/8 |
| Confrontos extremos (um lado vence > 80%), de 28 | ❌ 14.5 | ❌ 12 | ❌ 6 |
| Duração média 14–18s | ✅ 17.6s | ✅ 14.0s | ❌ 12.2s |
| Absurdos (classe > 70% ou < 25%, luta < 8s) | ⚠ Paladino, Bárbaro, Bardo | ⚠ Paladino, Bárbaro, Bardo | ✅ nenhum |

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Palad | Bárba | Bardo | Ladin | Patru | Mago | Alqui |
|---|---|---|---|---|---|---|---|---|
| **Guerreiro** | 54 | 27 | 25 | 87 | 38 | 60 | 82 | 75 |
| **Paladino** | 78 | 50 | 41 | 95 | 69 | 85 | 94 | 92 |
| **Bárbaro** | 78 | 59 | 53 | 98 | 80 | 91 | 98 | 98 |
| **Bardo** | 17 | 5 | 3 | 54 | 7 | 11 | 24 | 38 |
| **Ladino** | 58 | 33 | 22 | 91 | 52 | 38 | 64 | 92 |
| **Patrulheiro** | 41 | 13 | 10 | 89 | 56 | 48 | 84 | 75 |
| **Mago** | 13 | 6 | 2 | 73 | 30 | 15 | 63 | 57 |
| **Alquimista** | 21 | 7 | 4 | 58 | 9 | 19 | 38 | 45 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Palad | Bárba | Bardo | Ladin | Patru | Mago | Alqui |
|---|---|---|---|---|---|---|---|---|
| **Guerreiro** | 56 | 16 | 35 | 82 | 44 | 83 | 81 | 63 |
| **Paladino** | 84 | 43 | 58 | 90 | 48 | 89 | 79 | 87 |
| **Bárbaro** | 67 | 41 | 50 | 92 | 76 | 97 | 97 | 75 |
| **Bardo** | 15 | 11 | 6 | 53 | 11 | 55 | 8 | 37 |
| **Ladino** | 52 | 54 | 23 | 87 | 53 | 72 | 41 | 65 |
| **Patrulheiro** | 13 | 10 | 5 | 50 | 33 | 50 | 75 | 41 |
| **Mago** | 21 | 23 | 5 | 91 | 62 | 26 | 79 | 81 |
| **Alquimista** | 34 | 12 | 25 | 65 | 42 | 59 | 20 | 48 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Palad | Bárba | Bardo | Ladin | Patru | Mago | Alqui |
|---|---|---|---|---|---|---|---|---|
| **Guerreiro** | 49 | 35 | 48 | 81 | 61 | 83 | 67 | 49 |
| **Paladino** | 65 | 42 | 50 | 72 | 44 | 66 | 34 | 65 |
| **Bárbaro** | 53 | 46 | 59 | 78 | 61 | 88 | 87 | 63 |
| **Bardo** | 21 | 34 | 19 | 53 | 25 | 49 | 11 | 30 |
| **Ladino** | 38 | 57 | 43 | 76 | 52 | 61 | 53 | 38 |
| **Patrulheiro** | 18 | 24 | 12 | 54 | 37 | 55 | 75 | 33 |
| **Mago** | 34 | 74 | 14 | 88 | 52 | 27 | 58 | 93 |
| **Alquimista** | 49 | 31 | 42 | 72 | 65 | 61 | 4 | 46 |

_Tempo de simulação: 145.8s._
