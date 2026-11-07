# FRIDAY-003 — Estudo aprofundado e especificação do kit

> **Status:** DONE
>
> **Etapa:** Pesquisa e especificação para HIL

## Objetivo

Entregar comparação rastreável das duas bases, inventário de dependências e proposta concreta do catálogo de skills, perfis técnicos e instalador multiplataforma, sem implementar o kit.

## Fontes de verdade

[AGENTS](../../../AGENTS.md), [README](../../../README.md), [SOURCES](../../research/SOURCES.md), [EXECUTION-STATE](../EXECUTION-STATE.md), [HANDOFF](../HANDOFF.md) e [TASK-TEMPLATE](../TASK-TEMPLATE.md). Revisões upstream congeladas em SOURCES; fontes oficiais adicionais serão registradas no estudo.

## Dependências e autorização

FRIDAY-001 e FRIDAY-002 concluídas. Pedido de retomada em 07/11/2026 autoriza pesquisa e documentação e exige apresentação para HIL antes de implementar skills ou CLI. Definições aprovadas permanecem válidas. O mantenedor respondeu “aprovado” à pergunta de aceite das decisões HIL-003-01 a 07 em 07/11/2026. Esse aceite conclui a pesquisa/especificação e aprova o desenho e a sequência; implementação depende de uma tarefa concreta autorizada, conforme HIL-003-07. Não há autorização para commits, remotes, publicação, instalação de ferramentas, serviços pagos ou alterações externas.

## Estado identificado

Git local em `main`, sem primeiro commit e sem remote. Onze arquivos documentais esperados e não rastreados, preservados. Sem código executável, dependências, SKILL.md, CLI ou CI. Baseline do conteúdo guardada temporariamente fora do repositório para revisão das alterações desta tarefa.

## Escopo e não escopo

Estudar fluxos, templates, HIL, estado, retomada, instaladores e dependências; registrar matriz de reaproveitamento, contratos de skills, perfis e especificação do instalador. Consultar documentação oficial sem executar código upstream. Não implementar skills/CLI, instalar bibliotecas, modificar clientes ou MakerBuddy, nem publicar.

## Decisões permitidas autonomamente

Organização dos documentos, pesquisa somente leitura, critérios de análise e verificações documentais. Novas decisões materiais serão apresentadas como propostas com alternativas e consequências; não constituem aprovação de arquitetura ou execução.

## ADRs e impactos

Contratos, armazenamento e segurança documentados na especificação, com desenho aprovado pelas decisões HIL-003-01 a 07. Nenhuma migration, contrato executável ou nova dependência nesta entrega. Atribuição upstream exigida quando houver incorporação futura.

## Plano de implementação

1. Conferir leitura ordenada, Git e arquivos; abrir este plano.
2. Inspecionar as revisões congeladas, incluindo as 16 skills SDD, referências, templates, manifests e locks; mapear fluxos e integrações.
3. Consultar fontes oficiais de ferramentas, agentes e bibliotecas; distinguir inventário observado, proposta e lacunas de execução.
4. Produzir estudo comparativo e matriz, inventário de dependências, catálogo/fluxo HIL, perfis e instalador com critérios de validação futuros.
5. Revisar conteúdo e coerência, conferir links, whitespace e formatação sem instalar ferramentas; atualizar SOURCES, HANDOFF e EXECUTION-STATE.
6. Apresentar pacote concreto para HIL. Manter o plano ativo enquanto faltar o aceite humano; arquivar somente após o aceite aplicável.

## Arquivos e módulos esperados

Este plano; documentos com conteúdo real sob `docs/research/`; atualizações de SOURCES, HANDOFF e EXECUTION-STATE. Nenhum placeholder de implementação.

## Estratégia de validação

Revisar cada alteração contra a baseline; conferir caminhos relativos, nova linha final, whitespace inclusive em arquivos não rastreados, preservação de arquivos e limites Git. Usar formatter existente se disponível. Verificar cobertura das 16 skills e distinção entre decisões e propostas. Lint de aplicação, typecheck, testes funcionais e build são inaplicáveis à entrega documental. Compatibilidade dos perfis e três sistemas será somente documental, sem alegar integração executada.

## Riscos conhecidos

Fontes mutáveis e cadeias de dependências sem lock podem impedir reprodução completa; registrar revisões e limites. Licença da raiz não cobre serviços, modelos e transitivas automaticamente. Documentação atual não comprova integração entre versões. Aprovação de pesquisa não autoriza implementação nem publicação.

## Critérios de aceite

- [x] Duas bases e 16 skills SDD mapeadas com origem, fluxos e matriz de reaproveitamento.
- [x] Dependências necessárias, condicionais e excluídas inventariadas com limites e alternativas.
- [x] Catálogo com acionamento, entradas/saídas, artefatos, dependências e aceite.
- [x] Perfis condicionais e instalador nos três sistemas especificados.
- [x] Definições aprovadas preservadas; novas decisões apresentadas para HIL.
- [x] Validações documentais e revisão integral registradas; estado atualizado.
- [x] Aceite HIL registrado e plano movido para `completed/`.

## Resultado da execução

**DONE — pacote documental e decisões HIL-003-01 a 07 aprovados pelo mantenedor em 07/11/2026.** Pesquisa nas revisões congeladas e consulta adicional a fontes oficiais; 135 arquivos upstream recuperados, 16 contratos SDD mapeados, 12 upstreams opcionais identificados por revisão e metadados de 51 pacotes npm registrados. Os dados de pesquisa são duráveis, sem depender dos temporários externos usados para leitura.

Entregas: [estudo e matriz](../../research/UPSTREAM-STUDY.md), [dependências](../../research/DEPENDENCIES.md), [catálogo/estado/HIL](../../research/KIT-SPECIFICATION.md), [perfis](../../research/TECHNICAL-PROFILES.md), [instalador](../../research/INSTALLER-SPECIFICATION.md), [manifesto de fontes](../../research/source-manifest.json) e [snapshot npm](../../research/dependency-snapshot.json). SOURCES, HANDOFF e documentos de finalidade atualizados; README e decisões confirmadas preservados.

O pacote apresenta HIL-003-01 a 07 com recomendação, alternativa e consequências. A licença própria não foi definida. Implementação de skills/CLI, instalação de ferramentas, alterações externas e publicação não ocorreram. Não há SKILL.md, package.json, dependência instalada, teste de integração, commit, remote, push ou CI. O mantenedor respondeu literalmente “aprovado” à pergunta “aprova as propostas HIL-003-01 a 07 ou deseja ajustes?”. O aceite foi registrado na especificação, sem mudanças técnicas no desenho submetido, e este plano foi arquivado em `completed/`. A aprovação não transforma bibliotecas candidatas em versões selecionadas nem comprova compatibilidade prática.

Validação documental da entrega antes do HIL: Prettier 3.9.6 já existente no ambiente, aplicado apenas aos 13 arquivos novos/alterados e seguido de `--check` sobre todos os Markdown e os dois JSON: aprovado. Nenhuma ferramenta foi instalada. Verificação com Python 3: 19 arquivos, 92 links relativos válidos, dois JSON parseáveis, nova linha final, ausência de whitespace/caminhos pessoais e preservação dos 11 arquivos originais. Os seis arquivos não afetados permanecem idênticos à baseline; os outros cinco receberam apenas as atualizações documentais previstas. `git diff --no-index --check /dev/null` aplicado individualmente aos 19 arquivos, incluindo os não rastreados: aprovado. Cobertura conferida: 16 SKILL.md SDD nas fontes, 19 contratos únicos na proposta, 135 arquivos de fonte e 51 pacotes sem erro de consulta. Revisão integral das alterações contra a baseline e dos sete documentos/evidências novos, feita pelo próprio agente; não houve revisão independente. Git confirmado em `main`, sem commits/remotes. Testes de aplicação, typecheck e build são inaplicáveis. Compatibilidade dos perfis, descoberta nos clientes e matriz Windows/macOS/Linux não foram executadas. Pins finais, licenças de transitivas fora do lock Colibri e termos das distribuições/serviços selecionados permanecem para tarefas concretas futuras, sem ampliar o escopo desta pesquisa.

## Fechamento após HIL

Aprovação registrada em KIT-SPECIFICATION; SOURCES, HANDOFF, EXECUTION-STATE e documentos de finalidade reconciliados com o aceite. Próximo passo: preparar o plano concreto da etapa de contratos/templates e adapters prevista na sequência aprovada, antes da autorização de implementação. Licença própria continua pendente antes da distribuição. Nenhuma tarefa executável foi iniciada por este aceite. Validação do fechamento: Prettier 3.9.6 aprovado em todos os Markdown e JSON; 19 arquivos preservados, 97 links relativos válidos, dois JSON parseáveis, whitespace e novas linhas finais conferidos, sem caminhos pessoais. Revisão das alterações contra a versão apresentada: corpo técnico dos contratos preservado integralmente; atualizações restritas a status, aprovação, links e continuidade. Manifestos de pesquisa e demais arquivos fora do fechamento permanecem intactos. Git continua em `main`, sem primeiro commit ou remote.
