# OSR Battler — Relatório de Balanceamento

> Página viva: atualizada a cada teste ou mudança de regra.
> Markdown puro (para agentes): `https://osr.valiran.party/relatorio.md` · Página: `https://osr.valiran.party/`
> Última simulação completa (gerada por `npm run balance`): `https://osr.valiran.party/simulacao.md`
> Fonte no repositório: `docs/BALANCO.md` (branch `claude/awesome-fermi-2g5woc`). Regras completas: `CLAUDE.md`.

**Última atualização:** 2026-11-18 · Rodada 13 (respostas Q-09 a Q-11 aplicadas).

## Como os testes são feitos

- Ferramenta: `npm run balance -- --rooms 3,9,18 --fights 320` (simulação determinística por seed).
- **Classes:** todas as **512 composições** (8 classes x 3 posições, posição livre). Mostramos a **melhor posição** de cada classe
  e a taxa de vitória nela; "Diferença" = melhor classe − pior classe (em pontos percentuais).
- Jogador **e** ghost são montados pelo mesmo gerador de progressão (`progressParty`):

| Sala | Itens extras | Fusão | Encantamentos |
|---|---|---|---|
| 3 | 2 | +0 | 0 |
| 9 | 6 | +1 | 1 |
| 18 | 12 | +2 (25% dos itens +3) | 3 |

- Números absolutos sobem quando o jogador evolui junto; compare a **diferença entre classes**, não o valor isolado.

## Resultado atual (rodada 9)

Melhor posição de cada classe · taxa de vitória nela · (média geral nas 512 composições)

| Classe | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| Guerreiro | Vang 41% (26%) | Vang 48% (36%) | Vang 56% (48%) |
| Paladino | Vang 39% (23%) | Vang 39% (26%) | Vang 44% (34%) |
| Bárbaro | Vang 40% (30%) | Vang 43% (34%) | Vang 52% (48%) |
| Bardo | Meio 41% (32%) | Meio 57% (51%) | Meio 57% (49%) |
| Ladino | Meio 42% (30%) | Meio 40% (32%) | Meio 41% (35%) |
| Patrulheiro | Ret 32% (23%) | Ret 39% (35%) | Meio 57% (52%) |
| Mago | Ret 40% (30%) | Meio 54% (43%) | Meio 40% (35%) |
| Alquimista | Ret 40% (35%) | Ret 42% (38%) | Ret 35% (33%) |
| **Diferença** | **11 pp** | **18 pp** | **22 pp** |

### Ajustes aplicados nesta rodada

| Classe | Ajuste | Efeito medido |
|---|---|---|
| Mago | Sobrecarga com mais de **65% da mana máxima** (era 80 fixo); cajados geram mana +50% por nível de fusão (3 → 4.5 → 6 → 7.5) | Sala 18: 39% → 40% (sem efeito relevante) |
| Alquimista | Poções curam **base + 12% do HP máximo** do alvo; Bomba aplica **Ácido** (−20% de escudo ganho por stack, máx. 3, −1 stack a cada 4s) | Sala 18: 36% → 35% (sem efeito) |
| Guerreiro | Escudo por ataque (+4) no máximo **1x por segundo** (o +4 já era fixo) | Sala 18: 56% → 56% (sem efeito) |
| Patrulheiro | Cada mascote aproveita no máximo **2 comidas/ervas** (+50%) | Sala 18: 58% → 57% (sem efeito) |
| Bardo | Palco: **−14% e −0.25s** de recarga no Meio (−8% e −0.15s fora do Meio); um instrumento só | Sala 3: 34% → 41% ✅ · Sala 18: 51% → 57% ❌ |
| Ladino | Crítico por item diferente encostado **12% → 8%**; crítico acima de 100% vira dano crítico (+15% por 10% excedente) | Sala 3: 47% → 42% ✅ · Sala 18: 42% → 41% |

## Rodada 13 — respostas Q-09, Q-10 e Q-11

| Mudança | Antes | Agora |
|---|---|---|
| Fusão de armas (Q-09) | recarga −8%/nível | **−13%/nível** (+1 ≈ x1.95 de DPS) |
| Instrumentos fundidos (Q-09) | aceleração +50%/nível | **+75%/nível**; inspiração do Tambor +2 / +3 / +4 / +5 |
| Ladino (Q-10) | Veneno máx. 10, 2 por crítico, excedente máx. +60% | máx. **15**, **3** por crítico, excedente máx. **+80%** |
| Mago (Q-10) | Sobrecarga acima de 65% da mana | acima de **78%** |
| Patrulheiro (Q-10) | Ataque Coordenado 0.4s | **0.6s** |
| Paladino (Q-10) | relíquia gera 4 de escudo | **6** |
| Afiado (Q-11) | +30% de crítico | +30% de crítico **e cada crítico adianta 0.3s a recarga da arma** |

Também atualizei os textos das passivas na interface (estavam desatualizados desde rodadas antigas).

### Classes por sala (512 composições, 80 lutas cada)

| | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| **Duração média da luta** (meta 14–18s) | 19.4s | **14.9s** ✅ | **11.6s** (era 13.6) |
| Guerreiro | Vang 41% | Vang 46% | Vang 53% |
| Paladino | Vang 38% | Vang 38% | Vang **41%** (igual) |
| Bárbaro | Vang 38% | Vang 41% | Vang 50% |
| Bardo | Meio 34% | Meio 47% | Meio 54% |
| Ladino | Meio **47%** (era 42) | Meio 38% | Meio **35%** (igual) |
| Patrulheiro | Ret 31% | Ret 33% | Ret **39%** (igual) |
| Mago | Ret 35% (era 43) | Ret 45% | Meio 59% (era 61) |
| Alquimista | Ret 36% | Ret 49% | Ret 56% |
| **Diferença** | 16 pp (era 12) | 16 pp | **23 pp** (era 26) |

- Os buffs do Q-10 **não moveram** Ladino, Patrulheiro e Paladino na sala 18; o Ladino subiu só na sala 3 (47%).
- A Sobrecarga a 78% derrubou o Mago mais nas salas 3 e 9 (−8 e −6pp) do que na 18 (−2pp).
- A sala 18 encurtou para 11.6s: armas +2 com −26% de recarga disparam mais rápido.

### Encantamentos (sala 3; meta +20 a +40pp)

Armazenador +38.7 · Gélido +35.7 · Trovejante +35.3 · Flamejante +31.7 · Veloz +25.3 · Defensor +25.0 ·
**Afiado +23.3** (era +13.7) ✅ · Vorpal +23.0 · Mortal +22.0 · **Vampírico +17.7** (era +21.3).
A linha de base caiu de 38% para 28% (o Mago da party de referência perdeu a Sobrecarga cedo), o que mexe um pouco em todos os deltas.

### Fusão: +1 contra 2 cópias (sala 3)

Arco Curto +4.0 · Espada Curta +2.7 · Cajado +2.3 · Maça −1.0 · **Adaga −5.3** · **Gema Bruta −7.0** · **Tambor de Guerra −14.7**.
A causa agora não é o número da fusão: no teste, as **2 cópias podem ir para heróis diferentes** (cada um com sua estamina,
seu limite de escudo por golpe do Guerreiro etc.), e **2 Tambores** dão o adiantamento e a inspiração duas vezes para o grupo todo → **Q-12**.

## Rodada 12 — respostas Q-07, Q-08 e observações do agente de análise

| Mudança | Antes | Agora |
|---|---|---|
| HP (Q-07) | x(1 + 0.25·duelos) | x0.75 · (1 + 0.10·duelos + 0.10·duelos²) → x0.90 / x1.65 / x3.90 nas salas 3 / 9 / 18 |
| Fusão de armas (Q-07 + observação 2) | dano x1.85, recarga −5%/nível | dano **x1.7** e recarga **−8%/nível** (instrumentos seguem −5%) |
| Armazenador | 25 de mana | 20 |
| Veloz | −20% | −22% |
| Mortal | críticos x3 | críticos x3 **e +10% de crítico** |
| Afiado | +25% | +30% |
| Vampírico | 20% | 25% |
| Vorpal | 10% | 12% |
| Trovejante | só atordoa (25%) | **+20% de dano** e atordoa (25%) |
| Tambor de Guerra (observação 1) | adianta 0.5s | adianta 0.5s **e o próximo golpe de cada aliado causa +2** (não acumula, não escala com a fusão) |
| HP por duelo | por duelo vencido | por duelo **jogado** (pedido do usuário: evita bola de neve) |

### Duração das lutas e classes por sala (512 composições, 80 lutas cada)

| | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| **Duração média da luta** (meta 14–18s) | **19.5s** (era 26.1) | **15.7s** ✅ | **13.6s** (era 7.5) |
| Guerreiro | Vang 44% | Vang 47% | Vang 53% |
| Paladino | Vang 40% | Vang 40% | Vang 41% |
| Bárbaro | Vang 40% | Vang 42% | Vang 50% |
| Bardo | Meio **38%** (era 28) | Meio 47% | Meio 55% |
| Ladino | Meio 42% | Meio 37% | Meio **35%** |
| Patrulheiro | Ret 32% | Ret 34% | Ret 39% |
| Mago | Ret 43% | Ret 51% | Meio **61%** |
| Alquimista | Ret 39% | Ret 50% | Ret 56% |
| **Diferença** | **12 pp** | 17 pp | **26 pp** (era 21) |

- As durações ficaram como o teste previu (19.9 / 16.1 / 13.4s): todas perto da meta, sala 3 ainda 1.5s acima.
- O Bardo voltou de 28% para 38% na sala 3 com a inspiração do Tambor.
- Com lutas mais longas na sala 18, quem escala com tempo (Mago, Alquimista, Bardo) sobe; o Ladino cai (35%). Diferença 26pp → **Q-10**.

### Encantamentos (sala 3, em todas as armas; meta +20 a +40pp)

| Encantamento | Rodada 11 | Rodada 12 |
|---|---|---|
| Gélido | +39.3 | +35.3 ✅ |
| Armazenador | +18.0 | +32.7 ✅ |
| Trovejante | +17.0 | +32.3 ✅ |
| Flamejante | +33.7 | +30.0 ✅ |
| Defensor | +25.3 | +24.3 ✅ |
| Vampírico | +14.7 | +21.3 ✅ |
| Mortal | +7.7 | +21.0 ✅ |
| Vorpal | +19.3 | +20.7 ✅ |
| Veloz | +16.7 | +19.7 (no limite) |
| Afiado | +13.7 | **+13.7** ❌ |

9 de 10 na faixa. Afiado continua abaixo → **Q-11**.

### Fusão: item +1 contra 2 cópias +0 (sala 3)

| Item | +1 | 2 cópias | Delta |
|---|---|---|---|
| Espada Curta | 74.7% | 72% | +2.3 |
| Arco Curto | 78.7% | 77% | +1.7 |
| Cajado de Aprendiz | 75.0% | 74% | +1.3 |
| Maça | 73.7% | 75% | −1.7 |
| Adaga | 67.7% | 73% | **−5.7** |
| Tambor de Guerra | 57.7% | 71% | **−13.0** |

A regra "fundir nunca pior que 2 cópias" ainda falha na Adaga e no Tambor → **Q-09**. Em DPS bruto, uma arma +1
dá 1.7 / 0.92 = **x1.85** de uma cópia, contra x2 de duas cópias; o espaço que a fusão libera não aparece nesse teste
(as 2 cópias cabem na mochila).

## Rodada 11 — respostas do agente de análise (Q-01 a Q-06)

| Q | Decisão aplicada |
|---|---|
| Q-01 | HP base x(1 + 0.25 por duelo vencido); fusão de armas x1.85 por nível (+1 x1.85 · +2 x3.42 · +3 x6.33) |
| Q-02 | Catalisadores do mesmo tipo **somam**; tipos diferentes **multiplicam** |
| Q-03 | Veneno máx. 10 stacks; dano crítico excedente máx. +60% (multiplicador máx. x2.1) |
| Q-04 | Armazenador 25 de mana · Veloz −20% · Flamejante máx. 4 stacks · Mortal x3 · Afiado +25% · Trovejante 25% |
| Q-05 | Relatório de itens com colunas "Com Ladino" e "Sem Ladino" |
| Q-06 | Interpretações confirmadas; Bardo começa com 1 Tambor + Adaga + Poção |

> **Correção de design (usuário):** o HP cresce por duelo **jogado** (vitória ou derrota), não por duelo vencido —
> senão quem vence fica mais forte e quem perde não se recupera (bola de neve). As simulações já usavam duelos jogados
> (`floor(sala/3)`), então os números abaixo não mudam.

### Duração das lutas e classes por sala (512 composições, 320 lutas)

| | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| **Duração média da luta** (meta 14–18s) | 26.1s ❌ | **15.8s** ✅ | 7.5s ❌ (era 2.3s) |
| Guerreiro | Vang 41% | Vang 47% | Vang 53% |
| Paladino | Vang 38% | Vang 40% | Vang 41% |
| Bárbaro | Vang 42% | Vang 43% | Vang 51% |
| Bardo | Meio 28% | Meio 43% | Meio 58% |
| Ladino | Meio 42% | Meio 37% | Meio 37% |
| Patrulheiro | Ret 31% | Ret 36% | Ret 43% |
| Mago | Ret 40% | Ret 52% | Meio 57% |
| Alquimista | Ret 43% | Ret 50% | Ret 49% |
| **Diferença** | 14 pp | 16 pp | 21 pp |

- Mago e Alquimista **deixaram de afundar** na sala 18 (40% → 57% e 35% → 49%): com lutas mais longas, mana e poções agem.
- A meta de duração **não foi atingida** nas salas 3 e 18 → pergunta **Q-07** em `PENDENCIAS.md`, com uma curva testada que dá 19.9s / 16.1s / 13.4s.
- Bardo caiu para 28% na sala 3 com um Tambor só.

### Encantamentos (sala 3, em todas as armas; meta +20 a +40pp)

| Encantamento | Antes (rodada 10) | Agora |
|---|---|---|
| Gélido | +43.0 | **+39.3** ✅ |
| Flamejante | +43.7 | **+33.7** ✅ |
| Defensor | +26.0 | **+25.3** ✅ |
| Vorpal | +23.3 | +19.3 |
| Armazenador | +51.3 | +18.0 (corte passou do ponto) |
| Trovejante | +10.0 | +17.0 |
| Veloz | +46.0 | +16.7 (corte passou do ponto) |
| Vampírico | +17.3 | +14.7 |
| Afiado | +9.0 | +13.7 |
| Mortal | +7.3 | +7.7 (crítico base 5% → x3 quase nunca acontece) |

Seis encantamentos ficaram abaixo de +20pp → pergunta **Q-08**.

### Itens: Com e Sem Ladino (sala 3)

| Item | Com Ladino | Sem Ladino |
|---|---|---|
| Aljava | +8.7 | **+0.0** (sem espaço livre encostado no arco da party de referência) |
| Gema Bruta | +8.7 | +3.3 |
| Poção de Mana Menor | +8.7 | +4.0 |
| Pedra de Amolar | +16.7 | +6.3 |
| Ração de Viagem | +15.7 | **+25.3** |
| Rubi Ígneo (sala 9) | +0.0 | +10.0 |

Confirma o Q-05: Aljava, Gema Bruta e Poção de Mana valem quase só pelo Combo do Ladino.

> Correção de medição nesta rodada: a party de referência dos testes de itens/encantamentos passou a ter os mesmos
> duelos vencidos (HP) que os ghosts da sala. Sem isso, ela ficava mais fraca que o oponente e os deltas encolhiam.

## Rodada 10 — anomalias do relatório de itens (sala 3, 300 lutas)

| Problema | Causa encontrada | Correção | Resultado |
|---|---|---|---|
| Flamejante quebrado (97.7%, +64pp) | cada golpe de cada arma somava 1 stack de Queimadura (2 dano/s), sem limite | Queimadura **1 dano/s por stack, máx. 5 stacks** | **79.7%** (+43.7pp), junto de Veloz 82% e Gélido 79% |
| Aljava, Ração e Poção de Mana com +0.0pp | **artefato do teste:** a party de referência (Mago/Bardo/Guerreiro) não tem arcos nem mascotes; a Poção de Mana só disparava abaixo de 25% de mana | itens testados em **3 parties de referência** (+ Patrulheiro/Bardo/Guerreiro e Alquimista/Ladino/Paladino), fica a melhor; Poção de Mana dispara **abaixo de 50%** | Ração +19.3pp, Aljava +11.7pp, Poção de Mana +11.7pp |
| Alaúde "sem espaço" | item 2x2 e a mochila inicial do Bardo não tem 2x2 livre (bolsas expandidas ainda não existem) | sem espaço → o teste **troca** o item mais dispensável do herói | Alaúde +11.7pp (no lugar de um Tambor) |
| Itens avançados ~0% na sala 9 | a party de referência estava com o kit inicial contra ghosts da sala 9 | avançados medidos na **sala 9 com a party de referência evoluída** (mesmo gerador dos ghosts) e o item em +1 | Machado Grande +33.7, Espada Longa +20.3, Cajado Runado +20.3, Arco Longo +19.3, Pergaminho +16.0, Alaúde +11.7 |

Observações da rodada 10:
- **Armazenador** virou o encantamento mais forte (87.3%, +51pp). Mortal, Afiado e Trovejante são os mais fracos (+7 a +10pp).
- Poção de Mana, Gema Bruta e Aljava deram exatamente o mesmo resultado (+11.7pp) na party com Ladino: o ganho
  vem do **Combo do Ladino** (+8% de crítico por item diferente encostado na adaga), não da função do item.
- **Lobo Cinzento** (−7.3pp) e **Gema de Mana**/**Rubi** (~0) não compensam na sala 9: o Lobo só coube tirando o Arco
  Longo, e a mana quase não pesa em lutas de 7s (ver diagnóstico de duração abaixo).

## Diagnóstico principal: as lutas encurtam demais no fim da run

| Sala | Duração média de uma luta |
|---|---|
| 3 | 21.3 s |
| 9 | 7.1 s |
| 18 | **2.3 s** |

O dano das armas multiplica com a fusão (x2.2 por nível → x4.84 no +2) e as mochilas cheias têm mais armas,
mas **a vida dos heróis não cresce**. Na sala 18 a luta acaba no primeiro ataque. Consequências:

- **Perdem:** mecânicas que precisam de tempo — poções (disparam abaixo de 40% de HP), mana do Mago
  (tomo recarrega em 3s), Veneno do Ladino, Égide do Paladino (a cada 4s), Grito de Guerra (6s).
- **Ganham:** quem tem HP/escudo inicial alto (Guerreiro, Bárbaro) e quem ataca rápido (mascotes, corte do Bardo).

Por isso os ajustes de classe para o fim da run quase não mexeram nos números: o problema é de **ritmo**, não de classe.

Ocupação das mochilas na sala 18 (itens por herói e % dos slots usados): Guerreiro 8.6 (80%), Paladino 7.9 (90%),
Bárbaro 7.7 (79%), Bardo 7.6 (79%), Ladino 7.6 (82%), Patrulheiro 9.4 (87%), Mago 8.5 (84%), Alquimista 8.4 (84%).

## Próximo passo (pendente de decisão)

- **Vida crescendo com a profundidade** (ex.: HP x(1 + 0.4 por duelo vencido) → x2.2 na sala 9, x3.4 na sala 18),
  e/ou fusão de armas mais fraca. Meta: lutas de ~15–20s em todas as salas. *Teste ainda não executado.*

## Histórico de rodadas

| Rodada | Mudança | Diferença entre classes (melhor posição) |
|---|---|---|
| 1 | Posições fixas, passivas do GDD | 30 pp (sala 3) |
| 5 | Posição livre + passivas do CLAUDE.md | ~9 pp (sala 3) |
| 6 | Alquimista, Flanco no Meio, Guerreiro +4 escudo/ataque, Paladino 35% | 14 pp (sala 3) |
| 7 | Grito de Guerra (Bárbaro), Ataque Coordenado (Patrulheiro) | 4 pp (sala 3, sem progressão do jogador) |
| 8 | Gerador de progressão (jogador e ghost evoluem igual); Palco não acumula; Coordenado 1x/s | 14 / 18 / 21 pp (salas 3 / 9 / 18) |
| 9 | Seis ajustes de escalonamento (tabela acima) | 11 / 18 / 22 pp |
| 10 | Flamejante (1 dano/s, máx. 5); Poção de Mana a 50%; teste de itens com 3 parties, troca e sala 9 evoluída | classes não medidas nesta rodada |
| 13 | Q-09 a Q-11 (fusão −13%, instrumentos +75%, Ladino/Mago/Patrulheiro/Paladino, Afiado) | 16 / 16 / 23 pp · lutas 19.4 / 14.9 / 11.6s |
| 12 | Q-07 (curva de HP, fusão x1.7), Q-08 (encantamentos), fusão −8% recarga, Tambor +2 | 12 / 17 / 26 pp · lutas 19.5 / 15.7 / 13.6s |
| 11 | Respostas Q-01 a Q-06 (HP por duelo, fusão x1.85, catalisadores somam, tetos, encantamentos, Bardo) | 14 / 16 / 21 pp · lutas 26.1 / 15.8 / 7.5s |
