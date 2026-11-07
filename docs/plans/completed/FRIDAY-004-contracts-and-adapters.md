# FRIDAY-004 — Contratos, templates e adapters iniciais

> **Status:** DONE — conteúdo aceito para versionamento e publicação
>
> **Etapa:** Primeira implementação de conteúdo do kit

## Objetivo

Materializar os 19 contratos aprovados em um núcleo independente e produzir as respectivas skills de conteúdo para Codex e Claude Code, com templates, referências autocontidas e rastreabilidade upstream. Entregar conteúdo verificável localmente, sem alegar descoberta ou funcionamento nos clientes antes da etapa de integração.

## Fontes de verdade

[AGENTS](../../../AGENTS.md), [README](../../../README.md), [SOURCES](../../research/SOURCES.md), [EXECUTION-STATE](../EXECUTION-STATE.md), [HANDOFF](../HANDOFF.md), [TASK-TEMPLATE](../TASK-TEMPLATE.md), [FRIDAY-003](../completed/FRIDAY-003-kit-specification.md), [especificação aprovada](../../research/KIT-SPECIFICATION.md), [matriz upstream](../../research/UPSTREAM-STUDY.md) e [manifesto de fontes](../../research/source-manifest.json).

Na execução, consultar documentação oficial atual dos dois clientes e as instruções aplicáveis de criação de skills disponíveis na sessão. Registrar data, URL, versão do cliente quando observável e diferenças em relação à pesquisa de 07/11/2026. Reabrir decisão somente se houver incompatibilidade material; não substituir silenciosamente revisões upstream congeladas.

## Dependências e autorização

FRIDAY-001 a 003 concluídas. HIL-003-01 a 07 aprovaram o desenho e a sequência; continuam válidas para escopo inalterado. O pedido “pode prosseguir de acordo com onde paramos”, em 07/11/2026, retoma a próxima ação registrada: preparar este plano concreto. Em seguida, o mantenedor respondeu literalmente “sim” à pergunta “Autoriza executar a FRIDAY-004 nesse escopo local?”. Essa resposta autoriza a execução deste plano em 07/11/2026, conforme HIL-003-07; não reabre o desenho aprovado nem amplia os limites abaixo.

A autorização solicitada abrange autoria local dos arquivos previstos e verificações locais sem instalar ferramentas. Não abrange instalação das skills em clientes, edição de configurações, dependências novas, delegação, commits, remotes, push, release, publicação ou serviços pagos. A licença própria permanece por decidir antes de distribuição; sua ausência não impede autoria local. Se uma validação exigir ampliar esses limites, apresentar o impedimento e a proposta antes de agir.

## Estado identificado

- Git local em `main`, sem primeiro commit e sem remote; 19 arquivos documentais existentes antes deste plano, todos não rastreados e preservados.
- `skills/` e `installer/` contêm somente seus documentos de finalidade. Não há SKILL.md, código executável, package.json, dependências do FRIDAY ou CI.
- Catálogo, bundles, níveis, gates, propriedade dos artefatos e recuperação já possuem desenho aprovado. As fontes e a pesquisa são duráveis; o cache upstream não é dependência.
- Node.js 24.14.0 e Python 3 estão disponíveis neste ambiente. Nenhuma ferramenta disponível na máquina passa a ser requisito instalado do kit por esse fato.

## Escopo e não escopo

Entregar:

- 19 contratos centrais em Markdown, com gatilhos/exclusões, entradas, saídas, propriedade, dependências condicionais, gates, limitações e aceite.
- Referências comuns de HIL, estado/recuperação e qualidade/independência, carregadas somente quando pertinentes.
- Templates dos artefatos realmente usados pelos contratos, incluindo exemplo de checkpoint documental. O exemplo não constitui schema executável nem helper de persistência.
- Dois adapters de conteúdo por contrato: 19 entradas Codex e 19 Claude Code, cada uma com SKILL.md conciso e recursos locais necessários. A existência dos 38 arquivos não comprova descoberta nos hosts.
- Catálogo documental com bundles, `requires` e `requiresWhen`, distinguindo capacidade instalada de artefato existente suficiente para uma entrada.
- Origem por arquivo adaptado e avisos MIT completos aplicáveis, acompanhando também os recursos derivados nas duas saídas.
- Casos de avaliação e evidências de verificações estáticas, com limites explícitos.

Não entregar instalador, gerador/empacotador executável, schema ou runtime de checkpoint, perfis técnicos implementados, scaffolding de aplicações, integrações externas, hooks ou fluxo completo executado nos clientes. O estágio seguinte da sequência aprovada mantém os testes comportamentais em sessões reais; esses testes não serão substituídos por inspeção de texto.

## Decisões permitidas autonomamente

Redação, organização local dos recursos, divisão de referências para carga sob demanda, nomes internos e exemplos fictícios dentro dos contratos aprovados. Pode-se copiar recursos de autoria comum para as duas árvores locais; a revisão deve demonstrar paridade e impedir referências ao clone do FRIDAY ou a outra skill não incluída.

Não alterar nomes ou responsabilidades das 19 skills, gates, níveis, semântica de autorização, destinos aprovados ou limites do instalador. Se o suporte oficial atual impedir o desenho, apresentar evidência, opções e recomendação antes da mudança. Não escolher a licença própria por inferência.

## ADRs e impactos

Aplicar HIL-003-01 a 07, sem novo ADR para decisões já aceitas. A proposta local separa autoria compartilhada em `skills/core/` e saídas por cliente em `skills/adapters/`; nenhuma dessas pastas é um destino de instalação ativo.

Os templates preservam IDs, histórico e mapa de destinos do consumidor. O checkpoint documental conserva a separação entre estado versionável e runtime local e não promete operações atômicas implementadas. Não há migration, API executável, alteração de configurações ou efeito sobre o MakerBuddy. Eventual TypeScript executável exige plano reconciliado, modo estrito e validações próprias; não faz parte deste recorte.

## Plano de implementação

| Unidade | Dependência | Trabalho e resultado verificável |
| --- | --- | --- |
| 004-01 | Autorização deste plano | Registrar a autorização, conferir baseline e instruções; atualizar fontes oficiais de metadata e empacotamento dos clientes; reconferir arquivos e licenças congeladas antes de adaptar. |
| 004-02 | 004-01 | Escrever núcleo comum, contratos dos 19 IDs, catálogo e templates; mapear responsabilidades e fontes por arquivo. Nenhuma instrução de um host entra no contrato central. |
| 004-03 | 004-02 | Produzir 19 entradas Codex e 19 Claude Code, copiando somente recursos necessários para dentro de cada skill. Metadata opcional somente com suporte oficial confirmado. |
| 004-04 | 004-03 | Verificar inventário, metadata, referências, autocontenção, paridade e casos da matriz abaixo; corrigir divergências e registrar resultados estáticos. |
| 004-05 | 004-04 | Revisar todas as alterações contra a baseline, atualizar documentação e preparar pacote de aceite com limitações e próximos testes reais. Encerrar e arquivar somente após critérios e aceite aplicável. |

Execução serial pelo agente autorizado. A tabela não solicita trabalhadores nem revisores delegados. Revisão do próprio autor deve ser identificada como tal; não satisfaz independência por troca de persona.

## Arquivos e módulos esperados

Os caminhos abaixo foram materializados nesta execução com conteúdo efetivo. Cada unidade responde pelos destinos indicados e pelas reconciliações documentais de sua entrega; o padrão de ID expande conforme a especificação.

| Destino proposto | Unidade dona | Conteúdo |
| --- | --- | --- |
| `skills/core/catalog.md` | 004-02 | Inventário dos 19 IDs, bundles e dependências obrigatórias/condicionais. |
| `skills/core/contracts/<id>.md` | 004-02 | Um contrato por ID da especificação aprovada. |
| `skills/core/references/hil.md`, `state-and-recovery.md`, `quality-and-independence.md` | 004-02 | Invariantes, autoria, recuperação e qualidade; referências em contexto. |
| `skills/core/templates/` | 004-02 | `brief.md`, `product-plan.md`, `adoption.md`, `prd.md`, `techspec.md`, `tasks.md`, `task.md`, `decisions.md`, `review.md`, `design-review.md`, `remediation.md`, `snapshot.md`, `acceptance.md` e `checkpoint.example.json`. Handoff integra `task.md`; refatoração especializa PRD/TechSpec. |
| `skills/adapters/codex/<id>/SKILL.md` e `skills/adapters/claude-code/<id>/SKILL.md` | 004-03 | 38 entradas, com `references/`, `assets/` e avisos locais quando necessários, sem symlinks nem links para a árvore de autoria. |
| `docs/research/CONTENT-PROVENANCE.md` e `skills/core/notices/` | 004-02; 004-03 replica avisos pertinentes | Origem, revisão, caminho, adaptação e licença por arquivo; textos completos dos avisos aplicáveis. |
| `docs/validation/FRIDAY-004-content-checks.md` | 004-04 | Inventário e evidências estáticas; cenários comportamentais preparados e explicitamente não executados nos hosts. |
| `skills/README.md`, `docs/plans/HANDOFF.md`, `docs/plans/EXECUTION-STATE.md` e este plano | 004-05 | Capacidades realmente entregues, limites, autorização/aceite e continuidade. Atualizar SOURCES se a execução acrescentar evidência às fontes. |

Os 19 IDs são exatamente os de KIT-SPECIFICATION: flow, triage, discover, plan-product, bootstrap, adopt, specify-product, design-solution, review-design, plan-tasks, run-tasks, execute-task, review, plan-fixes, apply-fixes, plan-refactor, plan-remediation, checkpoint e accept, todos com prefixo `friday-`. O padrão `<id>` expande para esses IDs, sem novos contratos.

## Estratégia de validação

Para o conteúdo futuro: conferir `name` e `description` com o suporte oficial efetivo de cada cliente; inventariar 19 contratos e 19 entradas por adapter; comparar obrigações entre core e saídas; verificar todos os links e recursos locais e rejeitar fuga por caminho, symlink ou referência a checkout/cache. Parsear os exemplos JSON com ferramenta disponível; não chamar isso de validação de schema. Revisar carga sob demanda pelo grafo de referências, sem afirmar medição de contexto do host.

| Caso obrigatório | Verificação estática nesta tarefa | Evidência comportamental posterior |
| --- | --- | --- |
| Gatilho correto/incorreto | Exemplos positivos/negativos e exclusões em cada contrato/description. | Observar seleção e recusa no cliente real. |
| Autorização anterior válida | Rastrear decisão, escopo, fonte/hash e regra de não repetir o gate. | Retomar e demonstrar preservação da autorização. |
| Fonte ou etapa ausente | Instrução de pendência e próxima ação, sem requisito ou aprovação inventada. | Executar cenário com fonte/capacidade removida. |
| Arquivo manual existente | Templates/instruções exigem inspeção e preservação; não há cópia para destino de cliente nesta tarefa. | Demonstrar preservação na fixture do fluxo e, depois, no instalador. |
| Retomada sem HEAD | Exemplo com `base: null`, limitação e fontes verificáveis. | Retomar fixture sem Git/commit no host. |
| Mudança/corrupção | Invalidação parcial, preservação de checkpoint inválido e ausência de consentimento por snapshot. | Interromper, corromper e recuperar em sessões reais. |

Para esta preparação documental e o conteúdo futuro: revisão integral, links relativos, JSON, nova linha final, whitespace e ausência de caminhos pessoais/segredos. Reutilizar formatter disponível sem download ou registrar ausência. Como todos os arquivos são não rastreados, usar `git diff --no-index --check /dev/null <arquivo>` individualmente; `git diff --check` isolado não cobre a entrega. Comparar hashes com baseline para conferir preservação dos arquivos fora do escopo.

Lint de aplicação, typecheck e build são inaplicáveis ao recorte sem código. Não criar dependências ou aplicação fictícia para validar Markdown. Comandos efetivamente executados e resultados serão registrados abaixo. Se não houver ambiente para testes de host, mantê-los como pendentes da etapa seguinte, sem qualificá-los como aprovados.

## Riscos conhecidos

- Duplicação nas saídas sem gerador: comparar integralmente os contratos e manter mapa core → recurso de cada cliente; divergência impede o aceite do conteúdo.
- Metadata mutável: confirmar documentação oficial na implementação; presença no disco não prova descoberta.
- Recursos incompletos ou carregamento excessivo: validar fechamento local por skill e referências condicionais; comprovação de comportamento/contexto fica para sessão real.
- Atribuição incompleta: reconferir arquivos derivados e transportar avisos aplicáveis para cada saída; licença própria pendente impede distribuição até decisão do mantenedor.
- Confundir primeiro conteúdo com suporte verificado: manter avaliações estáticas e comportamentais separadas no relatório e na documentação de uso.

## Critérios de aceite

- [x] Autorização explícita para executar este plano registrada com origem e limites.
- [x] 19 contratos e catálogo/bundles cobrem integralmente as responsabilidades aprovadas, sem mudança material não autorizada.
- [x] Templates e referências preservam HIL, propriedade, fontes, histórico, fallback e recuperação; nenhum helper inexistente é prometido.
- [x] 19 entradas por cliente, metadata conferida e recursos autocontidos, com paridade documentada.
- [x] Origem por arquivo adaptado e avisos aplicáveis presentes; licença própria permanece explícita e bloqueia distribuição enquanto pendente.
- [x] Casos da matriz conferidos estaticamente; cenários reais ainda não executados identificados como pendentes.
- [x] Validações aplicáveis concluídas, com limitações e revisão de todas as alterações registradas.
- [x] Documentação durável reconciliada, sem alegar instalação, descoberta ou suporte prático não demonstrado.
- [x] Aceite aplicável registrado, estado atualizado e plano concluído movido para `completed/`.

## Resultado da execução

**WAITING_HIL — implementação local e verificações concluídas em 07/11/2026; falta o aceite desta entrega de conteúdo.** A resposta “sim” autorizou execução, não foi registrada como aceite de resultado ainda inexistente. O plano permanece em `active/` até resposta válida ao pacote final.

Validação da preparação em 07/11/2026: script temporário com Python 3 conferiu 20 arquivos, 110 links relativos válidos, dois JSON parseáveis, novas linhas finais, ausência de whitespace final e caminhos pessoais. `git diff --no-index --check /dev/null <arquivo>` executado em cada um dos 20 arquivos: aprovado. Comparação SHA-256 com baseline: 19 arquivos originais preservados, 17 idênticos; somente HANDOFF e EXECUTION-STATE alterados, além deste plano novo. Revisão integral deste plano e dos dois diffs feita pelo agente autor, sem revisão independente. Git confirmado em `main`, sem commits/remotes.

Prettier não localizado no PATH nem na busca pelo executável em cache npm; formatação automática não executada e nenhuma ferramenta instalada. Lint de aplicação, typecheck, testes de runtime/cliente e build são inaplicáveis à preparação documental. Não há commit, remote, push, CI, instalação ou alteração externa. Este registro não equivale ao aceite da implementação futura.


### Entrega e evidência da execução

- 004-01: autorização registrada; documentação oficial de Codex/Claude Code conferida; 71 arquivos congelados recuperados e seus Git blob SHAs comparados com source-manifest.json. Leitura focada, sem executar scripts upstream ou trocar revisões.
- 004-02: 19 contratos, três referências, 14 templates, catálogo/bundles/dependências e dois avisos MIT integrais. Proveniência individual do núcleo e das cópias por cliente registrada.
- 004-03: 19 entradas Codex e 19 Claude Code, metadata mínima name/description e recursos internos. Somente a instrução de host difere entre entradas; contratos recebem apenas remapeamento de links.
- 004-04: inventário, YAML real, paridade integral, alcance/localidade de recursos, ciclos/closure, JSON e higiene conferidos. Cópia isolada aprovada; falta de asset, fuga de caminho e symlink foram introduzidos em fixture temporária e corretamente rejeitados pelo check de recursos.
- 004-05: revisão integral da autoria nova e dos diffs, documentação reconciliada e pacote final em [validação](../../validation/FRIDAY-004-content-checks.md), [proveniência](../../research/CONTENT-PROVENANCE.md) e [catálogo](../../../skills/core/catalog.md). Revisão pelo próprio agente autor; nenhuma revisão independente ou sessão real de cliente foi simulada.

Não houve desvio material do plano. A autoria e as verificações usaram utilitários temporários fora do repositório, sem introduzir gerador/validador mantido no produto. O quick_validate.py foi tentado e falhou por ausência de PyYAML; os dois Python disponíveis não possuem esse módulo. Ruby/Psych já disponível fez parse dos 38 frontmatters; checks complementares cobriram naming, descrições, recursos e paridade. Prettier não encontrado; nenhuma ferramenta instalada.

Validações funcionais de host, independência por outra sessão, perfis e matriz de instalador não ocorreram e permanecem nas etapas próprias. Lint de aplicação, typecheck e build são inaplicáveis ao recorte sem código executável. Licença própria segue pendente antes de distribuição. Sem instalação em clientes, alteração externa, commit, remote, push, release ou CI.

Após aceite: registrar a resposta humana e o escopo, mover este plano a completed, atualizar links/estado e preparar tarefa concreta para descoberta/fluxo documental nos dois clientes. Não iniciar a próxima etapa ou publicação por efeito do aceite.

Conferência final da execução: 411 arquivos, 867 links relativos válidos e sete JSON parseáveis; whitespace individual, novas linhas finais e higiene aprovados. Baseline de execução com 20 arquivos preservada: 15 idênticos e cinco alterados somente no escopo documental; 391 arquivos novos. Pacote de conteúdo identificado por digest no relatório de validação. Git em main, sem primeiro commit e sem remote, confirmado por inspeção e status.

## Fechamento para publicação

Após a apresentação da entrega, o mantenedor solicitou “crie um repositorio publico e faça commit no meu github”. O pedido aceita o conteúdo apresentado para o marco de versionamento/publicação e autoriza essas ações em tarefa própria, sem afirmar validação de host. A FRIDAY-004 foi concluída e arquivada; a [FRIDAY-005](../active/FRIDAY-005-github-publication.md) registra publicação, conta e escolha posterior “MIT, preservando os avisos das duas bases”. A evidência anterior desta tarefa permanece histórica; a reconciliação de licença e seu novo digest pertencem à FRIDAY-005.
