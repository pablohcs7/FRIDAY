# friday-checkpoint

## Acionamento

Salvar ou carregar contexto seletivo e preparar retomada de uma unidade FRIDAY; snapshot não substitui contrato, handoff ou aprovação humana.

- Exemplo positivo: “Salve o contexto desta unidade e deixe a próxima ação pronta para retomada.”
- Fora deste contrato: “Aprove a solução porque o snapshot diz que está concluída.”

## Entradas e propriedade

Entrega/unidade inequívoca, estado parcial, fontes/decisões atuais e responsáveis/processos a reconciliar.

Snapshot seletivo, proposta de atualização do índice e instrução de retomada; índice persistido somente pelo coordenador designado.

## Procedimento

1. Resolva salvar ou carregar e a unidade exata. Leia instruções, índice/decisões pertinentes e estado real; não carregue histórico inteiro para reconstruir o que as fontes duráveis já dizem.
2. Ao salvar, atualize primeiro a fonte autoritativa e capture somente fatos necessários à próxima ação, com fonte/seção, cobertura, validade e gatilhos. Não copie PRD/TechSpec ou conversa inteira.
3. Prepare atualização para o coordenador de checkpoint; se a sessão assumir esse papel, confirme unicidade antes de gravar. Siga persistência conferida/última versão válida descrita em estado/recuperação; não prometa helper inexistente.
4. Antes de pausar, confirme término de escritores/processos e consistência; handle inacessível não prova término. Checkpoint inválido é preservado e recuperado de versão anterior/fontes atuais, sem aprovação presumida.
5. Ao carregar, valide raiz/caminhos, hashes, fontes, estado e gatilhos do snapshot. Divergência rebaixa resumo a pista; contrato/evidência atual vence. Revisão independente recebe só fatos operacionais, sem narrativa do autor.
6. Sem Git/HEAD, use base: null, limitação e evidência de arquivos, inclusive manuais/não rastreados. Informe próxima ação autorizada ou gate pendente; snapshot e hash não criam consentimento.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](../references/hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](../references/state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](../references/quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [snapshot.md](../templates/snapshot.md).
- [checkpoint.example.json](../templates/checkpoint.example.json) — exemplo documental, sem schema/helper executável.

## Aceite e handoff

Fontes existentes e estado reconciliado; índice consistente pelo dono, corrupção preservada e próxima ação autorizada sem HEAD inventado.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
