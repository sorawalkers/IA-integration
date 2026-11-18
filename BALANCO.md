# OSR Battler — Relatório de Balanceamento

> Página viva: atualizada a cada teste ou mudança de regra.
> Markdown puro (para agentes): `https://osr.valiran.party/relatorio.md` · Página: `https://osr.valiran.party/`
> Última simulação completa (gerada por `npm run balance`): `https://osr.valiran.party/simulacao.md`
> Fonte no repositório: `docs/BALANCO.md` (branch `claude/awesome-fermi-2g5woc`). Regras completas: `CLAUDE.md`.

**Última atualização:** 2026-11-18 · Fase 1, passo 2 (HP 0.80 x 1.30^nível, 8 receitas, painel de metas).

> **Fase atual: construção de mecânicas.** O balanceamento fino está pausado até as mecânicas fecharem (bolsa de expansão,
> venda/troca, economia, receitas, emboscada PvE e o que mais for decidido — ver `PENDENCIAS.md`, perguntas Q-21 a Q-27).
> Nesta fase as simulações continuam rodando, mas só para pegar absurdos (classe acima de 70% ou abaixo de 25%, lutas com menos
> de 8s, item dominante). Os números das rodadas abaixo são **provisórios**: o espaço da mochila ainda é fixo e o gerador de
> builds ainda não vende nem troca itens.

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

## Fase 1, passo 2 — HP x1.30 por nível, 8 receitas mágicas, painel de metas (checagem de absurdos)

| | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| **Duração média da luta** | 20.9s | 13.6s | **7.8s** ⚠ |
| Guerreiro | Vang 40% | Vang 45% | Vang 54% |
| Paladino | Vang 39% | Vang 43% | Vang 52% |
| Bárbaro | Vang 38% | Vang 41% | Vang 50% |
| Bardo | Meio 31% | Meio 39% | Meio 48% |
| Ladino | Meio 48% | Meio 42% | Meio 40% |
| Patrulheiro | Ret 36% | Ret 31% | Ret 43% |
| Mago | Ret 33% | Meio 49% | Meio **70%** ⚠ |
| Alquimista | Ret 35% | Ret 43% | Ret 55% |
| **Diferença** | 17 pp | 18 pp | 29 pp |

**Painel de metas (Q-27):** classes na faixa 44–56%: 1/8 · 2/8 · 5/8; diferença 17 / 18 / 29pp; duração ❌ nas três salas.
Absurdos: **luta da sala 18 < 8s** e **Mago no limite (70%)** → **Q-34**.

**Receitas** (item de receita somado à party de referência, sala 9, item +1): Cajado do Arquimago +57.0 · Égide do Cruzado +54.3 ·
Lobo Alfa +41.0 · Machado Trovejante +39.7 · Língua de Fogo +35.3 · Presa de Víbora +30.3 · Elixir +24.3 · Harpa +23.7pp.
São fortes como esperado de um item épico; o teste **soma** o item sem tirar os 2 ingredientes, então superestima o ganho real.
Fica para a Fase 3 (medir receita contra os 2 ingredientes).

## Fase 1, passo 1 — nível, economia, mochila expansível e gerador realista (checagem de absurdos)

| Mecânica | Como ficou |
|---|---|
| Nível (Q-26) | XP 0/3/7/12/18/25/33/42/52/63 (Nv1–10); +1 XP por sala, +2/+1 por duelo; **HP da classe x1.25 por nível** (substitui o HP por duelo). O mesmo fator escala os efeitos de valor fixo |
| Economia (Q-22) | 20 PO iniciais; +4 PO por sala; duelo +8 / +6 PO; venda 50% do preço x cópias fundidas |
| Mochila (Q-21) | +2 casas na borda nos níveis 3, 6 e 9; Bolsa de Couro (+2 casas, 6 PO, ~15% por loja, sem limite) |
| Gerador (Q-23) | XP típico por sala (Nv2 na sala 3, Nv4 na 9, Nv6 na 18); casas extras dos níveis + 15% de bolsa por duelo; funde cópias e vende +0 sem afinidade quando enche |

| | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| **Duração média da luta** | **25.1s** ⚠ | 15.9s | **8.0s** ⚠ |
| Guerreiro | Vang 38% | Vang 45% | Vang 53% |
| Paladino | Vang 38% | Vang 42% | Vang **51%** (era 41) |
| Bárbaro | Vang 38% | Vang 41% | Vang 49% |
| Bardo | Meio 27% | Meio 36% | Meio 43% |
| Ladino | Meio 47% | Meio 42% | Meio 37% |
| Patrulheiro | Ret 36% | Ret 32% | Ret **44%** (era 38) |
| Mago | Ret 31% | Ret 50% | Meio **67%** ⚠ |
| Alquimista | Ret 38% | Ret 47% | Ret 52% |
| **Diferença** | 21 pp | 18 pp | 30 pp |

**Checagem de absurdos** (limites da Fase 1: classe > 70% ou < 25%, luta < 8s):
- ⚠ **Lutas da sala 18 com 8.0s** (no limite) e da sala 3 com 25.1s: efeito da troca do HP por duelo pelo HP por nível → **Q-32**.
- ⚠ **Mago 67%** na sala 18 (perto do limite de 70%): já registrado no Q-18 (pausado).
- Com mais espaço na mochila, **Paladino** (41 → 51%) e **Patrulheiro** (38 → 44%) subiram na sala 18, como suspeitado.
- Nada passou dos limites; nenhum ajuste de número foi feito.

## Rodada 15 — respostas Q-15, Q-16 e Q-17

| Mudança | Antes | Agora |
|---|---|---|
| Fator de profundidade (Q-15) | — | `depthFactor` = 1 + 0.10·d + 0.13·d² → 1.23 / 2.47 / 6.28 nas salas 3 / 9 / 18 |
| Veneno e Queimadura (Q-15a) | 1 dano/s por stack | 1 dano/s por stack **x fator de profundidade do alvo** |
| Escudos fixos (Q-15d) | relíquia do Paladino 6; Guerreiro +4 por golpe | **x fator de profundidade** (sala 18: 38 e 25) |
| Gerador de builds (Q-16) | itens sorteados sem olhar a classe | **60% dos itens entre os que a classe aproveita** (`AFFINITY` em `ghost.ts`) |
| Patrulheiro (Q-17) | — | mascote com comida/erva encostada **cura 2 HP x fator** do Patrulheiro a cada ataque (13 na sala 18) |

### Classes por sala (512 composições, 80 lutas cada)

| | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| **Duração média da luta** (meta 14–18s) | 18.8s | 14.9s | 13.0s |
| Guerreiro | Vang 44% | Vang 44% | Vang 45% (era 52) |
| Paladino | Vang 38% | Vang 35% | Vang 41% |
| Bárbaro | Vang 39% | Vang 37% | Vang 43% (era 50) |
| Bardo | Meio 31% | Meio 34% | **Vang** 41% (era Meio 49) |
| Ladino | Meio 48% | Meio 46% | Meio **41%** (era 35) |
| Patrulheiro | Ret 39% | Ret 33% | Ret 38% |
| Mago | Ret 38% | Meio 52% | Meio **68%** (era 59) |
| Alquimista | Ret 35% | Ret 42% | Ret 51% |
| **Diferença** | 17 pp | 19 pp | **31 pp** (era 24) |

- O **Ladino subiu** na sala 18 (35 → 41%) com o Veneno escalando.
- O **gerador com afinidade fortaleceu demais o Mago**: com 3.6 armas mágicas na mochila (era 2.6) ele causa 434 de dano/s vivo e
  64% do dano da party; as lutas dele acabam em 6.5s. Por tabela, as classes de frente caíram (Guerreiro 52 → 45%, Bárbaro 50 → 43%).
- **Paladino e Patrulheiro não mudaram** (41% e 38%), mesmo com o escudo do Paladino subindo de 222 para 1003 por luta.

### Diagnóstico da sala 18 (rodada 15)

| Classe | Vitória | Morre primeiro | Dano direto/s vivo | % do dano da party | Escudo/luta | Cura/luta |
|---|---|---|---|---|---|---|
| Mago (Meio) | 63% | 14% | **434** | **64%** | 6 | 16 |
| Alquimista (Ret) | 49% | 28% | 47 | 18% | 8 | **2251** |
| Guerreiro (Vang) | 46% | 36% | 108 | 31% | 14 | 814 |
| Paladino (Vang) | 43% | 28% | **54** | 20% | **1003** | 763 |
| Bárbaro (Vang) | 41% | 47% | 192 | 39% | 15 | 93 |
| Bardo (Meio) | 37% | 5% | 58 | 19% | 27 | 676 |
| Ladino (Meio) | 37% | 5% | 85 | 33% | 22 | 552 |
| Patrulheiro (Ret) | 32% | 20% | 190 | **50%** | 14 | 74* |

\* A cura do mascote alimentado não aparece nessa coluna (não gera evento no registro).
Mochilas: Mago 3.6 armas mágicas; Paladino ainda **1.0 arma** (o kit inicial já ocupa 6 das 11 casas da cruz e sobra pouco espaço);
Patrulheiro 2.6 mascotes, 1.5 arcos, 4.5 catalisadores.

### Encantamentos e fusão (sala 3)

A linha de base caiu para 25% (os ghosts da sala 3 agora têm itens com afinidade), então todos os deltas subiram:
Flamejante +40.7 · Armazenador +40.7 · Gélido +38.7 · Trovejante +37.7 · Afiado +31.0 · Mortal +27.7 · Defensor +27.0 ·
Veloz +25.0 · **Vorpal +19.3** · **Vampírico +17.7**.

Fusão (+1 contra 2 cópias no mesmo herói): Tambor +13.3 · Arco Curto +8.7 · Poção de Vida +2.3 · ... · Adaga −0.3 ·
Gema Bruta −3.7 · **Maça −6.0** · **Cajado de Aprendiz −7.7**.

→ Perguntas **Q-18** (Mago), **Q-19** (Paladino e Patrulheiro) e **Q-20** (resíduos de encantamentos e fusão).

## Rodada 14 — respostas Q-12, Q-13 e Q-14 + diagnóstico da sala 18

| Mudança | Antes | Agora |
|---|---|---|
| Instrumentos (Q-12) | todos os instrumentos do herói tocavam | **só um instrumento por herói toca** (o de maior aceleração); os outros ficam em silêncio |
| Teste de fusão (Q-12) | melhor herói para as 2 cópias e melhor herói para o +1 (podiam ser diferentes) | o +1 é testado **no mesmo herói** onde as 2 cópias renderam mais |
| Mago (Q-13) | Sobrecarga acima de 78% | **70%** |
| HP (Q-14) | x0.75·(1 + 0.10·d + 0.10·d²) | **x0.70·(1 + 0.10·d + 0.13·d²)** → x0.86 / x1.73 / x4.39 nas salas 3 / 9 / 18 |

> **Correção minha sobre o Q-12:** eu tinha escrito que as 2 cópias podiam ir para heróis diferentes. Conferindo o código,
> as 2 cópias já iam sempre para o **mesmo** herói. O que distorcia era o +1 poder ser medido em outro herói, e os 2 Tambores
> tocando juntos. Com as duas correções, a fusão ficou empatada ou melhor (tabela abaixo).

### Classes por sala (512 composições, 80 lutas cada)

| | Sala 3 | Sala 9 | Sala 18 |
|---|---|---|---|
| **Duração média da luta** (meta 14–18s) | **18.6s** (era 19.4) | **15.3s** ✅ | **13.3s** (era 11.6) |
| Guerreiro | Vang 41% | Vang 45% | Vang 52% |
| Paladino | Vang 38% | Vang 38% | Vang 40% |
| Bárbaro | Vang 38% | Vang 41% | Vang 50% |
| Bardo | Meio 34% | Meio 44% | Meio 49% (era 54: 1 instrumento só) |
| Ladino | Meio 46% | Meio 38% | Meio 35% |
| Patrulheiro | Ret 31% | Ret 32% | Ret 39% |
| Mago | Ret 37% | Ret 47% | Meio 59% |
| Alquimista | Ret 35% | Ret 49% | Ret 56% |
| **Diferença** | 16 pp | 17 pp | **24 pp** |

### Encantamentos (sala 3; meta +20 a +40pp)

Armazenador +38.7 · Flamejante +33.0 · Gélido +32.7 · Trovejante +32.7 · Afiado +25.7 · Defensor +24.7 · Vorpal +22.7 ·
Veloz +22.0 · Mortal +20.7 · Vampírico +19.7 → **todos na faixa** (Vampírico no limite, dentro do erro de ±2.4).

### Fusão: +1 contra 2 cópias no mesmo herói (sala 3)

Tambor **+9.0** (era −14.7) · Poção de Vida +4.7 · Cajado +4.0 · Arco Curto +3.7 · Espada Curta +2.7 · Amuleto +1.3 · Pedra +0.7 ·
Adaga −0.3 · Gema Bruta −2.0 · Maça −2.7 · armaduras e Poção de Mana 0.0. Os negativos estão dentro do erro da medição (±2.2pp)
→ **fundir nunca fica pior que 2 cópias.**

### Diagnóstico da sala 18 (pedido no Q-13) — `scripts/diagnostico.ts`

Herói da classe na melhor posição, outros 2 sorteados, 300 lutas:

| Classe | Vitória | Tempo vivo | Morre primeiro | Dano direto/s vivo | % do dano da party | Escudo/luta | Cura/luta |
|---|---|---|---|---|---|---|---|
| Mago (Meio) | 60% | 67% da luta | 21% | **326** | 58% | 6 | 42 |
| Alquimista (Ret) | 50% | 83% | 26% | 58 | 21% | 16 | **1796** |
| Bárbaro (Vang) | 48% | 64% | 39% | 179 | 41% | 10 | 242 |
| Guerreiro (Vang) | 45% | 72% | 34% | 97 | 30% | 13 | 941 |
| Bardo (Meio) | 42% | 80% | 3% | 88 | 25% | 12 | 414 |
| Paladino (Vang) | 42% | 73% | 33% | **53** | 19% | 222 | 849 |
| Patrulheiro (Ret) | 34% | 76% | 21% | 165 | 44% | 16 | **163** |
| Ladino (Meio) | 31% | **78%** | **4%** | **75** | 33% | 12 | 581 |

Mochila montada pelo gerador (média de itens): Paladino **1.0 arma** e 3.2 catalisadores; Ladino 2.6 armas corpo a corpo;
Patrulheiro 2.2 mascotes, 1.2 armas à distância e 4.2 catalisadores; Mago 2.6 armas mágicas.

**Leitura:**
1. **Ladino não morre (4% morre primeiro) mas causa pouco dano direto** (75/s). Ele é o que mais aplica Veneno (18.7 golpes
   com DOT por luta), mas **Veneno e Queimadura não escalam**: 1 dano/s por stack contra heróis com HP x4.39 na sala 18
   (na sala 3 o HP é x0.86). O Veneno vale ~5x menos no fim da run.
2. **Paladino causa pouco dano** (53/s) porque o gerador dá a ele só 1 arma em média; o escudo dele (222 por luta) é pequeno perto
   de ~650 de HP. O escudo da relíquia (6) também não escala com a profundidade.
3. **Patrulheiro causa muito dano** (165/s, 44% da party) mas perde: a party dele quase não tem cura (163 por luta, contra 941 do
   Guerreiro e 1796 do Alquimista) e as lutas acabam rápido (10.9s).
4. O gerador `progressParty` sorteia itens sem olhar a classe (só respeita os exclusivos).

→ Perguntas **Q-15** (efeitos que não escalam), **Q-16** (gerador) e **Q-17** (Patrulheiro).

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
| F1.2 | HP 0.80 x 1.30^nível (Q-32), 8 receitas (Q-29), painel de metas (Q-27) | 17 / 18 / 29 pp · lutas 20.9 / 13.6 / 7.8s |
| F1.1 | Nível/XP (HP x1.25 por nível), economia, mochila expansível, gerador funde/vende | 21 / 18 / 30 pp · lutas 25.1 / 15.9 / 8.0s |
| — | **Pausa:** início da fase de construção de mecânicas; Q-18 a Q-20 pausadas | — |
| 15 | Q-15 a Q-17 (fator de profundidade, gerador com afinidade, cura do mascote) | 17 / 19 / 31 pp · lutas 18.8 / 14.9 / 13.0s |
| 14 | Q-12 a Q-14 (1 instrumento por herói, fusão no mesmo herói, Sobrecarga 70%, HP x0.70 e 0.13·d²) | 16 / 17 / 24 pp · lutas 18.6 / 15.3 / 13.3s |
| 13 | Q-09 a Q-11 (fusão −13%, instrumentos +75%, Ladino/Mago/Patrulheiro/Paladino, Afiado) | 16 / 16 / 23 pp · lutas 19.4 / 14.9 / 11.6s |
| 12 | Q-07 (curva de HP, fusão x1.7), Q-08 (encantamentos), fusão −8% recarga, Tambor +2 | 12 / 17 / 26 pp · lutas 19.5 / 15.7 / 13.6s |
| 11 | Respostas Q-01 a Q-06 (HP por duelo, fusão x1.85, catalisadores somam, tetos, encantamentos, Bardo) | 14 / 16 / 21 pp · lutas 26.1 / 15.8 / 7.5s |
