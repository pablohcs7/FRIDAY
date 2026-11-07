# HIL e níveis do fluxo

## Autoridade e decisão

Ao usar o fluxo, preserve instruções locais, pedido e autorizações válidas. Registre em `decisions.md` ID, gate, texto humano pertinente, origem, escopo, fontes e hashes SHA-256 das versões apresentadas. Não transcreva conversa privada além do necessário. Inspecione arquivos manuais antes de escrever; adapte templates ao destino existente, sem sobrescrita implícita.

Autorização acompanha conteúdo e escopo. Se já válida, continue sem perguntar de novo. Silêncio, tempo, snapshot, parecer ou teste passando não aprovam nada. Mudança editorial sem efeito na decisão permite reconciliação registrada; mudança material exige decisão sobre a parte afetada e invalidação dos derivados correspondentes. Hash novo identifica conteúdo, não consentimento. Não há modo `auto` na v1.

Antes de perguntar, prepare o pacote concreto com fontes, limites, opções e recomendação. Use pergunta nativa disponível ou texto claro; aguarde somente o trabalho dependente da resposta. Produto aprovado não autoriza automaticamente implantação, serviço pago, publicação ou configuração externa. Fechar uma entrega não cria commit, push ou deploy.

## Escolher o nível — HIL 0

| Nível | Sinais e resultado |
| --- | --- |
| `focused` | Mudança inequívoca, local, reversível, sem contrato público, área crítica, concorrência ou decisão aberta; até três arquivos de produção em um módulo é referência, não autorização automática. Plano curto, revisão proporcional e aceite. Registre quando o pedido já autoriza produto/técnica. |
| `lean` | Mudança limitada que não reúne todos os sinais de focused. PRD curto e solução/tasks compactas. HIL 1 e 2 podem ser uma decisão sobre o pacote concreto; revisão independente e HIL 3 permanecem. |
| `complete` | Contrato público, área crítica, dados irreversíveis, decisão de produto/arquitetura aberta ou múltiplas obrigações/módulos. PRD, TechSpec, DAG/tasks e HIL 0/1/2/3, mais gates pertinentes. |
| `concept-design` | Complete com incerteza de desenho: múltiplas arquiteturas, subsistema sem precedente, três ou mais módulos/fronteira de serviço ou triagem insuficiente. Exige pelo menos dois sinais, um com evidência. Acrescenta conceito e lentes de produto/projeto. |

Marque sinal sem fonte como `unknown`; se puder mudar o nível, recomende conservadoramente e exponha a lacuna. Risco alto com solução conhecida não obriga conceito aprofundado. O humano pode escolher outro nível; registre consequências, custos e capacidade de contextos independentes. Sinal material novo reabre apenas gates afetados.

## Gates e continuação

| Gate | Pacote pronto | Continuação |
| --- | --- | --- |
| HIL 0 | Sinais com evidência, nível, esforço e alternativas | Escolha humana ou autorização anterior explícita para o mesmo pedido. |
| Hipótese / Brief | Primeiro hipótese e opções; depois brief com lentes, limitações e respostas propostas | Humano ancora hipótese, aprova brief, itera ou encerra; somente no ramo de conceito pertinente. |
| HIL 1 | PRD com requisitos/aceite e revisão de produto quando aplicável | Produto aprovado libera planejamento dependente, dentro do escopo. |
| HIL 2 | TechSpec, DAG/tasks, perfis selecionados, dependências, efeitos, riscos e validação | Autoriza implementação ou correções delimitadas. |
| Resolução / teto de design | Achados classificados, edições propostas e custo de rodada extra | Decidir correções, pendências opcionais, rodada adicional ou retorno à redação. |
| Exceção | Fato novo, impacto no contrato, opções e recomendação já escritas | Só dependentes aguardam; independentes autorizados podem continuar. |
| Conferência visual | Artefato atual, roteiro e evidência | Humano confere antes da revisão global quando houver UI/resultado visual pertinente. Sem ambiente, fica pendente. |
| Ressalvas | Itens opcionais com impacto e esforço | Humano escolhe correções ou aceita pendências; obrigação essencial ausente continua bloqueante. |
| HIL 3 | Revisão correspondente, evidências integradas, limitações e conferências manuais/visuais aplicáveis | Resposta válida permite fechar/arquivar; sem resposta, `waiting_hil`. |

Requisito, segurança ou validação essencial pendente impede sucesso técnico, mesmo com consentimento para assumir risco. Descreva a pendência e encaminhe decisão de escopo quando cabível; não rotule como ressalva opcional. Duas rodadas sem progresso comprovado exigem diagnóstico e exceção. Teto de rodadas não equivale a aprovação.
