# friday-plan-remediation

## Acionamento

Transformar relatório de auditoria com evidências em frentes e destinos revisáveis; não exige ferramenta de auditoria específica nem implementa automaticamente.

- Exemplo positivo: “Planeje frentes a partir deste relatório de auditoria.”
- Fora deste contrato: “Execute uma auditoria nova e corrija tudo automaticamente.”

## Entradas e propriedade

Relatório identificável com origem/evidência, código atual e autorização para planejar.

Mapa de achados, frentes/rotas e destinos, com seleção humana e contratos das frentes aprovadas.

## Procedimento

1. Fixe relatório exato e versão/hash; ambiguidade requer escolha. Ausência de relatório bloqueia planejamento dessa origem; não execute ferramenta externa de auditoria por inferência.
2. Reconfira evidências no código/configuração atuais, preservando relatório. Classifique todo achado com identidade da origem, situação atual, impacto, dependências e destino.
3. Proponha frentes coesas: nova feature, refatoração, correção ou adiamento. Evite duplicar tasks/planos já existentes; confira dependências sem ciclos e colisões.
4. Apresente prioridades, efeitos e alternativas para seleção humana das frentes. Frentes aprovadas/adiadas ficam explícitas; autorização para planejar não autoriza implementação.
5. Encaminhe cada rota selecionada às capacidades pertinentes para produto/solução/tasks ou correções. Fonte, skill ou ambiente ausente fica como pendência do ramo; nada de sucesso ou aprovação inventados.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- nova feature: `friday-specify-product`.
- mudança estrutural: `friday-plan-refactor`.
- achados de revisão para correção: `friday-plan-fixes`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [remediation.md](../assets/remediation.md).

## Aceite e handoff

Todo achado classificado/reconferido, frente e destino explícitos, recorte escolhido pelo humano e nenhuma implementação automática.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
