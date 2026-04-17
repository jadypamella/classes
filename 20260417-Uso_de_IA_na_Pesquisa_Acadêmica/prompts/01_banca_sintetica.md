# Método 1: Banca sintética

> *"Leia o capítulo 3 como se você fosse o Prof. X, autor de [artigo]. Aponte as 5 objeções mais prováveis em ordem de severidade."*

## Objetivo
Transformar a IA numa simulação calibrada de leitores específicos (banca, orientador, revisor), usando como combustível os textos que eles mesmos publicaram.

## Quando usar
- 2 a 3 meses antes da qualificação.
- 1 mês antes de submissão em periódico, simulando o perfil do editor.
- Antes de reunião com orientador, para antecipar objeções.

## Ferramentas recomendadas
- **[Claude Projects](https://claude.ai/projects)** ou **[NotebookLM](https://notebooklm.google.com)**: melhor para corpus grande (10 a 30 artigos).
- **[ChatGPT](https://chatgpt.com) com Custom GPT**: se você quer reutilizar a persona em várias sessões.

## Passo a passo

1. **Reúna o corpus** de cada membro da banca:
   - Os 5 artigos mais citados do [Google Scholar](https://scholar.google.com).
   - A tese ou livro central deles.
   - 2 artigos recentes (últimos 2 anos), para captar posições atuais.

2. **Crie um projeto separado por banca** ([Claude Projects](https://claude.ai/projects)) ou notebook ([NotebookLM](https://notebooklm.google.com)). Não misture os corpus.

3. **Use o prompt abaixo**, substituindo [PROF X] e colando o fragmento da sua tese.

4. **Leia a resposta criticamente**. A IA pode errar o estilo. O que importa é se as objeções são plausíveis.

## Prompt

```
Você vai atuar como o [Prof. X], autor dos textos anexados. Estude o vocabulário, os critérios metodológicos, as referências recorrentes, e as objeções típicas que este autor faz em resenhas e debates.

Abaixo está um fragmento do capítulo [N] de uma tese que você foi convidado a avaliar. Você não deve elogiar. Não deve sugerir melhorias. Sua tarefa é identificar:

1. As 5 objeções metodológicas mais prováveis que o Prof. X levantaria, em ordem de severidade.
2. As 3 referências que o Prof. X certamente esperaria ver citadas e provavelmente não estão.
3. O principal ponto fraco de argumentação que o Prof. X não perdoaria.
4. Uma pergunta cruel que o Prof. X faria na arguição, dessas que travam o candidato.

Para cada item, cite literalmente (entre aspas) a passagem da obra anexada que justifica sua previsão.

Fragmento da tese:
[cole o fragmento aqui]
```

## Variações

**Orientador sintético**: se seu orientador não está respondendo, suba os textos dele e pergunte "o que o Prof. X me falaria se lesse isso agora?"

**Revisor de revista**: suba os 20 artigos mais citados publicados na revista-alvo. Pergunte "qual seria o parecer do revisor 2 mais experiente da [Revista X]?"

**Eu do futuro**: suba seu próprio trabalho. "Leia como se você fosse eu em 2029, depois do doutorado. O que o eu-de-2029 criticaria no eu-de-2026?"

## Cuidados

- Nunca use isso para atribuir opiniões reais a pessoas reais. É simulação calibrada, não oráculo.
- Não cite a resposta da IA em texto público como se fosse do Prof. X.
- Guarde os prompts para sua declaração de uso de IA.
