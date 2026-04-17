# IA na pesquisa: os 7 movimentos

**Aula de 30 min · UnB · Mestrandos e doutorandos**

Material para levar para casa. Aplique UM dos movimentos nos próximos 7 dias. Não tente aplicar todos.

---

## Os 7 movimentos (mais o bônus)

| # | Movimento | Use quando |
|---|-----------|------------|
| 1 | **Banca sintética** | Antes da qualificação ou defesa |
| 2 | **Triangulação multi-modelo** | Ao enfrentar questão metodológica disputada |
| 3 | **Literatura fantasma** | Ao fechar a revisão de literatura |
| 4 | **Red-team da própria tese** | Antes de submeter artigo |
| 5 | **Cartografia de controvérsias** | No começo do projeto |
| 6 | **O paper que deveria existir** | Ao procurar pergunta de pesquisa |
| 7 | **Diálogo longitudinal** | Quando você esqueceu o que pensou antes |
| 8 | **Prompt reverso** (bônus) | Ao encontrar paper que admira |

---

## Ferramentas principais

### Gerais
- **[Claude](https://claude.ai)**, conversas longas e análise profunda.
- **[ChatGPT](https://chatgpt.com)**, versátil, com Code Interpreter.
- **[Gemini](https://gemini.google.com)**, integrado ao Google Workspace.
- **[DeepSeek](https://chat.deepseek.com)**, alternativa com perspectiva asiática.

### Pesquisa específica
- **[NotebookLM](https://notebooklm.google.com)**, leitura de corpus grande.
- **[Elicit](https://elicit.com)**, revisão sistemática assistida.
- **[Consensus](https://consensus.app)**, respostas a partir de papers.
- **[Perplexity](https://perplexity.ai)** (modo acadêmico), busca com citações reais.
- **[Undermind](https://undermind.ai)**, busca científica profunda.
- **[SciSpace](https://scispace.com)**, explica termos complexos de papers.
- **[ResearchRabbit](https://researchrabbitapp.com)**, mapa de citações.
- **[Connected Papers](https://connectedpapers.com)**, grafo de papers correlatos.
- **[Inciteful](https://inciteful.xyz)**, descoberta de papers por rede.
- **[Semantic Scholar](https://semanticscholar.org)**, busca com TLDRs.
- **[Scite](https://scite.ai)**, mostra se citação é suportiva ou crítica.
- **[Scholarcy](https://scholarcy.com)**, resumo automático de papers.
- **[Humata](https://humata.ai)**, Q&A com PDFs.
- **[ChatPDF](https://chatpdf.com)**, conversa com PDF, grátis.

### Qualitativo e entrevistas
- **[Whisper](https://openai.com/research/whisper)** (OpenAI) ou **[Otter](https://otter.ai)**, transcrição.
- **[MAXQDA AI Assist](https://maxqda.com/products/ai-assist)**, **[NVivo](https://lumivero.com/products/nvivo)**, **[ATLAS.ti](https://atlasti.com)**, análise qualitativa com IA.

### Quantitativo
- **[Julius](https://julius.ai)**, análise estatística com IA.
- **[Rows](https://rows.com)**, planilha com IA integrada.
- **[Claude](https://claude.ai) / [ChatGPT](https://chatgpt.com)** com ferramenta de código.

### Dados sensíveis (privacidade)
- **[Ollama](https://ollama.com)** + Llama 3.3 ou Qwen 2.5, rodando localmente.
- **[LM Studio](https://lmstudio.ai)**, interface amigável para modelos locais.

### Escrita acadêmica
- **[Paperpal](https://paperpal.com)**, **[Writefull](https://writefull.com)**, específicos para pesquisa.
- **[DeepL Write](https://deepl.com/write)**, reescrita.
- **[Grammarly](https://grammarly.com)**, revisão gramatical.

### Gestão bibliográfica
- **[Zotero](https://zotero.org)** com plugins **[ARIA](https://github.com/lifan0127/ai-research-assistant)** e **[ZotFile](http://zotfile.com)**.
- **[Mendeley](https://mendeley.com)**, alternativa ao Zotero.

### Slides e apresentação
- **[Gamma](https://gamma.app)**, **[Tome](https://tome.app)**, **[SlidesGPT](https://slidesgpt.com)**, **[Beautiful.AI](https://beautiful.ai)**.

---

## Atenção, pós-graduando

- **Qualificação e defesa**: banca sintética é útil antes, não depois.
- **Qualis/Capes**: IA ajuda a traduzir, não transforma argumento fraco em A1.
- **Revisão sistemática**: IA acelera PRISMA, não substitui julgamento. Registre no [PROSPERO](https://www.crd.york.ac.uk/prospero/).
- **CEP/CONEP**: dados sensíveis não vão para API comercial. Use [Ollama](https://ollama.com) ou anonimize.
- **Autoplágio**: IA detecta overlap entre seus próprios textos. Periódicos usam [iThenticate](https://ithenticate.com).
- **Tese por artigos**: mapeie cada capítulo como paper com revista-alvo diferente.

---

## Ética: declaração de uso (modelo)

> "Este trabalho utilizou [modelo] nas seguintes etapas: [mapeamento de literatura, revisão de estilo, tradução, geração de exemplos]. Todos os argumentos, análises e conclusões são de autoria humana. Prompts relevantes estão arquivados em [link]."

Adote agora. Vai virar obrigação em breve.

---

## Riscos a lembrar

- **Alucinação de referências**: sempre verificar no [Google Scholar](https://scholar.google.com) ou [DOI](https://doi.org).
- **Viés anglófono**: pedir explicitamente autores do Sul Global, mulheres, perspectivas críticas.
- **Sycophancy**: a IA concorda com você. Configure para hostilidade quando precisar.
- **Detectores de IA**: falso positivo alto. Não use como prova única.

---

## Para começar amanhã

1. Escolha UM movimento que combina com o problema do seu capítulo atual.
2. Abra o prompt correspondente no pacote de prompts (ver QR code).
3. Execute. Guarde a resposta num arquivo `prompts-que-funcionam.md`.
4. Em 30 dias, reveja o arquivo. Você terá sua metodologia autoral.

---

## Nível 2: Claude e Claude Skills

Se os prompts viraram rotina, o passo seguinte é pacote-los em **[Claude Skills](https://www.anthropic.com/news/skills)**. Skill é um markdown com YAML no topo que o [Claude Code](https://docs.claude.com/en/docs/claude-code) carrega automaticamente quando reconhece o padrão da tarefa.

Cada um dos 7 movimentos pode virar uma skill. Você deixa de copiar prompt e passa a dizer "roda a banca sintética no capítulo 3". A especificação é aberta em [agentskills.io](https://agentskills.io). Exemplos prontos em [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) e [obsidian-skills](https://github.com/kepano/obsidian-skills).

Pesquisador que mantém um repositório próprio de skills constrói método autoral. Daqui a alguns anos, vai ser o equivalente do `.bib` de hoje.

---

## Material completo

Todos os prompts, demos detalhados e roteiro estão em:

**[QR code aqui]**

Dúvidas: jadypbs@gmail.com

---

*A pergunta não é mais "posso usar IA?". É: você consegue competir com quem usa melhor que você, sem terceirizar o que te torna pesquisador?*
