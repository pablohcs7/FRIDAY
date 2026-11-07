# friday-triage

## Acionamento

Recomendar e registrar o nível de processo para pedido novo de mudança, correção ou refatoração; retomada com nível válido pertence ao fluxo.

- Exemplo positivo: “Este pedido precisa de fluxo completo ou ajuste pontual?”
- Fora deste contrato: “Retome uma entrega com nível já aprovado e inalterado.”

## Entradas e propriedade

Pedido compreensível, instruções e inspeção local curta. Uma chave de issue sem descrição não basta.

Sinais com fonte, recomendação focused/lean/complete/concept-design e pacote/registro de HIL 0.

## Procedimento

1. Inspecione somente o necessário para reconhecer resultado, arquivos/módulos envolvidos, contratos, dados e reversibilidade. Não faça build ou auditoria ampla para decidir o processo.
2. Aplique a rubrica de níveis da referência HIL: classifique sinais com evidência, unknown e consequências. Área crítica, contrato público ou decisão material aberta encaminha complete; concept-design depende dos sinais de incerteza descritos, não só de risco alto.
3. Apresente nível recomendado, esforço, alternativas e disponibilidade de lentes independentes quando pertinentes. Não imponha roadmap ou stack para completar uma triagem.
4. Obtenha HIL 0, salvo decisão humana anterior explícita e válida para mesmo pedido/escopo. Prepare registro para o coordenador de decisões; não escreva no índice global se não for esse responsável.
5. Fonte ausente permanece unknown; peça apenas o que altera nível/aceite e encaminhe a próxima capacidade sem inventar requisito ou aprovação.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](../references/hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](../references/state-and-recovery.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [decisions.md](../templates/decisions.md).

## Aceite e handoff

Nível escolhido pelo humano ou autorização anterior comprovada; sinais e alcance documentados e nenhuma execução liberada por inferência.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
