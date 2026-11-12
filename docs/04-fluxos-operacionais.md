# Fluxos Operacionais — RN Foto & Mídia

- **Status:** mapa inicial para validação com os responsáveis pela operação
- **Objetivo:** transformar a rotina real em processos e requisitos do PhotoHub.

## 1. Princípio

O PhotoHub deve acompanhar o ciclo de vida de uma contratação, sem reduzir todas as modalidades de fotografia e audiovisual a um único checklist rígido. O fluxo geral é compartilhado; etapas, dados e entregáveis podem variar por serviço.

## 2. Jornada geral

~~~mermaid
flowchart TD
 A[Contato recebido] --> B[Lead registrado]
 B --> C[Qualificação e atendimento]
 C --> D[Orçamento / proposta]
 D --> E{Cliente aceitou?}
 E -->|Não| F[Negociação, retorno ou perdido]
 E -->|Sim| G[Contrato]
 G --> H[Confirmação e pagamento]
 H --> I[Trabalho / projeto criado]
 I --> J[Planejamento e agenda]
 J --> K[Execução do serviço]
 K --> L[Seleção e pós-produção]
 L --> M[Revisão e aprovação]
 M --> N[Entrega]
 N --> O[Encerramento e pós-venda]
~~~

## 3. Entrada e atendimento

Canais possíveis: Website, WhatsApp, Instagram, indicação e contato manual.

Dados candidatos:
- nome e meios de contato;
- modalidade de interesse;
- data e local do evento/ensaio;
- quantidade de pessoas, quando aplicável;
- descrição da necessidade;
- origem do contato;
- responsável pelo atendimento;
- consentimentos e preferências de comunicação, quando necessários.

O registro deve evitar duplicar clientes já existentes. Um lead pode existir antes de todos os dados do cliente estarem completos.

## 4. Qualificação e proposta

O atendimento identifica o tipo de serviço, coleta os dados necessários e apresenta a oferta adequada.

O PhotoHub deverá relacionar:
- modalidade e frente comercial;
- pacote e itens incluídos;
- adicionais;
- duração e local;
- deslocamento e condições;
- preço, validade e forma de pagamento;
- prazo e formato de entrega.

A proposta enviada precisa preservar a versão dos itens e condições apresentados, mesmo se o catálogo mudar posteriormente.

## 5. Contratação

Após aceite:
1. registrar a decisão comercial;
2. preparar o contrato com os dados acordados;
3. controlar versão e situação de assinatura;
4. registrar valores e parcelas;
5. criar o trabalho/projeto;
6. reservar data e equipe conforme disponibilidade.

A integração com assinatura eletrônica deverá ser escolhida após comparar custos, API, validade jurídica e experiência do cliente.

## 6. Planejamento e execução

Cada trabalho deverá conter dados do serviço, data(s), local(is), equipe, tarefas, prazos, documentos e observações.

As etapas podem variar:
- ensaio fotográfico;
- aniversário e eventos sociais;
- casamento e pré-wedding;
- chá revelação e eventos familiares;
- cobertura audiovisual, teatro, orquestra e eventos maiores.

O modelo deve permitir etapas configuráveis por modalidade sem duplicar a estrutura inteira do sistema.

## 7. Pós-produção e entrega

O Studio acompanhará status como:
- aguardando material;
- seleção;
- edição;
- revisão;
- aguardando seleção/aprovação do cliente;
- pronto para entrega;
- entregue.

Na primeira versão, o PhotoHub poderá armazenar metadados, prazos, responsáveis e links para ferramentas externas. Galeria privada, seleção avançada, downloads e armazenamento próprio são escopo futuro.

## 8. Financeiro e encerramento

O trabalho deve permitir consultar valor contratado, parcelas, vencimentos, pagamentos recebidos, pendências e situação final. O módulo é operacional e não substitui contabilidade.

Após a entrega, registrar conclusão, pendências, avaliação e histórico de relacionamento.

## 9. Uso do sistema anterior

O ERP/site anterior da RN já contemplou contratos e gerenciamento de projetos. Antes de implementar módulos equivalentes, inventariar:
- entidades e cadastros;
- formulários e dados capturados;
- modelos de contrato;
- etapas e estados dos projetos;
- relatórios e documentos;
- regras que funcionaram bem;
- limitações técnicas e problemas conhecidos.

O objetivo é reaproveitar conhecimento e regras validadas, não transportar automaticamente toda a implementação antiga.

## 10. Pontos que precisam ser confirmados

1. Campos obrigatórios por modalidade.
2. Diferenças do fluxo de fotografia e audiovisual.
3. Regras de orçamento, validade e adicionais.
4. Modelos de contrato e assinatura.
5. Critérios de reserva, sinal, parcelas e cancelamento.
6. Responsáveis e permissões por etapa.
7. Ferramentas atuais de seleção e entrega.
8. Prazos e critérios de conclusão por tipo de serviço.
