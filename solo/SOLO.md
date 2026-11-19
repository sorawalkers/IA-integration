# OSR Battler — Experimento: 1 classe solo (branch `feat/solo-class`)

> Branch alternativa para comparar com a party de 3 heróis (branch `claude/awesome-fermi-2g5woc`, que continua intacta).
> Decisão testada: **Q-37 (d)** — 1 herói por run, Arena 1 contra 1. A curva **Q-36 (b)** (HP = classe x 0.62 x 1.50^(nível−1),
> efeitos fixos x1.50^(nível−1)) já estava aplicada. Simulação completa: `relatorio-solo.md`.

**Data:** 2026-11-19 · base: rodada F3.4 da branch de 3 heróis (Sobrecarga 1x a cada 3s, `magic_aoe` 45%).

## O que mudou

| Área | Party de 3 | Solo |
|---|---|---|
| Run | 3 heróis, posições Retaguarda / Meio / Vanguarda | 1 herói, sem posições nem Elos Dourados |
| Taverna | 3 pedestais + 8 classes | 1 herói grande + 8 classes (clicar troca o herói) |
| Acampamento | 3 mochilas lado a lado | 1 mochila grande no centro |
| Arena | 3 x 3 | 1 x 1 no duelo; Emboscada = 1 herói contra o grupo de monstros |
| Balanço | 512 composições x ghosts sorteados | **8 x 8 = 64 confrontos** por sala, 300 lutas cada (2.5 min para as 3 salas) |

**Mochilas (~20–25 casas):**

| Classe | Antes | Solo |
|---|---|---|
| Guerreiro | 4x4 (16) | 5x5 (25) |
| Paladino | cruz 5x3 (11) | cruz 5x5 com centro 3x3 (17) |
| Bárbaro | 5x3 (15) | 6x4 (24) |
| Bardo | 4x4, Palco 2x2 | 5x5, **Palco 3x3** (25) |
| Ladino | 2x7 (14) | 4x6 (24) |
| Patrulheiro | 2x6 + 1x2 (14) | 4x5 + bolsa 2x2 dos mascotes (24) |
| Mago | 3x5 (15) | 4x6 (24) |
| Alquimista | 4x3 (12) | 5x4 (20) |

**Passivas refeitas para solo:**
- **Paladino:** sem repasse de escudo. Cada armadura/relíquia no **centro 3x3 da cruz** dá **+8% de dano às armas fora do centro**
  (máx. 3 fontes, +24%) e, a cada ativação da Égide, **remove 1 stack de Veneno, Queimadura e Ácido** do Paladino.
- **Bardo:** itens no **Palco 3x3** recarregam **20% mais rápido** e, a cada ativação, **curam 2 HP** do Bardo e causam **2 de dano
  sônico** no inimigo (x fator de nível). O corte de recarga do grupo e o repasse de efeitos saíram.
- **Alquimista:** cada poção bebida causa **4 de dano** (x fator de nível) e **1 de Ácido** no inimigo. O +30% das poções (antes só na
  Retaguarda) vale sempre.
- **Sem posição:** o Grito de Guerra do Bárbaro vale sempre; o arremesso do Ladino no Meio e os bônus de Vanguarda/Meio/Retaguarda saíram.
- **Feats fora da oferta** (dependem de aliados): Sinergia de Borda, Veterano, Aura Inabalável. Textos de Melodia Calmante, Dissonância,
  Bastião da Cruz, Luz Cegante, Palco Expandido e Elixir Vital ajustados para 1 herói (mesmos números).

## Resultado (8 x 8, 300 lutas por confronto)

Vitória média de cada classe contra as 8 classes (inclui o espelho):

| Classe | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 56% | 58% | 59% |
| Paladino | **76%** | **72%** | 55% |
| Bárbaro | **82%** | **74%** | **67%** |
| Bardo | **20%** | **24%** | **30%** |
| Ladino | 56% | 56% | 52% |
| Patrulheiro | 52% | **35%** | **39%** |
| Mago | **32%** | 48% | 55% |
| Alquimista | **25%** | **38%** | 46% |
| **Diferença** | **62pp** | **50pp** | **37pp** |
| Duração da luta | 17.6s ✅ | 14.0s ✅ | 12.2s |
| Classes na faixa 40–60% | 3/8 | 3/8 | 5/8 |
| Confrontos extremos (> 80%), de 28 | 14.5 | 12 | 6 |

**Comparação com a party de 3 (rodada F3.4):** diferença entre classes **20 / 28 / 24pp** (3 heróis) contra **62 / 50 / 37pp** (solo);
lutas 19.3 / 17.1 / 11.4s contra 17.6 / 14.0 / 12.2s. No solo nada dilui a força de uma classe: os tanques corpo a corpo (Bárbaro,
Paladino) atropelam no início e as classes de suporte (Bardo, Alquimista) ficam sem função. As diferenças diminuem com a sala (os itens
extras pesam mais que a classe).

Matriz completa de confrontos por sala em `relatorio-solo.md`.

## Emboscada PvE (recalibrada para 1 herói)

Com os números da party de 3, o herói solo vencia **2%**. Nova calibragem (`MONSTER.tune`): Goblins HP/dano x0.46 e crescimento 1.75;
Esqueletos x0.63 e 1.40; Cubos x0.48 e 1.10; Elite (HP/dano) x1.04/0.77, x0.89/0.66, x0.84/0.63.

| Encontro | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Horda de Goblins | 66% | 87% | 73% |
| Elite: Horda de Goblins | 49% | 63% | 44% |
| Câmara dos Esqueletos | 67% | 80% | 80% |
| Elite: Câmara dos Esqueletos | 43% | 54% | 67% |
| Ninho de Cubos Gelatinosos | 79% | 77% | 68% |
| Elite: Ninho de Cubos Gelatinosos | 54% | 46% | 51% |
| **Média normal** (meta ~75%) | **71%** | **81%** | **73%** |
| **Média Elite** (meta ~50%) | **48%** | **54%** | **54%** |

## Interpretações feitas (validar)

| Código | Interpretação |
|---|---|
| S-01 | Números das passivas solo (Paladino +8% por fonte, máx. 3, purifica 1 stack; Bardo −20% e 2 HP / 2 de dano; Alquimista 4 de dano + 1 Ácido) — a proposta não trazia números |
| S-02 | Paladino: "centro" = as 3x3 casas do meio da cruz; "pontas" = armas sem nenhuma casa no centro. A relíquia encostada em arma (+15%) continua |
| S-03 | Bardo: o Palco vale para **qualquer item que ativa** (armas incluídas); itens passivos (armaduras) não ganham nada |
| S-04 | Emboscada continua com o grupo de monstros (3 goblins, 3 esqueletos, 2 cubos) contra 1 herói, recalibrada |
| S-05 | **Economia e gerador iguais:** 20 PO + 4 por sala para 1 herói (antes para 3) e os mesmos 12 itens extras na sala 18 num herói só. O herói solo é "3x mais rico por herói" |

## Limitações da medição

- **Espelho desequilibrado:** o confronto da classe contra ela mesma deveria dar ~50%, mas o Mago dá 63 / 79 / 58% e o Guerreiro 54 / 56 / 49%.
  O lado do jogador (lado 0) age primeiro no mesmo passo de 50ms; em lutas de burst isso pesa. Correção sugerida: alternar o lado em metade
  das lutas.
- Gerador de builds igual ao da party (afinidade, venda, receitas), feito para mochilas de ~14 casas.

## Perguntas para o agente de análise

| Código | Pergunta | Opções |
|---|---|---|
| S-Q1 | **Seguir com o solo ou voltar para a party?** Solo: diferença 62 / 50 / 37pp (party: 20 / 28 / 24pp), Bardo 20–30%, Bárbaro 67–82%; a UI ficou bem mais limpa e o balanço roda em 2.5 min (512 composições: 8 min) | (a) voltar para a party de 3 e seguir a Fase 3 · (b) seguir no solo e balancear (Bárbaro/Paladino −, Bardo/Alquimista +) · (c) híbrido: 1 herói + 1 companheiro fixo (2 mochilas) |
| S-Q2 | Se seguir no solo: o Bardo e o Alquimista precisam de outra identidade (sem aliados, o suporte vira só "cura a si mesmo + dano pequeno") | (a) subir os números da passiva solo · (b) refazer como híbridos ofensivos (Bardo: atordoa/silencia o inimigo; Alquimista: veneno/ácido ofensivo) |
| S-Q3 | Economia e gerador no solo (S-05) | (a) manter · (b) dividir ouro e itens extras por 3 · (c) meio-termo (÷2) |
