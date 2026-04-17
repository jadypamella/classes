# Demo 9: Claude e Claude Skills

## Por que esse demo existe

Os 7 movimentos são prompts. Prompts são ferramenta. A pesquisadora que usa prompts é mais rápida que a que não usa, mas ainda está reescrevendo a mesma coisa toda semana.

O passo seguinte é parar de escrever prompts e começar a escrever **skills**: pacotes reutilizáveis que o agente carrega quando reconhece o padrão da tarefa. Você deixa de digitar "age como revisor 2 hostil, encontre a falha fatal..." e passa a dizer "roda red-team no capítulo 3". A skill faz o resto.

Isso ainda não é mainstream na pós-graduação. Justamente por isso vale mostrar.

## O ecossistema em 3 nomes

**[Claude](https://claude.ai)**
O modelo da Anthropic. Acessado pelo navegador ou app. É com o que você já conversa.

**[Claude Code](https://docs.claude.com/en/docs/claude-code)**
Um agente no terminal que vive dentro dos seus arquivos. Útil para pesquisadora que organiza a tese em markdown, usa Zotero com BibTeX, mantém scripts de análise. Lê e edita o repositório inteiro, não só a conversa.

**[Claude Skills](https://www.anthropic.com/news/skills)**
Skills são arquivos markdown com YAML frontmatter que o Claude carrega automaticamente quando a descrição da skill bate com a tarefa. Em vez de você escrever o prompt, a skill já está lá. Em vez de copiar prompt entre conversas, você versiona a skill no seu repositório.

Especificação aberta em [agentskills.io](https://agentskills.io). Funciona em Claude Code, [Codex CLI](https://github.com/openai/codex), [OpenCode](https://github.com/opencode-ai/opencode) e outros clientes.

## Anatomia de uma skill

Pasta com três partes:

```
minha-skill/
├── SKILL.md          # descrição + instruções principais
├── scripts/          # opcional: scripts que a skill pode rodar
└── templates/        # opcional: arquivos de apoio
```

O SKILL.md começa com YAML:

```yaml
---
name: banca-sintetica
description: Simula membros da banca lendo capítulos de tese,
  usando os artigos publicados por eles como base. Dispara quando
  o usuário pede "banca sintética", "simula o Prof. X",
  "o que meu orientador falaria sobre isso".
---
```

Depois do YAML, vem o corpo: o prompt, as regras, o passo a passo. O Claude carrega a skill sempre que a `description` bate com o contexto da conversa. Você não precisa invocar à mão.

## Skill de banca sintética (pronta para copiar)

```markdown
---
name: banca-sintetica
description: Simula um membro da banca lendo capítulo de tese,
  usando os artigos publicados pelo próprio membro como combustível.
  Use quando o usuário disser "banca sintética", "simula o Prof. X",
  "o que o orientador falaria disso", "revisão no estilo da [pessoa]".
---

# Banca sintética

## Pré-requisito
O usuário deve ter anexado (ou referenciado) os textos do membro
da banca cujo estilo será simulado. Se não houver corpus, pedir
ao usuário antes de prosseguir.

## Comportamento

Você atua como o autor do corpus anexado. Estude:
- O vocabulário recorrente.
- Os critérios metodológicos aplicados.
- As referências citadas em múltiplas obras.
- As objeções típicas que esse autor faz em resenhas.

não elogie. não sugira melhorias. Sua tarefa é identificar:

1. As 5 objeções metodológicas mais prováveis, em ordem de severidade.
2. As 3 referências esperadas que provavelmente não estão citadas.
3. O ponto fraco de argumentação que esse autor não perdoaria.
4. Uma pergunta cruel que ele faria na arguição.

Para cada item, cite literalmente (entre aspas) a passagem da obra
anexada que justifica sua previsão. Sem citação direta, o item
perde valor.

## Saída

Formato em 4 blocos numerados. Máximo 600 palavras. Sem rodapés
amigáveis no final do tipo "espero que ajude".
```

Salve esse arquivo como `banca-sintetica/SKILL.md` dentro da sua pasta de skills. Da próxima vez que você disser "roda a banca sintética no capítulo 3 com os artigos do Prof. X anexados", o Claude carrega isso sem você pedir.

## Outras skills óbvias para a pós

Aplicando a mesma lógica aos outros 6 movimentos:

- `red-team-tese/SKILL.md`, para hostilidade configurada.
- `literatura-fantasma/SKILL.md`, para detectar ausências no corpus.
- `cartografia-controversias/SKILL.md`, para mapear o debate.
- `paper-que-deveria-existir/SKILL.md`, para descrever o gap.
- `dialogo-longitudinal/SKILL.md`, para conversar com o eu-de-antes.
- `prompt-reverso/SKILL.md`, para engenharia reversa de excelência.

Cada uma é um arquivo. No fim do primeiro semestre do doutorado, você tem seu próprio sistema.

## Onde encontrar skills abertas

- **[awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code)**: lista curada, atualizada, organizada por categoria.
- **[obsidian-skills](https://github.com/kepano/obsidian-skills)**: exemplo real, skills para trabalhar com vault de notas.
- **[agentskills.io](https://agentskills.io)**: a especificação. Vale ler para entender o porquê das escolhas.

## Por que isso é wow na aula

Os alunos acham que IA é digitar no chatbot. A skill mostra que:

1. IA pode ser versionada, igual código.
2. Prompts podem virar artefato metodológico publicável (lembra o argumento do slide de ética?).
3. Pesquisador que mantém um repositório de skills constrói metodologia autoral, não depende da próxima versão do modelo.

Esse é o ponto alto da aula para quem é tech-curious, e o momento em que até os céticos param de mexer no celular.

## Cuidado

Skills são poderosas mas também replicam vieses. Se a skill de banca sintética está calibrada em cima do seu estilo, ela vai produzir crítica no seu estilo, e não no estilo real da banca. Revise manualmente as skills a cada 3 ou 6 meses.

E, como tudo que virou código: skills compartilhadas precisam de licença. Se publicar skills suas, declare. Se usar skills alheias, respeite a licença original.
