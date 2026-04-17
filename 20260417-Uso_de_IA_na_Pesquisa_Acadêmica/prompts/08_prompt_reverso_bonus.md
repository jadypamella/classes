# Demo 8 (bônus): Prompt reverso

## Objetivo
Engenharia reversa de excelência. Dado um paper que você admira, pedir à IA "qual prompt teria produzido isso?". Você extrai a estrutura mental invisível que gerou o trabalho de qualidade.

## Quando usar
- Quando você encontra um artigo particularmente bem escrito na sua área.
- Quando quer aprender a estrutura de um tipo de texto (abstract de Nature, resumo estendido da ANPOCS, introdução de Science).
- Para construir um banco pessoal de "prompts que funcionam".

## Ferramentas recomendadas
- **[Claude](https://claude.ai)** (bom em análise estrutural).
- **[ChatGPT](https://chatgpt.com)** com GPT-4o ou o1 (bom em extração de padrões).

## Prompt

```
O texto abaixo é um exemplo de [tipo de texto: abstract, introdução, revisão de literatura, metodologia, etc.] particularmente bem escrito. Quero aprender a estrutura que o produziu.

Texto:

[cole o texto que você admira]

Tarefa

1. Estrutura invisível: identifique a arquitetura retórica do texto. Divida em blocos funcionais (contextualização, tensão, gap, proposta, método, contribuição, etc.). Mostre onde cada bloco começa e termina.

2. Movimentos argumentativos: em cada bloco, que movimento o autor faz? Exemplo: "estabelece consenso", "introduz dúvida", "desloca foco", "propõe síntese".

3. Vocabulário discursivo: que verbos, conectores e marcadores de hedging o autor usa? Liste 10.

4. Prompt reverso: escreva o prompt que, se dado a um aluno iniciante que tivesse acesso a toda a literatura da área, teria produzido um texto com essa mesma estrutura, esse mesmo tipo de movimento argumentativo, e esse mesmo nível de sofisticação. O prompt deve ter:
   - System prompt (papel e restrições).
   - Instrução principal.
   - Critérios de saída.
   - Armadilhas a evitar.

5. Teste: aplique seu próprio prompt reverso a um contexto novo (use o tema [meu tema]) e gere um texto exemplo. Compare com o original. Onde seu prompt está incompleto? Ajuste.
```

## O que destacar ao vivo

- Mostrar que prompts bons são baseados em movimentos retóricos, não em instruções genéricas.
- Comentar: "A craft moderna de escrever acadêmico é também a craft de prompt. Vocês ainda não viram isso em aula porque é novo."

## Aplicação prática

Construa uma biblioteca pessoal de prompts reversos:
- `prompts/abstract-estilo-nature.md`
- `prompts/introducao-estilo-ARS.md` (Annual Review of Sociology)
- `prompts/metodologia-qualitativa-estilo-qrj.md`

Reutilize em cada novo capítulo ou artigo.

## Cuidados

- Prompt reverso ajuda a replicar forma, não conteúdo. Você ainda precisa ter ideia própria.
- Não use para "copiar" outro autor. Use para entender o que você admira e transpor para seu próprio trabalho.
- Não declare o prompt reverso como único responsável pelo texto final. Declaração de uso deve registrar que você usou esse método.
