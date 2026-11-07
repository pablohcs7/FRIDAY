# friday-plan-product

## Acionamento

Decompor um resultado amplo em recortes com aceite e dependências antes dos PRDs; um único PRD sem necessidade de recorte usa specify-product.

- Exemplo positivo: “Organize este produto em entregas coesas antes dos PRDs.”
- Fora deste contrato: “Detalhe apenas os requisitos de uma entrega já delimitada.”

## Entradas e propriedade

Visão/brief ou pedido amplo, resultados, restrições, decisões e recortes existentes.

Mapa de recortes, critérios, DAG entre entregas e destinos das obrigações, com escolha humana do recorte material.

## Procedimento

1. Inventarie obrigações e fontes; reutilize IDs e destinos existentes. Fonte incompleta vira pendência e não requisito inventado.
2. Proponha fatias com um resultado principal verificável, coesão e dependências explícitas. Um produto simples pode ficar em um recorte; não crie roadmap artificial.
3. Mapeie toda obrigação para recorte, adiamento ou fora de escopo explícito. Confira grafo acíclico, cobertura, prioridades e frentes que podem ser independentes.
4. Apresente opções de recorte e efeitos; preserve escolha anterior válida. Obtenha a decisão material antes de escrever os PRDs dependentes.
5. Encaminhe cada recorte selecionado a specify-product, sem implementar ou reabrir entrega concluída por escopo novo.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- criar/atualizar PRDs dos recortes: `friday-specify-product`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [product-plan.md](../assets/product-plan.md).

## Aceite e handoff

Cada obrigação tem destino, o DAG não tem ciclos e os recortes têm resultado/aceite e decisão rastreável.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
