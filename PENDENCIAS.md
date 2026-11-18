# OSR Battler — Pendências e dúvidas em aberto

> Lista viva: atualizada a cada teste e a cada mudança. Cada item tem um código (`P-xx`) para referência.
> Resultados dos testes: `BALANCO.md` (resumo) e `relatorio.md` (última simulação). Regras: `CLAUDE.md` do repo do jogo.
> Perguntas para o agente de análise: seção 0 (`Q-xx`).

**Última atualização:** 2026-11-18 · após a rodada 13 (respostas Q-09 a Q-11 aplicadas).

Legenda de status: 🔴 aguardando decisão · 🟡 proposta pronta, falta aplicar/testar · 🔵 em observação · ⚪ fora do escopo atual

## 0. Perguntas para o agente de análise

> **Como funciona:** o agente de análise lê este arquivo no repositório público e responde ao usuário, que repassa a
> resposta ao Claude Code (que roda os testes). A resposta é registrada aqui com a data, a decisão é aplicada e o
> efeito medido entra em `BALANCO.md`. Responda citando o código (`Q-xx`).

| Código | Ref. | Pergunta | Dados para decidir | Opções |
|---|---|---|---|---|
| Q-12 | P-31 | **Fusão: o que ainda perde para 2 cópias é estrutural. Como tratar?** | Rodada 13 (armas x1.7 e −13%/nível; instrumentos +75%, inspiração +1/nível): Arco Curto +4.0 · Espada Curta +2.7 · Cajado +2.3 · Maça −1.0 · **Adaga −5.3** · **Gema Bruta −7.0** · **Tambor −14.7** (pp do +1 contra 2 cópias, sala 3). No teste, cada cópia vai para o melhor herói, então as 2 cópias podem ficar em **heróis diferentes**: cada herói tem sua estamina (armas físicas gastam estamina) e seus limites por segundo. 2 Tambores (em qualquer lugar) dão adiantamento x2 e inspiração 2x por ciclo ao grupo; o Tambor +1 dá x1.75 e +3 uma vez. Para a Gema Bruta, as 2 cópias encostam em 2 armas diferentes; a +1 (bônus x2.2 no vizinho e alcance com diagonais) não compensa | (a) aceitar: em jogo real o espaço é o limite e o teste não mede isso; mudar o teste para comparar no **mesmo herói** · (b) Tambor: só **um instrumento por herói** dispara (2 tambores no mesmo herói não somam) · (c) instrumentos: adiantamento x2 no +1 · (d) Gema Bruta +1: bônus nos vizinhos x2.6 no +1 |
| Q-13 | P-03 | **Os buffs do Q-10 não moveram Ladino, Patrulheiro e Paladino na sala 18** | Sala 18 (rodada 12 → 13): Ladino 35 → 35% · Patrulheiro 39 → 39% · Paladino 41 → 41% · Mago 61 → 59% · Alquimista 56 → 56% · Bardo 55 → 54% · Guerreiro 53 → 53% · Bárbaro 50 → 50%. Diferença 26 → 23pp. Na sala 3 o Ladino subiu 42 → 47% e o Mago caiu 43 → 35%. Hipótese: na sala 18 as mochilas estão cheias de itens sorteados pelo gerador (12 extras), então a passiva pesa pouco perto dos itens; Mago/Alquimista/Bardo escalam com tempo de luta e com efeitos de grupo | (a) eu investigo onde o Ladino/Patrulheiro/Paladino perdem na sala 18 (dano causado, tempo vivo, item mais usado) antes de mexer em números · (b) buffs maiores só na escala: ex. passiva do Ladino/Patrulheiro/Paladino cresce +10% por duelo jogado · (c) reverter a Sobrecarga do Mago para 70% (o corte pesou nas salas 3/9) |
| Q-14 | P-01 | **Sala 18 encurtou para 11.6s** (meta 14–18s) | Lutas: 19.4 / 14.9 / **11.6s**. Encurtou porque as armas +2 agora recarregam 26% mais rápido. HP hoje = classe x0.75·(1 + 0.10·d + 0.10·d²) → x3.90 na sala 18 | (a) termo quadrático 0.10 → 0.13 (x0.90 / x1.88 / x4.71; ainda não medido — meço assim que for escolhida) · (b) aceitar ~12s no fim da run · (c) sala 3 também está acima (19.4s): base x0.75 → x0.70 junto com (a) |

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
- **Observação (P-05)** · 2026-11-18 · o Lobo Cinzento cai por precisar tirar o Arco Longo; se resolve com as Bolsas de expansão (P-20) ou com 2 slots extras no gerador das salas 9/18 · registrado em P-05/P-20

## 1. Balanceamento — problemas abertos

| Código | Status | Questão | Dados | Proposta / próximo passo |
|---|---|---|---|---|
| P-01 | 🟡 | Ritmo das lutas | Rodada 13: **19.4 / 14.9 / 11.6s** (salas 3 / 9 / 18); meta 14–18s | Aguardando **Q-14** |
| P-03 | 🔴 | Classes por sala | Rodada 13 (melhor posição): diferença **16 / 16 / 23 pp** nas salas 3 / 9 / 18. Sala 18: Ladino 35%, Patrulheiro 39%, Paladino 41% (fracos); Mago 59%, Alquimista 56%, Bardo 54% (fortes) | Aguardando **Q-13** |
| P-04 | 🔵 | Encantamentos | Rodada 13: 9 de 10 na faixa; Vampírico +17.7 (era +21.3, linha de base mudou) | Remedir na próxima rodada antes de mexer |
| P-31 | 🟡 | Fundir pior que 2 cópias | Rodada 13: Adaga −5.3, Gema Bruta −7.0, Tambor −14.7pp contra 2 cópias | Aguardando **Q-12** |
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
| P-20 | ⚪ | **Bolsa de expansão** de mochila (item fora da loja até existir a mecânica). Resolveria o Lobo Cinzento (P-05) e o Alaúde (P-06) |
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
