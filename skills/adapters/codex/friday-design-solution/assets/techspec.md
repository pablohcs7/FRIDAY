# TechSpec — {{featureId}}

## Fontes e solução

PRD aprovado, decisões, versão e evidência no código/contratos atuais. Resumo da abordagem e limites; não usar planos históricos como runtime.

## Decisões e rastreabilidade

| ID | Obrigação | Solução e evidência | Alternativas e consequência |
| --- | --- | --- | --- |
| DEC-01 | {{requirementId}} | {{solution}} | {{tradeoffs}} |

## Componentes, interfaces e dados

Responsabilidades, callers, contratos alterados, validação, erros, segurança, compatibilidade e migração. Usar fontes oficiais por versão para dúvida externa.

## Perfil e arquivos

Stack existente e seleção condicional com motivo, versões, licenças e ambiente. Arquivos afetados com operação, mudança e origem; detalhar por arquivo no nível concept-design. Reuso de UI/tokens; aparência provisória registrada quando faltar design final.

## Validação e baseline

| ID | Obrigação | Cenário | Comando real ou roteiro | Pré-requisito | Evidência esperada |
| --- | --- | --- | --- | --- | --- |
| TC-01 | {{requirementId}} | {{scenario}} | {{commandOrManual}} | {{environment}} | {{expected}} |

Registrar falhas/dívida preexistentes e limites. Não transformar comando proposto em executado.

## Sequência, observabilidade e recuperação

Dependências, efeitos, rollout e rollback pertinentes. Para refatoração: R-IDs, caracterização antes da mutação e rede de segurança.

## Riscos e HIL 2

Pendências materiais, itens afetados, opções e proposta; pacote inclui DAG/tasks concretas antes de autorizar execução.
