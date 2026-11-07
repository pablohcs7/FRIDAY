# friday-accept

## Acionamento

Preparar pacote final e obter aceite humano de uma entrega revisada; fechamento não autoriza commit, publicação ou deploy.

- Exemplo positivo: “Prepare o aceite final com revisão, evidências e pendências.”
- Fora deste contrato: “Faça push e publique porque os testes passaram.”

## Entradas e propriedade

Produto/solução correspondentes, revisão atual, validações integradas, decisões e visual/manual pertinentes.

Pacote de aceite, decisão HIL 3 e encaminhamento de fechamento/arquivo após aprovação válida.

## Procedimento

1. Reconcilie obrigações e evidências com o alvo atual, incluindo configuração/ambiente e revisão. Mudança posterior invalida parte afetada; status e task movida não bastam.
2. Confira parecer e independência exigida pelo nível/contrato. Reveja visual/manual pertinentes, limitações e pendências; obrigação essencial impede fechamento, mesmo se descrita como risco aceito.
3. Apresente opcionais com impacto/esforço para seleção de correção ou aceite como pendência. Não use ressalva para contornar requisito, segurança ou ambiente essencial não validado.
4. Prepare pacote concreto com resultado, fontes/hashes, revisão/evidências e continuidade. Peça HIL 3 somente se não houver resposta anterior válida para mesmo conteúdo/escopo; sem resposta mantenha waiting_hil.
5. Após aceite válido, entregue decisão ao coordenador para atualizar estado, arquivar plano e preservar contratos, revisões e histórico. Sem publicação, commit, push ou deploy por efeito desse fechamento.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [acceptance.md](../assets/acceptance.md).

## Aceite e handoff

Nenhuma obrigação bloqueante aberta e decisão HIL 3 atual registrada; sem resposta, entrega permanece aguardando e o plano não é arquivado como concluído.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
