# friday-adopt

## Acionamento

Diagnosticar e integrar FRIDAY a projeto existente preservando stack, UI, arquivos e configurações; bootstrap de produto novo pertence a bootstrap.

- Exemplo positivo: “Adote o fluxo neste projeto existente sem regenerá-lo.”
- Fora deste contrato: “Crie um aplicativo novo em diretório vazio.”

## Entradas e propriedade

Objetivo de adoção, instruções, código/manifests/lock, docs e mudanças locais.

Inventário rastreável, mapa único de destinos, lacunas/proposta e apenas o patch autorizado com evidências.

## Procedimento

1. Inspecione arquitetura, UI/tokens, linguagens, testes, comandos, estado Git e arquivos manuais. Sem fonte, marque desconhecido; não trate documentação histórica como runtime atual.
2. Reutilize planos e convenções equivalentes. Registre mapa canônico de artefatos; evite segundo PRD/estado concorrente ou migração só por preferência FRIDAY.
3. Proponha patch pequeno para lacuna concreta, com arquivos, efeito, reversão e validação. Ler/diagnosticar não autoriza instalar skills, alterar AGENTS/CLAUDE/settings/hooks ou trocar stack.
4. Aplique somente adoção explicitamente autorizada; rotina local reversível dentro desse plano pode seguir. Mudança material de arquitetura, dados, permissões ou contrato exige HIL concreto.
5. Valide o que mudou com ferramentas existentes, preserve manuais e registre antes/depois/limites. Ausência de integração externa vira pendência, sem configuração automática.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

- redigir produto da adoção: `friday-specify-product`.
- planejar solução dependente: `friday-design-solution`.
- planejar execução dependente: `friday-plan-tasks`.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [adoption.md](../assets/adoption.md).

## Aceite e handoff

Diagnóstico com fontes e patch limitado ao objetivo; projeto, contratos e stack preservados ou mudança material autorizada explicitamente.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
