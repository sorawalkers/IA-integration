# OSR Battler — Pendências e dúvidas em aberto

> Lista viva: atualizada a cada teste e a cada mudança. Cada item tem um código (`P-xx`) para referência.
> Resultados dos testes: `BALANCO.md` (resumo) e `relatorio.md` (última simulação). Regras: `CLAUDE.md` do repo do jogo.
> Perguntas para o agente de análise: seção 0 (`Q-xx`).

**Última atualização:** 2026-11-18 · início da fase de construção de mecânicas (Q-18 a Q-20 pausadas; Q-21 a Q-27 abertas).

Legenda de status: 🔴 aguardando decisão · 🟡 proposta pronta, falta aplicar/testar · 🔵 em observação · ⚪ fora do escopo atual

## Fase atual: construção de mecânicas (decisão do usuário, 2026-11-18)

**Motivo:** cada ajuste de número estava criando dois problemas novos, e cada mecânica grande nova (bolsa, venda, receitas…)
muda o valor de tudo o que já existe. Por isso o **balanceamento fino fica para depois que as mecânicas estiverem fechadas**.

1. **Fase 1 — fechar as mecânicas** (agora): implementar o que falta (perguntas Q-21 a Q-26). Depois de cada mecânica nova,
   o painel roda só para pegar **absurdos**: classe com mais de 70% ou menos de 25% de vitória, lutas com menos de 8s, um item
   que domina tudo. Diferenças de 3–5pp **não** são corrigidas nesta fase.
2. **Fase 2 — congelar o conteúdo e calibrar a régua:** gerador de builds realista (bolsas, venda/troca, economia) e congelado;
   metas por papel (Q-27).
3. **Fase 3 — balanceamento fino:** uma mudança por vez, cada uma medida sozinha contra o painel inteiro (antes/depois). Se uma
   mudança tirar da meta algo que estava dentro, ela não entra e volta como pergunta. Diferenças dentro do erro (±2–3pp) não contam.

**Pedido ao agente de análise:** nesta fase, responda as perguntas de mecânica (Q-21 a Q-27) e **não proponha ajustes finos
de números**. As perguntas de balanceamento Q-18 a Q-20 ficam pausadas (o resultado delas muda com bolsa, venda e economia).

## 0. Perguntas para o agente de análise

> **Como funciona:** o agente de análise lê este arquivo no repositório público e responde ao usuário, que repassa a
> resposta ao Claude Code (que roda os testes). A resposta é registrada aqui com a data, a decisão é aplicada e o
> efeito medido entra em `BALANCO.md`. Responda citando o código (`Q-xx`).

| Código | Ref. | Pergunta | Dados para decidir | Opções |
|---|---|---|---|---|
| Q-21 | P-20 | **Bolsa de Expansão: como funciona?** | Hoje a mochila é fixa e o item que não cabe é descartado pelo gerador. Ocupação média na sala 18 (casas usadas / total): Guerreiro 13/16 · Paladino **9.5/11** · Bárbaro 12/15 · Bardo 11/16 · Ladino 11/14 · Patrulheiro **12/14** · Mago 13/15 · Alquimista 10/12. Paladino (cruz de 11 casas, kit inicial ocupa 6) fica com ~1 arma; o Lobo (2x2) quase nunca cabe no Patrulheiro | Tamanho: (a) +1 linha na mochila · (b) bolsa como item (2x2) que vira 4 casas novas encostadas · (c) +2 casas escolhidas pelo jogador. Preço/onde: Mercador, 5–8 PO. Limite por herói: 1 · 2 · sem limite. As casas da bolsa contam para adjacência? Para Elos Dourados? |
| Q-22 | — | **Economia da run: quanto ouro o jogador ganha e gasta?** | Hoje: começa com 20 PO; só a Emboscada dá ouro (+12); a Armadilha tira 3 (e dá 1 item); duelo **não dá ouro** (nem vitória, nem derrota); preços 2–12 PO; rolar a loja 2 PO; vender devolve parte do preço (`sellValue`). O gerador de builds chuta "2 itens por duelo" sem ouro | (a) ouro fixo por sala (ex.: 5 PO) + duelo (ex.: 8 PO vitória / 6 PO derrota, para não virar bola de neve) · (b) juros (+1 PO a cada 10 guardados, máx. 5) · (c) só eventos dão ouro. Também: quanto vale vender (50% do preço?) e itens fundidos valem mais na venda? |
| Q-23 | — | **Venda e troca no gerador de builds** | A venda já existe na interface (arrastar para a área de venda), mas o gerador ignora: quando o item novo não cabe, ele é jogado fora. Um jogador real vende o item mais fraco e põe o novo. Isso afeta o resultado das classes de mochila pequena (Paladino, Patrulheiro) | (a) gerador troca o item que menos contribui (mede o ganho antes/depois) · (b) troca por regra simples (vende sempre o item +0 mais barato) · (c) gerador funde cópias iguais automaticamente quando dá (jogador real faria) |
| Q-24 | P-21 | **Receitas mágicas: entram nesta versão?** | Previsto no `CLAUDE.md` (Fase 2): itens encostados viram item novo ao avançar de sala (ex.: Espada Longa + Rubi → Língua de Fogo). Nada implementado | Escopo: (a) sim, 6–10 receitas na primeira versão · (b) adiar para depois do lançamento. Gatilho: (c) automático ao avançar de sala · (d) evento próprio (ex.: Altar/Alquimia) · (e) o jogador escolhe na Fogueira & Bigorna. Os ingredientes somem? A receita dá item exclusivo de classe? |
| Q-25 | P-23 | **Emboscada com combate de verdade (PvE)** | Hoje as 2 emboscadas ("Cubo Gelatinoso", "Esqueletos") só dão +12 PO, sem luta. Os eventos atuais são 4: Mercador, Fogueira & Bigorna, Corredor Armadilhado, Emboscada | (a) luta contra monstros pré-montados (um por emboscada), escalando com a sala · (b) derrota custa HP para o próximo duelo, ouro, ou uma tocha? · (c) recompensa: ouro, item, escolha entre 3 itens. Quer outros tipos de evento (Altar, Santuário, Tesouro, NPC)? |
| Q-26 | — | **Que outras mecânicas e conteúdos estão planejados?** | Conteúdo atual: 8 classes, 33 itens (21 básicos, 12 avançados; 10 exclusivos de classe), 10 encantamentos, 4 tipos de evento, fusão até +3, 3 posições. O usuário pediu a lista completa antes de balancear | Lista aberta — incluir tudo, mesmo só ideia: classes novas? mais itens por categoria? raridades/itens lendários? chefes? habilidades ativas? mascotes novos? eventos? itens que mudam com a posição? Para cada um: entra antes ou depois do balanceamento fino? |
| Q-27 | P-03 | **Critério final de "balanceado" (para a Fase 2)** | Até aqui todas as classes foram julgadas só por vitória; o Paladino foi apontado como fraco por causar pouco dano, mas tanque não precisa causar dano | (a) faixa de vitória por classe na melhor posição: 44–56% nas salas 3, 9 e 18 · (b) tanques julgados também por dano absorvido, escudo dado e aliados vivos no fim · (c) duração 14–18s; encantamentos +20 a +40pp; fusão ≥ 2 cópias · (d) a diferença entre a melhor e a pior classe ≤ 12pp |

**Pausadas até o fim da fase de mecânicas** (o resultado muda com bolsa, venda e economia):

| Código | Ref. | Pergunta | Dados para decidir | Opções |
|---|---|---|---|---|
| Q-18 | P-03 | ⏸ **Com o gerador com afinidade, o Mago domina a sala 18** | Rodada 15, melhor posição (salas 3 / 9 / 18): Mago 38 / 52 / **68%** (Meio nas salas 9 e 18). Diagnóstico da sala 18: 434 de dano direto/s vivo (o 2º é o Bárbaro com 192), **64% do dano da party**, lutas de 6.5s (média geral 13s). Mochila: 3.6 armas mágicas (era 2.6). No Meio, os itens que não são corpo a corpo recarregam 15% mais rápido; a Sobrecarga dispara tomos 2x acima de 70% da mana; `magic_aoe` acerta todos com 60% do dano. Diferença entre classes na sala 18: 24 → **31pp** | (a) Sobrecarga só no **primeiro** tomo que disparar a cada 3s (hoje vale para todos) · (b) `magic_aoe` 60% → 45% · (c) o bônus do Meio (+15%) não vale para tomos · (d) afinidade do Mago 60% → 40% (só ele) |
| Q-19 | P-03 | ⏸ **Paladino e Patrulheiro não respondem aos buffs** | Sala 18 (rodada 14 → 15): Paladino 40 → 41%, Patrulheiro 39 → 38%. **Paladino:** escudo/luta subiu 222 → 1003 com o fator, mas o dano continua 54/s; a mochila (cruz de 11 casas) já começa com 6 itens, então o gerador consegue pôr só ~1 arma. **Patrulheiro:** é quem mais causa dano depois do Mago (190/s, **50% do dano da party**), mas vence 32%; morre primeiro em 20% das lutas e a party dele cura pouco | Paladino: (a) kit inicial menor (tirar Pedra de Amolar e Gibão; abre 3 casas) · (b) Égide da Fé também dá +10% de dano às armas por armadura encostada. Patrulheiro: (c) HP 90 → 110 · (d) mascote alimentado também dá 3 de escudo (x fator) ao Patrulheiro |
| Q-20 | P-04 / P-31 | ⏸ **Resíduos depois da afinidade** | A linha de base da sala 3 caiu de 30% para 25% (ghosts mais fortes), e todos os deltas de encantamento subiram: Flamejante e Armazenador +40.7 (no teto), Vorpal **+19.3** e Vampírico **+17.7** (abaixo da faixa). Fusão no mesmo herói: Maça +1 **−6.0**, Cajado de Aprendiz +1 **−7.7** (o Cajado dá mana ao Mago por ativação: 2 cópias = 2 ativações; o +1 dá 1.5x de mana com 13% menos recarga ≈ 1.72x). Erro da medição ±2.2 a ±2.8pp | (a) Vorpal 12% → 14% e Vampírico 25% → 30% · (b) mana do Cajado por ativação x1.75 por nível de fusão (em vez de +50%) · (c) esperar a próxima rodada: a linha de base vai mudar de novo com o Q-18 |

### Respostas recebidas

Formato: `Q-xx · data · resposta resumida · decisão aplicada (rodada)`.

- **Q-01** · 2026-11-18 · (c) combinar brando: HP base x(1 + 0.25 por duelo; ajustado pelo usuário para duelo **jogado**, não vencido) e fusão de armas x1.85; meta 14–18s · aplicado na rodada 11 → lutas 26.1 / 15.8 / 7.5s, meta não atingida nas salas 3 e 18 (ver Q-07)
- **Q-02** · 2026-11-18 · (b) mesmo tipo soma, tipos diferentes multiplicam · aplicado na rodada 11
- **Q-03** · 2026-11-18 · Veneno máx. 10; dano crítico excedente máx. +60% · aplicado na rodada 11
- **Q-04** · 2026-11-18 · faixa +20 a +40pp; Armazenador 25 de mana, Veloz −20%, Flamejante máx. 4; Mortal x3, Afiado +25%, Trovejante 25% · aplicado na rodada 11 → 3 de 10 na faixa (ver Q-08)
- **Q-05** · 2026-11-18 · (a) duas colunas, Com e Sem Ladino · aplicado na rodada 11
- **Q-06** · 2026-11-18 · P-15, P-16 e P-18 confirmados; P-17 corrigido: Bardo com 1 Tambor + Adaga + Poção · aplicado na rodada 11
- **Q-07** · 2026-11-18 · (a) curva quadrática: HP x0.75·(1 + 10%·duelos + 10%·duelos²), fusão de armas x1.7 · aplicado na rodada 12 → 19.5 / 15.7 / 13.6s
- **Q-08** · 2026-11-18 · proposta aprovada (Armazenador 20, Veloz −22%, Mortal +10% de crítico, Afiado +30%, Vampírico 25%, Vorpal 12%) + Trovejante com +20% de dano · aplicado na rodada 12 → 9 de 10 na faixa (Afiado fora: ver Q-11)
- **Observação (Bardo na sala 3)** · 2026-11-18 · Tambor +0 mais forte no início · aplicado na rodada 12: cada toque dá +2 de dano no próximo golpe de cada aliado (não acumula, não escala) → Bardo 28% → 38% na sala 3
- **Observação (fusão vs 2 cópias)** · 2026-11-18 · armas fundidas com −8% de recarga por nível · aplicado na rodada 12 → Adaga e Tambor ainda perdem (ver Q-09)
- **Q-09** · 2026-11-18 · armas −13% de recarga por nível; instrumentos +75% por nível; inspiração do Tambor +2/+3/+4/+5 · aplicado na rodada 13 → Adaga e Tambor ainda perdem (ver Q-12)
- **Q-10** · 2026-11-18 · Ladino (Veneno 15, 3 por crítico, excedente +80%), Mago (Sobrecarga 78%), Patrulheiro (0.6s), Paladino (relíquia 6) · aplicado na rodada 13 → sala 18 quase não mudou (ver Q-13)
- **Q-11** · 2026-11-18 · (c) Afiado: +30% de crítico e cada crítico adianta 0.3s a recarga da arma · aplicado na rodada 13 → +23.3pp ✅
- **P-32 / P-33** · 2026-11-18 · confirmadas (Trovejante +20% de dano; Tambor +2 no próximo golpe, escalando com a fusão)
- **Q-12** · 2026-11-18 · (a) comparar no mesmo herói + (b) só 1 instrumento por herói toca · aplicado na rodada 14 → Tambor +9.0, fusão empatada ou melhor em todos (negativos dentro do erro). Correção: as 2 cópias já iam para o mesmo herói; o +1 é que podia ir para outro
- **Q-13** · 2026-11-18 · (c) Sobrecarga 70% + (a) diagnóstico da sala 18 · aplicado na rodada 14 → diagnóstico em `relatorio.md`, novas perguntas Q-15 a Q-17
- **Q-14** · 2026-11-18 · (c) HP x0.70 e 0.13·d² · aplicado na rodada 14 → 18.6 / 15.3 / 13.3s
- **Q-15** · 2026-11-18 · (a) DOT x fator de profundidade + (d) escudo da relíquia e do Guerreiro x fator · aplicado na rodada 15 → Ladino 35 → 41% na sala 18
- **Q-16** · 2026-11-18 · (a) gerador com 60% de afinidade de classe · aplicado na rodada 15 → Mago 59 → 68% na sala 18 (ver Q-18)
- **Q-17** · 2026-11-18 · (c) mascote alimentado cura o Patrulheiro (2 HP x fator) + (d) esperar o Q-16 · aplicado na rodada 15 → Patrulheiro 39 → 38% (ver Q-19)
- **Observação (P-05)** · 2026-11-18 · o Lobo Cinzento cai por precisar tirar o Arco Longo; se resolve com as Bolsas de expansão (P-20) ou com 2 slots extras no gerador das salas 9/18 · registrado em P-05/P-20

## 1. Balanceamento — problemas abertos

| Código | Status | Questão | Dados | Proposta / próximo passo |
|---|---|---|---|---|
| P-01 | 🔵 | Ritmo das lutas | Rodada 14: **18.6 / 15.3 / 13.3s** (salas 3 / 9 / 18); meta 14–18s; as pontas estão a <1s da faixa | Remedir a cada rodada |
| P-03 | ⚪ | Classes por sala | Rodada 15: diferença **17 / 19 / 31 pp**. Sala 18: Mago 68% (forte); Patrulheiro 38%, Paladino 41%, Bardo 41%, Ladino 41% (fracos) | **Pausado** até o fim da fase de mecânicas (Q-18, Q-19 pausadas) |
| P-05 | 🔵 | Itens avançados que não compensam na sala 9 | Rodada 11: Lobo Cinzento +2.0 (−4.3 com Ladino; só cabe tirando o Arco Longo), Gema de Mana +2.7, Rubi Ígneo +10.0 | Lobo: resolvido pelas Bolsas (P-20) ou 2 slots extras no gerador (observação do agente). Remedir depois de Q-07 |
| P-06 | 🔵 | Alaúde dos Ventos só cabe trocando um item | O kit inicial do Bardo não deixa espaço 2x2 livre | Aceitável enquanto não existir a Bolsa de expansão (P-20); rever com ela |

## 2. Ferramenta de teste (medição)

| Código | Status | Questão | Proposta |
|---|---|---|---|
| P-11 | 🔵 | Ghosts são gerados localmente (70% das vezes com a classe sugerida para cada posição) | Placeholder até existir o backend de PvP (P-22); os números absolutos dependem dessa mistura |

## 3. Interpretações feitas sem definição exata (validar)

_Nenhuma pendente._ P-15 a P-18 confirmadas no Q-06 (P-17 corrigido).

## 4. Funcionalidades não implementadas

| Código | Status | Funcionalidade |
|---|---|---|
| P-20 | 🔴 | **Bolsa de expansão** — ver **Q-21**. de mochila (item fora da loja até existir a mecânica). Resolveria o Lobo Cinzento (P-05) e o Alaúde (P-06) |
| P-21 | 🔴 | **Receitas mágicas** — ver **Q-24**. (Fase 2): combinações de itens encostados viram itens novos |
| P-22 | ⚪ | **PvP assíncrono real**: backend para salvar builds de jogadores; hoje o ghost é gerado localmente |
| P-23 | 🔴 | **Emboscada PvE** — ver **Q-25**. com combate de verdade (hoje só dá ouro) |
| P-24 | ⚪ | **Telas de fim de run** (vitória com 10 duelos / derrota sem tochas); hoje volta para a Taverna |
| P-25 | ⚪ | **Arte final** (retratos, ilustrações de eventos, ícones). Os ícones atuais são de game-icons.net (CC BY 3.0): se o jogo for publicado, os créditos precisam aparecer no jogo |
| P-26 | ⚪ | Ao arrastar, o "fantasma" do item usa o tamanho de célula da origem, não o da mochila de destino (só visual) |

## 5. Ações do usuário

| Código | Status | Ação |
|---|---|---|
| P-30 | 🔴 | Search Console: clicar em **Verificar**, enviar o sitemap `https://osr.valiran.party/sitemap.xml` e solicitar indexação das 4 URLs |

## Resolvidos recentemente

| Código | Resolvido em | Questão | Solução |
|---|---|---|---|
| R-14 | Rodada 15 | Veneno/Queimadura e escudos fixos não escalavam com o HP (Q-15) | Fator de profundidade 1.23 / 2.47 / 6.28 |
| R-15 | Rodada 15 | Gerador sorteava itens sem olhar a classe (Q-16) | 60% dos itens com afinidade de classe |
| R-12 | Rodada 14 | Encantamentos desiguais (P-04) | 10 de 10 na faixa +20 a +40pp (Vampírico +19.7, no limite) |
| R-13 | Rodada 14 | Fundir pior que 2 cópias (P-31) | Teste no mesmo herói + 1 instrumento por herói: fusão empatada ou melhor |
| R-10 | Rodada 13 | Afiado abaixo da faixa (Q-11) | +30% de crítico e cada crítico adianta 0.3s → +23.3pp |
| R-11 | Rodada 13 | Interpretações P-32 (Trovejante) e P-33 (Tambor) | Confirmadas; inspiração escala com a fusão |
| R-09 | Rodada 11 | HP por duelo vencido viraria bola de neve | HP cresce por duelo **jogado** (vitória ou derrota); herói recrutado entra com os duelos do grupo |
| R-05 | Rodada 11 | Escalonamento sem teto (P-02) | Catalisadores do mesmo tipo somam; Veneno máx. 10; crítico excedente máx. +60% (Q-02, Q-03) |
| R-06 | Rodada 11 | Combo do Ladino distorcia o teste de itens (P-10) | Colunas Com e Sem Ladino no relatório (Q-05) |
| R-07 | Rodada 11 | Interpretações P-15 a P-18 | Confirmadas; Bardo com 1 Tambor + Adaga + Poção (Q-06) |
| R-08 | Rodada 11 | Referência dos testes de itens mais fraca que os ghosts | Party de referência com os mesmos duelos (HP) que os ghosts da sala |
| R-01 | Rodada 10 | Flamejante quebrado (97.7%) | Queimadura 1 dano/s por stack, máx. 5 → 79.7% |
| R-02 | Rodada 10 | Aljava, Ração e Poção de Mana com +0.0pp | Era o teste (party sem arcos/mascotes); itens agora testados em 3 parties. Poção de Mana dispara abaixo de 50% |
| R-03 | Rodada 10 | Alaúde "sem espaço" e avançados ~0% na sala 9 | Teste troca o item mais dispensável; avançados medidos com party de referência evoluída e item +1 |
| R-04 | Rodada 8 | Bardo e Patrulheiro explodindo no meio/fim da run | Palco não acumula instrumentos; Ataque Coordenado no máximo 1x/s |
