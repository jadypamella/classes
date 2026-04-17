# Demo 6: O paper que deveria existir

## Objetivo
Dado um gap identificado na literatura, descrever o paper ideal que preencheria esse gap. Se o paper não existe, você acabou de achar sua pesquisa.

## Quando usar
- No início do projeto, quando você tem ideia do tema mas não da pergunta.
- Depois da revisão de literatura, para validar que seu gap é realmente um gap.
- Quando está travada, sem saber por onde começar.

## Ferramentas recomendadas
- **[Claude](https://claude.ai)** ou **[ChatGPT](https://chatgpt.com)** para a estrutura inicial.
- **[Google Scholar](https://scholar.google.com)**, **[Scite](https://scite.ai)**, **[Semantic Scholar](https://semanticscholar.org)** para verificar se o paper realmente não existe.
- **[Elicit](https://elicit.com)** para confirmar com outra abordagem.

## Pré-requisito
Você já precisa ter um gap identificado. Este movimento ajuda a descrever o paper ideal, não a descobrir o gap.

Se você ainda não tem gap, rode antes o demo 3 (literatura fantasma) e o demo 5 (cartografia).

## Prompt

```
Contexto

Identifiquei um gap na literatura sobre [tema]. O gap é: [descrição clara do gap, 3 a 4 linhas].

As referências relevantes para esse gap estão abaixo [ou em anexo]:

[lista de 20 a 40 referências principais ou arquivo anexado]

Tarefa

Descreva o paper ideal que preencheria este gap. Não invente. Construa a partir do que está no corpus acima.

Estrutura:

1. Título provável: em formato padrão de revista internacional (clear, specific, 12 a 20 palavras).

2. Resumo de 200 palavras: seguindo estrutura Contexto + Objetivo + Método + Resultado esperado + Contribuição.

3. Hipótese central: uma frase, testável, que o paper defenderia.

4. Método: que tipo de estudo (quantitativo, qualitativo, misto, revisão, teórico). Que dados precisariam ser coletados. Que análise aplicar. Quanto tempo levaria.

5. Dados necessários: quais, de onde, com que nível de acesso.

6. Resultado esperado: qual seria o achado que confirmaria a hipótese. Qual seria o achado que refutaria.

7. Limitação principal: qual é a vulnerabilidade metodológica que o revisor 2 atacaria.

8. Contribuição: por que esse paper importaria. Para quem. Em que debate ele entraria.

9. Revista-alvo: 3 opções de revistas que publicariam isso, com justificativa.

10. Busca de verificação: que string de busca no Google Scholar eu devo usar para confirmar que esse paper realmente não existe ainda.
```

## O que destacar ao vivo

- Depois de gerar a descrição, ir ao [Google Scholar](https://scholar.google.com) e colar a string de busca do item 10.
- Mostrar que o paper realmente não existe (ou existe, parcialmente, e aí se apresenta como trabalho relacionado).
- Comentar: "O que aconteceu agora é que, se o paper não existe, essa é a sua pesquisa. Você tem título, hipótese, método, dados, revista-alvo. Isso é um projeto de qualificação quase pronto."

## Caso real para ilustrar

Você pode narrar um exemplo hipotético:

> "Numa conversa com uma doutoranda em saúde coletiva, identificamos gap em políticas de contracepção para mulheres com deficiência intelectual no Brasil. A IA descreveu o paper que deveria existir. Buscamos no [Google Scholar](https://scholar.google.com). Existiam 3 estudos isolados, nenhum nacional, nenhum dos últimos 5 anos. Era projeto de tese."

## Cuidados

- A IA pode descrever o paper de forma otimista. Um revisor real vai atacar.
- Método proposto pela IA pode ser impraticável no seu contexto (tempo, recurso, acesso). Ajuste para sua realidade.
- Limitação principal identificada pela IA não é a única limitação. Adicione as suas.

## Follow-up poderoso

Depois de ter o paper descrito, rode o red-team (demo 4) no próprio paper descrito.

Pergunta:

```
Esse paper que você acabou de descrever: se fosse submetido amanhã, qual seria a falha fatal que o revisor 2 identificaria?
```

A IA vai atacar a própria proposta. Você aprende a fortalecer o projeto antes de começar.
