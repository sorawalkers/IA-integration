# OSR Battler — Relatório da simulação

> Gerado por `npm run balance --rooms 3,9,18 --fights 320 --out /tmp/claude-0/-home-user-OSRBattler/9c313045-93b3-5e24-94e7-7b32312bf85f/scratchpad/salas16.md` em 2026-11-18T20:26:35.518Z · commit `c66defc`
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
| Guerreiro | Vanguarda 38% (24%) | Vanguarda 45% (32%) | Vanguarda 53% (43%) |
| Paladino | Vanguarda 38% (24%) | Vanguarda 42% (30%) | Vanguarda 51% (40%) |
| Bárbaro | Vanguarda 38% (29%) | Vanguarda 41% (32%) | Vanguarda 49% (42%) |
| Bardo | Meio 27% (23%) | Meio 36% (32%) | Meio 43% (43%) |
| Ladino | Meio 47% (34%) | Meio 42% (33%) | Meio 37% (35%) |
| Patrulheiro | Retaguarda 36% (27%) | Retaguarda 32% (26%) | Retaguarda 44% (40%) |
| Mago | Retaguarda 31% (23%) | Retaguarda 50% (41%) | Meio 67% (56%) |
| Alquimista | Retaguarda 38% (32%) | Retaguarda 47% (43%) | Retaguarda 52% (48%) |
| **Diferença** | **21 pp** | **18 pp** | **30 pp** |
| **Duração média da luta** | 25.1s | 15.9s | 8.0s |

_Tempo de simulação: 201.1s._

---

## Diagnóstico das classes — sala 18

300 lutas por classe, na melhor posição; os outros 2 heróis são sorteados entre as 8 classes.

### Desempenho do herói da classe

Dano = dano direto dos golpes (sem Veneno/Queimadura, que não têm dono no registro). "Golpes com DOT" = golpes que aplicaram Veneno ou Queimadura. Escudo e cura = gerados pelos itens do herói (para qualquer aliado).

| Classe | Posição | Vitória | Tempo vivo | Morre primeiro | Dano/luta | % do dano da party | Dano/s vivo | Golpes/luta | Golpes com DOT | Escudo/luta | Cura/luta |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Guerreiro | Vanguarda | 47% | 6.3s de 9.6s (66%) | 37% | 682 | 28% | 108.1 | 12.8 | 0.4 | 6 | 496 |
| Paladino | Vanguarda | 47% | 6.8s de 8.9s (77%) | 29% | 608 | 27% | 89.4 | 10.8 | 0.4 | 276 | 472 |
| Bárbaro | Vanguarda | 43% | 4.5s de 7.5s (60%) | 43% | 871 | 38% | 194.7 | 16.3 | 0.6 | 4 | 91 |
| Bardo | Meio | 35% | 6.2s de 8.0s (78%) | 7% | 369 | 18% | 59.4 | 14.8 | 0.7 | 9 | 376 |
| Ladino | Meio | 34% | 6.9s de 8.4s (82%) | 3% | 659 | 35% | 95.1 | 20.4 | 14.0 | 8 | 349 |
| Patrulheiro | Retaguarda | 44% | 5.3s de 6.8s (78%) | 16% | 1096 | 50% | 207.7 | 23.6 | 0.6 | 9 | 40 |
| Mago | Meio | 62% | 2.7s de 4.2s (66%) | 12% | 1196 | 63% | 437.9 | 9.4 | 0.3 | 3 | 12 |
| Alquimista | Retaguarda | 48% | 8.4s de 9.8s (86%) | 22% | 364 | 15% | 43.2 | 11.1 | 0.2 | 5 | 1478 |

### Mochila montada pelo gerador (média de itens por tipo)

| Classe | arma corpo a corpo | arma à distância | arma mágica | mascote | instrumento | armadura | poção | catalisador/outro | Corpo a corpo na Retaguarda (-20%) |
|---|---|---|---|---|---|---|---|---|---|
| Guerreiro | 2.3 | 0.1 | 0.2 | 0.0 | 0.1 | 3.2 | 1.1 | 1.8 | — |
| Paladino | 2.0 | 0.1 | 0.2 | 0.0 | 0.1 | 2.8 | 1.0 | 3.0 | — |
| Bárbaro | 3.8 | 0.1 | 0.2 | 0.0 | 0.1 | 0.2 | 0.2 | 3.3 | — |
| Bardo | 1.2 | 0.1 | 0.2 | 0.0 | 1.7 | 0.2 | 2.2 | 1.3 | — |
| Ladino | 2.7 | 0.3 | 0.6 | 0.0 | 0.1 | 0.3 | 1.5 | 2.5 | — |
| Patrulheiro | 0.2 | 1.8 | 0.2 | 2.7 | 0.1 | 0.1 | 0.2 | 4.5 | 0.2 |
| Mago | 0.2 | 0.1 | 3.8 | 0.0 | 0.1 | 0.2 | 1.1 | 3.3 | — |
| Alquimista | 0.2 | 1.6 | 0.3 | 0.0 | 0.1 | 1.2 | 3.3 | 2.2 | 0.2 |

### Fusão no mesmo herói (sala 3, linha de base Mago/Bardo/Guerreiro, 300 lutas)

| Item | Herói | 2 cópias +0 | 1 cópia +1 | Delta (pp) |
|---|---|---|---|---|
| Adaga | Mago | 38.7% | 36.7% | -2.0 |
| Adaga | Bardo | 36.7% | 43.3% | +6.7 |
| Adaga | Guerreiro | 58.0% | 55.0% | -3.0 |
| Gema Bruta | Mago | 46.7% | 41.7% | -5.0 |
| Gema Bruta | Bardo | 22.7% | 22.7% | +0.0 |
| Gema Bruta | Guerreiro | 22.7% | 22.7% | +0.0 |
| Tambor de Guerra | Mago | 36.7% | 42.0% | +5.3 |
| Tambor de Guerra | Bardo | 22.7% | 23.0% | +0.3 |
| Tambor de Guerra | Guerreiro | 38.3% | 43.0% | +4.7 |
