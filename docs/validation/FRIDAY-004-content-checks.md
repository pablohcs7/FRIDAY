# Verificação de conteúdo — FRIDAY-004

> 07/11/2026 · Revisão pelo agente autor · Evidência histórica da FRIDAY-004, anterior à reconciliação de licença e publicação FRIDAY-005; sem teste comportamental nos clientes.

## Alvo e limites

19 contratos do [catálogo](../../skills/core/catalog.md), referências/templates de autoria e duas saídas por cliente sob `skills/adapters/`. A [proveniência](../research/CONTENT-PROVENANCE.md) identifica fontes e adaptações; avisos MIT completos acompanham as saídas. A licença própria continua pendente antes de distribuição.

A autorização é a resposta humana “sim” à pergunta de execução do [plano FRIDAY-004](../plans/completed/FRIDAY-004-contracts-and-adapters.md), no escopo local. Não houve instalação de skills, configuração de clientes, dependências novas ou delegação. Esta inspeção é do próprio autor e não comprova independência.

## Método de verificação

Checks executados com utilitários temporários fora do repositório, usando Python 3 padrão, Ruby/Psych já disponível e Git. Não existe gerador, validador mantido, schema ou helper de persistência entregue pelo FRIDAY.

- Comparar IDs com KIT-SPECIFICATION e bundles/dependências com o catálogo, incluindo ciclos e expansão transitiva de todos os ramos.
- Parsear frontmatter com Ruby/Psych, conferir tipos/campos, nomes e descrição contra o contrato central.
- Comparar contrato instalado ao core após normalizar somente os destinos dos links; referências/assets/avisos exigem igualdade byte a byte.
- Resolver todos os recursos relativos de cada skill dentro da própria árvore, com rejeição de symlinks, fuga de caminho e arquivo ausente; conferir alcance dos recursos e inventário da proveniência local.
- Copiar uma skill para diretório temporário isolado e conferir recursos sem consultar o clone; remover asset, introduzir fuga de caminho e symlink para confirmar rejeição pelo check estático.
- Parsear JSON, verificar links relativos globais, novas linhas finais, whitespace e higiene de caminhos pessoais; executar `git diff --no-index --check /dev/null <arquivo>` em todos os arquivos, inclusive os não rastreados.
- Comparar baseline SHA-256 para preservar arquivos anteriores e revisar integralmente conteúdo e diffs dentro do escopo.

O `quick_validate.py` da skill-creator foi tentado e falhou na importação de PyYAML, ausente nos dois Python consultados. Não foi instalada dependência. O fallback Ruby/Psych verifica o YAML real e os checks complementares verificam naming, recursos e paridade; não se afirma aprovação pelo validador original. Prettier não foi localizado no PATH nem na busca de executáveis em caches npm/plugins; formatação automática não executada.

## Resultados estáticos

Inventário aprovado: 19 contratos no núcleo, três referências, 14 templates, catálogo e dois avisos MIT; 19 entradas por cliente, com 350 arquivos ao todo nos adapters. Cada SKILL.md tem 14 linhas e a maior description tem 164 caracteres. Os 38 frontmatters foram parseados e comparados com os contratos. Comparação integral dos contratos após remapear somente links, e byte a byte dos demais recursos: aprovada.

Catálogo com 43 arestas de dependência, incluindo condicionais: sem ciclos ou IDs desconhecidos. Bundles têm 12/4/2/1 capacidades diretas e a união totaliza 19; a closure do fluxo chega aos 19 IDs. Não há resolvedor entregue: o resultado é da verificação temporária da tabela documental.

Todos os recursos dos adapters são alcançáveis e permanecem dentro da própria skill; inventário de proveniência individual e avisos integrais conferidos. Cópia isolada de friday-checkpoint: aprovada. Asset removido, link que escapa da árvore e symlink: rejeitados nos três probes, conforme esperado. Esses probes testam o check estático, não o comportamento de um cliente.

Conferência final de arquivos, links e preservação da baseline registrada no plano e no estado de execução após a reconciliação documental. Nenhuma verificação essencial deste recorte de conteúdo ficou pendente; validação comportamental é a próxima etapa explicitamente separada pelo plano.

## Ambiente, comandos e preservação

Ambiente observado: macOS, Python 3.9.6, Ruby 2.6.10/Psych e Git 2.50.1. `python3 --version`, `ruby --version`, `git --version`, `git status --short` e `git remote -v` foram executados. Git permanece em main, sem primeiro commit ou remote. Não houve instalação de pacotes nem mudança de cliente.

Os checks temporários foram invocados com Python 3 e chamaram Ruby com `YAML.safe_load` (classes permitidas vazias e aliases desabilitados) sobre os 38 frontmatters. A tentativa do validador original usou `python3` com `quick_validate.py` e a pasta `skills/adapters/codex/friday-flow`; parou na importação de yaml. O comando Git de whitespace acima foi executado individualmente em todos os arquivos. Caminhos dos utilitários temporários foram omitidos para não publicar diretórios pessoais; eles não são pré-requisitos do produto.

Conferência final: **411 arquivos, 867 links relativos válidos e sete JSON parseáveis**, incluindo os exemplos copiados. Novas linhas finais, whitespace, recursos, proveniência e higiene de caminhos: aprovados. Os 20 arquivos da baseline foram preservados; 15 permanecem byte a byte idênticos e somente skills/README, SOURCES, HANDOFF, EXECUTION-STATE e o plano ativo receberam mudanças. Foram adicionados 391 arquivos; não houve remoção de original.

Para vincular o pacote à revisão de conteúdo, o inventário dos 389 arquivos de core/adapters é ordenado pelo caminho relativo; cada registro concatena caminho, byte NUL, SHA-256 do conteúdo e nova linha. SHA-256 do inventário: `8382de8996d7b2e6c720ffbc41c8712024b705427756d0a7c785a3c66863bad6`. Esse digest identifica arquivos, não é aprovação humana nem prova de comportamento.

## Matriz de cobertura das 19 capacidades

Cada contrato contém exemplo positivo e exclusão concreta; os dois adapters compartilham a mesma description. As linhas abaixo registram a inspeção do conteúdo, sem afirmar que o host escolheu a skill.

| Capacidade | Resultado inspecionado | Limite principal |
| --- | --- | --- |
| flow | Roteamento, gates, fontes, ausência de etapa e próxima ação | Não substitui a dona do artefato. |
| triage | Sinais, quatro níveis e HIL 0 | Não retria nível anterior válido. |
| discover | Hipótese/brief, opções e seis lentes condicionais | Não inventa pesquisa ou independência. |
| plan-product | Recortes, aceite, destinos e grafo sem ciclos | Não exige roadmap para produto simples. |
| bootstrap | Fundação mínima após produto/HIL 2 | Não prepara máquina ou implementa produto inteiro. |
| adopt | Inventário, mapa de destinos e patch autorizado | Preserva stack/UI/manuais/settings. |
| specify-product | RF/RNF/US, aceite e HIL 1 | Não define arquitetura ou tasks. |
| design-solution | Cobertura técnica, perfis, testes, riscos e HIL 2 | Não inventa integração ou execução. |
| review-design | Lentes, hashes, rodadas, resolução e teto | Ausência de lente/contexto fica pendente. |
| plan-tasks | DAG único, contratos e cobertura | Não implementa por efeito do plano. |
| run-tasks | Elegibilidade, executor, integração e movimentos | Único dono do DAG, sem aceite próprio. |
| execute-task | Uma unidade, arquivos, checks e handoff | Não altera DAG/checkpoint global. |
| review | Matriz, achados, parecer e independência declarada | Não corrige alvo durante parecer. |
| plan-fixes | Revisão exata + ID, destinos e seleção de opcionais | Não altera relatório emitido. |
| apply-fixes | Execução pelo controle comum, evidência e re-revisão | Movimento de arquivo não encerra achado. |
| plan-refactor | R-IDs, baseline, caracterização e rollback | Sem funcionalidade extra. |
| plan-remediation | Evidência reconferida, frentes e rotas | Sem auditor específico ou execução automática. |
| checkpoint | Salvar/carregar, validade, recuperação e base null | Snapshot é pista e não consentimento. |
| accept | Pacote, revisão/evidências e HIL 3 | Sem resposta válida mantém waiting_hil. |

## Casos de avaliação preparados

| Caso | Inspeção estática e fonte | Roteiro no cliente real, ainda não executado |
| --- | --- | --- |
| Gatilho positivo/negativo | 19 pares no core e descriptions equivalentes nos adapters | Apresentar pedido positivo e exclusão para cada capacidade; observar seleção/recusa e destino. |
| Autorização anterior | [HIL](../../skills/core/references/hil.md) exige decisão, fonte/hash e escopo; hash novo não cria consentimento | Aprovar pacote, retomar sem mudanças e observar continuação sem repetir gate; alterar materialmente e observar invalidação parcial. |
| Fonte/capacidade ausente | Contratos especificam pendência exata e trabalho dependente; catálogo separa requires/requiresWhen | Retirar fonte/skill necessária; observar bloqueio do ramo, sem aprovação ou requisito inventado. |
| Arquivo manual | Templates são adaptados após inspeção; [adoção](../../skills/core/contracts/friday-adopt.md) preserva convenções | Criar documento manual conflitante; observar proposta/reconciliação sem sobrescrita implícita. |
| Sem HEAD | [Estado](../../skills/core/references/state-and-recovery.md) e [exemplo](../../skills/core/templates/checkpoint.example.json) usam base null e limitação | Retomar fixture sem Git/commit; observar fontes atuais, arquivos não rastreados preservados e nenhuma base inventada. |
| Corrupção e interrupção | Estado preserva inválido/última versão válida e exige reconciliação de escritores | Interromper e corromper checkpoint; observar recuperação sem perder fonte ou inferir consentimento. |
| Mudança após revisão | Qualidade/estado invalidam parte afetada por código/configuração/ambiente/obrigação | Alterar alvo após parecer e observar re-revisão correspondente; relatório anterior permanece imutável. |
| Lente ausente/teto | [Qualidade](../../skills/core/references/quality-and-independence.md) exige independência e rodadas limpas antes das correções | Indisponibilizar contexto/lente ou atingir teto; observar pendência/gate, sem sucesso automático. |
| Aceite/publicação | [Aceite](../../skills/core/contracts/friday-accept.md) exige HIL 3 e separa publicação | Sem resposta, observar waiting_hil; com aceite, conferir fechamento sem commit/push/deploy automático. |

## Pendências para etapas seguintes

Descoberta real nos dois clientes, seleção por prompt, carga efetiva de contexto, workflow documental com HIL 0/1/2/3, correções/ressalvas, interrupção e recuperação ainda não foram executados. A cópia isolada só comprova autocontenção dos arquivos. Não comprova carregamento pelo host ou comportamento do agente.

Perfis técnicos continuam orientação condicional, sem aplicação/integração executada. Instalador e matriz Windows/macOS/Linux continuam fora da FRIDAY-004. Nenhum comando de instalação ou suporte prático foi anunciado. Lint de aplicação, typecheck e build não se aplicam ao conteúdo sem código executável.
