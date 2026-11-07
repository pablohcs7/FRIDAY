# friday-review

## Acionamento

Revisar entrega, documentos ou diff contra contratos e evidências, com independência declarada; não corrige o alvo enquanto emite parecer.

- Exemplo positivo: “Revise este diff contra o PRD e as tasks e emita relatório.”
- Fora deste contrato: “Implemente as correções enquanto faz a revisão.”

## Entradas e propriedade

Conjunto revisável/base, contratos/obrigações, tasks/handoffs e evidências correspondentes.

reviews/<id>/review.md novo, matriz de cobertura, achados, parecer e limitações; relatório emitido é imutável.

## Procedimento

1. Fixe alvo, inventário de arquivos, base resolvida ou null sem HEAD, fontes/hashes e ambiente. Não descarte arquivos não rastreados; liste o conjunto real sem inventar commit.
2. Declare independência: contexto que escreveu alvo não satisfaz revisão independente. Sem delegação autorizada/disponível, prepare pacote para nova sessão; uma autoinspeção solicitada deve ser identificada como tal.
3. Mapeie todas as obrigações a implementação/documentos e evidência atual. Verifique diffs, extras, limites, segurança pertinente e falhas preexistentes, sem mudar o alvo para esconder achado.
4. Execute verificações proporcionais disponíveis e necessárias; resultado antigo só vale para o mesmo código/configuração/ambiente e obrigação. Teste opcional segundo contrato não vira requisito universal; verificação essencial ausente impede sucesso.
5. Registre identidade caminho desta revisão + ID, causa, evidência, impacto e destino. Emita approved, approved_with_notes, rejected ou blocked conforme referência de qualidade; notas apenas opcionais.
6. Encaminhe achados sem editar parecer emitido. Correções exigem plano e re-revisão nova por contexto independente, correspondente ao novo alvo; aprovação técnica não substitui HIL 3.

## Capacidades e ausência de recurso

Recursos locais deste contrato e suas entradas verificadas. Artefato existente válido pode satisfazer entrada sem recriar a skill autora.

Se uma fonte, capacidade, autorização ou ambiente necessário faltar, registre exatamente o que falta, o trabalho dependente e a próxima ação possível. Não instale ferramentas/configure clientes por inferência e não fabrique evidência. Preserve trabalho independente já autorizado.

## Referências em contexto

- Ao escolher nível, preservar autorização ou preparar decisão humana: [hil.md](../references/hil.md).
- Ao definir destinos/donos, gravar estado ou retomar trabalho: [state-and-recovery.md](../references/state-and-recovery.md).
- Ao selecionar perfil, validar, emitir parecer ou usar contextos/lentes independentes: [quality-and-independence.md](../references/quality-and-independence.md).

## Saídas de apoio

Adapte somente os templates necessários, respeitando os arquivos manuais e a convenção existente; não crie placeholders no consumidor.

- [review.md](../templates/review.md).

## Aceite e handoff

Cobertura total, parecer/independência explícitos, fontes e limitações rastreáveis; nenhuma aprovação com obrigação essencial não verificada.

Informe artefatos, fontes, verificações realmente executadas, limitações e próxima ação ao papel responsável. As referências de origem são atribuição, não dependência de execução.
