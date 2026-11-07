# Estado, autoria e recuperação

## Destinos e donos

Reutilize a convenção do consumidor, registrando um mapa único de destinos. Sem equivalente, use `docs/friday/features/<slug>/`. Crie apenas artefatos da fase: brief, PRD, TechSpec, `tasks.md`, `tasks/active/`, `tasks/completed/`, `decisions.md`, `checkpoint.json`, `snapshot.md` e `reviews/<id>/`. Não migre arquivos existentes só para seguir o fallback; nunca mantenha duas fontes concorrentes.

| Responsável | Escrita permitida |
| --- | --- |
| Coordenador do fluxo | Checkpoint e registro de decisões. Integra propostas dos demais papéis, sem inventar decisão humana. |
| Coordenador de tasks/correções | DAG, manifesto e movimentos de tasks; entrega atualização ao coordenador do fluxo. |
| Autor de produto/solução | Seus contratos e derivados explicitamente reconciliados. |
| Executor | Arquivos atribuídos e handoff da task exata. Não altera DAG nem checkpoint global. |
| Revisor | Relatório novo e evidências próprias; não corrige o alvo durante o parecer. |
| Checkpoint | Prepara snapshot e atualização; só persiste índice quando atua como coordenador designado e sem outro escritor. |

Uma sessão pode exercer papéis sequencialmente, respeitando essas fronteiras. Não usar escritores concorrentes na mesma unidade. Sem coordenador ativo, designe um único responsável na sessão antes da escrita do índice. Delegação exige autorização e capacidade real; execução serial é normal.

Preserve contratos, decisões, evidências, IDs e planos concluídos. Relatório emitido é imutável: nova revisão referencia a anterior. Artefatos históricos de outra entrega não estabelecem comportamento atual nem devem ser atualizados retroativamente; consulte código, testes e documentação durável atuais.

## Índice documental

O exemplo de checkpoint é material de autoria: não é schema executável ou helper. Preserve os campos propostos sem prometer validação automatizada. Antes do primeiro código de persistência, validar formatos/enums e compatibilidade em tarefa própria.

| Campo | Significado documental |
| --- | --- |
| `schemaVersion`, `generation` | Versão ilustrativa 1; geração aumenta somente depois de gravação conferida. Versão desconhecida impede uso automático. |
| `featureId`, `objective`, `level` | Entrega e resultado exatos; nível decidido ou `null` antes do HIL 0. |
| `phase` | `triage`, `concept`, `product`, `solution`, `tasks`, `execution`, `review`, `fixes`, `acceptance`, `completed`. |
| `status` | `active`, `waiting_hil`, `paused`, `blocked`, `completed`. |
| `sources` | Fontes existentes com caminhos relativos à raiz atual do consumidor; ausentes não ganham caminhos fictícios. |
| `approvedSources` | Itens com `path`, `sha256`, `decisionId` e `scope`. Devem resolver para decisão humana e conteúdo reais. |
| `pendingHil`, `blockers`, `reviewStatus` | Gate/pergunta/itens afetados, bloqueios com evidência e parecer atual, ou `null` quando não existe. |
| `correctionRound`, `roundsWithoutProgress` | Contadores persistidos entre sessões, sem reinício para contornar escalonamento. |
| `base`, `limitations` | HEAD resolvido ou `null` sem Git/commit; limitações e evidência das mudanças, inclusive não rastreadas. |
| `nextAction` | Ação concreta, capacidade necessária e fontes/seções a ler; pode aguardar autorização. |

Paths de documentos são relativos à raiz atual do consumidor; confirme o root e o mapa de destinos na retomada. Rejeite caminhos que escapem desse root ou apontem a recursos inesperados. Não execute absolutos herdados após clone/movimento. Owner real, PID/host, handles e evidência local de worktree pertencem a runtime local ignorado, por exemplo `.friday/runtime/`; não versionar esses dados, home, tokens ou credenciais. Confira o ignore do consumidor antes de gravar runtime; se a alteração não estiver autorizada, mantenha essa parte pendente e não grave dado sensível.

## Salvar, pausar e recuperar

1. Atualize primeiro a fonte autoritativa: contrato, decisão, handoff ou revisão. Confira estado real, referências, obrigações e escritores/processos ativos. Handle inacessível não prova término.
2. Prepare índice temporário na mesma pasta, faça parse do JSON e confira tipos/valores/referências manualmente. Preserve a última versão válida e substitua com operação local segura suportada pelo ambiente; releia o resultado. Sem operação segura disponível, preserve originais, registre limitação e não anuncie checkpoint íntegro.
3. Só registre pausa segura após confirmar ausência de escritores/processos ativos e persistência completa. Não estime porcentagem de contexto como telemetria. Falha de escrita ou fonte ausente mantém obrigação pendente; preservar parciais para recuperação.
4. Na retomada: instruções locais → índice/decisões pertinentes → fontes, hashes e estado real → snapshot pelos gatilhos → artefatos da próxima unidade. Evite carregar histórico inteiro.
5. Checkpoint ilegível/corrompido fica preservado. Reconstitua pela última versão válida e fontes atuais; não crie aprovação faltante. Reabra unidades só com ID, causa e evidência, preservando o histórico.

Snapshot é pista, não contrato. Registre cobertura, validade e entradas com gatilhos `now`, `on-select`, `on-edit` e `on-run`; leia somente as correspondentes. Código/configuração/ambiente ou escopo alterados invalidam a revisão afetada; movimento de arquivo e status não comprovam conclusão. Atualizar hash sem análise não restaura autorização. Sem HEAD, `base: null`, hashes de arquivos e limitação são suficientes para retomar documentalmente; nunca invente commit.
