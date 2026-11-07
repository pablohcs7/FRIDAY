# friday-discover

## Acionamento

Amadurecer problema, ideia ou conceito em brief antes do PRD, incluindo lentes quando o nível exigir; revisão de especificação já escrita usa review-design.

- Exemplo positivo: “Transforme esta ideia em um brief com hipóteses e opções.”
- Fora deste contrato: “Revise a clareza deste PRD já escrito.”

## Entradas e propriedade

Problema/público/contexto, restrições, evidência disponível e código existente quando pertinente.

Brief com visão, hipótese, opções, perguntas e decisões; evidência das lentes aplicáveis e encaminhamento a produto.

## Procedimento

1. Converse para esclarecer necessidade, uso atual, resultado e restrições; inspecione evidência local antes de pressupor produto novo. Diferencie fato, premissa e decisão. Pesquisa externa ausente exige premissas identificadas.
2. Compare não fazer, reusar e reduzir escopo; registre alternativas de produto e técnicas separadamente. Não selecione tecnologia como substituto da descoberta.
3. Em descoberta simples, produza brief proporcional. No ramo concept-design, prepare hipótese e opções para HIL Hipótese; só após âncora humana organize as seis lentes de conceito descritas em qualidade/independência.
4. Lentes recebem pacote delimitado, sem conversa ou justificativa do autor; registre fontes/hashes, resultado e falhas. Sem contexto independente autorizado/disponível, prepare pacote para nova sessão e leve a limitação ao gate; não declare lentes realizadas.
5. Consolide perguntas com respostas propostas, tradeoffs e alterações; apresente HIL Brief quando aplicável. Preserve estado do brief e decisões anteriores; desacordo material vai ao humano.
6. Encaminhe obrigações e alternativas rejeitadas ao PRD/solução, preservando IDs e rastreabilidade. Não transforme brief em autorização de implementação.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- decompor produto amplo: `friday-plan-product`.
- redigir PRD: `friday-specify-product`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [brief.md](../assets/brief.md).

## Aceite e handoff

Brief suficiente para o recorte, hipóteses e limitações explícitas; gates do ramo concluídos ou mantidos pendentes sem inventar independência.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
