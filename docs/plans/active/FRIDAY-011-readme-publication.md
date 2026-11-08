# FRIDAY-011 — Publicação do README visual

> **Status:** IN_PROGRESS
>
> **Etapa:** Publicação documental

## Objetivo

Publicar no GitHub o README, imagens e ajustes HIL aprovados nas FRIDAY-009/010.

## Fontes de verdade

[README](../../../README.md), [SOURCES](../../research/SOURCES.md), [estado](../EXECUTION-STATE.md), [template](../TASK-TEMPLATE.md), [FRIDAY-009](../completed/FRIDAY-009-readme-scenarios.md), [FRIDAY-010](../completed/FRIDAY-010-readme-workflow-language.md) e [publicação anterior](../completed/FRIDAY-005-github-publication.md).

## Dependências e autorização

O mantenedor respondeu “pode publicar” após revisar README e diagrama. Autoriza commit e push da revisão documental em main no origin existente, sem repetir confirmação. Não inclui publicação da frente paralela FRIDAY-008.

## Estado identificado

Main local e remota em b3e1e8c, origin pablohcs7/FRIDAY público, permissão push confirmada. Index limpo. README/assets e planos editoriais ainda locais; estado/HANDOFF e arquivos da FRIDAY-008 têm alterações concorrentes. README aponta para relatório ainda não publicado.

## Escopo e não escopo

Publicar README, três arquivos de assets, planos 009/010/011 e somente as partes editoriais do estado compartilhado. Substituir links ao relatório não publicado por resumo de estado com limitações. Preservar integralmente as mudanças da FRIDAY-008 no working tree. Sem release, CI, mudança em skills ou push forçado.

## Decisões permitidas autonomamente

Mensagem do commit, referências internas válidas e staging seletivo do estado. Conferência remota por Git e conector já autenticados.

## ADRs e impactos

Sem mudança de contrato. Resumo público de validação identifica amostragem Codex, falha parcial e Claude pendente; relatório detalhado pertence à frente separada. Publicação documental não concede suporte de runtime.

## Plano de implementação

1. Reconciliar links e preparar resumo público sem importar os arquivos paralelos.
2. Validar a árvore exata a publicar: links/âncoras, SVGs, whitespace e escopo.
3. Criar commit com paths explícitos e estado selecionado; enviar main sem força.
4. Conferir SHA e blobs remotos, registrar resultado e arquivar este plano.

## Arquivos e módulos esperados

README, docs/assets/readme, planos 009/010/011 e trecho editorial do EXECUTION-STATE. Nenhuma alteração em HANDOFF ou validação por esta tarefa.

## Estratégia de validação

Inspeção do staged diff, validação de links contra o index (não contra arquivos locais excluídos), SVG/XML, âncoras, asteriscos HIL, higiene documental e novas linhas finais. Reutilizar renderizações já conferidas para os SVGs inalterados. Git diff --cached --check, SHA remoto/local e árvore/blobs. Testes de aplicação não se aplicam; nenhuma dependência nova.

## Riscos conhecidos

Publicar links para conteúdo somente local ou incluir alterações paralelas pelo staging integral. Validar o index exato e preservar os arquivos excluídos sem sobrescrita. A outra frente continua escrevendo; mudanças nos seus hashes durante a publicação são registradas como concorrência, sem restaurar versões antigas. Mudança remota inesperada exige inspeção, nunca força.

## Critérios de aceite

- [ ] Árvore publicada contém somente o conjunto editorial e links resolvíveis.
- [ ] Arquivos paralelos preservados sem sobrescrita ou inclusão no commit.
- [ ] Commit e push concluídos; SHA e conteúdo remoto conferidos.
- [ ] Resultado/estado registrados e plano arquivado.

## Resultado da execução

Preparação: oito arquivos editoriais no index; 87 links/âncoras resolvem contra a árvore exata preparada, incluindo diretórios e a nota HIL. SVG/XML, title/desc, recursos locais, whitespace, novas linhas finais e git diff --cached --check aprovados. Renderizações anteriores preservadas porque as imagens não mudaram nesta tarefa. Diff preparado revisado pelo autor; sem revisão independente.

Links do README ao relatório ainda local passaram a apontar para um resumo público no estado, com amostragem, falha parcial e Claude pendente. Staging seletivo do estado foi feito a partir da revisão publicada e das seções editoriais, preservando o working tree compartilhado. HANDOFF, relatório/evidências/fixtures, plano FRIDAY-008 e mudanças nas skills permanecem fora do index desta publicação. A primeira comparação de hashes detectou escrita concorrente da outra frente, sem restauração ou sobrescrita. A checagem de links/escopo do index foi repetida e aprovada. Commit/push em execução.
