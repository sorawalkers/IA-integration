# OSR Battler — Pendências e dúvidas em aberto

> Lista viva: atualizada a cada teste e a cada mudança. Cada item tem um código (`P-xx`) para referência.
> Resultados dos testes: `BALANCO.md` (resumo) e `relatorio.md` (última simulação). Regras: `CLAUDE.md` do repo do jogo.
> Perguntas para o agente de análise: seção 0 (`Q-xx`).

**Última atualização:** 2026-11-18 · Fase 1, passo 1 (nível/XP, economia, mochila expansível e gerador realista implementados; Q-21 a Q-26 respondidas).

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

**Roteiro da Fase 1** (✅ feito · ⏳ em andamento · ⏸ esperando dados):
✅ Nível e XP (HP x1.25 por nível) · ✅ Economia e venda · ✅ Mochila expansível (níveis 3/6/9 + Bolsa de Couro) ·
✅ Gerador realista (casas extras, funde e vende quando enche) · ✅ Botão [FUNDIR] entre itens idênticos encostados (o arraste sobre o item igual continua valendo) ·
⏸ Feats (Q-28) · ⏸ 8 receitas (Q-29) · ⏸ 12 eventos (Q-30) · ⏸ Emboscada PvE (Q-31).

**Pedido ao agente de análise:** nesta fase, responda as perguntas de mecânica (Q-21 a Q-27) e **não proponha ajustes finos
de números**. As perguntas de balanceamento Q-18 a Q-20 ficam pausadas (o resultado delas muda com bolsa, venda e economia).

## 0. Perguntas para o agente de análise

> **Como funciona:** o agente de análise lê este arquivo no repositório público e responde ao usuário, que repassa a
> resposta ao Claude Code (que roda os testes). A resposta é registrada aqui com a data, a decisão é aplicada e o
> efeito medido entra em `BALANCO.md`. Responda citando o código (`Q-xx`).

| Código | Ref. | Pergunta | Dados para decidir | Opções |
|---|---|---|---|---|
| Q-28 | Q-26 | **Tabela de Feats (talentos) — não chegou até mim** | A decisão do Q-26 cita "a tabela de 4 Feats por classe + 6 genéricos" para o modal de subida de nível (3 opções: 2 da classe + 1 genérico), mas a tabela não veio na mensagem. O nível já está implementado (XP, HP, casas extras); o modal está esperando a tabela | Mandar a tabela: para cada um dos 38 Feats (8 classes x 4 + 6 genéricos), nome, efeito e números. Se preferir, eu escrevo uma proposta e vocês aprovam |
| Q-29 | Q-24 | **Receitas mágicas: ingredientes e efeitos** | Recebi só os nomes das 8 receitas: Língua de Fogo, Presa de Víbora, Égide do Cruzado, Cajado do Arquimago, Elixir da Restauração, Harpa da Fortuna, Machado Trovejante, Lobo Alfa Espiritual. O exemplo antigo do `CLAUDE.md` é Espada Longa + Rubi → Língua de Fogo | Para cada receita: os 2 ingredientes (itens do catálogo atual), tamanho do item novo, efeito e números, se é exclusivo de classe. O encantamento dos ingredientes passa para o resultado (já decidido). Se um ingrediente estiver fundido (+1/+2), o resultado herda o nível? |
| Q-30 | Q-25 | **Os 12 eventos: lista e efeitos** | Recebi 9 nomes novos: Mestre de Armas, Alquimista Louco, Santuário da Purificação, Baú Trancado, Forja Rúnica, Feira 2-por-1, Emboscada de Elite, Fonte de Mana, Bibliotecário Fantasma. Hoje existem 4: Mercador, Fogueira & Bigorna, Corredor Armadilhado, Emboscada (2 variações) | Os 12 nomes finais (os 4 atuais entram na conta?) e, para cada um: o que faz, risco, recompensa, custo em PO, se tem combate. Ex.: o que o Santuário "purifica"? o Baú Trancado precisa de Gazuas? |
| Q-31 | Q-25 | **Monstros da Emboscada PvE** | Decidido: combate real contra monstros pré-montados escalando com a profundidade; vitória +8 PO e escolha de 1 entre 3 itens; derrota +3 PO, sem perder tocha nem ouro. Falta definir os monstros | Opção (a): monstro = party de 3 "heróis-monstro" com mochila fixa (ex.: Cubo Gelatinoso, Esqueletos, Goblins), HP x fator de nível · (b) 1 monstro grande com vários ataques · (c) usar o gerador de builds com 80% da força de um ghost da mesma sala. E a Emboscada de Elite: mais forte com recompensa maior? Dá +2 XP como a emboscada normal? |
| Q-32 | Q-26 | **HP por nível: os números do enunciado não batem com "+25% cumulativo", e as lutas saíram do ritmo** | Implementei x1.25 por nível composto: Nv6 = **305%**, Nv10 = **745%** (o enunciado diz ~290% e 640%; isso daria x1.23 por nível). Com XP típico (1 por sala + 1.5 por duelo) o herói está no Nv2 na sala 3, Nv4 na 9 e Nv6 na 18. Duração das lutas: **25.1s / 15.9s / 8.0s** (antes 18.8 / 14.9 / 13.0; meta 14–18s). Na sala 3 o HP subiu (x1.25 contra x0.86 antes) e na sala 18 caiu (x3.05 contra x4.39) | (a) manter x1.25 · (b) x1.23 (bate com 290% / 640%) · (c) Nv1 começa em 80% do HP da classe e x1.30 por nível (estimativa 20 / 16 / 13s, a medir) · (d) aceitar agora e ajustar só na Fase 2 |
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
- **Q-21** · 2026-11-18 · mochila híbrida: +2 casas na borda nos níveis 3, 6 e 9 (contam para adjacência e Elos) + Bolsa de Couro (+2 casas, 6 PO, rara, ~15% por loja, sem limite) · implementado
- **Q-22** · 2026-11-18 · ouro inicial 20; +4 PO por sala; duelo +8 PO vitória / +6 PO derrota; venda = 50% do preço base x cópias fundidas (sem contar encantamento) · implementado
- **Q-23** · 2026-11-18 · gerador funde automaticamente e vende itens +0 sem afinidade quando a mochila enche · implementado
- **Q-24** · 2026-11-18 · fusão manual com botão [FUNDIR] entre itens idênticos (ou ingredientes de receita) encostados; 8 receitas mágicas que herdam o encantamento · botão [FUNDIR] implementado; **receitas pendentes** (faltam os dados, Q-29)
- **Q-25** · 2026-11-18 · Emboscada com combate real (vitória +8 PO e 1 de 3 itens; derrota +3 PO, sem perder tocha nem ouro); 12 eventos estilo The Bazaar · **pendente**: faltam os monstros (Q-31) e os efeitos dos eventos (Q-30)
- **Q-26** · 2026-11-18 · nível 1 a 10 (XP 0, 3, 7, 12, 18, 25, 33, 42, 52, 63; +1 XP por sala, +2 vitória / +1 derrota em duelo ou emboscada), HP base +25% por nível no lugar do HP por duelo; Feats na subida de nível · nível/XP/HP implementados; **Feats pendentes** (falta a tabela, Q-28; números do HP em Q-32)
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
| P-20 | ✅ | **Bolsa de expansão** — implementada (Q-21). de mochila (item fora da loja até existir a mecânica). Resolveria o Lobo Cinzento (P-05) e o Alaúde (P-06) |
| P-21 | 🔴 | **Receitas mágicas** — faltam ingredientes e efeitos (**Q-29**). (Fase 2): combinações de itens encostados viram itens novos |
| P-22 | ⚪ | **PvP assíncrono real**: backend para salvar builds de jogadores; hoje o ghost é gerado localmente |
| P-23 | 🔴 | **Emboscada PvE** — faltam os monstros (**Q-31**) e os eventos (**Q-30**). com combate de verdade (hoje só dá ouro) |
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
