# friday-apply-fixes

## Acionamento

Executar correções já planejadas e autorizadas, integrar evidências e encaminhar re-revisão independente; não cria ou reclassifica achados.

- Exemplo positivo: “Aplique as tasks de correção aprovadas para esta revisão.”
- Fora deste contrato: “Inventar correções para melhorias opcionais ainda não selecionadas.”

## Entradas e propriedade

Plano de correção, revisão exata, escopo/autorização e dependências atuais.

Correções, evidências/handoffs integrados e pacote para nova revisão independente; achados não fecham por movimento de arquivo.

## Procedimento

1. Confira identidade da revisão, plano canônico de correções, seleção humana de opcionais e autorização válida. Fonte ausente bloqueia dependentes, sem modificar o parecer.
2. Use run-tasks e execute-task para controle serial de unidades e integração de evidências. Sem essas capacidades necessárias, informe quais faltam; não replique coordenador concorrente.
3. Mantenha rastreabilidade revisão + ID → task → mudança → verificação. Trate causa e efeitos integrados, preservando falhas preexistentes e obrigações pendentes.
4. Ao terminar, prepare pacote de re-revisão com novo alvo/hashes e evidências atuais para friday-review em contexto que não escreveu as correções. Sem contexto autorizado, deixe pacote para nova sessão.
5. Preserve relatórios e contadores; causa reaparecida é reabertura. Duas rodadas sem progresso vão a exceção; não encerre achado ou entrega só por mover task, aprovar o próprio código ou atingir teto.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora. Para executar esta capacidade, requer `friday-run-tasks`, `friday-execute-task`.

- emitir re-revisão: `friday-review`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](../references/hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](../references/state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](../references/quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [task.md](../templates/task.md).

## Aceite e handoff

Correções autorizadas e integradas, causa/evidência ligadas aos achados e re-revisão nova encaminhada; fechamento depende de parecer/gates válidos.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
