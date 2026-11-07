# friday-review-design

## Acionamento

Avaliar clareza e coerência de brief, PRD ou TechSpec/tasks por lentes independentes antes da implementação; revisão de código entregue usa review.

- Exemplo positivo: “Teste se este PRD e esta TechSpec se sustentam para um leitor novo.”
- Fora deste contrato: “Corrija o código durante o parecer da entrega.”

## Entradas e propriedade

Pacote delimitado de produto/projeto/conceito, fontes permitidas, hashes, lentes exigidas e estado de rodadas.

Relatório novo por rodada com paráfrases, achados/destinos, independência, fontes e convergência; resolução do autor fica separada.

## Procedimento

1. Fixe pacote e escopo: produto tem duas lentes, projeto cinco; conceito usa seis quando solicitado pela descoberta. Aplique os papéis e critérios da referência qualidade/independência.
2. Confirme contexto independente autorizado/disponível. Sem ele, prepare pacote para nova sessão e registre pendência; não simule Goldfish por persona nem forneça conversa/justificativa do autor às lentes.
3. Registre hashes antes/depois e as fontes de cada lente; alteração do alvo invalida avaliação afetada. Colete paráfrase e achados com severidade, evidência, identidade e destino, sem editar o alvo no parecer.
4. Encaminhe ao autor a resolução separada: contestar só com prova acessível; escalar quando fonte faltar ou mudar produto aprovado; corrigir com edição concreta; recusar só opcional menor. Não reclassifique achado para obter convergência.
5. Avalie rodada limpa antes das correções: produto exige uma em até duas, projeto duas consecutivas em até três. Lente ausente nunca é limpa. Teto ou reabertura de achado vai a HIL com edições/custo e sem reauditoria automática.
6. Preserve relatórios emitidos e comunique quais gates podem prosseguir. Mudança material no PRD exige reconciliação/aprovação e invalida derivados atingidos.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](../references/hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](../references/state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](../references/quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [design-review.md](../templates/design-review.md).

## Aceite e handoff

Lentes previstas executadas com independência e fontes, ou limitação submetida ao gate; convergência demonstrada sem usar teto como aprovação.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
