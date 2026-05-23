# Vibecoding

**Do problema ao protótipo funcional**
Mestrado em Administração · 23/05/2026 · Jady Pamella

A pergunta não é mais *"Como vou explicar esse problema para o desenvolvedor?"*. É *"E se eu fizer o protótipo para conversar com o desenvolvedor?"*.

Este repositório é o material que sobrou da aula: slides, os prompts que foram colados no Lovable durante a hora, e os dois apps que ficaram no ar como resultado. Pegue, edite, cole. O que você precisa para reconstruir em casa.

---

## Índice do repositório

| Arquivo | O que é |
|---|---|
| [slides.pdf](slides.pdf) | Slides da aula |
| [prompts/](prompts/) | Os one-shot prompts que viraram apps publicados, mais o template genérico |
| `README.md` | Este material de referência |

---

## Os prompts e os resultados

Cada prompt foi colado no [Lovable](https://lovable.dev) e virou um app web funcional, publicado e jogável.

| # | Prompt | App publicado | O que faz |
|---|---|---|---|
| 1 | [lovable_prompt_sabetudo.md](prompts/lovable_prompt_sabetudo.md) | [jogosabetudo.lovable.app](https://jogosabetudo.lovable.app/) | Quiz ao vivo para plateias, semelhante a Kahoot e Mentimeter. Host cria o quiz, jogadores entram por PIN e apelido, perguntas com cronômetro, pontuação por velocidade, ranking e pódio. |
| 2 | [lovable_prompt_avalia_ptt.md](prompts/lovable_prompt_avalia_ptt.md) | [avaliaptt.lovable.app](https://avaliaptt.lovable.app/) | Autoavaliação de Produto Técnico Tecnológico (PTT) seguindo a Ficha de Avaliação 2025 da Área 27 da CAPES. O pesquisador cadastra o produto, responde os cinco critérios oficiais e recebe sugestão de estrato (TA1 a TB4). |
| 3 | [lovable_oneshot_prompt.md](prompts/lovable_oneshot_prompt.md) | Template genérico | Modelo de one-shot prompt destilado dos dois prompts acima. Use como ponto de partida para criar um prompt novo para outro app. |

Tente jogar o SabeTudo agora com colegas, ou abra o AvaliaPTT para uma ronda de autoavaliação. Os dois rodam direto no navegador, no celular ou no computador.

---

## O que é vibecoding

Você descreve, em português, o que o sistema precisa fazer. A inteligência artificial escreve o código, monta a tela, conecta o banco de dados e publica na internet.

Você não programa. Você conversa. O software aparece enquanto você fala.

O termo nasceu em 2025 e virou prática comum entre quem constrói produto. O que quase ninguém te contou é que funciona igualmente bem para quem trabalha com gestão, processo e política pública, não só para empresa de tecnologia. Você já tem a parte difícil: descrever o problema com clareza. Essa sempre foi a sua especialidade.

---

## O ciclo novo

```
ideia  →  protótipo em minutos  →  validação real  →  proposta com a tela pronta
```

O protótipo vem antes do pedido para área de TI. Você para de descrever o que quer e passa a mostrar.

**O caminho de hoje:** você identifica a necessidade, escreve requisitos, abre chamado, espera a fila da TI, estudo de viabilidade, processo de contratação, e dois anos depois talvez o sistema chega diferente do que você precisava.

**O caminho novo:** você constrói o protótipo funcional numa tarde, mostra para a equipe, valida o que serve, e aí sim escreve a proposta, agora com a tela pronta na mão.

---

## O que você consegue construir a partir de segunda

Oito formas concretas. Todas exigem só descrever o problema com clareza.

| # | O que | Para quem dói hoje |
|---|---|---|
| 1 | Painel a partir de uma planilha | Atualiza a planilha na mão e ninguém olha |
| 2 | Formulário que organiza os dados sozinho | Recebe resposta por email e copia para planilha |
| 3 | Analisador de documentos em massa | Quinhentos PDFs de prestação de contas |
| 4 | Triagem e pontuação de propostas | Avaliar pedidos de bolsa um por um |
| 5 | Gerador de relatório | Relatório quadrimestral que toma três dias |
| 6 | Conversar com os próprios documentos | A pessoa nova pergunta a mesma coisa toda semana |
| 7 | Portal de transparência | Página pública vira projeto, fornecedor, chamado |
| 8 | Automação do repetitivo | Classificar, encaminhar, registrar tudo na mão |

---

## Como cheguei no prompt

Pense num memorando para um estagiário muito rápido que nunca viu o seu problema.

1. **Contexto.** Quem vai usar, para quê, em que situação. Duas ou três frases.
2. **Exemplo concreto.** Não "um painel de acompanhamento", e sim "ver, por programa, bolsistas ativos, entregas atrasadas, alerta vermelho acima de 30 dias".
3. **Restrição.** O que não fazer. "Não invente dados, use só a planilha." "Linguagem formal." "Funciona no celular."
4. **Iteração.** Você não acerta de primeira. Ninguém acerta. Corrige e tenta de novo. Essa é a única diferença entre quem usa bem e quem desiste.

E quando quiser que o protótipo pareça caro, não amador, três truques mudam tudo:

- **Descreva o nível, não só o objeto.** "Isso é uma escultura, apresente como uma."
- **Nomeie o acabamento que você quer.** "Animações suaves, transições de produto premium."
- **Defina a filosofia da interação.** "A informação se revela conforme a pessoa explora, sem firula."

Adaptado de [designplusai.com](https://designplusai.com/p/how-to-prompt-high-end-websites-in).

---

## Atenção

### Dados sensíveis e LGPD

Se você é empresa ou servidor público. O dado que passa pela sua mão tem dono e tem lei.

A regra, simples e inegociável: protótipo se constrói com dado fictício ou anonimizado. Nome, CPF, dado pessoal de cidadão e informação sigilosa não vão para ferramenta pública. Para construir e mostrar, dado de mentira resolve. O sistema real, com dado real, é outra conversa, com a TI e a área jurídica.

### Protótipo não é produção

O que foi construído na hora prova a ideia. Não substitui o sistema oficial, não tem a segurança que dado público exige, não passou por auditoria.

O valor é outro: ele transforma a sua proposta de sistema de um texto que ninguém lê numa coisa que a diretoria clica e aprova. Aí sim entra a TI, agora construindo a coisa certa, porque você já provou qual é.

O protótipo não compete com a TI. Ele faz a TI construir o sistema certo da primeira vez.

---

## Ferramentas para você testar

### Construir o app conversando
[Lovable](https://lovable.dev), [Bolt.new](https://bolt.new), [v0 by Vercel](https://v0.dev). Todos com plano grátis. Foi o Lovable que rodou na aula.

### Pensar e refinar o prompt
[ChatGPT](https://chatgpt.com), [Claude](https://claude.ai), [Gemini](https://gemini.google.com). Os três com plano grátis. Use para limpar o prompt antes de colar no Lovable.

### Ler e analisar documentos
[NotebookLM](https://notebooklm.google.com) (Google, grátis), [Google AI Studio](https://aistudio.google.com) (grátis). Sobe seus PDFs e ele responde com a fonte.

### Para quem quiser ir além
[Cursor](https://cursor.com) (editor de código com IA, plano grátis), [Claude Code](https://www.anthropic.com/product/claude-code) (agente no terminal, pago), [Replit](https://replit.com) (constrói e publica no navegador, plano grátis).

Quase todas têm plano gratuito. Comece pelo grátis e pague só quando precisar de mais.

---

## O que você faz segunda de manhã

1. Escolha um problema pequeno e chato. Aquele relatório, aquela planilha, aquele formulário.
2. Abra o [Lovable](https://lovable.dev) e descreva ele como você descreveria para um colega competente.
3. Erre, corrija, erre de novo. Trinta minutos.
4. Mostre o resultado para uma pessoa da equipe e veja a cara dela.

Não construa o sistema da sua vida. Construa a coisa pequena. A emoção de ver funcionar é o que vai te fazer continuar.

---

## Contato

**Jady Pamella** · Master of AI Engineering

- LinkedIn: [linkedin.com/in/jadypamella](https://linkedin.com/in/jadypamella)
- E-mail: hello@jadypamella.com
- Portfólio: [jadypamella.com](https://jadypamella.com)

---

*A pergunta não é mais "quem vai construir isso pra mim?". É: "o que eu vou construir agora?"*
