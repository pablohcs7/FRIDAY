# friday-plan-tasks

## Acionamento

Decompor PRD e TechSpec em DAG e contratos de tasks executáveis; execução do plano aprovado pertence a run-tasks.

- Exemplo positivo: “Converta esta solução em tasks com dependências e verificações.”
- Fora deste contrato: “Execute agora uma task já aprovada.”

## Entradas e propriedade

PRD, TechSpec, decisões/riscos e planos/handoffs existentes.

tasks.md como manifesto único, contratos em tasks/active e pacote de HIL 2; nenhuma implementação.

## Procedimento

1. Leia fontes estáveis e inventarie tasks ativas/concluídas, IDs e evidências. Preserve manuais, handoffs e maior ID existente; não recrie uma task concluída para escopo novo.
2. Mapeie toda obrigação, decisão, risco e teste para unidade/destino. Para fonte legada sem ID, registre identificador local com origem, sem reescrever documento alheio.
3. Planeje fatias com resultado revisável, arquivos atribuídos, dependências e validação na mesma unidade. Confira DAG acíclico, órfãos e colisões; execução serial é suficiente.
4. Especifique efeitos autorizados, fora de escopo, pré-requisitos, comandos reais e evidências de aceite. Ambiente ausente é pendência com tarefas afetadas, não tarefa ficticiamente executável.
5. Apresente matriz de cobertura e TechSpec + DAG/tasks concretos para HIL 2. O autor do plano não implementa por efeito de escrevê-lo; preservar aprovação anterior inalterada.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- executar plano autorizado: `friday-run-tasks`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [tasks.md](../assets/tasks.md).
- [task.md](../assets/task.md).

## Aceite e handoff

Cobertura sem órfãos/ciclos, responsabilidades e limites por task claros, comandos/ambiente verificáveis ou bloqueios explícitos; HIL 2 recebe pacote completo.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
