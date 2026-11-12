# Escopo e Requisitos — PhotoHub

- **Status:** escopo preliminar para validação com a RN
- **Referência:** [Visão do Produto](./01-visao-do-produto.md)

## 1. Estratégia de escopo

O PhotoHub será desenvolvido primeiro para uso interno da RN Foto & Mídia. O MVP prioriza o **PhotoHub Studio** e um fluxo operacional completo. O Website comercial será uma aplicação separada, integrada ao Studio. O portal Client e galerias ficam para fase posterior.

Prioridades: **P0** indispensável ao fluxo principal; **P1** necessário para completar a primeira operação útil; **P2** evolução após validação; **Futuro** não bloqueia o MVP.

## 2. PhotoHub Studio — gestão interna

### 2.1 Clientes e contatos — P0
Cadastro, consulta, atualização e inativação; múltiplos contatos; histórico; associação com leads, propostas, contratos e trabalhos; busca e prevenção de duplicidade.

### 2.2 Comercial — P0
Registro de leads e origem; modalidade de interesse; dados preliminares; etapas de atendimento; histórico e próximos passos; propostas e orçamentos; conversão em trabalho sem redigitação.

### 2.3 Catálogo de serviços — P0/P1
Categorias e modalidades de fotografia/audiovisual; pacotes, itens, adicionais e condições; duração, entregáveis, prazos e deslocamento; preços configuráveis e histórico das condições apresentadas.

### 2.4 Contratos e documentos — P1
Modelos e dados variáveis; documentos relacionados a cliente, proposta e trabalho; controle de versão, status e datas; registro de assinatura e referência ao arquivo; trilha de alterações. Geração de PDF e assinatura eletrônica serão detalhadas separadamente.

### 2.5 Trabalhos, projetos e tarefas — P0/P1
Criação de trabalho a partir de proposta aceita; etapas por modalidade; tarefas, responsáveis, prazos e observações; documentos, pagamentos e entregáveis relacionados; histórico.

### 2.6 Agenda e equipe — P1
Datas, horários e locais; responsáveis e participantes; disponibilidade e conflitos; reagendamento e cancelamento.

### 2.7 Financeiro operacional — P1
Valores acordados; parcelas e vencimentos; pagamentos e pendências; resumo por cliente e trabalho. Não substitui contabilidade ou sistema financeiro completo.

### 2.8 Produção e entrega — P1
Etapas de seleção, edição, revisão e aprovação; prazos e responsáveis; links e referências externas; histórico e confirmação de entrega. No MVP, o sistema controla metadados e status, não armazenamento massivo de fotos.

## 3. PhotoHub Website — comercial público

- páginas institucionais e apresentação das frentes da RN;
- páginas de serviços, pacotes e portfólio;
- formulário de contato e solicitação de orçamento;
- campos condicionais por modalidade;
- validação, proteção contra spam e registro de consentimento;
- integração dos formulários à API para criar leads no Studio;
- conteúdo público sem exposição de contratos, dados privados ou galerias protegidas.

O Website não deve implementar um segundo CRM nem duplicar regras comerciais do Studio.

## 4. PhotoHub Client — futuro

- autenticação e recuperação de acesso;
- acesso restrito por cliente e trabalho;
- consulta de contratos e documentos;
- acompanhamento de etapas e pagamentos autorizados;
- galerias privadas;
- favoritos, seleção e aprovação de imagens;
- downloads e entrega final;
- notificações e histórico de comunicação.

Armazenamento, segurança de links, thumbnails, custos de tráfego e integrações serão decididos antes dessa fase.

## 5. Requisitos funcionais candidatos

- **RF-001:** Studio permite cadastrar e consultar clientes.
- **RF-002:** Studio mantém contatos e histórico de interações.
- **RF-003:** Studio registra leads e sua origem.
- **RF-004:** Studio acompanha etapas de atendimento e negociação.
- **RF-005:** Studio mantém catálogo de serviços, pacotes e adicionais.
- **RF-006:** Studio registra propostas vinculadas a clientes e serviços.
- **RF-007:** Studio converte propostas aceitas em trabalhos.
- **RF-008:** Studio relaciona contratos e documentos aos trabalhos.
- **RF-009:** Studio controla etapas, tarefas, responsáveis e prazos.
- **RF-010:** Studio registra datas, locais e participantes.
- **RF-011:** Studio registra valores, parcelas e pagamentos.
- **RF-012:** Studio acompanha produção e entrega.
- **RF-013:** Website apresenta serviços e portfólio público.
- **RF-014:** Website recebe solicitações e encaminha ao funil comercial.
- **RF-015:** Sistema mantém histórico de alterações relevantes.
- **RF-016:** Backend expõe operações por API documentada.
- **RF-017:** Sistema aplica autenticação e autorização no servidor.
- **RF-018:** Sistema permite consultar pendências e próximos passos.

Requisitos do Client serão especificados quando a fase for iniciada.

## 6. Requisitos não funcionais

- **RNF-001 Segurança:** segredos não podem ser armazenados no repositório.
- **RNF-002 Autorização:** operações protegidas validam permissões no backend.
- **RNF-003 Privacidade:** dados pessoais são tratados com finalidade e acesso apropriados, observando a LGPD.
- **RNF-004 Integridade:** transações críticas preservam consistência.
- **RNF-005 Auditoria:** ações relevantes registram ator, data e alteração.
- **RNF-006 Manutenibilidade:** módulos coesos, responsabilidades claras e testes.
- **RNF-007 Documentação:** API, instalação, operação e decisões são versionadas.
- **RNF-008 Observabilidade:** erros são rastreáveis sem expor segredos ou dados desnecessários.
- **RNF-009 Desempenho:** metas serão definidas a partir de cenários reais.
- **RNF-010 Recuperação:** backups e restauração devem ser testados antes do uso operacional.

## 7. Critérios de aceite do fluxo principal

1. Receber ou cadastrar um lead.
2. Localizar ou cadastrar o cliente.
3. Registrar serviço de interesse e dados do evento.
4. Preparar proposta/orçamento.
5. Formalizar contrato e registrar sua situação.
6. Criar trabalho com tarefas, prazos e responsáveis.
7. Registrar valores e pagamentos.
8. Acompanhar produção.
9. Registrar entrega e encerramento.

## 8. Fora do escopo do MVP

Multi-tenancy completo; planos e billing SaaS; gestão de assinantes; onboarding comercial de terceiros; marketplace; edição de fotos/vídeos; hospedagem massiva de mídia; galeria avançada própria; contabilidade e emissão fiscal; automações sem controle de permissão e auditoria; microserviços sem necessidade demonstrada.

## 9. Questões para validação

1. Quais funcionalidades do ERP/site anterior estão maduras e podem ser reaproveitadas?
2. Quais etapas mudam entre ensaios, eventos, casamentos e audiovisual?
3. Quais dados são obrigatórios para cada orçamento?
4. Quais modelos de contrato e regras de pagamento existem por serviço?
5. Como tratar reagendamentos, cancelamentos, reembolsos e alterações de escopo?
6. Quais perfis podem visualizar dados financeiros e documentos?
7. Qual ferramenta de galeria/seleção será usada inicialmente?
8. Quais integrações realmente economizam trabalho para a RN?

## 10. Definição de pronto

Cada requisito deve ter ator, justificativa, prioridade, regra de negócio, critérios de aceitação, dependências e cenários de erro. Uma funcionalidade só será concluída quando tiver validação, autorização, testes pertinentes e documentação atualizada.
