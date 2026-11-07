# Catálogo de skills

A primeira implementação de conteúdo está na bancada: **19 contratos comuns e 19 entradas para cada cliente, Codex e Claude Code**. As árvores locais passaram por verificações estáticas de metadata, recursos e paridade. Ainda não foram instaladas nem testadas em sessões reais dos clientes; a FRIDAY-004 foi aceita para versionamento/publicação pelo mantenedor na FRIDAY-005.

## Onde está cada peça

- [Catálogo](core/catalog.md): responsabilidades, bundles, `requires` e `requiresWhen`.
- [Contratos](core/contracts): autoria das 19 capacidades, com entradas, saídas e critérios.
- [Referências](core/references): HIL, estado/recuperação e qualidade/independência; ler por contexto.
- [Templates](core/templates): materiais para os artefatos do consumidor, incluindo exemplo JSON sem schema ou helper executável.
- [Adapter Codex](adapters/codex) e [adapter Claude Code](adapters/claude-code): SKILL.md por capacidade com recursos locais autocontidos.
- [Origem por arquivo e avisos](../docs/research/CONTENT-PROVENANCE.md) e [verificações/limitações](../docs/validation/FRIDAY-004-content-checks.md).

As saídas são cópias reconciliadas do núcleo; não há gerador mantido ou instalador. Cada skill leva apenas seu contrato e recursos necessários, sem depender do clone FRIDAY, repositório upstream, symlink ou pasta irmã. Metadata usa somente name/description; o texto específico de cada host fica na entrada. Não há configuração, hook ou pré-autorização de tools embutida.

## Direção preservada

O kit cobre descoberta de produto, recorte, bootstrap/adoção, especificação, tarefas, execução, revisão, correções, aceite e retomada. O núcleo independe de Jira e de ferramentas externas obrigatórias; capacidades indisponíveis são pendências explícitas do ramo.

O fluxo preserva participação humana HIL, autorização ligada a conteúdo/escopo e decisões anteriores válidas. Especificações, decisões, planos concluídos e evidências permanecem no consumidor. Snapshot é pista e não cria consentimento. O comportamento dessas instruções ainda precisa ser observado nos clientes.

## Perfis técnicos

As tecnologias são preferências condicionais, não dependências universais. Reutilizar arquitetura, UI, tokens e convenções existentes. Para web sem base de componentes: Mantine + styled-components; formulários com React Hook Form, Zod e `@hookform/resolvers`. Sem design definitivo, usar aparência provisória coerente e estados completos, limitados ao escopo. Expo/React Native e Kotlin/Android são perfis separados.

As referências orientam a seleção; nenhuma aplicação ou combinação de bibliotecas foi executada nesta tarefa. As definições estão em [SOURCES](../docs/research/SOURCES.md).

## Continuidade

Após a publicação do estado atual na FRIDAY-005, preparar tarefa concreta para validar descoberta e fluxo documental em sessões reais dos dois clientes, conforme a [sequência aprovada](../docs/research/KIT-SPECIFICATION.md). Instalação, comandos de uso verificados, perfis práticos e CLI pertencem às etapas seguintes.

Os avisos MIT aplicáveis acompanham o conteúdo derivado. O conteúdo próprio está sob [MIT](../LICENSE), conforme escolha do mantenedor; os avisos upstream foram preservados e cada saída inclui o aviso próprio. Nenhum pacote ou comando de instalação está publicado. O repositório público contém o estado de desenvolvimento.
