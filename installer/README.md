# Instalador do FRIDAY

Esta pasta reserva a área do futuro instalador próprio. Atualmente contém somente este documento: não existe CLI executável, pacote publicado ou comando de instalação do FRIDAY.

## Direção confirmada

O instalador será implementado em Node.js com TypeScript, atendendo Windows, macOS e Linux. O conceito do instalador Node.js da Colibri é uma referência de estudo, com catálogo, bundles, seleção de agentes, prévia de mudanças e proteção dos arquivos administrados.

Suas responsabilidades serão instalar, listar, atualizar e remover skills, além de diagnosticar pré-requisitos. A instalação de ferramentas da máquina e das bibliotecas de uma aplicação não será sua responsabilidade padrão. As skills tratarão as bibliotecas conforme o plano técnico aprovado do projeto consumidor.

## Interfaces previstas

Os nomes `list`, `install`, `update`, `remove` e `doctor` representam o desenho aprovado, ainda sem implementação. O plano também prevê seleção de Codex e Claude Code, escopos de projeto ou usuário e opções `--dry-run`, `--json` e `--cwd`. A cópia será o método padrão.

O diagnóstico deverá distinguir ferramentas encontradas, ausentes, incompatíveis e não verificadas. Declarar requisitos de sistema não comprova disponibilidade de binários, credenciais ou funcionamento de integrações.

## Dependências a validar

Commander, `@clack/prompts`, `yaml` e Zod são as bibliotecas propostas para o CLI. As APIs nativas do Node.js serão priorizadas para arquivos, processos e hashes. Nenhum pacote foi instalado, nenhuma versão foi selecionada e nenhum motor externo de instalação foi incorporado nesta etapa.

A [especificação aprovada do instalador](../docs/research/INSTALLER-SPECIFICATION.md) detalha catálogo/estado, agentes, prévia, conflitos, transações, recuperação, diagnóstico e validação futura nos três sistemas. O desenho aprovado da v1 usa cópia nativa de catálogo local, sem motor `skills`, symlink ou `--force`; essas escolhas foram aprovadas no [HIL](../docs/research/KIT-SPECIFICATION.md). Não há implementação nem teste prático de instalação. Consulte também [Fontes e definições](../docs/research/SOURCES.md).
