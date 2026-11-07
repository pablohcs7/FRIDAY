# TASK-ID — Título da tarefa

> **Status:** PLANNED
>
> **Etapa:** nome da etapa

## Objetivo

Definir o resultado observável e os critérios específicos da entrega.

## Fontes de verdade

Consultar AGENTS, fontes pertinentes, EXECUTION-STATE e a especificação ou o plano aprovado da etapa. Referenciar somente documentos existentes, com caminhos relativos válidos.

## Dependências e autorização

Registrar tarefas e condições necessárias, o escopo autorizado e decisões HIL já válidas. Se não houver dependências, declarar essa condição.

## Estado identificado

Descrever apenas os fatos necessários à execução: estrutura, implementações existentes, convenções, validações e limitações. Não usar como diário de desenvolvimento.

## Escopo e não escopo

Definir o que será entregue e os limites que não podem ser ampliados por inferência.

## Decisões permitidas autonomamente

Identificar detalhes locais e reversíveis resolvíveis dentro da autorização. Decisões materiais de produto, arquitetura, segurança, dados, contratos, infraestrutura ou escopo exigem HIL com uma proposta concreta.

## ADRs e impactos

Registrar decisões duráveis e possíveis efeitos em APIs, instalação, persistência, compatibilidade, segurança e observabilidade. Declarar quando um impacto ou uma migration não se aplicar.

## Plano de implementação

Descrever passos verificáveis, com dependências, resultado e evidência esperada. Reconciliar o plano antes de um desvio material.

## Arquivos e módulos esperados

Indicar os locais relevantes sem criar estruturas especulativas ou arquivos vazios para futuras funcionalidades.

## Estratégia de validação

Definir checks aplicáveis, comandos reais, ambiente necessário e limitações. Reutilizar ferramentas disponíveis. Lint, typecheck, testes e build só podem ser declarados aprovados quando executados; marcar os inaplicáveis explicitamente.

## Riscos conhecidos

Registrar riscos concretos, origem e tratamento. Manter decisões ou evidências indisponíveis como pendentes.

## Critérios de aceite

- [ ] Resultado específico entregue e verificado.
- [ ] Validações aplicáveis concluídas, com limitações registradas.
- [ ] Documentação e decisões duráveis atualizadas.
- [ ] Alterações integralmente revisadas e limitadas ao escopo.
- [ ] Estado de execução atualizado; plano concluído movido para `completed/`.

Acrescentar os critérios particulares antes da implementação.

## Resultado da execução

Preencher ao concluir ou bloquear: status, resumo da entrega, comandos e resultados, impactos, desvios materiais e continuidade. Informar commit, push e CI somente quando existirem e fizerem parte da autorização; caso contrário, declarar sua ausência.
