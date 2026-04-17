# Demo 4: Red-team da própria tese

## Objetivo
Forçar a IA a ser hostil e encontrar a falha fatal da sua tese, capítulo ou artigo antes de um humano hostil encontrar. Inversão do default bajulador.

## Quando usar
- Antes de submeter artigo (especialmente A1 ou A2).
- 1 mês antes da qualificação ou defesa.
- Quando você tem a sensação de que algo está fraco mas não sabe o que.

## Ferramentas recomendadas
- **[Claude](https://claude.ai)** (em modo com thinking estendido).
- **[ChatGPT](https://chatgpt.com) o1** ou **o3** (modos de raciocínio).
- Evite [Gemini](https://gemini.google.com) para isso. Ele é bajulador por design.

## Por que o default não funciona

Pergunte ao [ChatGPT](https://chatgpt.com) "o que está errado neste meu texto?" e ele vai dizer "nada grave, aqui estão sugestões menores". Isso é treinamento em feedback positivo (RLHF). Você precisa quebrar esse padrão na marra.

## System prompt (parte 1)

```
Instruções de comportamento

Você é Revisor 2 do Journal of [área da tese]. Este é o revisor temido do campo: rigoroso, experiente, cruel, mas tecnicamente impecável. Seu nome é desconhecido porque é sempre blind review.

Regras rígidas:
1. Você não elogia. Ignore a convenção de começar com pontos positivos.
2. Você não sugere melhorias. Seu trabalho é atacar, não consertar.
3. Você não é educado. Cortesia acadêmica é perda de tempo aqui.
4. Você não pede esclarecimentos. Trabalhe com o que foi dado.
5. Sua única meta é identificar a Falha fatal. Se não há falha fatal, diga explicitamente.

Estrutura da resposta:

1. Falha fatal: a razão principal pela qual este trabalho não deveria ser publicado (ou defendido). Uma única frase, contundente.

2. Evidência da falha: 3 citações literais do texto que comprovam a falha. Use aspas. Indique a linha ou parágrafo.

3. Como a falha escapou: por que o autor não viu isso. Diagnóstico cruel do viés ou cegueira que levou ao erro.

4. Teste de robustez: se o autor fosse corrigir, o que teria que mudar? Se mudar isso destrói o argumento central, a tese está quebrada. Diga.

5. Veredito: Reject, Major Revision, Minor Revision, Accept. Uma palavra. Justifique em 2 linhas.
```

## Prompt de entrada

Depois do system prompt, cole:

```
Texto a avaliar:

[cole aqui o capítulo, artigo ou fragmento]

Aplique as regras acima. Sem concessões.
```

## O que destacar ao vivo

- Ler em voz alta a "Falha fatal" que a IA produzir. Isso é o momento wow.
- Comentar: "Agora imagina que isso veio depois do desk reject. Custou 6 meses. Com a IA, custou 3 minutos."
- Reforçar: "Ainda não posso garantir que a IA está certa. Mas se EU concordo depois de ler, o problema é real."

## Variações

**Red-team por persona específica**: substitua "Revisor 2" por "Karl Popper", "Judith Butler", "John Rawls", "seu orientador crítico". Cada persona ataca de ângulo diferente.

**Red-team estatístico**: para tese quantitativa, use:

> "Você é um estatístico com 30 anos de experiência em peer review. Encontre todos os problemas de validade estatística: viés de seleção, multicolinearidade, poder estatístico insuficiente, p-hacking, ausência de correção para múltiplas comparações, falta de teste de robustez."

**Red-team metodológico qualitativo**: para tese qualitativa:

> "Você é um metodólogo qualitativo rigoroso. Avalie: saturação teórica, triangulação, reflexividade, validade de construto, transferibilidade. Aponte todas as fragilidades."

## Cuidados

- A IA pode ser hostil e estar errada. Não revise seu texto com base em cada crítica. Filtre com julgamento humano.
- Use para identificar problemas, não para consertá-los imediatamente. Consertar é trabalho seu.
- Se a IA disser que não há falha fatal, não significa que não há. Significa que ela não achou. Tente outra vez, com outra persona.

## Dica avançada

Peça o red-team duas vezes com prompts diferentes, ambas no mesmo chat. Depois peça:

```
Você fez dois red-teams diferentes deste texto. Compare os dois. Quais críticas apareceram em ambos? Essas são as mais prováveis de serem reais.
```

Isso é triangulação interna. A IA faz o trabalho de sintetizar.
