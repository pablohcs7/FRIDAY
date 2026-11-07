# FRIDAY

FRIDAY é um kit de skills para **Codex e Claude Code** que organiza o trabalho com agentes de IA, da descoberta de produto ao aceite da entrega. A proposta é transformar uma ideia, correção ou melhoria em trabalho com escopo claro, decisões registradas e resultados verificáveis.

Cada skill tem uma responsabilidade definida: quando deve ser acionada, quais informações recebe, quais artefatos produz e o que precisa ser conferido para concluir sua etapa. O kit reúne essas instruções, referências e templates para dar continuidade ao trabalho entre tarefas e sessões.

## Como o fluxo é organizado

O desenho combina **desenvolvimento guiado por especificações (`SDD`)** e **participação humana nas decisões (`HIL`)**. As etapas cobrem:

1. **Descoberta e recorte:** esclarecer problema, público, restrições e resultado esperado; dividir pedidos amplos em entregas coesas.
2. **Especificação e planejamento:** registrar requisitos e aceite no PRD, detalhar a solução na TechSpec e decompor a execução em tarefas com dependências e verificações.
3. **Implementação:** executar unidades autorizadas, respeitando arquitetura, componentes e convenções do projeto, com evidências do que foi alterado e validado.
4. **Revisão e correções:** confrontar a entrega com os contratos, registrar achados, planejar correções e preparar o aceite final.
5. **Retomada:** preservar decisões, fontes, planos e evidências no repositório para orientar a próxima sessão a partir do estado real do trabalho.

A profundidade do processo acompanha o risco e a complexidade da mudança. As decisões humanas delimitam produto, solução e execução; autorizações válidas são preservadas quando conteúdo e escopo continuam os mesmos. O fluxo também prevê bootstrap de produtos novos e adoção em projetos existentes.

## Organização do kit

O **núcleo compartilhado** concentra os contratos, referências e templates independentes do cliente. Os **adapters de Codex e Claude Code** apresentam esse conteúdo no formato de cada agente, com os recursos necessários dentro de cada skill.

As instruções direcionam a leitura de referências conforme a etapa. Os perfis técnicos orientam escolhas quando necessários, respeitando a stack e a UI existentes no projeto. O núcleo não exige Jira ou a instalação integral das ferramentas usadas como referência.

## Estado do projeto

O conteúdo inclui **19 contratos de skills, 19 entradas por cliente, referências e templates**, com verificações estáticas de metadata, paridade e recursos locais.

A descoberta e o fluxo ainda precisam ser testados nos clientes reais. O instalador para Windows, macOS e Linux está planejado; comandos de instalação serão documentados após implementação e validação.

## Documentação

- [Skills](skills/README.md): catálogo, organização e limites.
- [Instalador](installer/README.md): escopo da futura ferramenta.
- [Fontes e definições](docs/research/SOURCES.md): decisões e referências técnicas.
- [Estado de execução](docs/plans/EXECUTION-STATE.md): progresso e próxima etapa.

## Bases

- [vibe-coding-toolkit](https://github.com/soumatheusgomes/vibe-coding-toolkit): descoberta, planejamento e bootstrap.
- [agents-instructions](https://github.com/ColibriAgile/agents-instructions): SDD, HIL, revisão e retomada.

## Licença

[MIT](LICENSE), preservando os avisos das bases adaptadas. A [proveniência por arquivo](docs/research/CONTENT-PROVENANCE.md) registra origens e adaptações.

## Por que FRIDAY?

O nome homenageia a **F.R.I.D.A.Y.**, IA do Tony Stark que substitui J.A.R.V.I.S. no cinema. A expansão **Female Replacement Intelligent Digital Assistant Youth** é associada à variante de **Avengers Campus**.

Também remete a “girl Friday”: um braço direito para tarefas variadas. A origem literária está em Sexta-Feira, de *Robinson Crusoé*, de Daniel Defoe (**1719**); as expressões inglesas surgiram depois. As [fontes da homenagem](docs/research/SOURCES.md#fontes-da-homenagem) detalham essas referências e suas ressalvas.
