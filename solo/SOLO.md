# OSR Battler — Modo solo: 4 classes e sub-arquétipos (branch `feat/solo-class`, SPEC-SOLO)

> Branch alternativa ao jogo de 3 heróis (branch `claude/awesome-fermi-2g5woc`, intacta). Especificação aplicada: **SPEC-SOLO.md**
> (4 classes solo, Jaula do Patrulheiro, 24 Feats de classe em 2 métodos + 10 genéricos, matriz 4x4 com iniciativa alternada).
> Simulação completa: `relatorio-solo.md`. Primeira versão do experimento (8 classes): histórico no fim.

**Data:** 2026-11-19 · **Rodada S-3** (respostas S-Q7, S-Q8). HP = classe x **0.88** x 1.50^(nível − 1); efeitos fixos x1.50^(nível − 1), exceto Veneno/Queimadura: **x1.25^(nível − 1)**.

## 1. As 4 classes do lançamento

Paladino, Bárbaro, Bardo e Alquimista ficam **"em breve"** (`status: 'coming_soon'`): aparecem apagados na Taverna, não entram na run,
no ghost nem no balanço, e os itens exclusivos deles saem da loja.

| Classe | HP | Recurso | Mochila | Kit inicial | Pool exclusivo na loja |
|---|---|---|---|---|---|
| Guerreiro — Mestre de Aço | 160 | 45 escudo + 100 estamina | 5x5 (25) | Espada Curta, Broquel, Pedra de Amolar, Gibão, Poção de Vida | Escudo Torre, Armadura de Placas, Mangual Pesado, Estandarte de Guerra |
| Ladino — Mestre das Toxinas | 135 | 100 estamina, **8% de esquiva** | 4x6 (24) | 2 Adagas, Gazuas, Gibão, Poção de Vida (Frasco de Veneno só na loja) | Adaga Serrilhada, Frasco de Veneno, Capa das Sombras, Gazuas Mestras |
| Mago — Arquiteto Arcano | 125 | 120 mana | Altar em cruz 5x5 (17) | Cajado de Aprendiz, Tomo Menor, 2 Gemas Brutas, Poção de Mana | Grimório Proibido, Orbe de Cristal, Manto Arcano, Runa de Mana |
| Patrulheiro — Guardião da Matilha | 130 | 90 estamina | 4x5 + **Jaula 2x2** (24) | Arco Curto, Aljava, Ração, Erva (Mochila) + 2 Ratos (Jaula) | Lobo Cinzento, Falcão Caçador, Arco Composto, Erva Ancestral |

Passivas como na SPEC (Guerreiro +3/+4 de escudo x fator; Ladino crítico por item diferente, **2 de Veneno por crítico** (S-Q4), crítico excedente;
Mago Canalização + Sobrecarga 1x a cada 3s; Patrulheiro mascotes alimentados, cura 2 HP x fator, flecha adianta 0.6s).

**Jaula do Patrulheiro:** casas do tipo `cage` na borda direita. Itens `pet` **só** na Jaula; o resto **nunca** nela (validação em
`canPlace`, vale para arrastar, comprar, fundir e para o gerador). Comida/erva na coluna da Mochila encostada na Jaula alimenta os mascotes.
Casas extras (níveis 3/6/9 e Bolsa): o painel mostra **[Expandir Mochila] / [Expandir Jaula]**; o gerador de builds põe na Jaula até 6 casas
(2x3) e depois na Mochila.

### Itens novos (números propostos, validar — S-06)

| Item | Classe | Tamanho | Efeito |
|---|---|---|---|
| Armadura de Placas | Guerreiro | 2x2 | +25 HP, +30 escudo (armadura, metal) |
| Mangual Pesado | Guerreiro | 2x2 | 18-24 dano, 2.6s (metal) |
| Estandarte de Guerra | Guerreiro | 1x3 | +6 escudo; armas encostadas +15% dano e −10% recarga |
| Frasco de Veneno | Ladino (básico) | 1x1 | Arremesso 3-4 dano + 2 Veneno, 2.2s (tag `flask`) |
| Adaga Serrilhada | Ladino | 1x2 | 6-9 dano + 1 Veneno, 1.3s |
| Capa das Sombras | Ladino | 2x1 | +8% esquiva, +6 escudo |
| Gazuas Mestras | Ladino | 1x1 | armas encostadas +20% crítico |
| Grimório Proibido | Mago | 2x2 | 30-38 dano mágico + 1 Queimadura, 3.4s, 25 mana |
| Orbe de Cristal | Mago | 1x1 | gema: +1.5 mana/s, +5% dano mágico |
| Manto Arcano | Mago | 2x1 | +12 escudo, +0.5 mana/s |
| Runa de Mana | Mago (básico) | 1x1 | +0.5 mana/s; tomos encostados −15% recarga |
| Falcão Caçador | Patrulheiro | 1x2 | mascote à distância, 5-7 dano, 1.4s |
| Arco Composto | Patrulheiro | 1x3 | 11-14 dano, 1.7s |
| Erva Ancestral | Patrulheiro | 1x1 | 2 HP/s; mascotes encostados +25% dano e −10% recarga |

Escudo Torre e Lobo Cinzento passaram a ser só do Guerreiro e do Patrulheiro. Ícones dos itens novos: provisórios (cópias de ícones parecidos).

## 2. Feats: 2 métodos por classe (24 + 10 genéricos)

Subida de nível: 3 opções = 2 Feats da classe + 1 genérico (Sinergia de Borda fica fora: não há Elos no solo). O modal mostra o método.

| Classe | Método A | Método B |
|---|---|---|
| Guerreiro | **Bastião de Aço:** Muralha Viva (+25% escudo, devolve 20%), Arsenal Metálico (+5 por metal), Bastião Inabalável (25% do escudo vira cura a cada 4s) | **Colosso:** Fúria Blindada (40% do escudo ganho vira dano no próximo golpe), Golpe Pesado (2x2+: +25% dano, +15% velocidade), Sede de Batalha (metal: 12% roubo de vida sem escudo) |
| Ladino | **Toxinas:** Mestre dos Venenos (+35% velocidade, teto 22), Toxina Corrosiva (3 Venenos → 1 Ácido), Bolso Alquímico (frascos/poções 1x1: −20% recarga, frascos +2 Veneno) | **Assassino:** Passos nas Sombras (+15% esquiva, evita o 1º golpe), Ponto Vital (crítico x2.0), Execução (+45% abaixo de 35% de HP) |
| Mago | **Sobrecarga:** Sobrecarga Contínua (3s → 2s), Foco de Cristal (gemas +30%), Reserva Arcana (+40 mana) | **Elementalista:** Chama Arcana (magia aplica 2 Queimaduras, teto 8), Toque Glacial (atrasa 0.35s o item mais rápido do alvo), Barreira Elemental (30% da mana gasta vira escudo) |
| Patrulheiro | **Feras:** Vínculo Natural (cura 4 HP), Toca Farta (3 comidas por mascote), Chamado da Matilha (cada outro mascote +10% velocidade) | **Atirador:** Olho de Águia (arcos +25% crítico e +20% dano), Flechas Envenenadas (crítico à distância: 3 Venenos), Caçador Solitário (1 mascote: arcos +25% velocidade e 15% roubo de vida) |

## 3. Rodada S-3 — respostas S-Q7 e S-Q8 (matriz 4x4, 500 lutas por confronto, iniciativa alternada)

**Mudanças:** Veneno e Queimadura escalam **x1.25** por nível do alvo (era x1.50, o fator de nível) e o Veneno cai **1 stack a cada 2s**
(era 3s) (S-Q7 b+c); gerador solo com fusão **+1** a partir da sala 6 e só **20%** dos itens em +2 na sala 18 (era +2 em todos e 10% em +3)
(S-Q8 b); a crônica da Arena mostra os ticks no formato "Guerreiro sofre N de dano contínuo (Veneno 14)".

| Classe | Sala 3 (S-2 → S-3) | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 41 → **44%** | 42 → **46%** | 41 → **36%** |
| **Ladino** | 76 → **71%** | 83 → **75%** | 70 → **74%** |
| Patrulheiro | 45 → **48%** | 37 → **39%** | 38 → **41%** |
| Mago | 39 → **41%** | 38 → **41%** | 50 → **52%** |
| Diferença | 37 → 30pp | 45 → 37pp | 31 → 38pp |
| **Duração da luta** | 17.4 → **18.0s** ✅ | 13.0 → **14.4s** ✅ | 8.2 → **19.0s** (1s acima) |
| Classes na faixa 40–60% | 2 → **3** de 4 | 1 → **2** de 4 | 2 → 2 de 4 |
| Espelhos entre 45% e 55% | ✅ 55 / 51 / 47 / 50 | ✅ 49 / 53 / 51 / 51 | ✅ 50 / 53 / 50 / 49 |

- **A duração resolveu:** 18.0 / 14.4 / 19.0s (a sala 18 saiu de 8.2s; agora 1s acima da faixa).
- **Guerreiro, Patrulheiro e Mago** subiram 2–5pp e ficam entre si em 32–70% (sala 18: Mago vence o Patrulheiro 70%, o Patrulheiro vence o Guerreiro 67%).
- **O Ladino caiu pouco** (71 / 75 / 74%). Contra o Guerreiro 80 / 80 / 85%, contra o Patrulheiro 80 / 91 / 84%.

**Diagnóstico do Ladino depois da S-3 (contra o Guerreiro, 150 lutas):**

| Medida | Sala 9 | Sala 18 |
|---|---|---|
| Vitória do Ladino | 79% | 84% |
| Veneno médio no Guerreiro | 14.1 stacks | 17.0 stacks (Mestre dos Venenos: teto 22) |
| Dano de Veneno por luta | 446 | 1198 |
| Dano de golpes por luta | 596 | 1352 |

- O Veneno continua **no teto** e ainda é ~45% do dano: cada stack bate menos (x1.25), mas a luta ficou mais longa e as adagas recolocam
  stacks mais rápido do que eles caem (crítico em 65% dos golpes na sala 18).
- **Nova causa achada — poções:** na sala 18 o Ladino se cura **450 HP por luta** (Guerreiro 320, Patrulheiro 71, Mago 111), quase tudo de
  Poções de Vida (364 de Menores, 84 de Maiores). O gerador dá "afinidade" ao Ladino com **todo item 1x1** (`AFFINITY` em `ghost.ts`), então a
  mochila dele enche de poções, que se fundem e ganham usos. Pode ser viés do gerador ou uma build real (poções são baratas e cabem no 4x6).
- Feats mais escolhidos pelo gerador no Ladino (de 150): Mestre dos Venenos 92, Bolso Alquímico 91, Execução 79, Toxina Corrosiva 75.

Matrizes (linha = sua classe, % de vitória contra a coluna):

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

### Rodada S-2 — respostas S-Q4 e S-Q5

**Mudanças:** Ladino com esquiva base 15% → **8%**, Frasco de Veneno fora do kit (entra o Gibão) e Veneno por crítico 3 → **2** (S-Q4 b+c+d);
HP = classe x **0.88** x 1.50^(nível − 1) (era 0.62) e gerador solo com **2 / 4 / 8** itens extras nas salas 3 / 9 / 18 (eram 2 / 6 / 12),
no máximo **10%** dos itens em +3 na sala 18 (eram 25%) (S-Q5 c).

| Classe | Sala 3 (S-1 → S-2) | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 41 → 41% | 51 → 42% | 48 → 41% |
| **Ladino** | 83 → **76%** | 77 → **83%** | 64 → **70%** |
| Patrulheiro | 45 → 45% | 33 → **37%** | 43 → **38%** |
| Mago | 33 → **39%** | 37 → **38%** | 44 → 50% |
| Diferença | 50 → 37pp | 44 → 45pp | 21 → 31pp |
| **Duração da luta** | 12.4 → **17.4s** ✅ | 8.3 → **13.0s** | 4.7 → **8.2s** |
| Classes na faixa 40–60% | 2 → 2 de 4 | 1 → 1 de 4 | 3 → 2 de 4 |
| Espelhos entre 45% e 55% | ✅ 55 / 51 / 47 / 50 | ✅ 49 / 54 / 50 / 51 | ✅ 48 / 52 / 47 / 47 |

- **As lutas alongaram** (sala 3 na meta; sala 9 a 1s dela) e **Guerreiro, Patrulheiro e Mago ficaram equilibrados entre si**: nos confrontos
  entre eles, 36–65% (quase tudo entre 44% e 56%).
- **O Ladino continua dominando** (76 / 83 / 70%): contra o Guerreiro 87 / 93 / 84%, contra o Patrulheiro 89 / 96 / 85%. Ele sozinho puxa as
  outras três para 37–42%: sem os confrontos contra o Ladino, as outras ficam perto de 50%.

**Diagnóstico do Ladino (sala 9, contra o Guerreiro, 150–200 lutas):** metade do dano é **Veneno**.

| Medida | Ladino | Guerreiro | Patrulheiro | Mago |
|---|---|---|---|---|
| Dano por segundo em golpes (contra o Guerreiro) | 34.8 | 27.6 | 41.5 | 74.0 |
| HP + escudo inicial | 450 | 715 | 400 | 384 |
| Duração da luta contra o Guerreiro | 14.0s | 42.8s | 24.1s | 11.9s |

- O Guerreiro fica com **13.4 stacks de Veneno em média** durante a luta (teto 15; 22 com Mestre dos Venenos). Por luta: **488 de dano de Veneno**
  contra 477 de golpes. O Veneno ignora escudo (a defesa do Guerreiro) e escala x1.50 por nível do alvo (x3.4 no Nv4, x7.6 no Nv6).
- Com 2 stacks por crítico ainda chega no teto: as 2 adagas (1.2s de recarga) critam 56% das vezes (Gazuas +22%, Combo +16–24%).
- A esquiva quase não pesa (10% dos golpes do Guerreiro).
- O dano de Veneno e Queimadura não aparece na crônica de combate (só os golpes) — vale mostrar os ticks na Arena.

Matrizes (linha = sua classe, % de vitória contra a coluna):

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

### Rodada S-1 (antes das respostas, para comparação)

| Classe | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 41% | 51% | 48% |
| Ladino | 83% | 77% | 64% |
| Patrulheiro | 45% | 33% | 43% |
| Mago | 33% | 37% | 44% |
| Duração da luta | 12.4s | 8.3s | 4.7s |

Teste de economia da S-1 (não aplicado; `--items`): com 50% / 33% dos itens extras a sala 18 ia para 6.3 / 7.1s e o Ladino continuava em 67–85%.

## 4. Emboscada PvE (recalibrada na S-3)

|---|---|---|---|
| Horda de Goblins | 74% (10.3s) | 82% (6.9s) | 74% (6.9s) |
| Elite: Horda de Goblins | 55% (9.1s) | 48% (5.8s) | 50% (5.5s) |
| Câmara dos Esqueletos | 73% (23.1s) | 75% (14.4s) | 82% (17.3s) |
| Elite: Câmara dos Esqueletos | 43% (19.1s) | 44% (12.1s) | 70% (15.0s) |
| Ninho de Cubos Gelatinosos | 94% (18.5s) | 83% (25.0s) | 60% (40.0s) |
| Elite: Ninho de Cubos Gelatinosos | 77% (36.0s) | 47% (41.2s) | 30% (47.8s) |
| **Média normal** (meta ~75%) | **80%** | **80%** | **72%** |
| **Média Elite** (meta ~50%) | **58%** | **46%** | **50%** |

Calibragem (`MONSTER.tune`): Goblins HP/dano x0.59, crescimento 1.60; Esqueletos x0.75, 1.30; Cubos x0.23, 1.10; Elite (HP/dano):
x0.97/0.72, x0.87/0.65, x0.96/0.71. Os Cubos ganharam 3 Pseudópodes para cada Núcleo no pool (os Núcleos somam regeneração).
**Cubos seguem desiguais entre as salas** (94 → 60%; Elite 77 → 30%): lutas de 40–48s na sala 18, a regeneração deles empata com o dano
do herói com fusão +1. Médias na meta.

## 5. Interpretações (S-06 a S-14 confirmadas em 2026-11-19 ✅)

| Código | Interpretação |
|---|---|
| S-06 | Números dos 13 itens novos (tabela acima): a SPEC trazia só os nomes |
| S-07 | Guerreiro "45 de escudo inicial + 100 de estamina": a classe ganhou estamina extra além do escudo (antes só escudo) |
| S-08 | "Grimórios" = itens com tag `tome` (Tomo Menor, Grimório, Grimório Proibido) |
| S-09 | Bolso Alquímico: poções não têm recarga (são consumíveis), então o −20% vale para frascos e poções 1x1 **que tenham recarga**; os +2 Venenos valem para os frascos |
| S-10 | Chamado da Matilha: "cada mascote vivo" = cada mascote na Jaula (mascotes não morrem); cada outro mascote dá +10% de velocidade |
| S-11 | Flechas Envenenadas: "armas à distância" = armas `ranged` que não são mascotes (arcos, Frasco de Veneno) |
| S-12 | Toque Glacial: "item mais rápido" = o de menor recarga; o atraso usa a resistência a controle do alvo (Vontade de Ferro) |
| S-13 | Gerador de builds: Jaula cresce até 6 casas (2x3) antes da Mochila; Sinergia de Borda fora da oferta de genéricos (sem Elos no solo) |
| S-14 | Feats das classes "em breve" continuam no código, fora da oferta (voltam com a classe) |

## 6. Respostas recebidas

- **S-Q4** · 2026-11-19 · (b) esquiva 15% → 8% + (c) Frasco de Veneno fora do kit (kit: 2 Adagas, Gazuas, Gibão, Poção) + (d) Veneno por crítico 3 → 2; HP 135 mantido · aplicado (S-2) → Ladino 76 / 83 / 70%
- **S-Q5** · 2026-11-19 · (c) HP base 0.62 → 0.88 + gerador solo 2 / 4 / 8 itens extras e no máximo 10% de +3 na sala 18 · aplicado (S-2) → lutas 17.4 / 13.0 / 8.2s
- **S-Q6** · 2026-11-19 · reavaliar Mago e Patrulheiro depois de S-Q4/S-Q5 · Mago 39 / 38 / 50%, Patrulheiro 45 / 37 / 38%: os dois ficam perto de 50% contra Guerreiro e entre si; o que os derruba é o Ladino
- **S-06 a S-14** · 2026-11-19 · todas confirmadas
- **S-Q7** · 2026-11-19 · (b) Veneno e Queimadura x1.25 por nível + (c) Veneno −1 stack a cada 2s; teto 15 e "ignora escudo" mantidos · aplicado (S-3) → Ladino 71 / 75 / 74%
- **S-Q8** · 2026-11-19 · (b) gerador da sala 18 com fusão +1 e 20% em +2 + mostrar os ticks de Veneno/Queimadura na crônica · aplicado (S-3) → lutas 18.0 / 14.4 / 19.0s

## 7. Perguntas para o agente de análise

| Código | Pergunta | Dados | Opções |
|---|---|---|---|
| S-Q9 | **Ladino ainda em 71 / 75 / 74%** depois de S-Q4 e S-Q7 | Veneno no teto (14 stacks na sala 9, 17 na 18 com Mestre dos Venenos) e ~45% do dano; crítico em 65% dos golpes (2 adagas, Gazuas +22%, Combo +16–24%); cura de **450 HP/luta** na sala 18 vinda de Poções de Vida (o gerador trata todo item 1x1 como afinidade do Ladino). Contra Guerreiro 80 / 80 / 85%, contra Patrulheiro 80 / 91 / 84% | (a) **gerador:** afinidade do Ladino só com armas pequenas e catalisadores de crítico (tira poções e itens 1x1 genéricos) — mede se é viés da régua · (b) teto de Veneno 15 → 10 (Mestre dos Venenos 10 → 15) · (c) Veneno só nos críticos de armas 1x1/1x2 encostadas em Gazuas ou itens diferentes (hoje qualquer arma do Ladino) · (d) Combo +8% → +5% de crítico por item diferente |
| S-Q10 | Cubos da Emboscada desiguais (94 → 60% normal; Elite 77 → 30%) | Regeneração do Núcleo (3% do HP/s, x fusão) contra o dano com fusão +1; lutas de 40–48s na sala 18 | (a) Núcleo 3% → 2% do HP/s · (b) Cubos sem fusão extra na Elite · (c) aceitar (média na meta) |

## Histórico do experimento

| Data | Versão | Diferença entre classes (salas 3 / 9 / 18) | Lutas |
|---|---|---|---|
| 2026-11-19 | 8 classes solo, 8x8, sem alternar iniciativa | 62 / 50 / 37pp | 17.6 / 14.0 / 12.2s |
| 2026-11-19 | S-1 · SPEC-SOLO: 4 classes, 4x4, iniciativa alternada | 50 / 44 / 21pp | 12.4 / 8.3 / 4.7s |
| 2026-11-19 | S-2 · Ladino (esquiva 8%, sem Frasco, 2 Venenos), HP 0.88, gerador 2/4/8 | 37 / 45 / 31pp | 17.4 / 13.0 / 8.2s |
| 2026-11-19 | **S-3 · Veneno/Queimadura x1.25 e −1 stack a cada 2s; sala 18 com fusão +1 (20% +2)** | 30 / 37 / 38pp | 18.0 / 14.4 / 19.0s |

As lutas encurtaram de uma versão para a outra porque a média de 8 classes incluía classes lentas (Paladino, Bárbaro, Bardo, Alquimista) e porque Mago e Patrulheiro ganharam itens exclusivos fortes e mochilas novas (altar em cruz, Jaula).
