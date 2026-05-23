# Template genérico de one-shot prompt para o Lovable

Use este arquivo como ponto de partida ao escrever um novo one-shot prompt para o Lovable. Foi destilado a partir de [lovable_prompt_sabetudo.md](lovable_prompt_sabetudo.md) e [lovable_prompt_avalia_ptt.md](lovable_prompt_avalia_ptt.md). Mantém a estrutura, o tom e as restrições que funcionam bem com o Lovable em demos ao vivo.

> **Como usar:** copie este arquivo para `lovable_prompt_<slug>.md`, troque cada `{{placeholder}}` por conteúdo real, apague as instruções em blockquote `>` e remova as seções opcionais que não se aplicam. Antes de colar no Lovable, leia o arquivo de cabo a rabo confirmando que não sobrou nenhum placeholder e que toda regra de negócio está descrita sem ambiguidade.

> **Antes de preencher, decida estas seis coisas (passa rápido por cada uma):**
> 1. Nome curto do app e descrição em uma frase.
> 2. Stack: padrão é React + TS + Tailwind + shadcn/ui + lucide-react + framer-motion + Supabase. Mantenha o padrão a menos que o caso peça outro banco ou outra biblioteca.
> 3. Precisa de tempo real multiusuário? (Sim só se houver host e múltiplos clientes interagindo simultaneamente. Caso contrário, corte a seção de tempo real.)
> 4. Precisa de autenticação? (Padrão: opcional, com sessão local funcionando sem login.)
> 5. Quais 3 a 6 telas o app realmente precisa? (Liste só essas; não inventar rota.)
> 6. Casos de teste obrigatórios: pelo menos 3 cenários verificáveis que provam que a regra de negócio está certa.

> **Regras de estilo herdadas dos dois prompts de referência (não negociáveis):**
> - Tudo em português.
> - Nada de emoji na interface. Único uso permitido é nos blocos de atribuição da desenvolvedora.
> - Nada de travessão (—) em texto da UI ou documentação. Use vírgula, ponto ou dois-pontos.
> - Ícones sempre da `lucide-react`.
> - Variáveis de ambiente para qualquer chave ou URL externa. Nunca hardcoded.
> - RLS habilitada em todas as tabelas do Supabase com policies explícitas.
> - Validar toda entrada antes de gravar.
> - Dados de exemplo no MVP. Nenhum dado pessoal real.

---

# One-shot prompt para o Lovable — {{Nome do App}} ({{descrição curta de uma linha}})

Prompt completo para colar no Lovable. {{Em duas ou três frases, descreva o que o app faz, qual é o pico de uso, e o que torna ele divertido ou útil para o público-alvo.}}

Stack alinhada ao que o Lovable constrói bem: React, TypeScript, Tailwind, shadcn/ui, lucide-react, framer-motion{{, e Supabase com tempo real / e Supabase / sem backend}}. Tudo em português, dados de exemplo, sem dado pessoal real.

> Se o app implementa regras oficiais (CAPES, LGPD, ABNT, etc.) cite a fonte aqui em uma frase com link. Em prompts puramente lúdicos como o SabeTudo, apague esta linha.

---

## Objetivo

Construa um web app {{adjetivos do tom: moderno, sóbrio, divertido, energético, acadêmico, etc.}} e responsivo chamado {{Nome do App}}.

{{Parágrafo de 2 a 4 linhas explicando em prosa o que o app faz e como o fluxo principal funciona da perspectiva do usuário. Cite as personas que vão interagir, por exemplo "um host cria, jogadores entram", "um pesquisador cadastra e responde".}}

Resultado principal:
- {{Frase curta descrevendo o resultado mais importante que o usuário consegue do app.}}
- {{Segundo resultado, geralmente do ponto de vista de outra persona.}}
- {{Terceiro resultado, geralmente o pico ou o entregável final.}}

Fora de escopo (não implementar):
- {{Coisa que parece tentadora mas vai estourar o tempo da aula ou exigir integração externa.}}
- {{Login obrigatório / pagamento / email / notificação push, conforme o caso.}}
- {{Funcionalidade de admin / banco público / importação de dados, conforme o caso.}}
- {{Algo que daria escopo de "produto de verdade" mas não é necessário para a demo.}}

Restrições importantes:
- Use dados de exemplo. Nenhum dado pessoal real.
- Valide toda entrada antes de gravar.
- Trate estados previsíveis: {{liste os estados de falha mais óbvios do domínio, por exemplo "PIN inválido, partida já começou, sessão expirada, formulário incompleto"}}.
- Use variáveis de ambiente para toda configuração (URL e chaves do Supabase). Nunca hardcode chaves no código.
- Use ícones da `lucide-react` para tudo. Nunca renderize emoji na interface.
- Não use travessão (—) em texto de UI ou documentação. Use vírgula, ponto ou dois-pontos.

---

## Regras de negócio do domínio

> **Seção crítica. Use-a quando o app reproduz uma lógica externa (regras CAPES, jogo, regras de pontuação, fórmulas, fluxos legais).** Cole aqui as regras na ordem que o código vai precisar. Para apps puramente livres (CRUD simples), apague esta seção. Se for um jogo, transforme em "Pontuação" como no SabeTudo. Se for cálculo, mostre a fórmula crua e dê pelo menos 3 exemplos numéricos para checagem.

{{Defina aqui qualquer fórmula, faixa de valores, tabela de pesos, máquina de estados, restrição de integridade, ou critério eliminatório que o app precise honrar. Copie literalmente de fontes oficiais quando existirem. Sempre que possível, mostre a fórmula em bloco de código e os mapeamentos em tabela.}}

```
{{exemplo de fórmula ou pseudocódigo, se houver}}
```

| {{Coluna A}} | {{Coluna B}} |
|---|---|
| {{valor}} | {{valor}} |

---

## Identidade da marca

{{Uma linha sobre o caráter visual: divertido e energético, sóbrio e acadêmico, profissional e técnico, etc.}}

Tom de voz:
- {{Adjetivo principal}}, {{adjetivo secundário}}, {{adjetivo terciário}}.
- Frases curtas.
- {{Mais alguma regra de tom: sem promessa, sem exagero, sem jargão; ou com humor, lúdico, etc.}}

> **Se há logos prontos**, descreva a pasta local e os arquivos disponíveis (PNG, SVG) com as regras de uso de cada variação (completo / só ícone / só texto). Veja [SabeTudo](lovable_prompt_sabetudo.md) como exemplo.
>
> **Se não há logos**, descreva o wordmark a ser gerado (palavra + ícone `lucide-react`) e em qual tipografia. Veja [AvaliaPTT](lovable_prompt_avalia_ptt.md) como exemplo.

{{Descrição dos logos ou do wordmark.}}

---

## Paleta de cores

Defina os valores como tokens no `tailwind.config` e em variáveis CSS. Use de forma semântica.

Paleta principal:
- {{Cor primária}}: `#XXXXXX`
- {{Cor secundária}}: `#XXXXXX`
- {{Cor de sucesso ou acerto}}: `#XXXXXX`
- {{Cor de erro ou alerta}}: `#XXXXXX`
- {{Cor de destaque ou celebração}}: `#XXXXXX` (opcional)
- Cinza de texto principal: `#111827`
- Cinza de texto secundário: `#4B5563`
- Cinza de borda: `#E5E7EB`
- Fundo principal: `#FFFFFF`
- Fundo suave: `#F9FAFB`

Regras de uso:
- {{Cor primária}} é a cor principal de ação.
- {{Cor secundária}} é para {{contexto: estados informativos, navegação secundária, etc.}}.
- {{Cor de sucesso}} é exclusiva de {{contexto: acerto, aprovação, estado positivo}}.
- {{Cor de erro}} é exclusiva de {{contexto: erro, falha, alerta crítico}}.
- Não espalhe hex solto pelos componentes. Tudo vem dos tokens.

---

## Tipografia

- `{{Fonte principal de títulos}}` para títulos, botões e elementos principais.
- `{{Fonte de corpo}}` para textos menores, formulários e informação auxiliar.
- {{Regras de peso e estilo: bold em PIN/cronômetro, tabular numbers para pontuações, etc.}}

---

## Stack

Frontend:
- React com TypeScript
- Tailwind CSS com tokens para cores e tipografia
- shadcn/ui {{quando fizer sentido / para formulários, dialogs, accordion}}
- `lucide-react` para todos os ícones
- `framer-motion` para animações simples

Backend e dados:
- Supabase para banco (Postgres){{ e sincronização em tempo real / sem tempo real}}
- {{Autenticação obrigatória / opcional / inexistente, conforme o caso}}
- {{Outras libs específicas do domínio: recharts, jspdf, react-pdf, qrcode.react, etc.}}

Operação:
- Configuração por variáveis de ambiente: `VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`{{, outras}}.
- `.gitignore` deve incluir `.env`, `.env.*` (exceto `.env.example`), `.claude/`, `node_modules/`, `dist/`, `build/`.
- Habilite Row Level Security (RLS) em todas as tabelas do Supabase. Crie policies explícitas para cada operação.
- Valide toda entrada antes de gravar.
- Tratamento de erro centralizado com mensagens curtas para o usuário e log estruturado no console.

---

## Conceitos centrais

Use estes nomes de entidade no código:
- `{{entidade_1}}`: {{descrição curta}}.
- `{{entidade_2}}`: {{descrição curta}}.
- `{{entidade_3}}`: {{descrição curta}}.
- `{{entidade_4}}`: {{descrição curta}}.

{{Se houver máquina de estados (ex.: status de partida, status de avaliação), liste os valores exatos aqui e o que cada um significa.}}

Status de `{{entidade}}`:
- `{{status_1}}`: {{quando ocorre}}.
- `{{status_2}}`: {{quando ocorre}}.
- `{{status_3}}`: {{quando ocorre}}.

---

## Modelo de dados (Supabase)

Crie as tabelas necessárias. Toda tabela com RLS habilitada e policies explícitas.

`{{tabela_1}}`:
- `id`
- `{{campo}}` ({{tipo}})
- `{{campo}}` ({{tipo}}, fk para `{{outra_tabela}}`)
- `created_at`

`{{tabela_2}}`:
- `id`
- `{{campo}}` ({{tipo}})
- `{{campo}}` ({{tipo}})
- `created_at`

`{{tabela_3}}`:
- `id`
- `{{campo}}` ({{tipo}})
- `{{campo}}` ({{tipo}})
- `created_at`

Regras de integridade:
- {{Restrição 1: unicidade, FK, validação de domínio.}}
- {{Restrição 2: ordem permitida de transições de status.}}
- {{Restrição 3: sanitização de texto livre.}}

---

## Páginas e rotas

> **Liste apenas as telas que existem.** Para cada tela, descreva o que ela mostra em cada estado relevante do domínio (lobby, jogo, resultado, etc.). Não economize aqui: é o que mais influencia a qualidade do primeiro resultado do Lovable.

### 1. Landing page · `/`

Topo:
- {{Logo ou wordmark}}.
- Navegação: {{lista de links}}.

Hero:
- Título: `{{Frase curta que comunica o valor}}`.
- Subtítulo: `{{Uma linha sobre como funciona ou para quem é}}`.
- Botão principal: `{{Call to action principal}}`.
- Botão secundário: `{{Call to action alternativo}}`.
- {{Mockup, imagem ilustrativa ou aviso em destaque, conforme o caso.}}

Como funciona:
1. {{Passo 1}}
2. {{Passo 2}}
3. {{Passo 3}}
4. {{Passo 4}}

Recursos:
- {{Recurso 1}}
- {{Recurso 2}}
- {{Recurso 3}}
- {{Recurso 4}}

Para quem é:
- {{Persona 1 com 1 frase de contexto}}
- {{Persona 2 com 1 frase de contexto}}
- {{Persona 3 com 1 frase de contexto}}

Chamada final:
- `{{Frase de fechamento ou botão final}}`

### 2. {{Nome da tela 2}} · `/{{rota}}`

{{Descrição do propósito da tela.}}

{{Liste os componentes principais e suas ações. Se a tela muda conforme estado, descreva cada estado em um bloco próprio.}}

### 3. {{Nome da tela 3}} · `/{{rota}}`

{{Idem.}}

### 4. {{Nome da tela 4}} · `/{{rota}}`

{{Idem.}}

---

## Componentes

Implemente como componentes pequenos e reutilizáveis:

- `AppShell`
- `Header`
- `HeroSection`
- `{{ComponenteEspecífico1}}`
- `{{ComponenteEspecífico2}}`
- `{{ComponenteEspecífico3}}`
- `{{ComponenteEspecífico4}}`
- `{{ComponenteEspecífico5}}`

---

## Tempo real (opcional)

> **Inclua esta seção apenas se houver múltiplos clientes interagindo simultaneamente (jogo multiusuário, chat, colaboração).** Caso contrário, apague.

- {{Tabela X}} é a fonte da verdade do estado compartilhado.
- Use Supabase Realtime para propagar mudanças.
- Quando {{ação}}, todas as telas dos {{atores}} atualizam.
- {{Outros gatilhos de tempo real específicos do app.}}
- Se o cliente desconectar e voltar, ele retorna ao estado atual.

---

## Interações obrigatórias

- {{Ação principal 1 e o que ela aciona.}}
- {{Ação principal 2 e o que ela aciona.}}
- {{Ação principal 3 e o que ela aciona.}}
- {{Transição de estado importante.}}
- {{Transição de estado importante.}}

---

## Responsividade

- A landing page funciona bem no desktop e no mobile.
- {{Tela X é mobile-first / pensada para projetor / responsiva com layout que muda no breakpoint Y.}}
- Evite telas apertadas. Botões grandes, hierarquia visual clara, textos legíveis.

---

## Animações

Use `framer-motion` com moderação:
- {{Animação específica 1 e onde aparece.}}
- {{Animação específica 2 e onde aparece.}}
- {{Animação específica 3 e onde aparece.}}
- Sem exagero. Cada animação tem função.

---

## Estados obrigatórios

- Carregando.
- {{Estado vazio mais comum, ex.: "Nenhum quiz criado", "Nenhum PTT cadastrado"}}.
- {{Estado de erro específico do domínio.}}
- {{Estado de validação específico do domínio.}}
- {{Estado de conexão perdida, se houver tempo real.}}
- {{Estado de confirmação de ação destrutiva, se houver.}}

---

## Tom dos textos

{{Adjetivos do tom de voz, repetidos da seção de identidade.}} Frases curtas. {{Sem promessa / sem exagero / sem jargão / energético, conforme o caso.}}

Exemplos do vocabulário:
- `{{Botão 1}}`
- `{{Botão 2}}`
- `{{Mensagem de estado 1}}`
- `{{Mensagem de estado 2}}`
- `{{Frase recorrente da UI}}`

{{Se o app tem aviso legal recorrente (como o do AvaliaPTT sobre "Não substitui qualificação oficial"), repita-o aqui.}}

Evite:
- {{Palavra ou padrão a evitar 1}}
- {{Palavra ou padrão a evitar 2}}
- Exclamações
- Linguagem promocional

---

## Segurança e operação

- Habilite RLS em todas as tabelas ({{liste as tabelas}}).
- Crie policies explícitas: {{descreva quem pode ler, inserir, atualizar, e em que condições, para cada tabela}}.
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
- O que o {{Nome do App}} faz, em uma frase.
- Stack usada.
- Como rodar local (variáveis de ambiente, comando de start).
- {{Algo específico do domínio: como o tempo real funciona, como o cálculo funciona, como testar o fluxo principal.}}
- {{Aviso ou disclaimer relevante, se houver.}}
- {{Lista de fontes consultadas, se o app implementa regras oficiais.}}

---

## Definição de pronto

{{Persona 1}}:
- {{Verbo + ação}} concretamente.
- {{Verbo + ação}} concretamente.
- {{Verbo + ação}} concretamente.

{{Persona 2}}:
- {{Verbo + ação}} concretamente.
- {{Verbo + ação}} concretamente.

Sistema:
- {{Regra de negócio crítica está honrada.}}
- {{Cálculo principal bate com a fórmula.}}
- {{Fluxo de estados funciona ponta a ponta.}}

Identidade:
- {{Logo ou wordmark}} e paleta aplicados de forma consistente.
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

> **Sempre inclua esta seção.** Liste de 3 a 6 cenários que provam que a regra de negócio está certa. Se for jogo, cubra acerto, erro, empate, limite. Se for cálculo, cubra extremos (zero, máximo, limítrofe entre estratos). Se for fluxo, cubra caminho feliz e pelo menos uma falha esperada.

| Caso | Entradas | Resultado esperado |
|---|---|---|
| {{Caminho feliz}} | {{...}} | {{...}} |
| {{Limite superior}} | {{...}} | {{...}} |
| {{Limite inferior}} | {{...}} | {{...}} |
| {{Erro previsto}} | {{...}} | {{...}} |
| {{Estado limítrofe}} | {{...}} | {{...}} |

Se algum desses casos sair fora do esperado no QA, a lógica está errada e precisa ser corrigida antes da demo.

---

## Fontes consultadas (opcional)

> **Inclua esta seção apenas se o app implementa regras oficiais (CAPES, ABNT, LGPD, regulamentos, normas).** Caso contrário, apague.

Cite as fontes oficiais com links clicáveis dentro do app:

1. **{{Título oficial da fonte primária}}.** {{Órgão emissor}}. {{Página, seção, validade}}. Disponível em: {{URL completa}}
2. **{{Título da fonte secundária}}.** Disponível em: {{URL completa}}
3. **{{Título da terceira fonte}}.** Disponível em: {{URL completa}}

Inclua também no rodapé do app: `Lógica baseada em {{fonte primária resumida}}.`

---

## Diagrama de fluxo (opcional)

> **Inclua se há mais de uma persona interagindo ou se o fluxo de dados em tempo real é importante.** Caso contrário, apague.

```mermaid
flowchart LR
  A[{{Persona ou tela 1}}] -->|{{ação}}| DB[(Supabase)]
  A -->|{{ação}}| RT{{Supabase Realtime}}
  B[{{Persona ou tela 2}}] -->|{{ação}}| DB
  DB --> RT
  RT -->|{{evento}}| A
  RT -->|{{evento}}| B
```

---

## Como construir ao vivo

A decisão para esta aula é construir o {{Nome do App}} na frente da plateia, do zero, usando este prompt. {{Em 1 a 2 linhas, justifique por que o app é demonstrável ao vivo e por que ele tem uso real para o público específico.}}

Cole o prompt inteiro no Lovable de uma vez. Não vá pedindo parte por parte ao vivo. Um one-shot bem preenchido é o que faz o primeiro resultado já sair perto do final.

Fluxo esperado na aula:
- Cole o prompt no minuto de demo escolhido. O Lovable gera. Você narra slides enquanto ele trabalha. Tempo típico do primeiro resultado: 3 a 6 minutos.
- Resultado 1 aparece. Provavelmente tem furo ({{exemplo de furo típico para este domínio}}). Você corrige com 1 ou 2 prompts curtos, narrando mais slides nas esperas.
- Quando o app estiver com {{marco mínimo jogável ou usável}}, {{convide a plateia ou demonstre o pico}}. Esse é o pico.

Salvaguardas obrigatórias:
- Teste este prompt uma vez, 1 a 2 dias antes da aula. Não é construir antes da aula, é QA do prompt. Rode os casos de teste da seção anterior.
- Tenha o resultado desse teste salvo numa aba escondida do navegador como rede de segurança. Se o build ao vivo travar feio e não recuperar em 2 correções, abra a rede e fale com a sala: deixei essa versão adiantada no interesse do tempo, mesma técnica, mais iterações.
- Se mesmo a rede de segurança não funcionar, encerre o demo de construção e {{plano B mais simples: votação rápida, demonstração de outro prompt, exemplo pronto, etc.}}. Melhor um plano B que funciona do que o app principal travado.

O risco número um é {{principal risco técnico deste app, ex.: tempo real não sincronizar, cálculo errado da primeira geração, fluxo de etapas travado}}. Por isso a regra: faça o QA antecipado focado nesse risco.

O risco número dois é o tempo da aula acabar antes do app ficar usável. No minuto 40 da aula, se ainda não dá para a plateia testar, abra a rede de segurança.
