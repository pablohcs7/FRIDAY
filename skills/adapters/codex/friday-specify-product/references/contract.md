# friday-specify-product

## Acionamento

Criar ou atualizar PRD com requisitos e aceite para uma entrega delimitada; arquitetura e tasks pertencem às etapas técnicas.

- Exemplo positivo: “Escreva o PRD desta entrega com RF/RNF/US e aceite.”
- Fora deste contrato: “Escolha a arquitetura e implemente as tasks.”

## Entradas e propriedade

Pedido/brief, evidências, recorte, decisões e PRD anterior quando existir.

prd.md com obrigações estáveis, jornadas, aceite, limites, premissas e pacote HIL 1.

## Procedimento

1. Resolva entrega, mapa de destinos e operação criar/atualizar autorizada. Preserve PRD existente e IDs; brief aprovado é fonte inicial, não deve competir com outro documento de produto.
2. Mapeie problema, usuários, jornadas, RF/RNF/US, bordas, acessibilidade, métricas e restrições pertinentes. Use fontes do usuário/organização para regra interna, sem inferência normativa.
3. Reconcilie cada obrigação do brief/recorte a requisito ou destino explícito. Separe fato, premissa, decisão e fora de escopo; não desenhe arquitetura nem DAG.
4. No nível concept-design, encaminhe revisão de produto com duas lentes independentes antes de HIL 1. Sem capacidade, prepare pacote para sessão nova e mantenha limitação explícita.
5. Prepare PRD e aceite para HIL 1; registre proposta ao coordenador de decisões. Mudança material em PRD aprovado invalida derivados afetados e exige novo aceite somente dessa parte.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- revisão aprofundada de produto: `friday-review-design`.
- solução do PRD aprovado: `friday-design-solution`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [prd.md](../assets/prd.md).

## Aceite e handoff

Toda obrigação coberta ou pendência explícita; critérios observáveis e IDs preservados; HIL 1 válido antes de execução dependente.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
