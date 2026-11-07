# Especificação do instalador multiplataforma

> **FRIDAY-003 · Revisão 1 · APPROVED.** Não há CLI, pacote, binário ou comando de instalação disponível. Exemplos de nomes/flags abaixo são desenho de interface, não instruções de uso executáveis.

Desenho aprovado em 07/11/2026 pelas decisões HIL-003-05/06, no [aceite do kit](KIT-SPECIFICATION.md). Termos de proposta descrevem o desenho futuro aprovado; implementação e verificação permanecem pendentes.

## Objetivo e recorte

Gerenciar skills FRIDAY para Codex/Claude Code em escopos de projeto/usuário e diagnosticar pré-requisitos. Node.js/TypeScript estrito e cópia padrão já são direção aprovada. Propõe-se uma v1 sem download remoto próprio, backend `skills`, symlinks, adoção de arquivos manuais ou alteração de configuração do cliente. O pacote local conterá catálogo e payloads compilados/validados; distribuição via npm/GitHub ainda não foi decidida nem autorizada.

Não instalar ferramentas, bibliotecas de aplicação, browser, Docker, JDK/Android SDK ou MCP; não modificar PATH, login, modelos, permissões, hooks, `AGENTS.md`, `CLAUDE.md`, `.codex/config.toml` ou Claude settings. Listar uma ferramenta ausente não autoriza instalá-la. Não fazer telemetria, login ou chamada externa implícitos.

Referência de arquitetura: [estudo Colibri](UPSTREAM-STUDY.md), [dependências](DEPENDENCIES.md) e [decisões HIL-003-05/06](KIT-SPECIFICATION.md). Reusar ideias de catálogo/plano/propriedade; implementar contrato próprio, preservando atribuição ao derivar código.

## Catálogo, bundles e requisitos

Propor catálogo distribuído com schema versionado, YAML para autoria e validação estrita antes do empacotamento. Conteúdo: `catalogVersion`, `kitVersion`, `skills`, `bundles`, `profiles`, `agentAdapters` e `requirements`. Cada skill declara ID/name únicos, descrição, arquivos por cliente, SHA-256 por arquivo, origem/revisão/licença/notices, `requires`, `requiresWhen` e capacidades necessárias/condicionais. Bundles referenciam IDs existentes; ciclos, caminhos inválidos, hashes incorretos e notices ausentes rejeitam o catálogo.

O pacote contém apenas arquivos regulares permitidos; destinos são derivados de agente/escopo e ID validado, nunca uma string de destino arbitrária vinda do catálogo. Rejeitar caminhos absolutos, `..`, prefixos de drive/UNC no payload, symlinks, hardlinks, dispositivos, nomes reservados Windows, componentes com colon/trailing dot/space, duplicatas por case e colisões Unicode normalizadas. Limitar contagem/tamanho e rejeitar conteúdo fora do root resolvido. Schema desconhecido ou catálogo modificado sem hashes válidos bloqueia escrita.

Sem `--catalog` arbitrário, URLs, archives ou scripts pós-instalação na v1 proposta. Atualizar o kit exige obter outra distribuição por processo externo autorizado; `update` reconcilia o catálogo local selecionado, não consulta `latest`. Integridade local por hash detecta divergência; não prova autenticidade de uma distribuição, que deverá ser tratada na etapa de publicação.

Requisitos são dados: capacidade, necessidade, plataforma, versão/faixa, probe permitido, efeito, fallback e documentação. Ausência de entrada significa desconhecido. Não copiar o status de um pré-requisito de um sistema para outro nem tratar declaração como detecção.

## Escopos e destinos

| Agente      | Projeto                         | Usuário                         |
| ----------- | ------------------------------- | ------------------------------- |
| Codex       | `<root>/.agents/skills/<name>/` | `<home>/.agents/skills/<name>/` |
| Claude Code | `<root>/.claude/skills/<name>/` | `<home>/.claude/skills/<name>/` |

Esses destinos têm suporte documental nas [OpenAI Docs](https://learn.chatgpt.com/docs/build-skills) e [Claude Code Docs](https://code.claude.com/docs/en/skills), consultadas em 07/11/2026. Não implicam suporte a todas as versões/modos cloud. Uma configuração de diretório diferente deve ser detectada e reportada como destino não suportado nessa primeira interface, sem escrever em outro lugar ou sobrescrever a configuração. A implementação deverá definir a faixa de versões do cliente após provar descoberta real; ainda não há mínimo testado.

`--cwd` resolve a raiz alvo explicitamente, sem subir silenciosamente ao pai. Exibir caminho resolvido e eventual relação com Git/monorepo na prévia; Git não é obrigatório. Fora de repositório, operar no diretório explícito com limitação registrada. Root e home são caminhos locais resolvidos pelo sistema, sem presumir prefixos específicos do sistema. No Windows, usar APIs nativas de path e argumentos, suportando PowerShell/cmd sem exigir pwsh/fzf.

Projeto e usuário podem coexistir. Detectar duplicidade de names e avisar sobre descoberta/precedência do host; não remover cópia do outro escopo nem tratá-la como gerenciada. O inventário é independente por escopo e agente. Instalar para ambos os clientes produz dois payloads autocontidos; remover um não apaga o outro.

## Interfaces propostas

Nome de binário/package fica para a implementação/publicação; as cinco ações e flags abaixo especificam comportamento. CLI sem argumentos pode abrir wizard somente em TTY. Nenhuma preferência salva equivale a consentimento de uma mutação futura.

| Ação      | Seleção e leitura                                                                             | Resultado e limites                                                                                                                                                                                                     |
| --------- | --------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `list`    | Catálogo, bundles, agentes/escopos e inventário local                                         | Distingue available/managed/modified/manual/missing/unknown; mostra versões/hashes e duplicidades. Somente leitura; não adota conteúdo.                                                                                 |
| `install` | Skills ou bundles, agente(s), escopo e catálogo empacotado                                    | Expande dependências, monta prévia e aplica cópia só nos destinos livres/compatíveis. Idempotente: mesmo conteúdo e estado produz `unchanged`.                                                                          |
| `update`  | Itens gerenciados selecionados; sem seleção, todos daquele escopo/agentes, exibidos na prévia | Atualiza para o payload do catálogo local; não aumenta seleção para bundles novos silenciosamente. Inclusão de dependência nova entra na prévia; downgrade é explícito e destacado, sem aplicar por inferência.         |
| `remove`  | IDs gerenciados exatos e agente(s)/escopo                                                     | Remove somente arquivos comprovadamente gerenciados e intactos; dependentes instalados impedem remoção sem seleção coerente. Preserva manuais/modificados e diretórios com extras; nunca apaga pasta pai compartilhada. |
| `doctor`  | Kit/estado, agente e requisitos das skills/perfis selecionados                                | Relatório de ferramentas, descoberta não comprovada, conflitos, journal e instruções de correção manual. Sem instalar/reparar ou abrir login.                                                                           |

Flags comuns propostas: `--agent codex|claude-code` repetível; `--scope project|user`; `--cwd`; seleção por `--skill`/`--bundle`; `--dry-run`; `--json`. `--yes` aceita uma prévia sem prompt apenas dentro das guardas, nunca suprime conflito. Ausência de flags essenciais em automação produz erro acionável; não escolher usuário/global por default. Wizard pode recomendar projeto, mas exige escolha explícita antes de escrever. Combinações ambíguas são erro; flags de leitura não podem ativar mutação por acidente.

`--dry-run` não grava lock, journal, diretórios, preferências ou caches; lê e produz plano. Mutação real recalcula/verifica a prévia sob lock imediatamente antes de aplicar. Em TTY, mostrar seleção, closure, escopo, destinos, versão/hash anterior e novo, inclusão/remoção, requisitos, conflitos e limitações, antes da confirmação. No uso automatizado, argumentos + `--yes` autorizam somente esse plano revalidado; mudança nos arquivos desde a prévia exige novo plano e falha segura.

`--json` garante stdout com um objeto, sem ANSI/spinner/prompt; diagnóstico humano pode ir a stderr sem dados sensíveis. Proposta de envelope v1: `schemaVersion`, `command`, `scope`, `agents`, `catalogVersion`, `status`, `plan`, `changes`, `diagnostics`, `recovery`. Ações são `create`, `replace`, `remove`, `unchanged`, `conflict`, com caminhos locais exibidos somente no contexto local. Códigos propostos: 0 sucesso/prévia sem conflito; 1 falha operacional; 2 argumentos/schema inválidos; 3 conflito; 4 pré-requisito obrigatório ausente/incompatível no diagnóstico; 5 recuperação necessária; 130 cancelamento/SIGINT. Os testes deverão fixar o contrato, incluindo JSON válido em erro.

## Propriedade e arquivos manuais

Propor estado local de projeto em `.friday/installer/state.json` e de usuário em `<home>/.friday/installer/state.json`. Locks/journal/staging/backups vivem no mesmo domínio de estado, com staging de payload junto do destino para renomeação no mesmo filesystem. Os metadados locais não são contratos de produto e devem ser ignorados no consumidor; não editar `.gitignore` automaticamente. A documentação de adoção explica como ignorar, caso o mantenedor queira.

Estado v1 proposto: `schemaVersion`, `generation`, `kitVersion`, `catalogDigest`, `scope`, `installationId`, `managedSkills`; por item: `skillId`, `agent`, `adapterVersion`, `sourceRevision`, `payloadDigest`, `installedFiles` com paths/hashes, `installedAt` e `updatedAt`. O root é resolvido a cada execução; não executar destino absoluto guardado em estado importado. Preferências não incluem credenciais, modelo ou permissões.

Uma entrada de estado sozinha não autoriza apagar: confrontar lista de arquivos, hashes e destino real. Diretório idêntico sem propriedade é `manual`, sem adoção automática. Estado inválido é preservado e impede mutação; `doctor` explica recuperação sem inventar owner. Não implementar `--force` na v1.

| Situação                                  | Comportamento proposto                                                                                                                                                          |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Destino livre                             | Criar após prévia/autorização e journal preparados                                                                                                                              |
| Gerenciado, hash atual igual ao instalado | Atualizar/remover conforme plano; operação repetida sem mudança é no-op                                                                                                         |
| Manual, mesmo name, mesmo conteúdo        | Conflito de propriedade; mostrar alternativa de manter/renomear manualmente, sem tomar posse                                                                                    |
| Gerenciado mas editado                    | Conflito; preservar conteúdo e mostrar arquivos divergentes. Usuário pode salvar fora e reconciliar manualmente antes de nova execução                                          |
| Arquivo extra numa pasta gerenciada       | Preservar; não remover pasta toda; bloquear substituição/remoção que apagaria o extra                                                                                           |
| Arquivo gerenciado ausente                | Reportar drift; `install` pode planejar recriar somente ausentes se todos os demais corresponderem; `remove` pode limpar registro após verificar nenhum remanescente inesperado |
| Pai/destino symlink ou junction           | Rejeitar mutação e mostrar caminho real, sem seguir para fora do root exibido                                                                                                   |
| Estado/catálogo com schema desconhecido   | Somente diagnóstico; não reinterpretar nem recriar arquivo por cima                                                                                                             |

Não prometer proteção absoluta contra outro processo malicioso alterando paths durante cópia. O contrato exige revalidar pais/tipos/hashes sob lock, usar operações exclusivas e evitar seguir links; alterações concorrentes detectadas falham preservando evidência. Repositórios/máquinas sem confiança e filesystems remotos não entram no suporte inicial sem testes próprios.

## Transação, concorrência e interrupções

Propor operação atômica no nível lógico da seleção inteira, com journal para recuperação. Não prometer uma renomeação única cobrindo múltiplos diretórios. Fases:

1. Resolver escopo, validar catálogo/estado e preparar plano somente leitura; em conflito, não aplicar parcialmente os itens válidos.
2. Após autorização, adquirir lock exclusivo do escopo, conferir geração/hash e paths atuais; dois processos sobre o mesmo root/estado não escrevem juntos. Detectar aliases/case para o mesmo escopo. Estado de lock inclui token/PID/host; PID reutilizado ou host inacessível não autoriza remover lock automaticamente.
3. Gravar journal `prepared` com seleção, hashes esperados, destinos e localização de backups; stage completo e validado antes de qualquer troca. Se criação do journal/stage falhar, destinos ficam intactos.
4. Para cada item, preservar backup anterior, registrar intenção, substituir/criar no destino com operação local segura e conferir hash. Atualizar journal após cada transição; todo registro necessário à reversão deve anteceder a mutação correspondente.
5. Conferir seleção inteira; gravar estado novo de forma segura com geração incrementada; marcar journal `committed`; só então limpar stage/backups e liberar lock. Falha de limpeza é pendência de housekeeping, não instalação desconhecida.
6. Falha antes do commit lógico inicia rollback dos itens aplicados em ordem inversa, desde que seus hashes ainda correspondam ao que a operação gravou. Arquivo alterado por terceiro impede rollback destrutivo: preservar backups e sinalizar `recovery_required`, com caminhos e ações, sem sobrescrever intervenção manual.

Em SIGINT/SIGTERM cooperativos, parar novas mutações e tentar rollback antes de sair. Crash, SIGKILL, falta de energia e encerramento do Windows não garantem handler: próxima operação detecta journal e bloqueia novas escritas até reconciliar. `doctor` apresenta estado e procedimento; repetir a mesma ação com confirmação explícita de recuperação deve oferecer restaurar a transação incompleta, ou finalizar cleanup se o commit já estiver comprovado, sem criar subcomando obrigatório novo. Recuperação revalida hashes/owner, gera prévia e tem seu próprio journal; não se baseia só em idade do lock.

Primeira v1 deverá suportar apenas filesystem local com semântica comprovada. Mesmo com renomeação local, durabilidade após queda de energia depende do filesystem/OS; estratégia de flush e Windows file locking precisa de teste. Não declarar atomicidade física de lote ou rollback infalível. Código upstream e seus testes são referência, não evidência dessas garantias FRIDAY.

## Diagnóstico e ferramentas ausentes

Status por check: `found`, `missing`, `incompatible`, `unverified`, `not_applicable`; separar severidade de necessidade. Cada registro traz ID, comando/probe, versão observada, faixa exigida e motivo, plataforma, consequência e alternativa. Binário encontrado não comprova credencial; credencial configurada não comprova serviço.

Probes locais curtos e permitidos: versão Node; binário/version do cliente, Git/pnpm quando aplicáveis; JDK/Gradle/Android SDK para perfil selecionado; disponibilidade do executável Docker sem iniciar daemon. Usar argumentos separados, timeout e limites de saída; não executar arbitrariamente strings do catálogo. Consulta ao daemon, navegador, rede/cloud ou autenticação não entra em `doctor` básico; testes adicionais exigem escopo próprio. Não disparar `npx`/download ao verificar uma ausência.

Para clientes, reportar diretório de destino, conflitos, metadata e instrução de reabrir/verificar descoberta. O CLI não pode provar descoberta sem executar o host; marca `unverified`. Ausência do cliente permite copiar as skills se isso for a intenção explícita e destino estiver válido, com descoberta pendente; ausência de Node impede executar o CLI. Ausência de ferramenta de um perfil não bloqueia copiar instruções, mas mantém sua execução/aceite pendentes.

## Matriz de validação futura

Nenhum caso abaixo foi executado nesta pesquisa. Propor Node 24 e 26, ambos LTS na consulta; o floor e os pins reais virão do plano da implementação. Validar pelo menos Windows x64, macOS arm64 e Linux x64; não prometer suporte às demais arquiteturas sem execução.

| Dimensão               | Casos e critério de aceite                                                                                                                                                                |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Windows/macOS/Linux    | Install/update/remove/list/doctor nos dois agentes e escopos, a partir de pacote compilado em caminho temporário; sem PowerShell obrigatório, Git, symlink ou dependência global de build |
| Portabilidade          | Espaços, acentos/Unicode, diretório sem Git, CRLF/LF em arquivo manual, case-insensitive, nomes Windows, caminhos longos, junction/symlink e permissões negadas; nenhum escape de root    |
| Propriedade            | Manual/modificado/extra/ausente/estado inválido e duplicidade projeto/usuário; hashes dos manuais e settings permanecem iguais antes/depois                                               |
| Idempotência e bundles | Instalar duas vezes; update sem mudança; dependência transitiva/ciclo ausente; remover dependente/provedor; seleção dos dois agentes; no-op sem mudar geração injustificadamente          |
| Concorrência           | Dois processos no mesmo escopo/aliases; estado alterado após prévia; lock ativo/órfão/PID reutilizado; sem takeover automático e sem perda de dados                                       |
| Interrupções           | Injeção de falha em cada fase; SIGINT/SIGTERM; encerramento forçado/SIGKILL e reexecução; rollback/recovery preserva conteúdo e não anuncia sucesso parcial                               |
| I/O e recuperação      | Disco cheio/erro de rename/backup/journal/estado/cleanup; mudança externa durante rollback; backups preservados e JSON com recovery claro                                                 |
| Automação/TTY          | `--dry-run` com snapshot de filesystem intacto; JSON parseável em sucesso/erro; cancelamento sem gravação; sem TTY e sem flags falha sem aguardar; `--yes` não ignora conflito            |
| Diagnóstico            | PATH vazio, versões incompatíveis, ferramentas ausentes e probes com timeout; found não vira authenticated/working; nenhuma rede/download/configuração alterada                           |
| Descoberta             | Sessões reais de Codex/Claude Code com versões registradas, carregamento de referências e uma operação documental; sem simular discovery só pela pasta                                    |
| Empacotamento          | Catálogo/payload completo e notices, sem credenciais/arquivos pessoais/source maps indevidos; execução sem TypeScript/pnpm dev no destino; inspeção do artefato antes de publicação       |

Critério de release: cenários de lifecycle e proteção/recuperação essenciais passam nos três sistemas; resultados persistidos com versões/arquiteturas e falhas conhecidas. Se um sistema não estiver disponível, registrar `not run` e limitar a alegação de suporte, sem usar o resultado macOS como validação Windows/Linux. CI e publicação pertencem a etapas futuras autorizadas.
