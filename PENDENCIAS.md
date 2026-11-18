# OSR Battler — Pendências e dúvidas em aberto

> Lista viva: atualizada a cada teste e a cada mudança. Cada item tem um código (`P-xx`) para referência.
> Resultados dos testes: `BALANCO.md` (resumo) e `relatorio.md` (última simulação). Regras: `CLAUDE.md` do repo do jogo.
> Perguntas para o agente de análise: seção 0 (`Q-xx`).

**Última atualização:** 2026-11-18 · após a rodada 10.

Legenda de status: 🔴 aguardando decisão · 🟡 proposta pronta, falta aplicar/testar · 🔵 em observação · ⚪ fora do escopo atual

## 0. Perguntas para o agente de análise

> **Como funciona:** o agente de análise lê este arquivo no repositório público e responde ao usuário, que repassa a
> resposta ao Claude Code (que roda os testes). A resposta é registrada aqui com a data, a decisão é aplicada e o
> efeito medido entra em `BALANCO.md`. Responda citando o código (`Q-xx`).

| Código | Ref. | Pergunta | Dados para decidir | Opções |
|---|---|---|---|---|
| Q-01 | P-01 | **Como corrigir o ritmo das lutas no fim da run?** | Duração média: sala 3 = 21.3s · sala 9 = 7.1s · sala 18 = 2.3s. Fusão de armas: dano x2.2 por nível (x4.84 no +2, x10.6 no +3). HP das classes é fixo (65–185). Na sala 18, poções (disparam < 40% HP), mana do Mago, Veneno e a Égide (4s) quase não agem | (a) HP x(1 + 0.4 por duelo vencido) → x2.2 na sala 9, x3.4 na sala 18 · (b) fusão de armas x1.8 por nível em vez de x2.2 · (c) as duas, mais brandas · Qual duração-alvo por sala? (proposta: 15–20s em todas) |
| Q-02 | P-02 | **Catalisadores devem se multiplicar entre si?** | Hoje cada catalisador multiplica o dano do vizinho: 1 Pedra de Amolar +0 = x1.20; 4 Pedras +0 na mesma arma = x2.07; 4 Pedras +2 (x1.68 cada) = x7.97, em cima do x4.84 da arma +2 | (a) máximo de 3 catalisadores do mesmo tipo por item · (b) bônus do mesmo tipo somam (4 x +20% = +80%) e tipos diferentes multiplicam · (c) manter |
| Q-03 | P-02 | **Tetos para Veneno e crítico do Ladino?** | Veneno: 1 dano/s por stack, sem máximo (Queimadura tem máx. 5, Ácido máx. 3); stacks aplicados escalam x2.2 por nível de fusão. Crítico acima de 100%: cada 10% excedente = +15% de dano crítico, sem teto | Proposta: Veneno máx. 10 stacks; dano crítico extra máx. +60% |
| Q-04 | P-04 | **Faixa-alvo para encantamentos e quais ajustar?** | Sala 3, encantamento em todas as armas, delta vs linha de base: Armazenador +51.3pp (87.3%) · Veloz +46.0 · Flamejante +43.7 · Gélido +43.0 · Defensor +26.0 · Vorpal +23.3 · Vampírico +17.3 · Trovejante +10.0 · Afiado +9.0 · Mortal +7.3 | Proposta: faixa +20 a +40pp. Armazenador: custo 15 → 25 de mana. Mortal: críticos x2.5 → x3. Afiado: +15% → +25% de crítico. Trovejante: chance 15% → 25% |
| Q-05 | P-10 | **O Combo do Ladino deve contar no valor de um item?** | Poção de Mana, Gema Bruta e Aljava deram exatamente +11.7pp, todos melhores encostados na adaga do Ladino (+8% de crítico por item diferente encostado), não pela função do item | (a) mostrar duas colunas: com e sem Ladino · (b) medir sem Ladino · (c) manter (o Combo é parte real do valor) |
| Q-06 | P-15 a P-18 | **As interpretações abaixo estão corretas?** | Ver seção 3 (Paladino 4s/25%/35%; Tomo Menor e mana 3/4.5/6/7.5; dois Tambores e Palco fora do Meio −8%/−0.15s; Bomba Alquímica) | Confirmar ou corrigir cada uma |

### Respostas recebidas

_Nenhuma ainda. Formato: `Q-xx · data · resposta resumida · decisão aplicada (rodada)`._

## 1. Balanceamento — problemas abertos

| Código | Status | Questão | Dados | Proposta / próximo passo |
|---|---|---|---|---|
| P-01 | 🟡 | **Lutas encurtam demais com a profundidade** — causa principal do desequilíbrio no fim da run | Duração média: sala 3 = 21.3s · sala 9 = 7.1s · sala 18 = 2.3s. Dano multiplica com a fusão (x4.84 no +2), a vida dos heróis não cresce | Testar **vida crescendo com a profundidade** (ex.: HP x(1 + 0.4 por duelo) → x2.2 na sala 9, x3.4 na sala 18) e/ou fusão de armas mais fraca. Meta: lutas de 15–20s em todas as salas. *Teste ainda não executado.* |
| P-02 | 🟡 | **Escalonamento sem teto** (ver P-01) | Catalisadores se multiplicam entre si (4 Pedras +2 numa espada ≈ x8 de dano); Veneno sem limite de stacks; crítico excedente do Ladino sem teto | Limitar a 3 catalisadores do mesmo tipo por item (ou somar em vez de multiplicar); Veneno máx. 10 stacks; crítico excedente máx. +60% de dano crítico |
| P-03 | 🔵 | Classes no fim da run | Rodada 9 (melhor posição): diferença 11 / 18 / 22 pp nas salas 3 / 9 / 18. Sala 18: Mago 40%, Alquimista 35% (fracos); Guerreiro 56%, Patrulheiro 57%, Bardo 57% (fortes). **Não remedido após a rodada 10** | Depende de P-01/P-02; remedir com `npm run balance -- --rooms 3,9,18` depois deles |
| P-04 | 🔴 | Encantamentos desiguais | Armazenador 87% (+51pp) é o mais forte; Mortal +7pp, Afiado +9pp, Trovejante +10pp são fracos | Decidir: reduzir o Armazenador (custo de mana maior?) e/ou subir Mortal/Afiado/Trovejante |
| P-05 | 🔵 | Itens avançados que não compensam na sala 9 | Lobo Cinzento −7pp (só cabe tirando o Arco Longo), Gema de Mana ~0, Rubi Ígneo ~0 (mana pesa pouco em lutas de 7s) | Remedir depois de P-01; se continuarem fracos, buff ou mudança de função |
| P-06 | 🔵 | Alaúde dos Ventos só cabe trocando um item | O kit inicial do Bardo não deixa espaço 2x2 livre | Aceitável enquanto não existir a Bolsa de expansão (P-20); rever com ela |

## 2. Ferramenta de teste (medição)

| Código | Status | Questão | Proposta |
|---|---|---|---|
| P-10 | 🟡 | **Combo do Ladino distorce o teste de itens**: Poção de Mana, Gema Bruta e Aljava deram o mesmo +11.7pp porque o ganho vem do Ladino (+8% de crítico por item diferente encostado), não do item | Medir itens também numa party sem Ladino e mostrar as duas colunas, ou descontar o efeito do Combo |
| P-11 | 🔵 | Ghosts são gerados localmente (70% das vezes com a classe sugerida para cada posição) | Placeholder até existir o backend de PvP (P-22); os números absolutos dependem dessa mistura |

## 3. Interpretações feitas sem definição exata (validar)

| Código | Status | O que foi interpretado |
|---|---|---|
| P-15 | 🔴 | Paladino, "armadura/relíquia ativa": ativa a cada 4s; gera 25% do escudo da armadura (relíquia: 4) e passa 35% ao aliado com menos HP |
| P-16 | 🔴 | Mago: criado o item básico **Tomo Menor** para a passiva funcionar desde o início; mana dos cajados 3 → 4.5 → 6 → 7.5 por nível (a proposta original citava 15/22/30) |
| P-17 | 🔴 | Bardo: começa com **dois Tambores no Palco**; fora do Meio o Palco dá −8% e −0.15s (a proposta só definia o Meio) |
| P-18 | 🔴 | Alquimista: **Bomba Alquímica** (exclusiva, à distância, cura o aliado mais ferido em 50% do dano, aplica Ácido) no lugar do "Cetro de Luz" |

## 4. Funcionalidades não implementadas

| Código | Status | Funcionalidade |
|---|---|---|
| P-20 | ⚪ | **Bolsa de expansão** de mochila (item fora da loja até existir a mecânica) |
| P-21 | ⚪ | **Receitas mágicas** (Fase 2): combinações de itens encostados viram itens novos |
| P-22 | ⚪ | **PvP assíncrono real**: backend para salvar builds de jogadores; hoje o ghost é gerado localmente |
| P-23 | ⚪ | **Emboscada PvE** com combate de verdade (hoje só dá ouro) |
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
| R-01 | Rodada 10 | Flamejante quebrado (97.7%) | Queimadura 1 dano/s por stack, máx. 5 → 79.7% |
| R-02 | Rodada 10 | Aljava, Ração e Poção de Mana com +0.0pp | Era o teste (party sem arcos/mascotes); itens agora testados em 3 parties. Poção de Mana dispara abaixo de 50% |
| R-03 | Rodada 10 | Alaúde "sem espaço" e avançados ~0% na sala 9 | Teste troca o item mais dispensável; avançados medidos com party de referência evoluída e item +1 |
| R-04 | Rodada 8 | Bardo e Patrulheiro explodindo no meio/fim da run | Palco não acumula instrumentos; Ataque Coordenado no máximo 1x/s |
