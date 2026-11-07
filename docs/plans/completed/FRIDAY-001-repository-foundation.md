# FRIDAY-001 — Fundação do repositório

> **Status:** DONE
>
> **Etapa:** Fundação documental
>
> **Autorização:** implementar o plano aprovado de estrutura inicial e README, em repositório local separado.

## Objetivo

Criar a fundação documental do FRIDAY, com a apresentação aprovada, decisões persistentes e acompanhamento recuperável.

## Fontes de verdade

- Plano aprovado pelo mantenedor nesta conversa, registrado neste documento.
- [TASK-TEMPLATE](../TASK-TEMPLATE.md), criado nesta tarefa a partir da estrutura de planejamento consultada no MakerBuddy.
- [AGENTS](../../../AGENTS.md), com instruções próprias do FRIDAY.
- [SOURCES](../../research/SOURCES.md), com fontes, revisões e decisões confirmadas.
- [EXECUTION-STATE](../EXECUTION-STATE.md), com o estado atual.

## Dependências e estado identificado

Nenhuma dependência de aplicação. O diretório FRIDAY ainda não existia na verificação inicial. O MakerBuddy é um repositório vizinho independente e não faz parte da entrega. Não há skills, instalador, testes automatizados ou CI do FRIDAY implementados.

## Escopo

- Inicializar um repositório Git local separado.
- Criar README, AGENTS, gitignore e documentos de finalidade de `skills/` e `installer/`.
- Registrar fontes e decisões anteriores sem apresentar planos como funcionalidades disponíveis.
- Criar template de tarefa e estado mínimo de execução.
- Validar Markdown, caminhos, links relativos, fontes externas principais e consistência documental.
- Arquivar este plano ao concluir a etapa local.

## Não escopo

Implementar ou instalar skills, bibliotecas, CLI, MCPs ou serviços; publicar no GitHub/npm; criar remotes, commits ou push; configurar CI; modificar o MakerBuddy; escolher uma licença para o código futuro.

## Decisões permitidas autonomamente

Organizar documentos e links, adotar nomes técnicos em inglês e concluir a tarefa em `docs/plans/completed/`. Produto, arquitetura, contratos e dependências futuras seguem o HIL definido para o projeto.

## ADRs e impactos

Nenhuma ADR, migration, API pública ou alteração de dados persistentes. As decisões confirmadas ficam em SOURCES; contratos do instalador e das skills continuam por especificar. Não armazenar segredos, caminhos pessoais no conteúdo público ou referências ao ambiente privado do MakerBuddy.

## Plano de implementação

1. Registrar este plano antes da criação do conteúdo substantivo.
2. Inicializar Git e criar os documentos aprovados.
3. Conferir a homenagem, a expansão da sigla e a origem literária, mantendo a distinção entre fontes primárias e secundárias.
4. Registrar stack, HIL, lifecycle documental e escopo do instalador.
5. Executar formatação, verificação de links relativos, checagem de whitespace e revisão completa dos arquivos novos.
6. Arquivar a tarefa e atualizar EXECUTION-STATE com os resultados reais.

## Arquivos e módulos esperados

README, AGENTS, gitignore, `skills/README.md`, `installer/README.md`, SOURCES, TASK-TEMPLATE, EXECUTION-STATE e este plano. Nenhum código executável nesta etapa.

## Estratégia de validação

Usar Prettier já disponível no ambiente somente sobre arquivos do FRIDAY; não instalar dependências. Conferir links e estrutura com ferramentas locais e verificar as fontes externas principais. Revisar os documentos novos com `git diff --no-index /dev/null <arquivo>` e checar whitespace. Lint de aplicação, typecheck, testes funcionais e build não se aplicam a esta entrega documental.

## Riscos conhecidos

A expansão da sigla é associada à variante de Avengers Campus, e não deve ser atribuída sem ressalva a todas as continuidades da Marvel. O livro é de 1719; as expressões em inglês são posteriores. Uma pasta documental não comprova descoberta de skill nem funcionamento de instalador.

## Critérios de aceite

- [x] Estrutura local própria criada.
- [x] README em português, informal e coerente com a homenagem aprovada.
- [x] Sigla, tradução e curiosidade preservadas com precisão de contexto.
- [x] Stack e decisões confirmadas registradas.
- [x] Skills e instalador claramente identificados como futuros.
- [x] Formatação, links, whitespace e revisão documental concluídos.
- [x] MakerBuddy preservado.
- [x] Plano arquivado e checkpoint atualizado.

## Resultado da execução

**DONE — entrega local em 07/11/2026.** Criados nove arquivos e um repositório Git próprio na branch `main`. README com a homenagem aprovada, AGENTS, gitignore, documentos de finalidade das duas áreas futuras, fontes e decisões, template de tarefa e checkpoint entregues. O plano foi movido para `completed/` ao concluir a etapa.

### Validações executadas

- Prettier disponível no ambiente, aplicado aos documentos FRIDAY e seguido de `prettier --check '**/*.md'`: aprovado. Nenhuma dependência instalada no FRIDAY.
- Verificação local dos links relativos, limites do repositório, nova linha final e ausência de caminhos pessoais nos arquivos públicos: aprovada, repetida após o arquivamento.
- `git diff --no-index --check /dev/null <arquivo>` para cada arquivo novo: aprovado. Uma linha vazia extra no fim do gitignore foi corrigida antes da aprovação.
- Revisão documental de todos os arquivos: aprovada; interfaces futuras estão identificadas como não implementadas.
- Licenças MIT das duas bases recuperadas pelo conector GitHub nas revisões registradas: conferidas. Os dois verbetes Merriam-Webster foram reabertos para conferir os significados e a origem; a atribuição da sigla ao quadrinho permanece descrita como evidência secundária, sem declarar inspeção direta dos quadros.
- HEAD, status e hash do diff do MakerBuddy comparados antes e depois: inalterados.
- Lint de aplicação, typecheck, testes funcionais e build: não aplicáveis; somente documentação e gitignore foram criados. Não há scripts de validação ou CI próprios implementados.

### Impactos e continuidade

Nenhuma ADR, migration, dependência de runtime ou contrato público implementado. Nenhum desvio material do plano; o mapa de documentos foi incluído no README para navegação. A continuidade é o estudo aprofundado e a especificação, ainda sem início automático.

### Git e CI

Repositório local inicializado, sem commit, remote, push ou publicação, conforme o escopo deste marco. CI: `NOT_CONFIGURED`.
