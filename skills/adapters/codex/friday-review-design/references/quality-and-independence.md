# Qualidade, independência e perfis condicionais

## Evidência e parecer

Mapeie cada obrigação a implementação/documento e evidência. Use comandos existentes pertinentes à mudança; registre comando, ambiente, estado de arquivos, resultado e limitação. Ausência de teste não é aprovação. Reutilize resultado somente se código, configuração, ambiente e obrigação continuam correspondentes; execute o que ficou faltante ou foi invalidado. Separe falha preexistente de regressão, sem ocultar impacto.

Testes são proporcionais ao risco. Documentação não exige aplicação fictícia ou dependências novas. Para UI e artefatos visuais, verifique estados/interações e obtenha conferência humana quando aplicável. Manual essencial sem execução impede fechamento. Browser, logs e serviços têm escopo e credenciais próprios; registre só evidência necessária, sem segredos ou payload privado.

Pareceres: `approved`, `approved_with_notes`, `rejected`, `blocked`. Notes são exclusivamente opcionais; requisito, segurança ou verificação essencial pendente impede parecer favorável. Registre achados com identidade composta caminho da revisão + ID, causa, evidência, impacto e destino. Cada revisão é nova e imutável. A sessão que emite parecer não corrige o alvo simultaneamente.

## Contextos independentes

Independência requer contexto que não escreveu o alvo. Prepare pacote delimitado com artefatos, fontes, hashes e pergunta, sem conversa ou justificativa do autor. Só delegue com autorização e suporte do host; sem eles, prepare encaminhamento a nova sessão independente. Revisão pelo autor é declarada e não satisfaz independência; trocar de persona não cria outro contexto. Snapshot para revisor carrega apenas fatos operacionais necessários, sem enquadramento autoral.

No ramo `concept-design`, consulte os gates HIL pertinentes antes de iniciar lentes. Cada lente recebe somente o pacote permitido e registra resultado e fontes; hashes antes/depois detectam alteração/contaminação da rodada. Se o alvo mudar durante avaliação, invalide a rodada afetada.

- Conceito: necessidade/reuso, desempenho/recursos, UX/ergonomia, migração/compatibilidade, observabilidade e dívida/acoplamento; seis contextos independentes, sequenciais quando necessário.
- Produto: compreensão (paráfrase do resultado/aceite) e visão do conjunto (cobertura/conflitos); uma rodada limpa dentro de duas.
- Projeto: compreensão, visão do conjunto, crítica (riscos/alternativas), prontidão (passos/comandos/ambiente) e código (aderência aos contratos/callers atuais); duas rodadas limpas consecutivas dentro de três.

Rodada limpa é avaliada antes das correções da própria rodada: nenhuma obrigação bloqueante/maior aberta ou reaberta e nenhuma lente ausente. Corrigir não torna a rodada retroativamente limpa. Achado reaparecido no mesmo escopo é reabertura; preserve identidade e causa. Limite atingido ou correção que reabre achado anterior vai ao gate com achados, edições e custo, sem reauditoria automática.

O autor resolve em documento separado, sem editar o relatório emitido: contestar só com prova acessível ao revisor; escalar quando faltar fonte ou mudar produto aprovado; corrigir com edição exata; recusar somente melhoria menor opcional. Não reclassifique severidade para obter aprovação. Lacuna de compreensão pede contexto no artefato, não defesa oral. Lente indisponível fica pendente e nunca conta como limpa. Duas rodadas sem progresso comprovado exigem diagnóstico e HIL de exceção; nenhum teto produz sucesso.

## Seleção técnica por necessidade

Inspecione arquitetura, manifests/lock, componentes, tokens, testes e comandos do consumidor. Reuse o que existe. Núcleo não requer Jira, plugins, MCP ou repositórios upstream instalados. Use integrações já disponíveis e autorizadas ou fallback explícito, sem configurar autenticação/hooks por efeito da skill.

Quando for preciso escolher stack, registre versão, motivo, fonte oficial e validação real na solução; não converta candidato em dependência obrigatória. TypeScript executável novo usa modo estrito. Perfis não testados ficam como orientação documental.

Para web sem base de componentes, prefira Mantine + styled-components: tema/Styles API para internos Mantine; styled-components para layouts/componentes próprios, tokens compartilhados e limites de portals documentados. Formulários usam React Hook Form + Zod + `@hookform/resolvers`, com Controller/useController quando necessário; não adicionar `@mantine/form`, Tailwind ou shadcn/ui por padrão. Confira coerção, campos vazios, entrada/saída e callbacks na versão real. Sem design final, construa só componentes necessários com aparência provisória coerente e estados completos; registre a condição provisória.

Expo/React Native e Kotlin/Android nativo são perfis separados; biblioteca web não implica reuso nativo. NestJS, dados relacionais/documentais, AWS, Docker, RabbitMQ e Redis são condicionais ao produto. Preparar a máquina, instalar ferramentas, migrar stack e contratar serviços exigem escopo próprio. Scaffolder ou serviço ausente vira pendência/proposta, sem alegar execução.
