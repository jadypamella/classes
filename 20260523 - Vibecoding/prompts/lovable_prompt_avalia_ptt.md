# One-shot prompt para o Lovable — AvaliaPTT (análise de Produto Técnico Tecnológico, Área 27 da CAPES)

Prompt completo para colar no Lovable. Reproduz a ficha oficial de qualificação de PTT da **Área 27 da CAPES** (Administração Pública e de Empresas, Ciências Contábeis e Turismo), conforme a **Ficha de Avaliação 2025 da Área 27**, válida para o quadriênio 2021-2024. O pesquisador descreve seu produto, responde os 5 critérios oficiais (aderência, impacto, aplicabilidade, inovação, complexidade), e o sistema calcula o estrato sugerido entre **TA1 e TB4** (oito níveis, análogos a A1-B4 do Qualis Periódicos).

Stack alinhada ao que o Lovable constrói bem: React, TypeScript, Tailwind, shadcn/ui, lucide-react, framer-motion e Supabase. Tudo em português, dados de exemplo, sem dado pessoal real.

> Toda a lógica de pontuação, faixas de estrato e definições de níveis abaixo está copiada da seção 4 "Considerações sobre a qualificação de produtos técnicos/tecnológicos" da Ficha de Avaliação 2025 da Área 27 da CAPES, páginas 35 a 41. Fonte oficial: ver lista no final do prompt.

---

## Objetivo

Construa um web app sóbrio, acadêmico e responsivo chamado AvaliaPTT.

O AvaliaPTT é uma ferramenta de autoavaliação de Produto Técnico Tecnológico (PTT) para pesquisadores e coordenadores de programas da Área 27 da CAPES (Administração Pública e de Empresas, Ciências Contábeis e Turismo). O usuário cadastra um PTT, responde um questionário guiado pelos cinco critérios oficiais da Ficha de Avaliação 2025 (quadriênio 2021-2024), e o sistema calcula uma sugestão de estrato (TA1 a TB4), explica como chegou nessa sugestão e permite exportar um relatório.

Resultado principal:
- Pesquisador cadastra um PTT com tipo, título, descrição, programa e linha de pesquisa.
- Pesquisador responde o questionário em cinco blocos, um por critério.
- Sistema calcula sugestão de estrato, mostra a justificativa por critério e gera relatório.

Fora de escopo (não implementar):
- Submissão oficial à CAPES ou integração com Sucupira ou Lattes.
- Avaliação por pares ou múltiplos avaliadores.
- Outras áreas CAPES. A lógica padrão é da Área 27. Outras áreas usam ficha diferente.
- Pagamento, planos, cobrança.
- Envio de email, SMS ou notificação push.

Restrições importantes:
- O resultado é uma sugestão de autoavaliação, nunca uma classificação oficial. A qualificação oficial é feita por comissão mista de acadêmicos e profissionais designada pela CAPES. Deixe isso explícito em todo lugar visível.
- A lógica padrão segue a Ficha de Avaliação 2025 da Área 27 (Administração Pública e de Empresas, Ciências Contábeis e Turismo), válida para o quadriênio 2021-2024. Cada área CAPES define sua própria ficha; outras áreas usam estratos e pesos diferentes.
- Use dados de exemplo. Nenhum dado pessoal real.
- Valide toda entrada antes de gravar.
- Use variáveis de ambiente para configuração (URL e chaves do Supabase). Nunca hardcode chaves no código.
- Use ícones da `lucide-react` para tudo. Nunca renderize emoji na interface.
- Não use travessão (—) em texto de UI ou documentação. Use vírgula, ponto ou dois-pontos.

---

## Lógica oficial da Área 27 (copiada da Ficha de Avaliação 2025)

Esta é a base obrigatória do app. Implemente exatamente como descrito. Os textos abaixo foram extraídos da seção 4 da Ficha de Avaliação 2025 da Área 27 da CAPES (`ADM_FICHA_DE_AVALIACAO_v1.pdf`, páginas 35 a 41), publicada pela DAV/CAPES para a avaliação do quadriênio 2021-2024. Mostre uma versão resumida desta seção na página de Metodologia, com link para o PDF oficial.

### Estratos

Oito estratos, análogos ao Qualis Periódicos: TA1, TA2, TA3, TA4, TB1, TB2, TB3, TB4. A soma das pontuações dos critérios totaliza 100 pontos. Faixas oficiais:

| Pontuação mínima | Estrato |
|---|---|
| ≥ 87,5 | TA1 |
| ≥ 75,0 | TA2 |
| ≥ 62,5 | TA3 |
| ≥ 50,0 | TA4 |
| ≥ 37,5 | TB1 |
| ≥ 25,0 | TB2 |
| ≥ 12,5 | TB3 |
| < 12,5 | TB4 |

Se a aderência falhar, o PTT **não é qualificável** (não recebe estrato). Exiba uma marca distinta para esse caso.

### Critério 1: Aderência (eliminatório)

Relação ou afinidade da produção com a área de concentração do programa, em especial:
- (a) Aderência do produto às linhas de pesquisa ou atuação do programa.
- (b) Aderência do produto aos projetos de pesquisa, inovação ou desenvolvimento tecnológico do programa.

Implementação: duas perguntas Sim/Não. Se qualquer uma for Não, o PTT é marcado como **não qualificável** e o cálculo é interrompido. Mostre uma mensagem em destaque vermelho explicando o motivo. Permita que o usuário continue preenchendo o restante apenas para registro.

### Critério 2: Impacto (Peso: 25%)

Transformação causada pelo PTT no ambiente (organização, comunidade, localidade) ao qual se destina.

Dois subitens, cada um com pontos 0, 5, 10 ou 15:

**Impacto realizado (peso interno 60%)**
- Ausência de impacto: 0
- Baixo impacto: 5
- Médio impacto: 10
- Alto impacto: 15

**Impacto potencial (peso interno 40%)**
- Ausência de impacto: 0
- Baixo impacto: 5
- Médio impacto: 10
- Alto impacto: 15

Score interno do critério (0 a 15): `impacto_realizado * 0,6 + impacto_potencial * 0,4`.

Peça uma descrição textual do motivo de criação, da relevância da questão do demandante e do foco de aplicação. Esse texto entra no relatório.

### Critério 3: Aplicabilidade (Peso: 25%)

Facilidade com que se pode empregar o PTT para alcançar seus objetivos específicos e sua capacidade de ser replicado em outros contextos.

Três subitens, cada um com pontos 0, 5, 10 ou 15:

**Aplicabilidade realizada (peso interno 40%)**
- Não aplicada: 0
- Baixa: 5
- Média: 10
- Alta: 15

**Aplicabilidade potencial (peso interno 20%)**
- Não aplicável: 0
- Baixa: 5
- Média: 10
- Alta: 15

**Replicabilidade (peso interno 40%)**
- Não replicável: 0
- Restrita: 5
- Irrestrita: 10
- Escalável: 15

Score interno do critério (0 a 15): `aplicabilidade_realizada * 0,4 + aplicabilidade_potencial * 0,2 + replicabilidade * 0,4`.

### Critério 4: Inovação (Peso: 25%)

Intensidade do conhecimento inédito na criação e desenvolvimento do produto.

Um único item, com pontos 0, 5, 10 ou 15:
- Sem inovação: 0
- Baixo teor de inovação (inovação adaptativa, utilização de conhecimento pré-existente): 5
- Médio teor de inovação (inovação incremental, modificação de conhecimentos pré-estabelecidos): 10
- Alto teor de inovação (inovação radical, mudança de paradigma): 15

Score interno do critério (0 a 15) é diretamente o valor escolhido.

Peça uma breve justificativa em texto.

### Critério 5: Complexidade (Peso: 25%)

Grau de interação dos atores, relações e conhecimentos necessários à elaboração e ao desenvolvimento do produto.

Um único item, com pontos 0, 5, 10 ou 15:
- Não complexo: 0
- Baixa complexidade (combinação de conhecimento pré-existente por atores diferentes ou não): 5
- Média complexidade (alteração ou adaptação de conhecimentos pré-estabelecidos por atores diferentes): 10
- Alta complexidade (associação de novos conhecimentos e diferentes atores, como laboratórios e empresas, para solução de problemas): 15

Score interno do critério (0 a 15) é diretamente o valor escolhido.

### Cálculo do total

Cada critério (Impacto, Aplicabilidade, Inovação, Complexidade) tem peso de 25% e contribui com até 25 pontos no total. A conversão de score interno (0 a 15) para pontos do critério (0 a 25) é proporcional:

```
pontos_criterio = score_interno * (25 / 15)
```

Soma dos quatro: `total = pontos_impacto + pontos_aplicabilidade + pontos_inovacao + pontos_complexidade`.

Total varia de 0 a 100. Use as faixas da tabela acima para definir o estrato sugerido. Se aderência falhar, marca **Não qualificável** em destaque vermelho, sem estrato.

### Limite de relato

No quadriênio 2021-2024, o coordenador de programa profissional deve relatar entre 1 e 3 PTTs por docente permanente, além de poder indicar PTTs entre os 10 destaques do PPG. O relato é feito no Módulo de Destaques da Plataforma Sucupira, com campo de observações para justificar a escolha do produto segundo os cinco critérios, acompanhado de documentos comprobatórios. Informe esse limite e a forma de relato no app como nota informativa, sem bloquear cadastros.

### Tipos de PTT considerados pela Área 27

O cadastro de PTT deve oferecer estas 12 categorias (use exatamente esses nomes, na ordem da Área 27):

1. Empresa ou organização social inovadora
2. Processo ou tecnologia não patenteável
3. Relatório técnico conclusivo
4. Tecnologia social
5. Marco regulatório ou norma
6. Patente ou registro de propriedade intelectual
7. Produto ou processo com sigilo
8. Software ou aplicativo
9. Base de dados técnico-científica
10. Curso de formação profissional
11. Material didático
12. Artigo técnico-tecnológico em veículo de difusão

Cada item com tooltip de definição curta.

---

## Identidade da marca

O AvaliaPTT é uma ferramenta acadêmica. Visual sóbrio, profissional, confiável. Não infantilize, não use linguagem promocional, não use exclamação.

Tom de voz:
- Direto, técnico, respeitoso.
- Frases curtas.
- Sem jargão promocional.
- Sem prometer aprovação ou sucesso na avaliação oficial.

Sem logo pronto. Crie um wordmark simples com a palavra `AvaliaPTT` em tipografia sóbria, com um ícone de medidor ou checklist da `lucide-react` ao lado (`Gauge`, `ClipboardCheck` ou `BarChart3`).

---

## Paleta de cores

Defina os valores como tokens no `tailwind.config` e em variáveis CSS. Use de forma semântica.

Paleta principal:
- Azul institucional: `#1E3A8A`
- Azul de ação: `#2563EB`
- Azul claro de apoio: `#DBEAFE`
- Verde de estrato alto: `#16A34A`
- Amarelo de estrato intermediário: `#CA8A04`
- Laranja de estrato baixo: `#EA580C`
- Vermelho de falha de aderência ou erro: `#DC2626`
- Cinza de texto principal: `#111827`
- Cinza de texto secundário: `#4B5563`
- Cinza de borda: `#E5E7EB`
- Fundo principal: `#FFFFFF`
- Fundo suave: `#F9FAFB`

Mapeamento semântico dos estratos:
- TA1 e TA2: verde
- TA3 e TA4: amarelo
- TB1 e TB2: laranja
- TB3 e TB4: vermelho atenuado
- Não qualificável: vermelho cheio

Não espalhe hex solto pelos componentes. Tudo vem dos tokens.

---

## Tipografia

- `Inter` para corpo, formulários, tabelas e textos auxiliares.
- `Plus Jakarta Sans` para títulos e cabeçalhos.
- Tabular numbers nas pontuações e estratos para alinhamento.
- Sem itálico decorativo. Negrito apenas em rótulos curtos e valores numéricos.

---

## Stack

Frontend:
- React com TypeScript
- Tailwind CSS com tokens para cores e tipografia
- shadcn/ui para formulários, tabs, cards, dialog, accordion
- `lucide-react` para todos os ícones
- `framer-motion` para microanimações em transições de etapa
- `recharts` para o gráfico radar de critérios

Backend:
- Supabase para banco (Postgres) e autenticação opcional por email
- Sem auth obrigatório no MVP. O app funciona com identificação por sessão local; se o usuário criar conta, os PTTs ficam vinculados.

Exportação:
- Botão de exportar para PDF usando impressão nativa do navegador com folha de estilo dedicada.
- Botão de exportar para Markdown copiando para a área de transferência.

Operação:
- Configuração por variáveis de ambiente: `VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`.
- `.gitignore` deve incluir `.env`, `.env.*` (exceto `.env.example`), `.claude/`, `node_modules/`, `dist/`, `build/`.
- Habilite Row Level Security (RLS) em todas as tabelas do Supabase. Crie policies explícitas para cada operação.
- Valide toda entrada antes de gravar.
- Tratamento de erro centralizado com mensagens curtas para o usuário e log estruturado no console.

---

## Conceitos centrais

Use estes nomes de entidade no código:
- `ptt`: o produto técnico tecnológico avaliado, com tipo, título, descrição, programa, linha de pesquisa, ano, motivo de criação, demandante.
- `assessment`: uma avaliação do PTT com respostas aos cinco critérios, estrato sugerido e justificativa.
- `criterion_response`: resposta a um critério específico (`adherence`, `impact`, `applicability`, `innovation`, `complexity`) com indicadores escolhidos, subscores internos e justificativa.
- `user_profile`: pesquisador opcional, com nome, programa, IES.

Status de uma avaliação:
- `draft`: em preenchimento.
- `completed`: questionário finalizado, com estrato calculado.
- `archived`: avaliação arquivada.

---

## Modelo de dados (Supabase)

Crie as tabelas necessárias. Toda tabela com RLS habilitada e policies explícitas.

`ptts`:
- `id`
- `user_id` (fk, opcional se anônimo)
- `session_id` (uuid de sessão local quando não há login)
- `type` (uma das 12 categorias da Área 27)
- `title`
- `description`
- `program_name`
- `research_line`
- `creation_motive` (texto, motivo de criação e relevância para o demandante)
- `application_focus` (texto, foco de aplicação)
- `year` (int)
- `author_name`
- `created_at`

`assessments`:
- `id`
- `ptt_id` (fk)
- `status` (`draft`, `completed`, `archived`)
- `adherence_passes` (boolean)
- `impact_points` (decimal, 0 a 25)
- `applicability_points` (decimal, 0 a 25)
- `innovation_points` (decimal, 0 a 25)
- `complexity_points` (decimal, 0 a 25)
- `total_points` (decimal, 0 a 100)
- `suggested_stratum` (`TA1`, `TA2`, `TA3`, `TA4`, `TB1`, `TB2`, `TB3`, `TB4`, `NOT_QUALIFIABLE`)
- `summary_text` (justificativa gerada)
- `completed_at`
- `created_at`

`criterion_responses`:
- `id`
- `assessment_id` (fk)
- `criterion` (`adherence`, `impact`, `applicability`, `innovation`, `complexity`)
- `selected_indicators` (jsonb com cada subitem e seu valor 0/5/10/15 e os Sim/Não da aderência)
- `internal_score` (decimal, 0 a 15)
- `criterion_points` (decimal, 0 a 25, exceto aderência)
- `justification` (texto livre)
- `created_at`

Regras de integridade:
- Um PTT pode ter várias avaliações (rascunhos e versões), mas só uma `completed` por vez.
- Se `adherence_passes` for falso, `suggested_stratum` é `NOT_QUALIFIABLE` e os demais pontos ficam zerados no resumo (mas as respostas seguem registradas em `criterion_responses`).
- Sanitize todo texto livre antes de gravar (limite de tamanho, remova caracteres de controle).

---

## Páginas e rotas

### 1. Landing page · `/`

Topo:
- Wordmark `AvaliaPTT` com ícone `Gauge` da `lucide-react`.
- Navegação: Como funciona, Critérios, Metodologia, Entrar.

Hero:
- Título: `Qualifique seu Produto Técnico Tecnológico pela Área 27 da CAPES.`
- Subtítulo: `Questionário guiado pelos cinco critérios oficiais. Sugestão de estrato TA1 a TB4 com justificativa por critério. Resultado exportável.`
- Botão principal: `Iniciar avaliação`.
- Botão secundário: `Ver metodologia`.
- Aviso em destaque, em caixa cinza: `O resultado é uma autoavaliação de referência baseada na Ficha de Avaliação 2025 da Área 27 da CAPES, válida para o quadriênio 2021-2024. A qualificação oficial cabe à comissão mista de acadêmicos e profissionais designada pela CAPES.`

Como funciona:
1. Cadastre seu PTT
2. Responda os cinco critérios
3. Veja o estrato sugerido
4. Exporte o relatório

Recursos:
- Os cinco critérios oficiais da Área 27 no mesmo fluxo
- Cálculo automático do estrato segundo as faixas oficiais
- Justificativa por critério
- Exportação em PDF e Markdown
- Histórico das avaliações

Para quem é:
- Mestrandos e doutorandos de programas profissionais e acadêmicos da Área 27
- Coordenadores de programa preparando o relato do quadriênio
- Orientadores planejando produção técnica de discentes
- Servidores em programas profissionais (Administração Pública) organizando seu portfólio

Chamada final:
- Botão: `Iniciar avaliação`

### 2. Painel · `/painel`

Lista os PTTs do usuário. Mostra:
- Tabela com título, tipo, ano, estrato sugerido (badge colorido) e ações (ver, editar, duplicar, arquivar).
- Botão `Novo PTT`.
- Cartões de resumo no topo: total de PTTs, distribuição por estrato (gráfico de barras horizontais), média de pontuação total.
- Nota informativa: `Limite oficial: até 3 PTTs por docente permanente no quadriênio.`

### 3. Novo PTT · `/painel/novo`

Formulário de cadastro:
- Tipo de PTT (select com as 12 categorias da Área 27, cada uma com tooltip explicativo).
- Título.
- Descrição (textarea).
- Programa de pós-graduação.
- Linha de pesquisa.
- Ano (entre 2021 e 2024 marcado como quadriênio padrão, mas livre).
- Motivo de criação e relevância para o demandante (textarea obrigatória, conforme exige o Ficha de Avaliação 2025 no critério Impacto).
- Foco de aplicação (textarea).
- Nome do autor principal (preenchido se houver login).

Validações:
- Todos os campos obrigatórios.
- Título com no máximo 250 caracteres.
- Descrição e motivo de criação com no mínimo 100 caracteres cada.

Ao salvar, redireciona para o questionário do critério 1 (aderência).

### 4. Questionário · `/painel/[pttId]/avaliar`

Fluxo de cinco etapas, uma por critério, com barra de progresso fixa no topo.

Cada etapa tem:
- Cabeçalho do critério com a definição oficial da CAPES copiada literalmente do Ficha de Avaliação 2025 (em card cinza claro).
- Perguntas em formulário.
- Campo de justificativa em texto livre.
- Botão `Voltar` e `Próximo`.
- Resumo lateral com o subscore parcial do critério (0 a 15 internamente, e a conversão para pontos do total, 0 a 25, exceto aderência).

Etapa 1: Aderência
- Pergunta a: O PTT é aderente às linhas de pesquisa ou atuação do programa? (Sim/Não)
- Pergunta b: O PTT é aderente aos projetos de pesquisa, inovação ou desenvolvimento tecnológico do programa? (Sim/Não)
- Se qualquer resposta for Não, mostre aviso vermelho: `Sem aderência o PTT não é qualificável pela Área 27.` Permita continuar para registro.

Etapa 2: Impacto
- Impacto realizado (radio com 4 opções: Ausência, Baixo, Médio, Alto).
- Impacto potencial (radio com 4 opções: Ausência, Baixo, Médio, Alto).
- Campo de evidência (textarea).
- Mostre cálculo do subscore em tempo real: `impacto_realizado * 0,6 + impacto_potencial * 0,4`.

Etapa 3: Aplicabilidade
- Aplicabilidade realizada (radio com 4 opções: Não aplicada, Baixa, Média, Alta).
- Aplicabilidade potencial (radio com 4 opções: Não aplicável, Baixa, Média, Alta).
- Replicabilidade (radio com 4 opções: Não replicável, Restrita, Irrestrita, Escalável).
- Campo de contexto de aplicação (textarea).
- Mostre cálculo do subscore em tempo real.

Etapa 4: Inovação
- Grau (radio com 4 opções: Sem inovação, Baixo, Médio, Alto). Cada opção com a definição oficial entre parênteses.
- Campo de justificativa (textarea).

Etapa 5: Complexidade
- Grau (radio com 4 opções: Não complexo, Baixa, Média, Alta). Cada opção com a definição oficial entre parênteses.
- Campo de justificativa (textarea).

Ao final, botão `Calcular estrato sugerido` leva ao resultado.

### 5. Resultado · `/painel/[pttId]/resultado`

Tela de saída da avaliação.

Topo:
- Estrato sugerido em destaque (badge grande, cor segundo paleta semântica).
- Pontuação total com uma casa decimal, em escala 0 a 100.
- Selo: `Autoavaliação. Não substitui qualificação oficial da comissão CAPES.`

Corpo:
- Gráfico radar com os quatro critérios pontuáveis em escala 0 a 25 (recharts).
- Cards expansíveis por critério, com:
  - Pontos do critério (0 a 25) e score interno (0 a 15).
  - Subitens escolhidos com os valores (0, 5, 10 ou 15).
  - Texto explicativo do que aquela combinação significa, citando a definição oficial.
  - Justificativa textual escrita pelo pesquisador.
- Card de aderência (separado, mostra Sim/Sim ou alerta de Não qualificável).
- Card de recomendações: pontos fortes e pontos a melhorar, gerados por regras simples (exemplos):
  - `Inovação baixa: descreva o avanço frente ao estado da arte e cite trabalhos comparáveis.`
  - `Impacto somente potencial: levante evidências mensuráveis (uso, citações, casos atendidos) para fortalecer o relato.`
  - `Replicabilidade restrita: documente o produto de forma que terceiros possam aplicar em contextos similares.`

Ações:
- Botão `Exportar para PDF` (usa `window.print` com folha de estilo dedicada).
- Botão `Copiar como Markdown`.
- Botão `Refazer avaliação`.
- Botão `Voltar ao painel`.

### 6. Metodologia · `/metodologia`

Página estática explicando:
- Que o app implementa a ficha de qualificação de PTT da Área 27 (Administração Pública e de Empresas, Ciências Contábeis e Turismo) da CAPES, conforme a Ficha de Avaliação 2025 publicada pela DAV/CAPES, válida para o quadriênio 2021-2024.
- Tabela dos 8 estratos com faixas de pontuação (exatamente como na seção "Lógica oficial da Área 27" acima).
- Tabela de cada critério com seus subitens e valores.
- Definições oficiais de cada nível (alto, médio, baixo de inovação e complexidade) copiadas do documento.
- Lista das fontes consultadas com links clicáveis (ver final do prompt).
- Aviso explícito: outras áreas CAPES (Enfermagem, Educação, Computação, etc.) usam estratos diferentes (T1 a T5 ou outros) e pesos diferentes. Este app cobre apenas a Área 27.

### 7. Histórico · `/painel/historico`

Lista todas as avaliações `completed` e `archived`, com filtros por estrato e por ano. Permite duplicar uma avaliação para refazer com ajustes.

---

## Componentes

Implemente como componentes pequenos e reutilizáveis:

- `AppShell`
- `Header`
- `HeroSection`
- `MethodologySection`
- `FeatureGrid`
- `AudienceGrid`
- `PttDashboard`
- `PttList`
- `PttSummaryCards`
- `PttForm`
- `AssessmentStepper`
- `CriterionCard`
- `IndicatorRadio`
- `JustificationField`
- `LiveSubscoreSummary`
- `StratumBadge`
- `RadarCriteriaChart`
- `CriterionResultCard`
- `AdherenceResultCard`
- `RecommendationsCard`
- `MethodologyTable`
- `PrintableReport`

---

## Interações obrigatórias

- Botão `Iniciar avaliação` na landing leva ao cadastro de novo PTT (cria sessão local se não houver login).
- Ao salvar o PTT, o sistema cria automaticamente um `assessment` em `draft`.
- O usuário pode sair no meio do questionário e voltar. Estado salvo a cada etapa.
- O resultado só é calculado depois das cinco etapas concluídas.
- Falha de aderência marca `NOT_QUALIFIABLE` e exibe alerta. Permite ver o que foi respondido nas demais etapas mas não atribui estrato.
- Exportação para PDF usa `window.print` em uma rota dedicada `/painel/[pttId]/relatorio` com folha de estilo `@media print`.
- Exportação para Markdown copia o conteúdo para a área de transferência e mostra confirmação.
- Refazer avaliação cria um novo `assessment` e arquiva o anterior.

---

## Responsividade

- A landing page funciona bem no desktop e no mobile.
- O questionário é responsivo, com etapas em uma coluna no mobile e duas colunas (formulário + resumo) no desktop.
- A tela de resultado é responsiva. No mobile, o gráfico radar fica no topo e os cards de critério empilham.
- Evite telas apertadas. Inputs com altura confortável, hierarquia visual clara, textos legíveis.

---

## Animações

Use `framer-motion` com moderação:
- Transição suave entre etapas do questionário (fade e slide horizontal pequeno).
- Aparição do estrato sugerido na tela de resultado com escala leve.
- Expansão dos cards de critério no resultado.
- Sem exagero. Cada animação tem função.

---

## Estados obrigatórios

- Carregando.
- Nenhum PTT cadastrado.
- Avaliação em rascunho.
- Aderência negativa (não qualificável).
- Campos obrigatórios vazios.
- Erro ao salvar.
- Confirmação de cópia para área de transferência.
- Confirmação de arquivamento.

---

## Tom dos textos

Sóbrio, técnico, respeitoso. Frases curtas. Sem promessa, sem exagero, sem linguagem motivacional.

Exemplos do vocabulário:
- `Iniciar avaliação`
- `Próximo critério`
- `Voltar`
- `Calcular estrato sugerido`
- `Estrato sugerido`
- `Não qualificável`
- `Justificativa`
- `Indicadores escolhidos`
- `Recomendações`
- `Exportar relatório`
- `Autoavaliação. Não substitui qualificação oficial da comissão CAPES.`

Evite:
- `Parabéns`
- `Excelente`
- Exclamações
- Linguagem promocional
- Promessas de aprovação

---

## Segurança e operação

- Habilite RLS em todas as tabelas (`ptts`, `assessments`, `criterion_responses`).
- Crie policies explícitas: usuário autenticado lê e modifica apenas suas próprias linhas; usuário anônimo identificado por `session_id` lê e modifica apenas linhas com o mesmo `session_id`.
- Variáveis de ambiente para a configuração do Supabase. Nada de chave hardcoded.
- CORS configurado, não use `*` em produção.
- Sanitize textos livres antes de gravar (limite de tamanho, remova caracteres de controle, não execute como HTML).
- Erros para o usuário são mensagens curtas e genéricas. Detalhes ficam no log.

---

## Atribuição da desenvolvedora

Inclua em todo o app:

Comentário HTML no topo do `<body>` da página principal:

```html
<!--
    ================================================================

    ❤️ This website was developed with love and dedication by Jady Pamella
    🌐 Portfolio: https://jadypamella.com

    ================================================================
-->
```

`console.log` no arquivo principal de inicialização (`main.tsx` ou equivalente):

```ts
console.log(
  '❤️ This website was developed with love and dedication by Jady Pamella\n🌐 Portfolio: https://jadypamella.com'
);
```

Os emojis acima são a única exceção à regra de não usar emoji. Eles ficam apenas no comentário HTML e no `console.log`, nunca na interface visível.

---

## README e documentação

Inclua um `README.md` na raiz do projeto explicando:
- O que o AvaliaPTT faz, em uma frase, citando que a lógica é da Área 27 da CAPES.
- Stack usada.
- Como rodar local (variáveis de ambiente, comando de start).
- Como o cálculo do estrato funciona (resumo dos pesos e faixas, com link para o Ficha de Avaliação 2025).
- Aviso de que o resultado é referência, não qualificação oficial.
- Lista das fontes CAPES consultadas.

---

## Definição de pronto

Pesquisador:
- Cadastra um PTT com tipo, título, descrição, programa, linha, ano, motivo de criação e foco de aplicação.
- Responde os cinco critérios em fluxo guiado.
- Vê o estrato sugerido com gráfico radar, justificativa por critério e recomendações.
- Exporta o relatório em PDF e em Markdown.

Sistema:
- Aderência eliminatória funciona (Não em qualquer pergunta resulta em Não qualificável).
- Cálculo de cada subscore e do total bate com as fórmulas oficiais da Área 27 descritas acima.
- As faixas TA1 a TB4 estão corretas (87,5 / 75 / 62,5 / 50 / 37,5 / 25 / 12,5).
- Avaliação fica salva e pode ser editada antes de finalizar.
- Histórico no painel mostra todas as avaliações.

Identidade:
- Wordmark e paleta aplicados de forma consistente.
- Nenhum emoji na interface (apenas no comentário HTML e no `console.log` de atribuição).
- Nenhum travessão (—) em textos da UI.
- Ícones todos de `lucide-react`.

Operação:
- Configuração por variáveis de ambiente.
- RLS habilitada em todas as tabelas com policies explícitas.
- `.gitignore` correto.
- Dados de exemplo, nenhum dado pessoal real.
- App responsivo e pronto para demonstração.

---

## Casos de teste obrigatórios para QA

Antes da aula, valide manualmente os seguintes casos:

| Caso | Respostas | Resultado esperado |
|---|---|---|
| Não qualificável | Aderência (a) Não | NOT_QUALIFIABLE, sem estrato |
| TA1 | Aderência Sim/Sim; tudo Alto em todos os subitens; replicabilidade Escalável | 100,0 pontos, TA1 |
| TA4 limítrofe | Impacto realizado Médio, potencial Médio; Aplicabilidade Média em todos; Inovação Médio; Complexidade Média | 50,0 pontos, TA4 |
| TB3 | Tudo Baixo; replicabilidade Restrita | aproximadamente 16,7 pontos, TB3 |
| TB4 | Tudo Ausência/Não em todos os subitens | 0 pontos, TB4 |

Se algum desses casos sair fora do estrato esperado, a fórmula está errada.

---

## Fontes CAPES consultadas (lista para a página de Metodologia)

Cite estas fontes oficiais com links clicáveis dentro do app, sendo a primeira a fonte primária da lógica:

1. **CAPES. Ficha de Avaliação 2025 - Área 27 - Administração Pública e de Empresas, Ciências Contábeis e Turismo.** Diretoria de Avaliação (DAV). Coordenador da Área: Marcio Andre Veras Machado. Seção 4 "Considerações sobre a qualificação de produtos técnicos/tecnológicos", páginas 35 a 41. Válida para a avaliação do quadriênio 2021-2024. Disponível em: https://www.gov.br/capes/pt-br/acesso-a-informacao/acoes-e-programas/avaliacao/sobre-a-avaliacao/areas-avaliacao/sobre-as-areas-de-avaliacao/colegio-de-humanidades/ciencias-sociais-aplicadas/ADM_FICHA_DE_AVALIACAO_v1.pdf
2. **CAPES. Grupo de Trabalho de Produção Técnica, junho de 2019.** Relatório do GT DAV/CAPES com a definição dos 21 produtos técnicos/tecnológicos. Disponível em: https://www.gov.br/capes/pt-br/centrais-de-conteudo/10062019-producao-tecnica-pdf
3. **CAPES. Considerações sobre Classificação de Produção Técnica e Tecnológica.** Diretoria de Avaliação. Disponível em: https://www.gov.br/capes/pt-br/centrais-de-conteudo/documentos/avaliacao/ENF_ConsideraessobreClassificaodeProduoTcnicaeTecnolgica.pdf
4. **CAPES. Diretrizes para qualificação de produtos técnicos e tecnológicos (consolidado, 16/07/2021).** Disponível em: https://www.gov.br/capes/pt-br/centrais-de-conteudo/documentos/avaliacao/03___Diretrizes_para_qualificacao_de_PTT.16.07.2021.pdf
5. **CAPES. Página oficial da Área 27.** https://www.gov.br/capes/pt-br/acesso-a-informacao/acoes-e-programas/avaliacao/sobre-a-avaliacao/areas-avaliacao/sobre-as-areas-de-avaliacao/colegio-de-humanidades/ciencias-sociais-aplicadas/27-administracao-publica-e-de-empresas-ciencias-contabeis-e-turismo

Inclua também no rodapé do app: `Lógica baseada na Ficha de Avaliação 2025 da Área 27 da CAPES, quadriênio 2021-2024.`

---

## Como construir ao vivo

A decisão para esta aula é construir o AvaliaPTT na frente da plateia, do zero, usando este prompt. O público de mestrandos em Administração Pública conhece o problema (estão na Área 27 da CAPES, exatamente no ciclo de produção técnica avaliada), então o app tem uso real para eles.

Cole o prompt inteiro no Lovable de uma vez. Não vá pedindo parte por parte ao vivo. Um one-shot bem preenchido é o que faz o primeiro resultado já sair perto do final.

Fluxo esperado na aula:
- Cole o prompt no minuto de demo escolhido. O Lovable gera. Você narra slides enquanto ele trabalha. Tempo típico do primeiro resultado: 3 a 6 minutos.
- Resultado 1 aparece. Provavelmente tem furo (cálculo errado, ou exportação não funciona, ou fluxo de etapas trava). Você corrige com 1 ou 2 prompts curtos, narrando mais slides nas esperas.
- Quando o app estiver com o questionário rodando e o cálculo bater, convide alguém da plateia para cadastrar um PTT real e ver o estrato sugerido. Esse é o pico.

Salvaguardas obrigatórias:
- Teste este prompt uma vez, 1 a 2 dias antes da aula. Não é construir antes da aula, é QA do prompt.
- Rode os 5 casos de teste da seção acima e confira se o estrato sai certo. Esse é o risco número um: cálculo errado da primeira geração (peso ou faixa trocada).
- Tenha o resultado desse teste salvo numa aba escondida do navegador como rede de segurança.
- Se o build ao vivo travar feio, abra a rede e fale com a sala: deixei essa versão adiantada no interesse do tempo, mesma técnica, mais iterações.

O risco número dois é o tempo da aula acabar antes do app ficar usável. Se no minuto 40 não dá para a plateia testar, abra a rede de segurança.
