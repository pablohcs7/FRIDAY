# friday-execute-task

## Acionamento

Implementar uma única task exata com escopo e autorização válidos, registrando validação e handoff; não gerencia o DAG nem aprova a entrega.

- Exemplo positivo: “Execute somente T-03 conforme o contrato e os arquivos atribuídos.”
- Fora deste contrato: “Escolha novas frentes e altere todas as dependências do plano.”

## Entradas e propriedade

Task inequívoca, fontes pertinentes, dependências comprovadas, autorização e escopo de escrita.

Artefatos/código atribuídos, checks proporcionais e handoff na task; sem alteração de DAG/checkpoint global.

## Procedimento

1. Resolva uma task exata e fontes atuais, incluindo contrato curto equivalente quando o nível permitir. Ambiguidade ou fonte/dependência ausente bloqueia a unidade; task concluída só é reaberta com causa e autorização.
2. Confira instruções locais, arquivos/manuais, callers e testes pertinentes. Preserve alterações preexistentes. Mapeie cada critério ao ponto de implementação e à evidência necessária.
3. Implemente a menor mudança coerente nos arquivos atribuídos. Detalhes locais reversíveis podem ser resolvidos autonomamente; mudança material de produto, contrato, dados, arquitetura ou infraestrutura vai ao gate com proposta concreta.
4. Execute checks que correspondem à mudança e registre comando, ambiente, resultado e falhas. Ausência de ferramenta/serviço mantém obrigação pendente com erro/comando/impacto; não marque teste não executado.
5. Atualize documentação durável afetada dentro do escopo e grave handoff, incluindo parciais, riscos, recursos ativos e próxima ação. Retorne ao coordenador para integração; não mova tasks nem altere DAG global ou emita autoaceite.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](../references/hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](../references/state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](../references/quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [task.md](../templates/task.md).

## Aceite e handoff

Critérios atendidos e evidência atual para cada obrigação ou bloqueio explícito; nenhuma task concluída apenas porque houve edição.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
