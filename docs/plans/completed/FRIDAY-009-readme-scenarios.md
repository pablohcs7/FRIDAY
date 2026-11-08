# FRIDAY-009 — README visual e cenários de uso

> **Status:** DONE
>
> **Etapa:** Documentação de entrada

## Objetivo

Reorganizar o README com abertura visual, navegação por objetivo e exemplos copiáveis para produto novo, projeto existente e uma única task, inspirado na estrutura do vibe-coding-toolkit.

## Fontes de verdade

[AGENTS](../../../AGENTS.md), [README](../../../README.md), [SOURCES](../../research/SOURCES.md), [EXECUTION-STATE](../EXECUTION-STATE.md), [template](../TASK-TEMPLATE.md), [catálogo](../../../skills/core/catalog.md), contratos e referências nele ligados. Referência editorial: [README upstream](https://github.com/soumatheusgomes/vibe-coding-toolkit/blob/7ef68dd7b00ddfc5cd464458855e4ab66dd2128f/README.md), consultado em 08/11/2026. Essa consulta não substitui as revisões congeladas de conteúdo.

## Dependências e autorização

Pedido do mantenedor autoriza ajustar a documentação, começando pelo README, em paralelo à finalização. Trabalho editorial independente da FRIDAY-008; não executar seu piloto nem alterar seus arquivos de evidência/fixture. Não depende do encerramento dos testes para explicar contratos, desde que exemplos e evidências sejam distinguidos.

## Estado identificado

README explica proposta/fluxo, mas não possui imagens nem exemplos de entrada. Existem 19 contratos e adapters por cliente. A validação real está em andamento na FRIDAY-008, com amostragem Codex e lacunas registradas; Claude permanece pendente. Instalador, CI e release não existem. O checkout contém mudanças preexistentes da FRIDAY-008.

## Escopo e não escopo

README, imagens SVG próprias, registro de origem editorial e plano/estado desta tarefa. Exemplos devem corresponder aos contratos atuais, com pré-requisitos e distinção entre pedido novo e task já autorizada. Não alterar skills, destinos, settings, ferramentas ou validar aplicações fictícias. Não publicar nem incluir mudanças concorrentes em commit nesta tarefa.

## Decisões permitidas autonomamente

Organização, redação, paleta e diagramas estáticos próprios; prompts em linguagem natural e tabela com formas de seleção já documentadas nos adapters. Sem novos contratos de uso ou promessas de integração.

## ADRs e impactos

Sem mudança arquitetural. SVGs estáticos locais, sem scripts, fontes remotas, animação ou dependência de serviço. Estrutura editorial inspirada no upstream; texto e desenhos próprios, sem copiar seus assets ou instruções de configuração.

## Plano de implementação

1. Conferir referência editorial, contratos e limites de validação.
2. Criar abertura/diagrama de fluxo e reestruturar README com três cenários, retomada e mapa de skills/documentação.
3. Registrar revisão consultada, adaptação e autoria das imagens.
4. Validar links/âncoras, SVGs, renderização e whitespace; revisar diff completo.
5. Registrar resultados, arquivar plano e acrescentar estado desta frente sem reescrever andamento concorrente.

## Arquivos e módulos esperados

`README.md`, `docs/assets/readme/`, este plano e adição delimitada ao EXECUTION-STATE. Registro editorial junto aos assets.

## Estratégia de validação

Python 3 para links/âncoras e XML/SVG; Git para diff/whitespace, incluindo arquivos novos; renderização local com ferramenta disponível e inspeção visual. Conferir prompts contra contratos e metadata atuais. Sem dependências novas. Testes de aplicação, lint, typecheck e build não se aplicam à entrega documental. Renderização local não comprova uso real das skills.

## Riscos conhecidos

Estado de validação muda na frente paralela: usar resumo explícito e linkar evidência viva, sem antecipar conclusão. Task isolada não pode dispensar autorização ou encerrar o fluxo global. Imagens ilustram o processo, não resultados medidos. Não importar setup de máquina, stack universal ou badges de CI da referência.

## Critérios de aceite

- [x] README com imagens locais e navegação por cenário.
- [x] Exemplos copiáveis de projeto novo, existente e task isolada, com pré-requisitos e saídas.
- [x] Fluxo/HIL, retomada, organização, limites, fontes/licença e homenagem preservados.
- [x] Origem editorial e autoria dos assets registradas.
- [x] Links, imagens, renderização e diff integral revisados; alterações concorrentes preservadas.
- [x] Resultado registrado, estado atualizado e plano arquivado.

## Resultado da execução

README reorganizado com abertura e mapa do fluxo em dois SVGs próprios, atalhos, tabela de entrada, preparação manual por cliente e cinco prompts copiáveis: projeto novo, adoção, task autorizada, pedido novo de correção e retomada. Os exemplos seguem contratos existentes e permanecem identificados como ilustrativos. Níveis/HIL, autorização anterior, fontes atuais, revisão/correções, organização do kit, pendências de validação, licença e homenagem foram preservados. A revisão editorial upstream está registrada junto aos assets; não houve cópia de texto ou imagens upstream.

Validação com Python 3: 52 links/âncoras relativos válidos nos três Markdown da entrega antes do registro final; XML dos dois SVGs válido, title/desc e ausência de recursos externos/scripts conferidos; 19 IDs do README correspondem aos 19 contratos, e os cinco blocos de prompt estão presentes. Check final aprovado para seis arquivos e 72 links/âncoras, incluindo o plano arquivado e o registro de estado. `git diff --check`, whitespace de arquivos novos e novas linhas finais conferidos. Diff completo e novos arquivos revisados pelo agente autor; sem contexto independente de revisão.

Renderização final via `sips -s format png docs/assets/readme/hero.svg --out /tmp/friday009-hero.png` e equivalente para workflow: imagens de 1600 × 640 e 1600 × 650 inspecionadas visualmente, sem corte ou sobreposição. As miniaturas quadradas de Quick Look recortavam o conteúdo e foram descartadas para QA. O browser de inspeção estava indisponível; não houve preview da página renderizada no GitHub. Fontes do sistema podem variar entre renderizadores.

Entrega limitada a README, assets/registro editorial e plano/estado desta frente. Arquivos/evidências/skills da FRIDAY-008 não foram editados por esta tarefa. O estado recebeu somente seção própria, sem reconciliação dos contadores do piloto. Plano arquivado em completed. Sem novas ferramentas, dependências, testes de aplicação, commit ou push; lint, typecheck e build de aplicação não se aplicam.
