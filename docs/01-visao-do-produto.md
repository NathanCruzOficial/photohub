# Visão do Produto — PhotoHub

- **Status:** direção estratégica definida; requisitos em validação
- **Produto inicial:** sistema de gestão para RN Foto & Mídia

## 1. Resumo executivo

O PhotoHub é um ecossistema para organizar negócios de fotografia e audiovisual. Será construído primeiro para resolver necessidades reais da RN Foto & Mídia e, simultaneamente, servir como projeto público de portfólio e aprendizagem de engenharia de software.

A visão contempla três aplicações conectadas por uma API: Website comercial, Studio de gestão interna e Client, portal privado para documentos e galerias. O Studio é o centro operacional e o primeiro produto a ser desenvolvido. O Website é uma interface comercial separada, integrada ao fluxo de leads. O Client é uma etapa futura.

## 2. Contexto e problema

A rotina de fotografia e audiovisual envolve captação, atendimento, orçamento, negociação, contratos, pagamentos, agenda, equipe, execução, pós-produção e entrega. Essas informações podem ficar distribuídas entre conversas, planilhas, documentos, sistemas próprios e ferramentas especializadas.

O projeto parte da experiência operacional da RN e dos aprendizados do ERP/site anteriormente desenvolvido, que já contemplava contratos e gerenciamento de projetos. A descoberta deverá confirmar quais processos funcionam bem, quais apresentam gargalos e quais componentes podem ser reaproveitados.

## 3. Estratégia RN-first e distribuição futura

A RN será a primeira usuária e ambiente de validação. A prioridade é entregar um fluxo utilizável, confiável e seguro para a operação real.

O código e a arquitetura devem evitar acoplamentos que impeçam atender outras empresas futuramente. Entretanto, não haverá compromisso de lançar um SaaS no MVP.

Ficam fora da primeira etapa: multi-tenancy completo, isolamento de várias empresas na mesma instalação, planos, assinaturas, cobrança recorrente, onboarding automatizado, painel de assinantes, suporte comercial e operação para terceiros. Uma eventual distribuição dependerá de validação de mercado, capacidade de suporte, custos, segurança, obrigações legais e viabilidade econômica.

## 4. Aplicações e responsabilidades

### 4.1 PhotoHub Website
- apresentar a empresa e suas frentes comerciais;
- divulgar serviços, pacotes e portfólio;
- receber contatos e solicitações de orçamento;
- encaminhar solicitações ao funil comercial do Studio.

Não gerencia contratos, pagamentos ou projetos diretamente.

### 4.2 PhotoHub Studio
- clientes, contatos e histórico;
- leads, atendimento e oportunidades;
- catálogo de serviços, pacotes e adicionais;
- propostas, orçamentos e contratos;
- trabalhos, projetos, tarefas e responsáveis;
- agenda e planejamento;
- financeiro operacional;
- produção, status de mídia e entregas;
- usuários, permissões, auditoria e relatórios.

### 4.3 PhotoHub Client
- login e acesso privado;
- leitura de contratos e documentos autorizados;
- acompanhamento do serviço;
- seleção e aprovação de imagens;
- galerias privadas, downloads e entrega.

O portal só será iniciado quando o fluxo interno e a API estiverem estáveis. Armazenamento e galeria próprios deverão ser comparados com integrações especializadas.

## 5. Público e usuários

**Usuários iniciais:** sócios e equipe da RN Foto & Mídia. Perfis a validar: administração, atendimento/comercial, fotografia e audiovisual, produção/edição e financeiro.

**Usuários externos futuros:** clientes que solicitam serviços e acessam documentos ou materiais entregues.

## 6. Objetivos

1. Centralizar informações de clientes e oportunidades.
2. Representar o fluxo real de fotografia e audiovisual.
3. Reduzir redigitação, retrabalho e perda de contexto.
4. Relacionar contratos, pagamentos, projetos e entregas.
5. Dar visibilidade a pendências, prazos e próximos passos.
6. Separar experiência pública, gestão interna e portal privado.
7. Construir API consistente para integrações e futuras aplicações.
8. Demonstrar práticas profissionais de engenharia de software.

## 7. Indicadores de sucesso

- Um lead pode ser acompanhado até a contratação.
- Um trabalho contratado possui cliente, serviço, contrato, valores, agenda e responsáveis relacionados.
- A equipe localiza histórico, documentos e situação de cada trabalho.
- Prazos, pendências e entregas são acompanhados no Studio.
- Dados e documentos só são acessíveis a usuários autorizados.
- Fluxos críticos possuem testes automatizados.
- A RN consegue realizar um piloto sem processos paralelos para funções já migradas.

Metas quantitativas serão definidas após observar a operação.

## 8. Princípios

- Domínio antes da tecnologia.
- Operação simples e sem duplicidade.
- Separação de responsabilidades entre as aplicações.
- Rastreabilidade de alterações relevantes.
- Segurança e privacidade desde o desenho.
- Evolução incremental validada pela RN.
- Código compreensível, testável e documentado.
- Distribuição opcional, sem antecipar a complexidade SaaS.

## 9. Fora do escopo inicial

- SaaS comercial com cobrança recorrente;
- marketplace;
- editor de fotos ou vídeos;
- hospedagem massiva e processamento de mídia;
- contabilidade e obrigações fiscais;
- aplicativo mobile nativo;
- microserviços sem necessidade comprovada;
- portal completo e galeria própria no primeiro MVP.

## 10. Próxima revisão

Revisar após inventariar o ERP/site anterior, mapear os fluxos da RN por modalidade, levantar contratos e catálogo de serviços e validar os critérios de aceite do MVP.
