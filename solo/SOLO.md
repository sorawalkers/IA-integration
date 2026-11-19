# OSR Battler — Modo solo: 4 classes e sub-arquétipos (branch `feat/solo-class`, SPEC-SOLO)

> Branch alternativa ao jogo de 3 heróis (branch `claude/awesome-fermi-2g5woc`, intacta). Especificação aplicada: **SPEC-SOLO.md**
> (4 classes solo, Jaula do Patrulheiro, 24 Feats de classe em 2 métodos + 10 genéricos, matriz 4x4 com iniciativa alternada).
> Simulação completa: `relatorio-solo.md`. Primeira versão do experimento (8 classes): histórico no fim.

**Data:** 2026-11-19 · **Rodada S-6** (respostas S-Q12 e S-Q13; S-Q11 não aplicada) sobre a S-5 (SPEC-RUNIC-FLOW). HP = classe x **0.88** x 1.50^(nível − 1); efeitos fixos x1.50^(nível − 1), exceto Veneno/Queimadura: **x1.25^(nível − 1)**.

## 1. As 4 classes do lançamento

Paladino, Bárbaro, Bardo e Alquimista ficam **"em breve"** (`status: 'coming_soon'`): aparecem apagados na Taverna, não entram na run,
no ghost nem no balanço, e os itens exclusivos deles saem da loja.

| Classe | HP | Recurso | Mochila | Kit inicial | Pool exclusivo na loja |
|---|---|---|---|---|---|
| Guerreiro — Mestre de Aço | 160 | 45 escudo + 100 estamina | 5x5 (25) | Espada Curta, Broquel, Pedra de Amolar, Gibão, Poção de Vida | Escudo Torre, Armadura de Placas, Mangual Pesado, Estandarte de Guerra |
| Ladino — Mestre das Toxinas | 135 | 100 estamina, **8% de esquiva** | 4x6 (24) | 2 Adagas, Gazuas, Gibão, Poção de Vida (Frasco de Veneno só na loja) | Adaga Serrilhada, Frasco de Veneno, Capa das Sombras, Gazuas Mestras |
| Mago — Arquiteto Arcano | 125 | 120 mana | Altar em cruz 5x5 (17) | Cajado de Aprendiz, Tomo Menor, 2 Gemas Brutas, Poção de Mana | Grimório Proibido, Orbe de Cristal, Manto Arcano, Runa de Mana |
| Patrulheiro — Guardião da Matilha | 130 | 90 estamina | 4x5 + **Jaula 2x2** (24) | Arco Curto, Aljava, Ração, Erva (Mochila) + 2 Ratos (Jaula) | Lobo Cinzento, Falcão Caçador, Arco Composto, Erva Ancestral |

Passivas como na SPEC (Guerreiro +3/+4 de escudo x fator; Ladino **+8% de crítico por arma, frasco ou ferramenta diferente encostada** (S-Q9), **2 de Veneno por crítico** (S-Q4), **teto de Veneno 10** (S-Q9), crítico excedente;
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
| Ladino | **Toxinas:** Mestre dos Venenos (+35% velocidade, teto 10 → 15), Toxina Corrosiva (3 Venenos → 1 Ácido), Bolso Alquímico (frascos/poções 1x1: −20% recarga, frascos +2 Veneno) | **Assassino:** Passos nas Sombras (+15% esquiva, evita o 1º golpe), Ponto Vital (crítico x2.0), Execução (+45% abaixo de 35% de HP) |
| Mago | **Sobrecarga:** Sobrecarga Contínua (3s → 2s), Foco de Cristal (gemas +30%), Reserva Arcana (+40 mana) | **Elementalista:** Chama Arcana (magia aplica 2 Queimaduras, teto 8), Toque Glacial (atrasa 0.35s o item mais rápido do alvo), Barreira Elemental (30% da mana gasta vira escudo) |
| Patrulheiro | **Feras:** Vínculo Natural (cura 4 HP), Toca Farta (3 comidas por mascote), Chamado da Matilha (cada outro mascote +10% velocidade) | **Atirador:** Olho de Águia (arcos +25% crítico e +20% dano), Flechas Envenenadas (crítico à distância: 3 Venenos), Caçador Solitário (1 mascote: arcos +25% velocidade e 15% roubo de vida) |

## 3. Rodada S-6 — respostas S-Q12 e S-Q13 (matriz 4x4, 500 lutas por confronto, iniciativa alternada)

**Mudanças:** fusão de consumíveis dá **+1 uso por nível** (1 / 2 / 3 / 4 usos; era x2 por nível: 1 / 2 / 4 / 8) (S-Q12 b); HP = classe x **0.83**
x 1.50^(nível − 1) **a partir do nível 5** (0.88 até o nível 4) e **Tomo Menor 10-13** de dano (era 9-12) (S-Q13 b).

**S-Q11 não foi aplicada:** a resposta (Ladino com HP 135 → 125 e Combo +8% → +6%) foi escrita sobre os números da S-4, quando o Ladino
vencia 71 / 67 / 61%. Na S-5 o Combo deixou de existir (a passiva virou Mãos Rápidas) e o Ladino caiu para **38 / 41 / 38%**; cortar o HP
agora deixaria a classe mais fraca ainda mais fraca. Fica para o agente confirmar ou trocar por uma das opções da S-Q15.

| Classe | Sala 3 (S-5 → S-6) | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 62 → 60% | 69 → 68% | 63 → 62% |
| Ladino | 38 → 36% | 41 → 40% | 38 → 38% |
| Patrulheiro | 57 → 55% | 50 → 49% | 51 → 51% |
| **Mago** | 43 → **48%** | 40 → **43%** | 48 → 49% |
| Diferença | 24 → 24pp | 29 → 28pp | 25 → 24pp |
| Duração da luta | 18.8 → 18.6s | 16.3 → 16.2s ✅ | 22.7 → **21.1s** |
| Classes na faixa 40–60% | 2 de 4 | 2 de 4 | 2 de 4 |

- **Mago** saiu da borda na sala 3 (+5pp) e subiu 3pp na sala 9 (Tomo +1).
- **Sala 18** encurtou 1.6s (22.7 → 21.1s), menos que os ~17.5s previstos: as lutas longas vêm do Guerreiro (forte em defesa com o fluxo de aço).
- **Poções:** com +1 uso por nível, a cura por poções cai nas builds com poções fundidas; quase não mexeu na média porque o Ladino já não é a classe forte.
- O quadro geral é o da S-5: **Guerreiro forte (60–68%) e Ladino fraco (36–40%)** — perguntas S-Q14 e S-Q15, ainda sem resposta.

Matrizes (linha = sua classe, % de vitória contra a coluna):

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

### Rodada S-5 — SPEC-RUNIC-FLOW

### O que mudou

**Canais de Fluxo Rúnico** (`src/game/flow.ts`, substitui a adjacência genérica):
- Cada item tem **saídas** (setas ▶ ▼ ◀ ▲) e **entradas** nas bordas, com tipo de fluxo: `steel` (âmbar), `venom` e `nature` (verde),
  `arcane` (azul safira) ou `universal`. A rotação agora tem **4 passos** (R / botão direito / roda: 0°, 90°, 180°, 270°) e as setas giram junto.
- Uma saída liga no item vizinho na direção dela se ele tiver entrada na borda oposta e o fluxo for compatível (igual ou `universal`).
  A Arena e o Acampamento desenham as setas e um **fio luminoso** da cor do fluxo em cada ligação ativa.
- **O bônus de um catalisador só chega no item para onde a seta aponta** (antes: em todos os vizinhos encostados). Mesmo tipo soma,
  tipos diferentes multiplicam, como antes. **Condutores** (Pedra de Amolar, Estandarte, Prisma) retransmitem o bônus recebido pela própria
  seta (circuito em série). O alcance extra da fusão de catalisadores (diagonal/2 casas) saiu; a fusão continua multiplicando o bônus.
- **Padrões (S-16):** sem portas definidas, catalisadores, metais, gemas, cajados, comidas e ervas saem pela **direita** (fluxo pelo tipo do item);
  todo item recebe por **qualquer borda** (universal). Portas explícitas: Aljava (◀ e ▶), Estandarte (▲ e ▼), Prisma (entra ◀, sai ▲ ▶ ▼),
  Mangual Pesado (4 entradas, uma por lado), Bolsa de Moedas, Flechas Tóxicas.
- **Passivas pelo fluxo:** Guerreiro — cada item metálico transmite **+12%** de dano (arma) ou de escudo (armadura) pela seta; Mago — gemas e
  cajados lançam **feixes** em linha reta (atravessam casas vazias) e o tomo atingido ganha +20%; Patrulheiro — comida/erva alimenta o mascote
  para onde a seta aponta (Erva Ancestral também é feixe); Ladino — **Mãos Rápidas**: itens 1x1 recarregam 15% mais rápido e cada ativação manda um
  pulso pela seta que adianta 0.25s o item ligado. O Ladino **não** aplica mais Veneno por crítico nem tem Combo/crítico excedente (o Veneno vem dos itens).
- Kits iniciais já vêm apontados (ex.: Guerreiro com Broquel ◀ e Pedra ▲ na Espada; Mago com as gemas ◀ no Tomo).

**Expansão na loja:** o Mercador tem **6 slots**: 5 itens + 1 expansão sempre presente (renova no reroll): **Bolso Simples** 1x1 (+1 casa, 3 PO, 50%),
**Alforje Duplo** 1x2 (+2, 5 PO, 35%), **Compartimento Reforçado** 2x2 (+4, 9 PO, 15%). Solta no herói, a expansão vira casas para clicar na borda
(o Patrulheiro escolhe Mochila ou Jaula). Níveis 3/6/9: **+1 casa** (eram +2). A Bolsa de Couro saiu da loja. A loja solo só oferece itens que o herói usa.

**4 motores por classe + itens-ponte (19 itens novos; números propostos — S-17):**

| Classe | Itens novos | Mecânicas novas |
|---|---|---|
| Guerreiro | Machado Serrilhado (1x2, 6-8, 1 Sangramento, +8% velocidade a cada 20% de HP perdido), Escudo Cravado (2x1, +12 escudo; 10 de escudo gerado = 1 Sangramento no inimigo), Cota de Sangue (2x2, +16 escudo; 0.5 de escudo por ponto de Sangramento causado) | **Sangramento**: DOT físico, 1/s por stack x1.25 por nível, máx. 10, −1 a cada 2s |
| Ladino | Seringa Tóxica (1x2, 3-5, 2 Veneno + 1 Ácido), Adaga Dourada (1x2, 4-6, +1 por 5 PO), Bolsa de Moedas (1x1, +1 PO por combate; arma ligada +1% crítico por 3 PO, máx. 15%), Bomba de Fumaça (1x1, +6% esquiva, contra-ataque 6 x fator), Lâmina do Contrabandista (1x2, 5-7; ao esquivar, 2 Veneno no atacante), Moeda Tóxica (1x1, gasta 1 PO: 4 Veneno, 3s) | Contra-ataque e Veneno ao esquivar; **ouro em combate** (o bolso da run; o gerador usa 8 + sala); Capa das Sombras ganhou contra-ataque 3 |
| Mago | Pergaminho de Bola de Fogo (1x2, área 12-16 + 2 Queimaduras, 15 mana), Orbe Glacial (1x1, magia ligada: Gélido 0.25s), Cajado de Gelo (1x3, 9-12, Gélido 0.35s), Runa de Escudo (1x1, 25% da mana gasta vira escudo; a cada 5s, 50% do escudo explode em dano), Prisma Elemental (condutor 1x1, divide o feixe em 3), Cajado do Fogo Frio (1x2, 8-11, Queimadura + Gélido) | Rubi Ígneo: o item ligado aplica +1 Queimadura |
| Patrulheiro | Urso Pardo (pet 2x2, 12-16, +15 escudo), Aranha Gigante (pet 1x2, 4-6 + 2 Veneno), Flechas Tóxicas (1x1, arco ligado +1 Veneno), Berrante da Caçada (1x2, crítico do arco dispara todos os mascotes, 1x a cada 3s) | Aljava virou 1x2 (◀ ▶); Erva Ancestral é feixe |

Gazuas Mestras: +25% de crítico na arma ligada (era +20%). Ícones dos itens novos: provisórios.

### Resultado

| Classe | Sala 3 (S-4 → S-5) | Sala 9 | Sala 18 |
|---|---|---|---|
| **Guerreiro** | 45 → **62%** | 52 → **69%** | 42 → **63%** |
| **Ladino** | 71 → **38%** | 67 → **41%** | 61 → **38%** |
| Patrulheiro | 47 → **57%** | 40 → **50%** | 45 → **51%** |
| Mago | 40 → **43%** | 41 → **40%** | 55 → **48%** |
| Diferença | 31 → **24pp** | 27 → 29pp | 19 → 25pp |
| Duração da luta | 17.9 → **18.8s** | 14.7 → **16.3s** ✅ | 20.3 → **22.7s** |
| Classes na faixa 40–60% | 2 → 2 de 4 | 3 → 2 de 4 | 3 → 2 de 4 |
| Espelhos entre 45% e 55% | 50 / 52 / 45 / 56 | ✅ 51 / 52 / 51 / 51 | ✅ 49 / 49 / 51 / 49 |

- **Inverteu:** o Ladino perdeu o Veneno por crítico (o motor dele) e caiu para 38–41%; o **Guerreiro** passou a dominar (62–69%), principalmente
  contra o Ladino (**85 / 90 / 80%**). Patrulheiro e Mago ficaram perto de 50% entre si.
- **Por quê (diagnóstico, sala 9 contra o Guerreiro):** Ladino causa 23 de dano por segundo (Guerreiro 29, Patrulheiro 38, Mago 66) com 447 de
  HP + escudo contra 745 do Guerreiro. O gerador monta, na sala 18, **12.6 ligações úteis** no Guerreiro (todo metal transmite +12%), 9.8 no Ladino,
  7.7 no Mago e **6.0 no Patrulheiro** (as comidas só alimentam o mascote se apontarem para a Jaula).
- **Mochilas maiores:** com 1 expansão por duelo, o herói da sala 18 tem ~37 casas para ~13 itens (Mago ~30 no altar). Sobra espaço.
- Sala 18 em 22.7s (meta 14–18s): as lutas alongaram com o Guerreiro mais forte em defesa.

Matrizes (linha = sua classe, % de vitória contra a coluna):

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

### Rodada S-4 — respostas S-Q9 e S-Q10

**Mudanças:** Combo do Ladino conta só **armas, frascos e ferramentas/catalisadores de arma** encostados (Gazuas, Gazuas Mestras, Pedra de
Amolar, Estandarte) — poções, armaduras e comidas não dão mais crítico; afinidade do gerador do Ladino = armas pequenas, frascos e
catalisadores de arma (sem poções nem itens 1x1 genéricos); teto de Veneno **15 → 10** (Mestre dos Venenos **22 → 15**) (S-Q9).
Núcleo Gelatinoso: regeneração **3% → 2%** do HP/s, sem escalar com a fusão (S-Q10).

| Classe | Sala 3 (S-3 → S-4) | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 44 → **45%** | 46 → **52%** | 36 → **42%** |
| **Ladino** | 71 → **71%** | 75 → **67%** | 74 → **61%** |
| Patrulheiro | 48 → **47%** | 39 → **40%** | 41 → **45%** |
| Mago | 41 → **40%** | 41 → **41%** | 52 → **55%** |
| Diferença | 30 → 31pp | 37 → **27pp** | 38 → **19pp** |
| Duração da luta | 18.0 → **17.9s** ✅ | 14.4 → **14.7s** ✅ | 19.0 → **20.3s** (2.3s acima) |
| Classes na faixa 40–60% | 3 → **2** de 4 | 2 → **3** de 4 | 2 → **3** de 4 |
| Confrontos extremos (> 80%) | 1 | 1 | **0** |
| Espelhos entre 45% e 55% | ✅ 55 / 50 / 47 / 50 | ✅ 49 / 51 / 51 / 51 | ✅ 50 / 52 / 51 / 49 |

- **Salas 9 e 18 quase na meta:** só o Ladino fica fora (67% e 61%, a 1–7pp do teto de 60%). Sala 18 sem nenhum confronto acima de 80%.
- **Sala 3 continua com o Ladino em 71%** (contra Patrulheiro 83%, Mago 76%, Guerreiro 76%) e o Mago no limite (40%).
- **Ladino contra Guerreiro (150 lutas):** 61% na sala 9 e 59% na 18 (eram 79% e 84%). Veneno médio 10.0 / 11.8 stacks; dano de Veneno por
  luta 382 / 1066 contra 654 / 1440 de golpes (o Veneno caiu de ~45% para ~37% do dano).
- **A cura por poções não mudou** (~400 HP/luta na sala 18, de Poções de Vida Menores): não vinha da afinidade. O kit do Ladino já traz uma
  Poção de Vida, e o gerador ainda compra poções nos 40% de itens sem afinidade e **funde** as repetidas (+1/+2 = mais usos e mais cura).
  As outras classes também podem fazer isso; a diferença é que o Ladino tem casas 1x1 sobrando no 4x6.

Matrizes (linha = sua classe, % de vitória contra a coluna):

### Confrontos — sala 3

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 55 | 26 | 48 | 52 |
| **Ladino** | 76 | 50 | 83 | 76 |
| **Patrulheiro** | 54 | 20 | 47 | 66 |
| **Mago** | 50 | 23 | 35 | 50 |

### Confrontos — sala 9

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 49 | 46 | 57 | 57 |
| **Ladino** | 58 | 51 | 83 | 77 |
| **Patrulheiro** | 41 | 15 | 51 | 53 |
| **Mago** | 44 | 24 | 45 | 51 |

### Confrontos — sala 18

Linha = sua classe, coluna = oponente; % de vitória da linha.

|  | Guerr | Ladin | Patru | Mago |
|---|---|---|---|---|
| **Guerreiro** | 50 | 36 | 38 | 43 |
| **Ladino** | 66 | 52 | 66 | 60 |
| **Patrulheiro** | 66 | 32 | 51 | 30 |
| **Mago** | 57 | 41 | 72 | 49 |

### Rodada S-3 — respostas S-Q7 e S-Q8

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

## 4. Emboscada PvE (S-6, mesma calibragem da S-5)

MONSTER {"items":0.5,"tune":{"goblins":{"hp":0.69,"dmg":0.69,"growth":1.45,"elite":{"hp":0.99,"dmg":0.73}},"skeletons":{"hp":0.68,"dmg":0.68,"growth":1.3,"elite":{"hp":0.9,"dmg":0.67}},"cubes":{"hp":0.52,"dmg":0.52,"growth":1.1,"elite":{"hp":1.15,"dmg":0.85}}}} · ELITE {"plus":1,"items":1} · 300 lutas por célula

| Encontro | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Horda de Goblins | 74% (11.7s) | 83% (9.1s) | 77% (9.5s) |
| Elite: Horda de Goblins | 47% (10.3s) | 58% (7.8s) | 55% (7.8s) |
| Câmara dos Esqueletos | 80% (23.9s) | 70% (16.0s) | 80% (16.1s) |
| Elite: Câmara dos Esqueletos | 46% (20.1s) | 42% (13.2s) | 64% (13.6s) |
| Ninho de Cubos Gelatinosos | 73% (32.9s) | 81% (27.2s) | 75% (33.5s) |
| Elite: Ninho de Cubos Gelatinosos | 43% (29.1s) | 58% (23.5s) | 63% (29.8s) |
| **Média normal** (meta ~75%) | **76%** | **78%** | **77%** |
| **Média Elite** (meta ~50%) | **46%** | **52%** | **61%** |

Calibragem (`MONSTER.tune`, sem mudança na S-6): Goblins HP/dano x0.69, crescimento 1.45; Esqueletos x0.68, 1.30; Cubos x0.52, 1.10;
Elite (HP/dano): x0.99/0.73, x0.90/0.67, x1.15/0.85.

## 5. Interpretações

**SPEC-RUNIC-FLOW (validar):**

| Código | Interpretação |
|---|---|
| S-15 | Gerador: compra 1 expansão no slot fixo a cada duelo (média 1.8 casas) e leva **8 + sala** PO no bolso para a luta (Adaga Dourada, Bolsa de Moedas, Moeda Tóxica) |
| S-16 | Portas padrão: saídas pela direita em catalisadores, metais, gemas, cajados, comidas e ervas; entradas universais em todas as bordas. "Universal" casa com qualquer fluxo |
| S-17 | Números dos 19 itens novos (tabela da seção 3) e das mecânicas: Sangramento 1/s por stack x1.25 por nível, máx. 10, −1 a cada 2s; contra-ataque x fator de nível; Runa explode 50% do escudo a cada 5s |
| S-18 | Expansão solta no herói vira casas para clicar na borda (Bolso 1, Alforje 2, Compartimento 4), não uma peça com forma; o Patrulheiro escolhe Mochila ou Jaula |
| S-19 | Ladino: "Mãos Rápidas" substitui a passiva inteira (sem Veneno por crítico, sem Combo, sem crítico excedente); o pulso vale para qualquer item que ativa |
| S-20 | Passiva do Guerreiro: o +12% vai só para o item na ponta da seta do metal (não é retransmitido por condutores) |
| S-21 | A loja solo só oferece itens que o herói pode usar (gerais + exclusivos da classe) |
| S-22 | A fusão de catalisadores não dá mais alcance (diagonal/2 casas); continua multiplicando o bônus |

**S-06 a S-14:** confirmadas em 2026-11-19 ✅

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
- **S-Q9** · 2026-11-19 · Combo só com armas, frascos e ferramentas + afinidade do gerador sem poções + teto de Veneno 15 → 10 (Mestre dos Venenos 22 → 15) · aplicado (S-4) → Ladino 71 / 67 / 61%
- **S-Q10** · 2026-11-19 · Núcleo 3% → 2% do HP/s, sem escalar com a fusão · aplicado (S-4) → Cubos estáveis (75 / 87 / 70%) depois de recalibrar
- **S-Q11** · 2026-11-19 · (a) leve + (b): Ladino HP 135 → 125 e Combo +8% → +6% · **não aplicada** (resposta sobre os dados da S-4; na S-5 o Combo saiu e o Ladino caiu para 38–41%) — aguardando confirmação
- **S-Q12** · 2026-11-19 · (b) fusão de consumíveis +1 uso por nível · aplicado (S-6)
- **S-Q13** · 2026-11-19 · (b) HP base 0.83 a partir do Nv5 + Tomo Menor +1 de dano · aplicado (S-6) → Mago 48 / 43 / 49%, sala 18 em 21.1s

## 7. Perguntas para o agente de análise

| Código | Pergunta | Dados | Opções |
|---|---|---|---|
| S-Q14 | **Guerreiro dominante com o fluxo** (62 / 69 / 63%) | Contra o Ladino 85 / 90 / 80%. O gerador monta 12.6 ligações úteis no Guerreiro (todo metal transmite +12% de dano/escudo), contra 6–10 nas outras. HP + escudo 745 (sala 9) | (a) +12% só de **armas** metálicas (armaduras não transmitem) · (b) +12% → +8% · (c) o +12% exige fluxo `steel` dos dois lados (entrada de aço no alvo) |
| S-Q15 | **Ladino sem motor** (38 / 41 / 38%) | Sem Veneno por crítico, o dano dele caiu para 23/s (sala 9). O Veneno agora vem só da loja (Frasco, Seringa, Moeda Tóxica, Lâmina do Contrabandista) | (a) Mãos Rápidas: pulso 0.25s → 0.4s · (b) devolver 1 Veneno por crítico só em armas 1x1/1x2 · (c) HP 135 → 150 · (d) kit com Frasco de Veneno de novo |
| S-Q16 | **Mochilas com espaço sobrando** (~37 casas para ~13 itens na sala 18) | 1 expansão por duelo no gerador (S-15) + níveis | (a) gerador compra expansão só em 1 de cada 2 duelos · (b) expansões mais caras (Bolso 4, Alforje 7, Compartimento 12) · (c) aceitar (espaço livre ajuda a montar circuitos) |
| S-Q17 | Sala 18 em **21.1s** depois da S-Q13 (meta 14–18s) | Salas 3 e 9: 18.6 / 16.2s | Reavaliar depois de S-Q14 |
| S-Q18 | **S-Q11 com os dados da S-5/S-6** | Ladino 36 / 40 / 38%, sem Combo (Mãos Rápidas). A resposta S-Q11 (HP 135 → 125) foi pensada para o Ladino em 71% | (a) cancelar a S-Q11 e decidir a S-Q15 · (b) aplicar mesmo assim |

## Histórico do experimento

| Data | Versão | Diferença entre classes (salas 3 / 9 / 18) | Lutas |
|---|---|---|---|
| 2026-11-19 | 8 classes solo, 8x8, sem alternar iniciativa | 62 / 50 / 37pp | 17.6 / 14.0 / 12.2s |
| 2026-11-19 | S-1 · SPEC-SOLO: 4 classes, 4x4, iniciativa alternada | 50 / 44 / 21pp | 12.4 / 8.3 / 4.7s |
| 2026-11-19 | S-2 · Ladino (esquiva 8%, sem Frasco, 2 Venenos), HP 0.88, gerador 2/4/8 | 37 / 45 / 31pp | 17.4 / 13.0 / 8.2s |
| 2026-11-19 | S-3 · Veneno/Queimadura x1.25 e −1 stack a cada 2s; sala 18 com fusão +1 (20% +2) | 30 / 37 / 38pp | 18.0 / 14.4 / 19.0s |
| 2026-11-19 | S-4 · Combo só armas/frascos/ferramentas, teto de Veneno 10, Núcleo 2% | 31 / 27 / 19pp | 17.9 / 14.7 / 20.3s |
| 2026-11-19 | S-5 · SPEC-RUNIC-FLOW: fluxo rúnico, expansão na loja, 4 motores + pontes | 24 / 29 / 25pp | 18.8 / 16.3 / 22.7s |
| 2026-11-19 | **S-6 · poções +1 uso por nível, HP 0.83 a partir do Nv5, Tomo +1** | 24 / 28 / 24pp | 18.6 / 16.2 / 21.1s |

As lutas encurtaram de uma versão para a outra porque a média de 8 classes incluía classes lentas (Paladino, Bárbaro, Bardo, Alquimista) e porque Mago e Patrulheiro ganharam itens exclusivos fortes e mochilas novas (altar em cruz, Jaula).
