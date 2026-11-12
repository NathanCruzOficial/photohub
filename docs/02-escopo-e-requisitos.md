# Escopo e Requisitos — PhotoHub

- **Status:** rascunho inicial
- **Referência:** [Visão do Produto](./01-visao-do-produto.md)

## 1. Objetivo

Definir a primeira fronteira funcional do PhotoHub e registrar requisitos candidatos. Este documento orienta a descoberta e não representa funcionalidades já implementadas.

## 2. Escopo candidato do produto

### 2.1 Gestão de clientes e contatos
- cadastro e consulta de clientes;
- múltiplos meios de contato;
- histórico de interações;
- associação entre clientes, oportunidades e trabalhos.

### 2.2 Gestão comercial
- registro de oportunidades/solicitações;
- acompanhamento de etapas do atendimento;
- registro de serviços de interesse;
- elaboração e acompanhamento de propostas/orçamentos;
- conversão de oportunidade em trabalho confirmado.

### 2.3 Serviços e eventos
- cadastro de categorias e tipos de serviço;
- criação de ensaios, eventos e produções;
- registro de data, local, duração e observações;
- associação de equipe e responsáveis;
- controle de status e pendências.

### 2.4 Documentos e contratos
- associação de documentos ao cliente e ao trabalho;
- controle de situação de contratos;
- registro de datas importantes;
- histórico de alterações relevantes.

A geração, assinatura eletrônica e armazenamento de documentos deverão ser avaliados separadamente.

### 2.5 Financeiro operacional
- registro de valores acordados;
- controle de pagamentos previstos e recebidos;
- acompanhamento de parcelas e pendências;
- visão resumida por cliente e trabalho.

O módulo não tem como objetivo substituir contabilidade, emissão fiscal ou um sistema financeiro completo.

### 2.6 Produção e entrega
- acompanhamento das etapas de produção;
- registro de seleção, edição e revisão;
- controle de prazo e situação da entrega;
- registro de links ou referências para materiais entregues;
- histórico de conclusão do trabalho.

O armazenamento dos arquivos originais e finais não está incluído no escopo inicial.

### 2.7 Integrações e automações
- API documentada para operações do domínio;
- possibilidade de integração com ferramentas externas;
- mecanismos de autenticação e autorização para integrações;
- registro de falhas e rastreabilidade de operações;
- automações para reduzir tarefas repetitivas.

Os provedores e integrações prioritários ainda precisam ser levantados. Nenhuma integração deve ser considerada garantida antes da análise de API, custos, limites e termos do fornecedor.

## 3. Priorização inicial

| Prioridade | Área | Justificativa |
|---|---|---|
| P0 | Clientes e contatos | Base dos relacionamentos |
| P0 | Oportunidades e atendimento | Entrada do fluxo comercial |
| P0 | Serviços e trabalhos | Representa a operação principal |
| P1 | Agenda e equipe | Planejamento da execução |
| P1 | Propostas e contratos | Formalização comercial |
| P1 | Pagamentos | Controle operacional |
| P1 | Produção e entrega | Acompanhamento ponta a ponta |
| P2 | API e integrações | Expansão e automação |
| P2 | Relatórios e indicadores | Gestão e tomada de decisão |

A prioridade é provisória e deverá ser confirmada com usuários.

## 4. Requisitos funcionais candidatos

- **RF-001:** O sistema deve permitir cadastrar, consultar, atualizar e inativar clientes.
- **RF-002:** O sistema deve permitir registrar contatos e histórico de interações.
- **RF-003:** O sistema deve permitir registrar oportunidades comerciais.
- **RF-004:** O sistema deve permitir acompanhar a etapa de cada oportunidade.
- **RF-005:** O sistema deve permitir cadastrar tipos de serviço.
- **RF-006:** O sistema deve permitir criar trabalhos associados a clientes.
- **RF-007:** O sistema deve permitir registrar data, local e observações de um trabalho.
- **RF-008:** O sistema deve permitir acompanhar o status de execução de um trabalho.
- **RF-009:** O sistema deve permitir associar documentos a clientes e trabalhos.
- **RF-010:** O sistema deve permitir registrar valores acordados e pagamentos.
- **RF-011:** O sistema deve permitir acompanhar etapas de produção e entrega.
- **RF-012:** O sistema deve manter histórico de alterações relevantes.
- **RF-013:** O sistema deve expor operações selecionadas por uma API documentada.
- **RF-014:** O sistema deve permitir controlar acesso conforme usuário e permissões.
- **RF-015:** O sistema deve permitir consultar pendências e próximos passos.

## 5. Requisitos não funcionais candidatos

- **RNF-001 — Segurança:** credenciais e segredos não devem ser armazenados em texto puro.
- **RNF-002 — Autorização:** operações devem verificar as permissões do usuário no servidor.
- **RNF-003 — Privacidade:** dados pessoais devem ser tratados com finalidade e acesso apropriados, observando a LGPD.
- **RNF-004 — Integridade:** operações críticas devem preservar consistência dos dados.
- **RNF-005 — Auditoria:** ações relevantes devem permitir identificar o que ocorreu e quando.
- **RNF-006 — Manutenibilidade:** código organizado por responsabilidades e acompanhado de testes.
- **RNF-007 — Documentação:** API e decisões arquiteturais devem possuir documentação versionada.
- **RNF-008 — Observabilidade:** erros relevantes devem ser registrados sem expor dados sensíveis.
- **RNF-009 — Desempenho:** metas de resposta deverão ser definidas a partir dos cenários de uso.
- **RNF-010 — Disponibilidade e recuperação:** estratégia de backup e recuperação deverá ser definida antes de uso operacional.

## 6. Regras e decisões ainda pendentes

1. Uma pessoa pode ser cliente em vários trabalhos?
2. Um trabalho pode incluir mais de um serviço?
3. Como representar eventos com múltiplas datas ou etapas?
4. Como tratar cancelamentos, reagendamentos e reembolsos?
5. Quais usuários podem visualizar dados financeiros?
6. A plataforma atenderá uma empresa por instalação ou várias empresas na mesma instância?
7. Quais ferramentas externas precisam ser integradas primeiro?
8. Quais dados e documentos precisam de trilha de auditoria?

## 7. Critérios para considerar um requisito pronto

Um requisito deverá possuir identificador único, descrição objetiva, justificativa de negócio, prioridade, critérios de aceitação verificáveis, dependências e regras de negócio conhecidas.

## 8. Fora do escopo da primeira entrega

- edição de fotos e vídeos;
- hospedagem própria de grandes bibliotecas de mídia;
- contabilidade e obrigações fiscais;
- marketplace público;
- automações sem controle de permissão, histórico e tratamento de falhas.

## 9. Histórico

| Versão | Alteração |
|---|---|
| 0.1 | Primeira versão dos requisitos candidatos |
