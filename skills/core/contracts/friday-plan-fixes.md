# friday-plan-fixes

## Acionamento

Converter achados de uma revisão exata em tasks de correção rastreáveis; não aplica correções nem altera retroativamente o parecer.

- Exemplo positivo: “Planeje correções para os achados desta revisão específica.”
- Fora deste contrato: “Corrija o código e declare os achados encerrados agora.”

## Entradas e propriedade

Revisão exata/imutável, achados atuais, código/contratos pertinentes e seleção humana dos opcionais.

Tasks de correção e DAG integrado ao manifesto canônico, ligados a caminho da revisão + ID.

## Procedimento

1. Resolva uma revisão inequívoca por caminho/ID; múltiplas candidatas exigem escolha. Preserve relatório emitido e identidade composta dos achados.
2. Classifique cada item como acionável, informativo, resolvido comprovadamente ou pendente. Reconheça duplicatas pela identidade/causa; status desconhecido permite só acionáveis explícitos. Opcionais dependem de seleção humana.
3. Reconfira evidência no estado atual e atribua destino a todos os itens. Agrupe mesma causa somente quando produzir resultado revisável; não reclassifique parecer nem edite relatório para removê-lo.
4. Escreva tasks com arquivos, resultado, testes/pré-requisitos e DAG local de correções integrado à fonte única da entrega. Reutilize IDs/handoffs existentes; não crie plano concorrente.
5. Prepare autorização de execução pertinente com efeitos e escopo. Planejamento não aplica correção; encaminhe apply-fixes somente após autorização válida.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- executar correções autorizadas: `friday-apply-fixes`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](../references/hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](../references/state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](../references/quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [tasks.md](../templates/tasks.md).
- [task.md](../templates/task.md).

## Aceite e handoff

Todo acionável tem destino sem duplicação; opcionais selecionados, DAG acíclico, parecer preservado e execução ainda condicionada ao gate pertinente.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
