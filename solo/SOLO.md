# OSR Battler — Modo solo: 4 classes e sub-arquétipos (branch `feat/solo-class`, SPEC-SOLO)

> Branch alternativa ao jogo de 3 heróis (branch `claude/awesome-fermi-2g5woc`, intacta). Especificação aplicada: **SPEC-SOLO.md**
> (4 classes solo, Jaula do Patrulheiro, 24 Feats de classe em 2 métodos + 10 genéricos, matriz 4x4 com iniciativa alternada).
> Simulação completa: `relatorio-solo.md`. Primeira versão do experimento (8 classes): histórico no fim.

**Data:** 2026-11-19 · HP = classe x 0.62 x 1.50^(nível − 1); efeitos fixos x1.50^(nível − 1).

## 1. As 4 classes do lançamento

Paladino, Bárbaro, Bardo e Alquimista ficam **"em breve"** (`status: 'coming_soon'`): aparecem apagados na Taverna, não entram na run,
no ghost nem no balanço, e os itens exclusivos deles saem da loja.

| Classe | HP | Recurso | Mochila | Kit inicial | Pool exclusivo na loja |
|---|---|---|---|---|---|
| Guerreiro — Mestre de Aço | 160 | 45 escudo + 100 estamina | 5x5 (25) | Espada Curta, Broquel, Pedra de Amolar, Gibão, Poção de Vida | Escudo Torre, Armadura de Placas, Mangual Pesado, Estandarte de Guerra |
| Ladino — Mestre das Toxinas | 135 | 100 estamina, **15% de esquiva** | 4x6 (24) | 2 Adagas, Frasco de Veneno, Gazuas, Poção de Vida | Adaga Serrilhada, Frasco de Veneno, Capa das Sombras, Gazuas Mestras |
| Mago — Arquiteto Arcano | 125 | 120 mana | Altar em cruz 5x5 (17) | Cajado de Aprendiz, Tomo Menor, 2 Gemas Brutas, Poção de Mana | Grimório Proibido, Orbe de Cristal, Manto Arcano, Runa de Mana |
| Patrulheiro — Guardião da Matilha | 130 | 90 estamina | 4x5 + **Jaula 2x2** (24) | Arco Curto, Aljava, Ração, Erva (Mochila) + 2 Ratos (Jaula) | Lobo Cinzento, Falcão Caçador, Arco Composto, Erva Ancestral |

Passivas como na SPEC (Guerreiro +3/+4 de escudo x fator; Ladino crítico por item diferente, Veneno, crítico excedente;
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

## 3. Resultado — matriz 4x4 (`npm run balance -- --rooms 3,9,18 --fights 500`)

16 confrontos x 500 lutas por sala, **iniciativa alternada** (metade das lutas com os lados trocados).

| Classe | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | 41% | 51% | 48% |
| **Ladino** | **83%** | **77%** | **64%** |
| Patrulheiro | 45% | **33%** | 43% |
| Mago | **33%** | **37%** | 44% |
| Diferença | 50pp | 44pp | 21pp |
| Duração da luta | 12.4s | **8.3s** | **4.7s** |
| Classes na faixa 40–60% | 2/4 | 1/4 | 3/4 |
| Espelhos entre 45% e 55% | ✅ 4/4 (54/48/50/50) | ✅ 4/4 (51/50/50/47) | ✅ 4/4 (52/52/49/46) |

- **Alternar a iniciativa resolveu o espelho** (antes: Mago 63 / 79 / 58%). A regra empate = derrota do lado 0 também se compensa.
- **Ladino domina** em todas as salas: 135 HP + 15% de esquiva + Frasco de Veneno no kit. Contra ele: Guerreiro 3 / 14 / 23%, Patrulheiro 3 / 4 / 21%.
- **Lutas curtas demais** (4.7s na sala 18). Não é Feat (sem Feats: Guerreiro 21s, Ladino 7s, Patrulheiro 2s e Mago 2s no espelho da sala 18).
  É o gerador: o herói solo recebe sozinho os 12 itens extras fundidos em +2 (antes repartidos por 3). Ex.: Mago da sala 18 com 3 Tomos +2,
  2 Pergaminhos de Fogo e Cajado do Arquimago (~440 de dano/s contra 590 de HP); catalisadores +2 dão +100% de dano (gemas) e −60% de recarga (aljavas).

**Teste de economia (não aplicado; `--items`):**

| Itens extras do gerador | Lutas (salas 3 / 9 / 18) | Ladino | Diferença |
|---|---|---|---|
| 100% (12 na sala 18) | 12.4 / 8.3 / 4.7s | 83 / 77 / 64% | 50 / 44 / 21pp |
| 50% | 14.0 / 10.1 / 6.3s | 85 / 84 / 67% | 54 / 52 / 26pp |
| 33% | 14.0 / 11.0 / 7.1s | 85 / 85 / 72% | 54 / 55 / 31pp |

Menos itens alonga pouco as lutas e não resolve o Ladino. O que mais acelera é a **fusão +2** (dano x2.89, catalisadores x3.4).

Matrizes (linha = sua classe, % de vitória contra a coluna):

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

## 4. Emboscada PvE (recalibrada para as 4 classes)

|---|---|---|---|
| Horda de Goblins | 81% (7.3s) | 77% (4.0s) | 74% (1.7s) |
| Elite: Horda de Goblins | 58% (6.7s) | 49% (3.3s) | 52% (1.4s) |
| Câmara dos Esqueletos | 73% (15.6s) | 71% (8.1s) | 81% (3.2s) |
| Elite: Câmara dos Esqueletos | 50% (13.0s) | 44% (7.0s) | 68% (3.2s) |
| Ninho de Cubos Gelatinosos | 86% (24.8s) | 69% (23.9s) | 76% (18.6s) |
| Elite: Ninho de Cubos Gelatinosos | 58% (28.0s) | 35% (25.0s) | 56% (22.8s) |
| **Média normal** (meta ~75%) | **80%** | **72%** | **77%** |
| **Média Elite** (meta ~50%) | **55%** | **43%** | **59%** |

Calibragem (`MONSTER.tune`): Goblins HP/dano x0.58, crescimento 1.75; Esqueletos x0.75, 1.40; Cubos x0.63, 1.10; Elite (HP/dano):
x0.98/0.73, x0.88/0.65, x0.84/0.62. Na sala 18 os Goblins e Esqueletos morrem em 1.4–3.2s (mesma causa das lutas curtas).

## 5. Interpretações feitas (validar)

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

## 6. Perguntas para o agente de análise

| Código | Pergunta | Dados | Opções |
|---|---|---|---|
| S-Q4 | **Ladino domina o solo** | 83 / 77 / 64%; contra Guerreiro 95 / 83 / 72% e Patrulheiro 96 / 96 / 77%. Espelho correto (48–52%). Tem 135 HP + 15% de esquiva + Frasco de Veneno; o Veneno ignora escudo e escala x1.50 por nível | (a) HP 135 → 110 · (b) esquiva base 15% → 8% · (c) Frasco de Veneno fora do kit (só na loja) · (d) Veneno por crítico 3 → 2 |
| S-Q5 | **Lutas curtas no solo (4.7s na sala 18)** | Gerador dá 12 itens +2 a um herói só; cortar os itens para 50% / 33% leva a sala 18 a 6.3 / 7.1s. Fusão +2 multiplica dano x2.89 e catalisadores x3.4 | (a) gerador solo: itens extras x0.5 e fusão um nível abaixo (sala 18: +1) · (b) HP x1.5 no solo (curva 0.93 x 1.50^(nível−1)) · (c) as duas |
| S-Q6 | Mago fraco no início (33 / 37%) e Patrulheiro na sala 9 (33%) | Mago: altar de 17 casas com kit de 5 itens; Patrulheiro perde 4 / 4% para o Ladino | Reavaliar depois de S-Q4/S-Q5 (o Ladino distorce a média das outras) |

## Histórico do experimento

| Data | Versão | Diferença entre classes (salas 3 / 9 / 18) | Lutas |
|---|---|---|---|
| 2026-11-19 | 8 classes solo, 8x8, sem alternar iniciativa | 62 / 50 / 37pp | 17.6 / 14.0 / 12.2s |
| 2026-11-19 | **SPEC-SOLO: 4 classes, 4x4, iniciativa alternada** | 50 / 44 / 21pp | 12.4 / 8.3 / 4.7s |

As lutas encurtaram de uma versão para a outra porque a média de 8 classes incluía classes lentas (Paladino, Bárbaro, Bardo, Alquimista) e porque Mago e Patrulheiro ganharam itens exclusivos fortes e mochilas novas (altar em cruz, Jaula).
