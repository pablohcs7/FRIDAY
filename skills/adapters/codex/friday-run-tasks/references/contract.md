# friday-run-tasks

## Acionamento

Coordenar DAG e executar sequência de tasks autorizadas com um executor por unidade; para uma única task exata, use execute-task.

- Exemplo positivo: “Execute o plano autorizado e continue entre as tasks elegíveis.”
- Fora deste contrato: “Redija um novo plano de implementação ainda não aprovado.”

## Entradas e propriedade

Plano/HIL 2 válidos, estado atual, dependências e handoffs com evidência.

Seleção elegível, manifesto/DAG atualizado, integração de evidências e movimentos de tasks; o coordenador de fluxo recebe atualização do índice.

## Procedimento

1. Reconcilie plano, mudanças locais, fontes/hash, autorização e estado real; arquivo em completed não basta como prova. Mantenha uma fonte do DAG e um escritor por unidade.
2. Selecione task pendente com dependências comprovadamente concluídas, sem colisão de arquivos/processos. Bloqueio permite seguir somente independentes já autorizadas; não amplie o plano para evitar espera.
3. Use friday-execute-task para uma unidade por vez com contrato/arquivos/fontes exatos. Sem essa capacidade, bloqueie execução e informe o ID necessário; não simule implementação ou handoff. Delegação somente autorizada e suportada.
4. Confira resultado e evidências integradas antes de marcar conclusão ou mover task. Executor não muda DAG; este coordenador integra status e informa o responsável pelo checkpoint.
5. Continue entre elegíveis dentro do limite do chamador. Ao receber tarefa única, retorne após sua integração; ao completar plano, prepare revisão independente e visual pertinente, sem aceitar o próprio trabalho.
6. Falhas ou duas rodadas sem progresso exigem diagnóstico/exceção; pausa exige reconciliação de escritores/processos e checkpoint consistente, sem assumir término por handle inacessível.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora. Para executar esta capacidade, requer `friday-execute-task`.

- revisão global ao terminar: `friday-review`.
- salvar/carregar contexto: `friday-checkpoint`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [tasks.md](../assets/tasks.md).

## Aceite e handoff

Cada conclusão sustentada por evidência e dependências; DAG e movimentos reconciliados, sem falsa conclusão por arquivo ou contagem.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
