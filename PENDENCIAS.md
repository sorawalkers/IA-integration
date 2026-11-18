# OSR Battler — Pendências e dúvidas em aberto

> Lista viva: atualizada a cada teste e a cada mudança. Cada item tem um código (`P-xx`) para referência.
> Resultados dos testes: `BALANCO.md` (resumo) e `relatorio.md` (última simulação). Regras: `CLAUDE.md` do repo do jogo.
> Perguntas para o agente de análise: seção 0 (`Q-xx`).

**Última atualização:** 2026-11-18 · após a rodada 12 (respostas Q-07 e Q-08 aplicadas).

Legenda de status: 🔴 aguardando decisão · 🟡 proposta pronta, falta aplicar/testar · 🔵 em observação · ⚪ fora do escopo atual

## 0. Perguntas para o agente de análise

> **Como funciona:** o agente de análise lê este arquivo no repositório público e responde ao usuário, que repassa a
> resposta ao Claude Code (que roda os testes). A resposta é registrada aqui com a data, a decisão é aplicada e o
> efeito medido entra em `BALANCO.md`. Responda citando o código (`Q-xx`).

| Código | Ref. | Pergunta | Dados para decidir | Opções |
|---|---|---|---|---|
| Q-09 | P-31 | **Como garantir que fundir nunca fique pior que 2 cópias soltas?** | Rodada 12 (fusão de armas x1.7 e −8% de recarga por nível): Espada Curta +2.3 · Arco Curto +1.7 · Cajado +1.3 · Maça −1.7 · **Adaga −5.7** · **Tambor de Guerra −13.0** (pp do item +1 contra 2 cópias +0, sala 3). Em DPS bruto, arma +1 = 1.7 / 0.92 = **x1.85** de uma cópia; 2 cópias = x2. Para empatar: −15% de recarga por nível (1.7 / 0.85 = 2.0), ou dano x1.84 com −8%. O Tambor perde porque 2 tambores dão o +2 de inspiração e o adiantamento duas vezes; o fundido dá +50% de adiantamento e o +2 não escala | (a) armas: recarga −15%/nível (empate exato em DPS; +2 = x2.89 / 0.70 ≈ x4.1, +3 = x4.91 / 0.55 ≈ x8.9) · (b) armas: −12%/nível e aceitar perda pequena (o espaço livre compensa no jogo real) · (c) Tambor: inspiração +2 / +3 / +4 / +5 por nível de fusão · (d) instrumentos: adiantamento x2 no +1 (como 2 cópias) |
| Q-10 | P-03 | **Diferença de 26pp entre classes na sala 18** | Rodada 12, melhor posição (sala 3 / 9 / 18): Mago 43 / 51 / **61**% (Meio na 18) · Alquimista 39 / 50 / 56 · Bardo 38 / 47 / 55 · Guerreiro 44 / 47 / 53 · Bárbaro 40 / 42 / 50 · Paladino 40 / 40 / 41 · Patrulheiro 32 / 34 / 39 · Ladino 42 / 37 / **35**. Lutas mais longas na 18 (13.6s, eram 7.5s) favorecem quem escala com tempo (mana, poções). O Ladino perde força com a profundidade: Veneno tem teto de 10 stacks e o crítico excedente teto de +60% | (a) Ladino: Veneno máx. 10 → 15 e stacks por crítico 2 → 3 · (b) Mago: Sobrecarga dispara acima de 65% → 75% da mana · (c) Patrulheiro: Ataque Coordenado 0.4s → 0.6s · (d) Paladino: relíquia gera 4 → 6 de escudo · combinações |
| Q-11 | P-04 | **Afiado continua abaixo da faixa** | Afiado +13.7pp nas rodadas 11 e 12 (subir +25% → +30% não mudou nada). Os outros 9 encantamentos estão entre +19.7 e +35.3pp. Crítico base é 5% e dano crítico x1.5; +30% de chance dá ≈ +15% de dano médio | (a) Afiado: +30% de crítico **e** críticos x1.75 · (b) Afiado: +45% de crítico · (c) Afiado: +30% de crítico e cada crítico adianta 0.3s a recarga da arma |

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
- **Observação (P-05)** · 2026-11-18 · o Lobo Cinzento cai por precisar tirar o Arco Longo; se resolve com as Bolsas de expansão (P-20) ou com 2 slots extras no gerador das salas 9/18 · registrado em P-05/P-20

## 1. Balanceamento — problemas abertos

| Código | Status | Questão | Dados | Proposta / próximo passo |
|---|---|---|---|---|
| P-01 | 🔵 | Ritmo das lutas | Rodada 12 (curva Q-07): **19.5 / 15.7 / 13.6s** (salas 3 / 9 / 18); meta 14–18s. Sala 3 1.5s acima, sala 18 0.4s abaixo | Aceitável; remedir a cada rodada |
| P-03 | 🔴 | Classes por sala | Rodada 12 (melhor posição): diferença **12 / 17 / 26 pp** nas salas 3 / 9 / 18. Sala 18: Ladino 35%, Patrulheiro 39%, Paladino 41% (fracos); Mago 61%, Alquimista 56%, Bardo 55% (fortes) | Aguardando **Q-10** |
| P-04 | 🔵 | Encantamentos desiguais | Rodada 12: 9 de 10 na faixa +20 a +40pp; Afiado +13.7 | Aguardando **Q-11** |
| P-31 | 🟡 | Fundir pior que 2 cópias | Rodada 12: Adaga +1 −5.7pp, Tambor +1 −13.0pp contra 2 cópias | Aguardando **Q-09** |
| P-05 | 🔵 | Itens avançados que não compensam na sala 9 | Rodada 11: Lobo Cinzento +2.0 (−4.3 com Ladino; só cabe tirando o Arco Longo), Gema de Mana +2.7, Rubi Ígneo +10.0 | Lobo: resolvido pelas Bolsas (P-20) ou 2 slots extras no gerador (observação do agente). Remedir depois de Q-07 |
| P-06 | 🔵 | Alaúde dos Ventos só cabe trocando um item | O kit inicial do Bardo não deixa espaço 2x2 livre | Aceitável enquanto não existir a Bolsa de expansão (P-20); rever com ela |

## 2. Ferramenta de teste (medição)

| Código | Status | Questão | Proposta |
|---|---|---|---|
| P-11 | 🔵 | Ghosts são gerados localmente (70% das vezes com a classe sugerida para cada posição) | Placeholder até existir o backend de PvP (P-22); os números absolutos dependem dessa mistura |

## 3. Interpretações feitas sem definição exata (validar)

| Código | Status | Interpretação | Validar |
|---|---|---|---|
| P-32 | 🟡 | **Trovejante "+20% no dano do raio"**: o Trovejante não tinha dano próprio (só atordoava). Implementado como +20% de dano no golpe da arma encantada | Confirmar ou indicar outra forma (ex.: raio separado de N de dano que ignora escudo) |
| P-33 | 🟡 | **Tambor "+2 de dano plano ao grupo"**: implementado como +2 no **próximo** golpe de cada aliado vivo (inclusive o Bardo); não acumula entre toques e não escala com a fusão | Confirmar (alternativa: +2 em todos os golpes por X segundos) |

P-15 a P-18 confirmadas no Q-06 (P-17 corrigido).

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
| R-09 | Rodada 11 | HP por duelo vencido viraria bola de neve | HP cresce por duelo **jogado** (vitória ou derrota); herói recrutado entra com os duelos do grupo |
| R-05 | Rodada 11 | Escalonamento sem teto (P-02) | Catalisadores do mesmo tipo somam; Veneno máx. 10; crítico excedente máx. +60% (Q-02, Q-03) |
| R-06 | Rodada 11 | Combo do Ladino distorcia o teste de itens (P-10) | Colunas Com e Sem Ladino no relatório (Q-05) |
| R-07 | Rodada 11 | Interpretações P-15 a P-18 | Confirmadas; Bardo com 1 Tambor + Adaga + Poção (Q-06) |
| R-08 | Rodada 11 | Referência dos testes de itens mais fraca que os ghosts | Party de referência com os mesmos duelos (HP) que os ghosts da sala |
| R-01 | Rodada 10 | Flamejante quebrado (97.7%) | Queimadura 1 dano/s por stack, máx. 5 → 79.7% |
| R-02 | Rodada 10 | Aljava, Ração e Poção de Mana com +0.0pp | Era o teste (party sem arcos/mascotes); itens agora testados em 3 parties. Poção de Mana dispara abaixo de 50% |
| R-03 | Rodada 10 | Alaúde "sem espaço" e avançados ~0% na sala 9 | Teste troca o item mais dispensável; avançados medidos com party de referência evoluída e item +1 |
| R-04 | Rodada 8 | Bardo e Patrulheiro explodindo no meio/fim da run | Palco não acumula instrumentos; Ataque Coordenado no máximo 1x/s |
