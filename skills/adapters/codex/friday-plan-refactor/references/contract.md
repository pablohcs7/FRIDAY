# friday-plan-refactor

## Acionamento

Planejar mudança estrutural preservando comportamento com baseline, R-IDs e rede de segurança; não implementa refatoração nem adiciona feature.

- Exemplo positivo: “Planeje refatorar este módulo sem mudar o comportamento público.”
- Fora deste contrato: “Reescreva o produto e acrescente novos fluxos sem escopo.”

## Entradas e propriedade

Alvo exato, comportamento atual, motivação, limites e evidências do código/testes.

PRD/TechSpec de refatoração com R-IDs, baseline, melhoria estrutural mensurável, validação, sequência e rollback.

## Procedimento

1. Resolva alvo/operação e preserve documentos anteriores/IDs. Inspecione entradas, saídas, erros, efeitos, callers, persistência e bordas; planos de outra entrega não descrevem o runtime atual.
2. Numere comportamentos R-01 em diante, com fonte e verificação. Separe intenção, defeito aparente e mudança solicitada; lacuna que muda aceite vai ao humano.
3. Planeje caracterização onde falta proteção; baseline/snapshot exige revisão do comportamento capturado. Sequencie rede de segurança antes da mutação e fatias reversíveis antes de risco irreversível.
4. Descreva melhoria estrutural mensurável, contratos que permanecem, dados/migrações pertinentes e rollback. Reuse PRD/TechSpec com seção de refatoração, sem novas funcionalidades ou reescrita total por preferência.
5. Prepare produto/solução para gates pertinentes e encaminhe plan-tasks após decisões necessárias. Não implemente por efeito do plano; lacuna crítica permanece impedimento explícito.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- tasks da solução autorizável: `friday-plan-tasks`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [prd.md](../assets/prd.md).
- [techspec.md](../assets/techspec.md).

## Aceite e handoff

Todos os comportamentos do escopo têm R-ID, origem e proteção/pendência; melhoria verificável sem expansão funcional e execução condicionada à autorização.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
