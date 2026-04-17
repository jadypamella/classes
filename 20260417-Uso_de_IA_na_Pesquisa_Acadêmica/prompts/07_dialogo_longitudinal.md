# Demo 7: Diálogo longitudinal

## Objetivo
Conversar com o próprio pesquisador que você foi há 1, 2 ou 5 anos. Detectar a evolução silenciosa da sua tese, o que você abandonou sem perceber, o que seu eu-de-antes diria sobre seu eu-de-hoje.

## Quando usar
- No meio do doutorado, quando você não lembra mais por que tomou decisões iniciais.
- Antes da qualificação, para escrever a seção de objetivos que ainda faz sentido.
- Quando o tema saiu do controle e você não sabe mais qual era a pergunta original.

## Ferramentas recomendadas (critério de privacidade)

**Se suas notas contêm dados sensíveis** (identificação de entrevistados, material inédito de terceiros, informação confidencial de instituição parceira):
- **[Ollama](https://ollama.com)** + modelo Llama 3.3 ou Qwen 2.5 rodando local.
- **[LM Studio](https://lmstudio.ai)** com Mistral ou outro modelo aberto.
- Jamais subir em API comercial sem anonimizar.

**Se suas notas são só suas próprias reflexões** (sem terceiros identificáveis):
- **[Claude Projects](https://claude.ai/projects)** (conta paga recomendada).
- **[NotebookLM](https://notebooklm.google.com)** com conta acadêmica Google.

## Pré-requisito crítico
Você precisa ter arquivado o que pensou antes. Se você não guarda notas, rascunhos e versões, esse movimento não funciona. Dica para o futuro: abra um arquivo diário na primeira semana do mestrado e nunca mais feche.

## O que subir

- Rascunhos e versões antigas da tese (cada versão nomeada com data).
- Fichamentos de leituras antigas.
- Notas de reuniões com orientador.
- Diário de pesquisa (se tiver).
- E-mails importantes sobre a pesquisa (exportar do Gmail, filtrar).
- Apresentações antigas (seminários, congressos).
- Pré-projeto de entrada no programa.

Organize em pastas com data clara.

## Prompt

```
Você vai ajudar a comparar o pesquisador que escreveu os textos de [ano anterior] com o pesquisador que escreve hoje [ano atual]. O corpus anexado inclui rascunhos, fichamentos, notas de reunião e versões antigas da tese.

Tarefa

Responda 6 perguntas, sempre citando literalmente (entre aspas) a passagem que justifica cada resposta:

1. Como a pergunta de pesquisa evoluiu? Qual era a pergunta original? Qual é a pergunta hoje? Em que momento ela mudou?

2. Quais posições foram abandonadas sem justificativa? Encontre afirmações, autores ou abordagens que apareciam antes e sumiram, sem que o autor tenha explicado por quê.

3. Que ideias tive e não desenvolvi? Identifique hipóteses, intuições ou linhas de investigação mencionadas e nunca retomadas.

4. Onde o autor de hoje contradiz o autor de antes sem reconhecer a contradição? Liste as 5 principais.

5. Qual era o entusiasmo original e se ele se perdeu? Há sinais textuais (adjetivos, exclamações, comprometimento) que mudaram?

6. Se o autor de [ano anterior] lesse o texto de hoje, qual seria a crítica mais dura que ele faria?

Ao final, produza um parágrafo de carta escrito na voz do autor de [ano anterior], endereçado ao autor de hoje, apontando o que ele acha que se perdeu no caminho.
```

## O que destacar ao vivo

- Esse é o movimento que mais emociona. Avisar: "Pode ser desconfortável."
- Mostrar a "carta do eu-anterior" como o ponto alto.
- Comentar: "Pesquisa de pós é longa. Você perde a memória de você mesmo. Essa ferramenta é nova na história. Nosso orientador não teve isso."

## Variações

**Diálogo com orientador-aliado-histórico**: subir todas as trocas com orientador. Perguntar "em que ponto o orientador concordou e em que ponto houve atrito não resolvido?"

**Diálogo com leitura antiga**: subir um fichamento de livro feito há 3 anos. Ler hoje o mesmo livro. Perguntar "como minha leitura mudou?"

**Diálogo com autor original**: se você está trabalhando com teoria de um autor específico, subir a obra completa. Perguntar: "se o autor lesse meu capítulo 4, que crítica ele faria à minha aplicação da teoria?"

## Cuidados

- Se usar API comercial, anonimize nomes de terceiros citados em suas notas.
- Nunca use dados de entrevistas identificáveis sem aprovação CEP para esse uso.
- As respostas da IA são hipóteses sobre sua própria evolução. Você decide o que fazer com elas.

## Uso terapêutico

Avisada a audiência: esse movimento não é só ferramenta, é espelho. Algumas pessoas choram. Tudo bem. A pesquisa de doutorado é processo longo e solitário; redescobrir sua voz de anos atrás pode ser reconciliador.
