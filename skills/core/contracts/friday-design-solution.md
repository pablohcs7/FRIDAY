# friday-design-solution

## Acionamento

Desenhar TechSpec rastreável a PRD aprovado e código atual; decomposição em tasks pertence a plan-tasks e implementação exige autorização.

- Exemplo positivo: “Desenhe a solução técnica deste PRD aprovado.”
- Fora deste contrato: “Crie novos requisitos de produto sem validar o recorte.”

## Entradas e propriedade

PRD aprovado, decisões, contratos/código atuais, restrições e perfis pertinentes.

techspec.md com decisões/alternativas, componentes, contratos/dados, testes, riscos, observabilidade e rollout pertinentes.

## Procedimento

1. Confira PRD, autorização de planejamento, código atual e TechSpec anterior. Preserve IDs; plano histórico de outra feature não comprova comportamento implementado.
2. Mapeie cada obrigação a consequência técnica, componente/interface e validação. Inspecione callers, dados, erros, concorrência e configuração atingidos; escolha mudança mínima coerente.
3. Reutilize arquitetura/UI e selecione perfil condicional com motivo e versões. Consulte docs oficiais para APIs/compatibilidade; candidato sem execução não se torna integração comprovada.
4. Documente alternativas reais, impactos materiais, segurança, migrations e reversão. Decisão material aberta vai ao humano com proposta; sem credencial/serviço, registre cenário e evidência faltante.
5. Defina comandos reais ou bloqueios, baseline e testes proporcionais, incluindo visual/manual pertinente. No concept-design, detalhe alterações por arquivo e encaminhe revisão de projeto com tasks.
6. Encaminhe a plan-tasks; HIL 2 recebe TechSpec + DAG + tasks já concretos. Não implemente nem trate documento técnico isolado como autorização de execução.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- DAG e contratos de tasks: `friday-plan-tasks`.
- revisão aprofundada de projeto: `friday-review-design`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](../references/hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](../references/state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](../references/quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [techspec.md](../templates/techspec.md).

## Aceite e handoff

Cobertura integral do PRD e dependências/efeitos claros; testes com comandos/ambiente ou impedimentos, decisões materiais resolvidas antes da execução.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
