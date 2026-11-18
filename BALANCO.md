# OSR Battler — Relatório de Balanceamento

> Página viva: atualizada a cada teste ou mudança de regra.
> Markdown puro (para agentes): `https://osr.valiran.party/relatorio.md` · Página: `https://osr.valiran.party/`
> Última simulação completa (gerada por `npm run balance`): `https://osr.valiran.party/simulacao.md`
> Fonte no repositório: `docs/BALANCO.md` (branch `claude/awesome-fermi-2g5woc`). Regras completas: `CLAUDE.md`.

**Última atualização:** 2026-11-18 · Rodada 11 (respostas Q-01 a Q-06 do agente de análise aplicadas).

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
| 11 | Respostas Q-01 a Q-06 (HP por duelo, fusão x1.85, catalisadores somam, tetos, encantamentos, Bardo) | 14 / 16 / 21 pp · lutas 26.1 / 15.8 / 7.5s |
