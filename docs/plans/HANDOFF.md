# Handoff — FRIDAY

> **Checkpoint:** 07/11/2026
>
> **Situação:** FRIDAY-004 concluída e aceita para versionamento/publicação. FRIDAY-005 em execução: repositório público criado, MIT escolhida e primeiro commit/push em preparação. Descoberta nos clientes ainda não verificada e CLI inexistente.

## 1. Retomada

Abra a próxima sessão na raiz do repositório **FRIDAY**. Ele é independente do repositório vizinho MakerBuddy.

Leia nesta ordem:

1. [AGENTS](../../AGENTS.md).
2. [EXECUTION-STATE](EXECUTION-STATE.md).
3. Este handoff.
4. [README](../../README.md).
5. [SOURCES](../research/SOURCES.md), fonte das definições e referências.
6. [Finalidade das skills](../../skills/README.md) e [finalidade do instalador](../../installer/README.md).
7. [TASK-TEMPLATE](TASK-TEMPLATE.md).
8. [Plano concluído FRIDAY-003](completed/FRIDAY-003-kit-specification.md).
9. [Especificação aprovada](../research/KIT-SPECIFICATION.md), com decisões HIL-003-01 a 07.
10. [Plano concluído FRIDAY-004](completed/FRIDAY-004-contracts-and-adapters.md), com escopo, arquivos, dependências e critérios da primeira implementação.
11. [Proveniência](../research/CONTENT-PROVENANCE.md) e [validação FRIDAY-004](../validation/FRIDAY-004-content-checks.md).
12. [Plano ativo FRIDAY-005](active/FRIDAY-005-github-publication.md), autorização de publicação e licença.
13. Consultar estudo, dependências, perfis e instalador pelos links da especificação, conforme o item em revisão.

Confira Git e arquivos atuais antes de agir. A conversa anterior e caches de ferramentas não são necessários para retomar. Em caso de divergência, reconcilie a evidência atual e as decisões registradas; não sobrescreva mudanças desconhecidas.

## 2. O que existe

- Repositório Git local inicializado na branch `main`, **sem commit e sem remote** no momento deste checkpoint.
- README aprovado, com homenagem à F.R.I.D.A.Y., sigla e curiosidade sobre Robinson Crusoé.
- AGENTS, gitignore, finalidade de `skills/` e `installer/`, fontes, decisões, template e acompanhamento de tarefas.
- Estudo e especificação FRIDAY-003 em `docs/research/`: comparação das 16 skills SDD, matriz, inventário, contratos aprovados de 19 skills, perfis e instalador; manifests de pesquisa com 135 arquivos recuperados, 12 upstreams opcionais e metadados de 51 pacotes npm. Essas contagens medem a pesquisa, não integrações testadas.
- Conteúdo FRIDAY-004: 19 contratos, três referências, 14 templates, catálogo/bundles, 38 entradas autocontidas, proveniência por arquivo e avisos MIT completos. Verificação estática não comprova execução das instruções.
- Fundação concluída em [FRIDAY-001](completed/FRIDAY-001-repository-foundation.md) e handoff registrado em [FRIDAY-002](completed/FRIDAY-002-session-handoff.md).

Os arquivos aparecem como **não rastreados** porque o primeiro commit não foi criado. São a entrega esperada deste checkpoint, não resíduos a apagar ou motivo para reiniciar a fundação.

Existem 38 arquivos `SKILL.md` nas árvores de autoria locais. Não há `package.json`, dependências instaladas do FRIDAY, gerador mantido, schema/helper executável de checkpoint, CLI, CI, release ou publicação. Nenhuma skill foi instalada ou executada em cliente real. Os nomes de comandos no documento do instalador descrevem interfaces previstas.

## 3. Decisões que permanecem válidas

- Kit de **skills separadas**, com núcleo independente, para Codex e Claude Code.
- Cobrir descoberta, planejamento e criação de produtos, SDD, execução, revisão, correções, aceite e retomada; incluir adoção de projetos existentes.
- Extrair do vibe-coding-toolkit a dinâmica de produto/bootstrap e da Colibri o fluxo SDD padronizado, com seu conceito de HIL.
- Preservar documentação concluída e evidências no repositório consumidor. **Jira não é requisito.**
- Respeitar arquitetura e UI existentes. Na falta da definição visual definitiva, usar componentes necessários ao escopo com uma aparência provisória bonita e consistente, sem exigir construir tudo a partir de primitives sem estilos.
- Para web sem base de componentes: **Mantine + styled-components**. Formulários: **React Hook Form + Zod + `@hookform/resolvers`**, sem adicionar `@mantine/form` por padrão. Tailwind e shadcn/ui não são preferências padrão.
- Base de tecnologias: TypeScript, React, Next.js, Expo/React Native, NestJS, PostgreSQL/TypeORM, MongoDB/Mongoose, Kotlin para Android nativo, AWS, Docker, Git, pnpm, RabbitMQ e Redis. Aplicar perfis conforme a necessidade, sem instalar tudo em todo produto.
- Instalador próprio em Node.js/TypeScript para Windows, macOS e Linux: gerenciar skills e diagnosticar pré-requisitos. Não preparar automaticamente a máquina nem instalar as bibliotecas de aplicações.
- README informal, direto e com energia de oficina. Documentação narrativa em português; AGENTS e EXECUTION-STATE em inglês; código, identificadores e filenames em inglês.

As bibliotecas auxiliares e integrações listadas em SOURCES são propostas a verificar, salvo as escolhas já confirmadas. Não reabrir decisões encerradas sem evidência ou necessidade material.

## 4. Fontes congeladas do estudo preliminar

| Base                                                                                                                        | Revisão                                    |
| --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------ |
| [vibe-coding-toolkit](https://github.com/soumatheusgomes/vibe-coding-toolkit/tree/21b71b68679c11184f49c23168852014bf6dde8b) | `21b71b68679c11184f49c23168852014bf6dde8b` |
| [agents-instructions](https://github.com/ColibriAgile/agents-instructions/tree/9c8ca3b1baca119aa2c2f6ded46454530d3e587a)    | `9c8ca3b1baca119aa2c2f6ded46454530d3e587a` |

A pesquisa preliminar foi aprofundada na FRIDAY-003. Na FRIDAY-004, 71 arquivos congelados foram recuperados com Git blob SHAs conferidos; houve adaptação de conteúdo com origem por arquivo e cópia integral dos avisos MIT. Não há código executável upstream copiado. Consulte novamente somente fontes necessárias à alteração. As licenças MIT das duas revisões foram conferidas; dependências externas têm suas próprias distribuições e licenças a auditar. O conteúdo próprio está sob MIT, escolhido explicitamente pelo mantenedor na FRIDAY-005; avisos upstream preservados.

Pode consultar revisões mais recentes para documentação e compatibilidade. Registre diferenças em relação à base congelada; não troque silenciosamente o alvo da comparação.

## 5. Próxima ação: concluir publicação autorizada

O mantenedor respondeu **“aprovado”** à pergunta de aceite das decisões **HIL-003-01 a 07** em 07/11/2026. O [plano FRIDAY-003](completed/FRIDAY-003-kit-specification.md) foi concluído e arquivado. O [registro de aceite](../research/KIT-SPECIFICATION.md) preserva o escopo e a origem da aprovação. Não repetir esse HIL para conteúdo e escopo inalterados.

O desenho aprovado cobre 19 skills com adapters separados, estado durável e runtime local separado, níveis/HIL sem modo auto na v1, perfis condicionais, instalador de cópia nativa sem `skills`/symlink/`--force`, integrações opcionais e sequência de implementação. Bibliotecas auxiliares continuam candidatas até seleção por necessidade; versões observadas não são pins aprovados e compatibilidade ainda não foi executada.

Os detalhes e evidências estão no [estudo e matriz](../research/UPSTREAM-STUDY.md), [inventário](../research/DEPENDENCIES.md), [perfis](../research/TECHNICAL-PROFILES.md), [instalador](../research/INSTALLER-SPECIFICATION.md), [manifesto de fontes](../research/source-manifest.json) e [snapshot npm](../research/dependency-snapshot.json). Não dependem do cache temporário usado na pesquisa.

O pedido de retomada preparou o [plano FRIDAY-004](completed/FRIDAY-004-contracts-and-adapters.md). Em seguida, o mantenedor respondeu literalmente “sim” à pergunta “Autoriza executar a FRIDAY-004 nesse escopo local?”. A autorização foi registrada e aplicada sem ampliar o escopo.

As unidades 004-01 a 004-05 produziram o conteúdo e o pacote de aceite. Após a apresentação, o mantenedor pediu “crie um repositorio publico e faça commit no meu github”. Esse pedido aceita o conteúdo para o marco de versionamento/publicação e autoriza repositório, commit, remote e push na [FRIDAY-005](active/FRIDAY-005-github-publication.md). A FRIDAY-004 foi arquivada como DONE; não repetir seu aceite nem a autorização da publicação.

O mantenedor escolheu “MIT, preservando os avisos das duas bases”. LICENSE e aviso próprio nas saídas foram adicionados; atribuições upstream preservadas. O repositório https://github.com/pablohcs7/FRIDAY foi criado vazio e público; autenticação SSH confirmada como pablohcs7. Próximo passo: validar os arquivos, criar commit e enviar main, conferindo visibilidade e SHA. Depois do marco, preparar plano concreto da validação de descoberta/fluxo documental nos clientes, sem iniciá-la por inferência.

## 6. Validação disponível e limitações

As verificações atuais de conteúdo constam da [validação FRIDAY-004](../validation/FRIDAY-004-content-checks.md): metadata YAML, inventário, paridade, recursos autocontidos, dependências e higiene documental. O parser Ruby/Psych disponível substituiu o quick_validate.py, que falhou por falta de PyYAML; nenhuma dependência foi instalada. Prettier não foi localizado e não foi executado. Não houve testes comportamentais dos clientes ou dos três sistemas. Os registros a seguir preservam a evidência histórica da fundação.

A fundação passou por Prettier, revisão de nove arquivos, verificação de 13 links relativos, whitespace, nova linha final e ausência de caminhos pessoais no conteúdo público. O MakerBuddy foi preservado. O registro completo está na FRIDAY-001.

O FRIDAY ainda não possui ferramentas locais de qualidade. A sessão anterior reutilizou um executável Prettier já disponível no ambiente, sem instalar dependências; sua disponibilidade não é um requisito reproduzível do projeto. Reutilize uma ferramenta disponível ou registre a limitação em outro ambiente. Para arquivos novos não rastreados, `git diff --check` sozinho não verifica seu conteúdo: a fundação usou `git diff --no-index --check /dev/null <arquivo>` para cada arquivo.

Lint de aplicação, typecheck, testes funcionais e build não se aplicaram à fundação documental. Nenhuma integração com Mantine, serviços, agentes ou plataformas foi executada para demonstrar compatibilidade.

A atribuição da sigla ao quadrinho de Avengers Campus tem evidência secundária documentada; não foi feita inspeção direta dos quadros. O ano 1719 corresponde ao livro, não às expressões posteriores. Preservar essas distinções no README.

## 7. Limites da retomada

O desenho, o conteúdo apresentado e sua publicação atual estão autorizados no alcance registrado. A FRIDAY-005 inclui criar repositório público, commit, remote e push, sem release ou promessa de suporte prático. Instalação de ferramentas/skills, configurações de agentes, delegação, serviços pagos e AWS continuam fora do escopo. Não modificar o MakerBuddy.
