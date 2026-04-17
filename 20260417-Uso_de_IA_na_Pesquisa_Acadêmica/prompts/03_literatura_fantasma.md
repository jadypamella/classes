# Demo 3: Literatura fantasma

## Objetivo
Detectar o que está ausente da sua revisão de literatura. A revisão reproduz os vieses de quem fez. A IA vê o ponto cego porque não está no seu ponto cego.

## Quando usar
- Antes de fechar a revisão de literatura da qualificação.
- Antes de enviar artigo para revista internacional (revistas de impacto pedem diversidade de citações).
- Quando o orientador disse "falta alguma coisa" mas não soube dizer o quê.

## Ferramentas recomendadas
- **[Claude Projects](https://claude.ai/projects)** ou **[NotebookLM](https://notebooklm.google.com)** para subir as referências.
- **[Elicit](https://elicit.com)** e **[Consensus](https://consensus.app)** para validar autores sugeridos.

## Passo a passo

1. Exporte sua lista de referências do [Zotero](https://zotero.org) em formato BibTeX ou RIS.
2. Suba no [Claude Projects](https://claude.ai/projects) ou [NotebookLM](https://notebooklm.google.com).
3. Rode o prompt principal.
4. Valide as sugestões: toda sugestão vai para o Scholar para confirmar existência.
5. Leia os autores realmente sugeridos. A IA pode errar. Seu julgamento filtra.

## Prompt principal

```
Anexei a lista completa de referências de uma revisão de literatura sobre [tema específico, 2 a 3 linhas].

Sua tarefa não é validar o que está aqui. É identificar o que está ausente.

Estruture a resposta em 5 blocos, cada um com 3 a 5 itens justificados:

1. Autores ausentes que o campo considera obrigatórios neste recorte, e não aparecem.
2. Disciplinas adjacentes que teriam contribuição relevante e foram ignoradas (ex: sociologia se a tese é de engenharia; estudos de gênero se a tese é de saúde pública).
3. Geografias ausentes: literatura do Sul Global, brasileira, ibero-americana, africana, asiática. Sinalize se o corpus atual é majoritariamente anglófono.
4. Contra-argumentos ausentes: quem discorda das posições que esta revisão adota e não foi citado.
5. Períodos ausentes: há décadas inteiras sem citação? Algum debate clássico foi pulado?

Para cada item, indique a razão pela qual seria relevante E a fonte exata (autor, ano, título plausível). Se você não tem certeza de que a fonte existe, marque com [VERIFICAR].
```

## O que destacar ao vivo

- A instrução "[VERIFICAR]" é crítica. Ela disciplina a IA a admitir incerteza em vez de alucinar referências.
- Mostrar que o viés anglófono aparece em quase 100% das revisões feitas por pós-graduandos brasileiros. Não é pessoal, é estrutural.
- Comentar que esse movimento responde diretamente à pressão de banca por "diversidade de referências".

## Prompt complementar para diversidade

```
Revise o corpus novamente com foco específico em:

1. Autoras mulheres que contribuíram para este debate.
2. Pesquisadores brasileiros e latino-americanos relevantes que publicaram em português ou espanhol.
3. Autores indígenas, negros ou de comunidades historicamente sub-representadas.
4. Perspectivas críticas ou decoloniais que complicariam as conclusões.

Liste 10 nomes com a obra mais relevante de cada um. Marque [VERIFICAR] para qualquer incerteza.
```

## Validação

Toda sugestão da IA passa por três filtros:
1. **Existe?** Busque no [Google Scholar](https://scholar.google.com), [Lattes](http://lattes.cnpq.br) ou [ORCID](https://orcid.org).
2. **É relevante?** Leia o resumo. Se encaixa no recorte, citar.
3. **Está no idioma?** Se é texto em espanhol ou português relevante e seu corpus é só em inglês, incluir é bônus de diversidade.

## Cuidados

- IA também tem viés. Vai sugerir mais autores do Norte Global se você não pedir explicitamente.
- Ganhos reais aparecem quando você pede múltiplas passadas com focos diferentes (método, geografia, gênero, disciplina).
- Sugestão não é citação. Você ainda precisa ler, entender e citar corretamente.
