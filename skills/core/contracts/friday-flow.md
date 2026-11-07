# friday-flow

## Acionamento

Conduzir ou retomar uma entrega FRIDAY entre fases, usando estado e gates existentes; para produzir um artefato isolado, use a skill da etapa.

- Exemplo positivo: “Retome a entrega e continue pela próxima etapa autorizada.”
- Fora deste contrato: “Escreva somente o PRD desta mudança.”

## Entradas e propriedade

Pedido/ID inequívoco, instruções locais, fontes existentes e escopo autorizado.

Índice do fluxo, decisões/gates, seleção de fase e próxima ação. O coordenador mantém checkpoint e decisões; cada etapa permanece dona de seu artefato.

## Procedimento

1. Reconcilie raiz, instruções, mapa de destinos, estado real e autorizações; se houver checkpoint, siga a recuperação seletiva antes de escolher fase. Sem entrega identificável, peça somente o dado que impede localizá-la.
2. Sem nível decidido, encaminhe triage. Para ideia incerta, discover; para pedido amplo, plan-product. Produto novo segue bootstrap e existente pode seguir adopt, sempre conforme escopo e gates. Não refaça decisão anterior válida.
3. Na rota SDD: specify-product → HIL 1 → design-solution + plan-tasks → HIL 2 → run-tasks/execute-task → conferência visual pertinente → review → accept/HIL 3. Nível focused permite contrato curto equivalente; lean permite pacote conjunto. No nível concept-design, acrescente conceito e review-design nos pontos descritos em HIL.
4. Parecer com achados acionáveis segue plan-fixes → HIL de execução pertinente → apply-fixes → nova review independente. Refatoração usa plan-refactor; auditoria usa plan-remediation. Registrar seleção humana para opcionais. Não tratar review favorável como HIL 3.
5. Antes de cada ramo, confira capacidade realmente disponível ou artefato existente válido. Etapa ausente bloqueia somente a criação/atualização dependente; informe o ID necessário e como encaminhar a uma sessão/capacidade adequada. Não simule uma skill, lente, aprovação ou instalação.
6. Integre handoffs e evidências por seus donos antes de atualizar índice; não avance por movimento de arquivo. Ao aguardar gate, grave waiting_hil e o pacote concreto. Ao pausar, reconcilie escritores/processos; não encerre por snapshot.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- pedido sem nível: `friday-triage`.
- ideia/conceito: `friday-discover`.
- recorte amplo: `friday-plan-product`.
- fundação nova: `friday-bootstrap`.
- adoção existente: `friday-adopt`.
- produto: `friday-specify-product`.
- solução: `friday-design-solution`.
- lentes de design: `friday-review-design`.
- plano: `friday-plan-tasks`.
- execução: `friday-run-tasks`.
- revisão: `friday-review`.
- planejar correções: `friday-plan-fixes`.
- aplicar correções: `friday-apply-fixes`.
- refatoração: `friday-plan-refactor`.
- auditoria: `friday-plan-remediation`.
- salvar/carregar: `friday-checkpoint`.
- aceite: `friday-accept`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](../references/hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](../references/state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](../references/quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [decisions.md](../templates/decisions.md).
- [checkpoint.example.json](../templates/checkpoint.example.json) — exemplo documental, sem schema/helper executável.

## Aceite e handoff

Fase e próxima ação correspondem às fontes atuais e ao alcance humano; cada pendência tem destino e o índice não inventa progresso.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
