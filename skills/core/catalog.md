# Catálogo de conteúdo FRIDAY

> Revisão de conteúdo 2 · FRIDAY-004 + licença FRIDAY-005 · 07/11/2026. Conteúdo local, sem instalação ou descoberta comprovada nos clientes.

## Uso do catálogo

Os IDs abaixo identificam contratos e entradas de conteúdo. Cada entrada tem saídas distintas por cliente; bundle disponibiliza capacidades, não escolhe nível ou autoriza execução. Recursos locais viajam dentro da respectiva skill; nenhuma exige clone upstream.

`requires` enumera capacidades necessárias ao contrato em execução; `requiresWhen` condiciona a um ramo. Fontes já válidas satisfazem entradas sem exigir a skill que as criou; ausência da skill só bloqueia criar/atualizar esse artefato. Recursos locais são obrigatórios e não são skills adicionais. Se faltar capacidade, informar o ID e encaminhamento, sem fingir invocação ou instalar por inferência.

O futuro instalador deverá mostrar expansão transitiva/closure e detectar ciclos antes de copiar. Aqui a tabela é documental; não há resolvedor ou comando instalado. O grafo de dependências abaixo foi verificado estaticamente, inclusive união das arestas condicionais.

## Contratos e dependências

| ID | Contrato central | requires | requiresWhen — ramo: capacidade |
| --- | --- | --- | --- |
| `friday-flow` | [friday-flow](contracts/friday-flow.md) | — | pedido sem nível: `friday-triage`; ideia/conceito: `friday-discover`; recorte amplo: `friday-plan-product`; fundação nova: `friday-bootstrap`; adoção existente: `friday-adopt`; produto: `friday-specify-product`; solução: `friday-design-solution`; lentes de design: `friday-review-design`; plano: `friday-plan-tasks`; execução: `friday-run-tasks`; revisão: `friday-review`; planejar correções: `friday-plan-fixes`; aplicar correções: `friday-apply-fixes`; refatoração: `friday-plan-refactor`; auditoria: `friday-plan-remediation`; salvar/carregar: `friday-checkpoint`; aceite: `friday-accept` |
| `friday-triage` | [friday-triage](contracts/friday-triage.md) | — | — |
| `friday-discover` | [friday-discover](contracts/friday-discover.md) | — | decompor produto amplo: `friday-plan-product`; redigir PRD: `friday-specify-product` |
| `friday-plan-product` | [friday-plan-product](contracts/friday-plan-product.md) | — | criar/atualizar PRDs dos recortes: `friday-specify-product` |
| `friday-bootstrap` | [friday-bootstrap](contracts/friday-bootstrap.md) | — | redigir produto ausente: `friday-specify-product`; redigir solução ausente: `friday-design-solution`; planejar unidades ausentes: `friday-plan-tasks`; revisar fundação: `friday-review` |
| `friday-adopt` | [friday-adopt](contracts/friday-adopt.md) | — | redigir produto da adoção: `friday-specify-product`; planejar solução dependente: `friday-design-solution`; planejar execução dependente: `friday-plan-tasks` |
| `friday-specify-product` | [friday-specify-product](contracts/friday-specify-product.md) | — | revisão aprofundada de produto: `friday-review-design`; solução do PRD aprovado: `friday-design-solution` |
| `friday-design-solution` | [friday-design-solution](contracts/friday-design-solution.md) | — | DAG e contratos de tasks: `friday-plan-tasks`; revisão aprofundada de projeto: `friday-review-design` |
| `friday-review-design` | [friday-review-design](contracts/friday-review-design.md) | — | — |
| `friday-plan-tasks` | [friday-plan-tasks](contracts/friday-plan-tasks.md) | — | executar plano autorizado: `friday-run-tasks` |
| `friday-run-tasks` | [friday-run-tasks](contracts/friday-run-tasks.md) | `friday-execute-task` | revisão global ao terminar: `friday-review`; salvar/carregar contexto: `friday-checkpoint` |
| `friday-execute-task` | [friday-execute-task](contracts/friday-execute-task.md) | — | — |
| `friday-review` | [friday-review](contracts/friday-review.md) | — | — |
| `friday-plan-fixes` | [friday-plan-fixes](contracts/friday-plan-fixes.md) | — | executar correções autorizadas: `friday-apply-fixes` |
| `friday-apply-fixes` | [friday-apply-fixes](contracts/friday-apply-fixes.md) | `friday-run-tasks`, `friday-execute-task` | emitir re-revisão: `friday-review` |
| `friday-plan-refactor` | [friday-plan-refactor](contracts/friday-plan-refactor.md) | — | tasks da solução autorizável: `friday-plan-tasks` |
| `friday-plan-remediation` | [friday-plan-remediation](contracts/friday-plan-remediation.md) | — | nova feature: `friday-specify-product`; mudança estrutural: `friday-plan-refactor`; achados de revisão para correção: `friday-plan-fixes` |
| `friday-checkpoint` | [friday-checkpoint](contracts/friday-checkpoint.md) | — | — |
| `friday-accept` | [friday-accept](contracts/friday-accept.md) | — | — |

## Bundles

| Bundle | Conteúdo direto | Uso condicional |
| --- | --- | --- |
| `workflow` | `friday-flow`, `friday-triage`, `friday-specify-product`, `friday-design-solution`, `friday-plan-tasks`, `friday-run-tasks`, `friday-execute-task`, `friday-review`, `friday-plan-fixes`, `friday-apply-fixes`, `friday-checkpoint`, `friday-accept` | Fluxo básico completo. |
| `product` | `friday-discover`, `friday-plan-product`, `friday-bootstrap`, `friday-adopt` | Artefatos/capacidades do workflow conforme ramo; descoberta/planejamento avulsos não obrigam execução. |
| `maintenance` | `friday-plan-refactor`, `friday-plan-remediation` | Artefatos/capacidades do workflow conforme ramo; descoberta/planejamento avulsos não obrigam execução. |
| `design` | `friday-review-design` | Artefatos/capacidades do workflow conforme ramo; descoberta/planejamento avulsos não obrigam execução. |
| `full` | União dos quatro bundles: 19 IDs únicos por cliente. | Sem bibliotecas de aplicação instaladas. |

## Autoria, paridade e limites

O núcleo é a fonte de autoria; cada adapter contém uma cópia local do contrato e somente os recursos referenciados. Ao alterar núcleo, reconciliar as duas saídas e repetir a comparação; não há geração automática mantida. Metadata comum limita-se a `name` e `description`; instrução do host fica na entrada, fora do contrato.

As dependências de execução não concedem delegação. Sem contexts independentes autorizados, preparar pacote para nova sessão. Critérios de cliente, UI/perfis e instalador permanecem sujeitos a seus próprios testes.

A [proveniência](../../docs/research/CONTENT-PROVENANCE.md) registra revisões/adaptações e os avisos aplicáveis. O conteúdo próprio está sob MIT por escolha explícita do mantenedor na FRIDAY-005; o [aviso FRIDAY](notices/FRIDAY-MIT.txt) acompanha cada saída. Os avisos das bases cobrem suas parcelas e foram preservados. Publicação do estado atual não comprova suporte dos clientes.
