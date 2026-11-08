# FRIDAY-010 — Linguagem do fluxo e explicação de HIL

> **Status:** DONE
>
> **Etapa:** Revisão editorial

## Objetivo

Trocar a chamada para “Da ideia ao produto”, tornar a explicação do fluxo mais natural e incluir nota de rodapé sobre HIL.

## Fontes de verdade

[README](../../../README.md), [SOURCES](../../research/SOURCES.md), [estado](../EXECUTION-STATE.md), [template](../TASK-TEMPLATE.md), [FRIDAY-009](../completed/FRIDAY-009-readme-scenarios.md), [HIL](../../../skills/core/references/hil.md) e [fluxo](../../../skills/core/contracts/friday-flow.md).

## Dependências e autorização

Pedido atual autoriza os ajustes editoriais no README e nas imagens. Preservar o desenho visual aprovado e a frente paralela FRIDAY-008. Sem publicação ou commit nesta tarefa.

## Estado identificado

A FRIDAY-009 criou abertura e diagrama SVG com seis etapas. O mantenedor aprovou o design, mas pediu explicação mais clara e linguagem natural. HIL aparece como sigla no texto e nas imagens, sem nota de rodapé.

## Escopo e não escopo

README, texto/descrições dos dois SVGs e registros desta tarefa/estado. Preservar contratos, exemplos, layout, cores, fontes e limites de validação. Sem mudança de skills ou execução de clientes.

## Decisões permitidas autonomamente

Redação de etapas e explicações, posição da chamada da nota e ajuste local de texto para caber nos cartões existentes.

## ADRs e impactos

Sem alteração de arquitetura, contrato ou comportamento. HIL mantém as decisões previstas nas fontes; simplificação é editorial.

## Plano de implementação

1. Atualizar chamada e texto alternativo da abertura.
2. Reescrever etapas/legendas do diagrama e explicação no README com linguagem cotidiana.
3. Acrescentar nota de rodapé que explique HIL e seus quatro momentos de decisão.
4. Conferir links, nota, SVGs e renderização; revisar diff, registrar resultado e arquivar.

## Arquivos e módulos esperados

`README.md`, `docs/assets/readme/hero.svg`, `docs/assets/readme/workflow.svg`, este plano e seção própria no EXECUTION-STATE.

## Estratégia de validação

Python 3 para XML, links/âncoras, referência/definição da nota, whitespace e novas linhas finais. Renderização dos SVGs com sips e inspeção visual. Conferência de linguagem contra HIL/contrato; diff integral. Testes de aplicação, lint, typecheck e build não se aplicam.

## Riscos conhecidos

Simplificar linguagem sem sugerir que revisão aprova entrega ou que qualquer produto exige todos os passos. A nota esclarece participação humana e o texto preserva decisões anteriores válidas.

## Critérios de aceite

- [x] Chamada atualizada para “Da ideia ao produto” no README e na abertura.
- [x] Fluxo explicado com linguagem natural no texto e diagrama, preservando o design.
- [x] Nota de rodapé define HIL e as decisões correspondentes.
- [x] Checks documentais, renderização e revisão concluídos, com limites registrados.
- [x] Estado atualizado e plano arquivado; trabalho paralelo preservado.

## Resultado da execução

Retomada concluída para indicar, após a descrição de HIL no rodapé do workflow: “Veja a explicação completa de HIL na nota ao final do README.” A descrição anterior foi preservada e deslocada dez unidades para cima; orientação ocupa a linha seguinte dentro do mesmo SVG de 1600 × 650. XML e existência da nota de destino verificados com Python 3; sips gerou /tmp/friday010-footer-workflow.png, inspecionado sem cortes/sobreposições. Diff pontual revisado e git diff --check aprovado. Plano arquivado novamente; sem alteração de contrato, commit ou push.

Retomada concluída para o pedido de asterisco visível junto a HIL: duas chamadas sobrescritas com link para a âncora única nota-hil substituem a chamada numérica. Nota ao final usa asterisco literal, preservando integralmente a explicação. Quatro marcadores HIL no diagrama receberam asterisco, assim como a legenda inferior. Python 3 conferiu links à âncora, marcadores, preservação do conteúdo da nota e dos prompts, XML, whitespace e nova linha final; git diff --check aprovado. Workflow renderizado com sips em /tmp/friday010-marker-workflow.png e inspecionado sem cortes/sobreposições. Diff revisado pelo autor; sem preview da página no GitHub. Layout e cores preservados; plano arquivado novamente, sem commit/push ou mudança de contrato.

Retomada editorial concluída: o mantenedor considerou vaga a nota de HIL e autorizou esclarecer responsabilidades, parada para decisão e exemplo concreto. A nota agora explica que o agente apresenta proposta/opções e aguarda resposta antes do trabalho dependente, exemplifica a aprovação do recorte de agendamento sem pagamentos e da solução, e distingue revisão de aceite humano. Decisões anteriores válidas continuam permitindo execução dos detalhes. Somente a nota mudou no README, confirmado por comparação com cópia anterior; imagens e prompts preservados. Python 3 conferiu referência/definição únicas, indentação dos parágrafos de continuação, whitespace e nova linha final; `git diff --check` aprovado. Diff integral da nota revisado. Sem novo link ou alteração visual que exija repetir renderização dos SVGs; a nota continua sem preview no GitHub. Plano reaberto e arquivado novamente, com registro de continuidade no estado. Resultados da primeira revisão preservados abaixo.

Chamada “Da ideia ao produto” aplicada ao README e ao hero, incluindo title/texto alternativo. Diagrama usa Entender → Definir → Planejar → Construir → Revisar → Entregar, com perguntas/ações curtas e explicações cotidianas de conferência visual, correções e decisões. Texto da seção de fluxo e tabela de níveis simplificados. Nota de rodapé Markdown define Human-in-the-Loop e os papéis de HIL 0/1/2/3. Aprovações válidas e revisão antes do aceite permanecem explícitas; os cinco prompts foram preservados byte a byte.

Python 3 conferiu 44 links/âncoras relativos, a referência e a definição únicas da nota, XML dos dois SVGs, ausência de scripts/recursos de imagem e igualdade dos elementos geométricos com a versão anterior. Whitespace/novas linhas finais e `git diff --check` aprovados. Diff desta revisão inspecionado integralmente contra cópia anterior fora do repositório; revisão pelo agente autor, sem contexto independente.

SVGs renderizados com `sips -s format png docs/assets/readme/hero.svg --out /tmp/friday010-hero.png` e comando equivalente para workflow. PNGs de 1600 × 640 e 1600 × 650 inspecionados: texto cabe nos espaços existentes sem corte ou sobreposição; desenho preservado. Sem preview da nota na página do GitHub; sintaxe Markdown e correspondência verificadas estaticamente.

Plano arquivado; estado recebeu seção própria. Sem alterações em contratos, conteúdo do piloto ou seus contadores, sem novas dependências, commit ou push. Testes de aplicação, lint, typecheck e build não se aplicam.
