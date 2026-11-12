# Arquitetura do Ecossistema — PhotoHub

- **Status:** proposta arquitetural inicial
- **Relacionados:** [Visão do Produto](./01-visao-do-produto.md), [Arquitetura](./architecture/README.md)

## 1. Visão geral

O PhotoHub terá aplicações com finalidades distintas, conectadas a um backend compartilhado. A separação é de experiência e responsabilidade, não uma exigência de três backends independentes.

~~~mermaid
flowchart TB
  subgraph Apps[Aplicações]
    W[Website comercial]
    S[Studio interno]
    C[Client portal futuro]
  end
  W --> API[PhotoHub API]
  S --> API
  C -. fase futura .-> API
  API --> D[(PostgreSQL)]
  API --> FS[Armazenamento de documentos e mídia]
  API --> EXT[Adaptadores de serviços externos]
  EXT --> GAL[Galerias / assinatura / e-mail / pagamentos]
~~~

## 2. PhotoHub Website

Responsabilidade: presença pública e captação.

Pode conter:
- páginas institucionais;
- páginas de fotografia e audiovisual;
- portfólio público;
- formulários de contato e orçamento;
- perguntas frequentes e informações comerciais.

O Website envia solicitações para a API. Não mantém um banco paralelo de clientes, contratos ou projetos e não deve conter regras comerciais duplicadas.

## 3. PhotoHub Studio

Responsabilidade: operação interna.

É a interface principal do MVP e consome a API para gerenciar:
- clientes e leads;
- catálogo e propostas;
- contratos;
- trabalhos, projetos e tarefas;
- agenda e equipe;
- financeiro operacional;
- produção e entregas;
- usuários, permissões e auditoria.

## 4. PhotoHub Client

Responsabilidade futura: autosserviço do cliente.

A aplicação só será iniciada após estabilizar o Studio e o modelo de autorização. O acesso será sempre limitado ao cliente e aos trabalhos relacionados à sua identidade. Contratos, pagamentos, galerias e downloads exigirão autorização no backend; ocultar links na interface não é controle de segurança.

## 5. Backend compartilhado

A API será implementada em FastAPI como monólito modular. Módulos iniciais candidatos:
- identity/access;
- customers;
- sales;
- catalog;
- proposals/contracts;
- jobs/projects;
- scheduling/team;
- finance;
- production/deliveries;
- media references;
- audit;
- integrations.

As regras do domínio devem ficar no backend e ser independentes das telas. Integrações externas devem ser encapsuladas por adaptadores.

## 6. Dados e armazenamento

PostgreSQL guarda dados transacionais e metadados. Documentos e arquivos de mídia devem usar armazenamento apropriado. O banco guarda referências, metadados, estados e permissões, não arquivos grandes por padrão.

A política de backup, retenção, exclusão, links privados e recuperação deve ser definida antes do piloto.

## 7. Organização do repositório

Estrutura pretendida, sujeita a ADR:

~~~text
photohub/
  apps/
    website/
    studio/
    client/          # futura etapa
  backend/
    api/
  docs/
    adr/
    architecture/
  infrastructure/
  .github/
~~~

A implementação pode começar com Website e Studio separados no frontend e uma API. Não criar app Client até sua fase.

## 8. RN-first e evolução

A primeira instalação atenderá uma única operação. RN Fotografia e RN Audiovisual podem ser representadas como marcas/frentes comerciais da mesma operação, compartilhando clientes e gestão.

Não implementar agora isolamento multi-tenant, billing, planos ou painel de assinantes. Antes de distribuir para outras empresas, revisar autorização, isolamento de dados, provisionamento, backups, observabilidade, suporte, custos e obrigações legais.

## 9. Ordem de implementação

1. Modelar domínio e regras do MVP.
2. Construir API e Studio para o fluxo principal.
3. Construir Website e integrar formulários ao funil comercial.
4. Estabilizar operação, testes, segurança e backups.
5. Implementar integrações selecionadas.
6. Avaliar Client e galerias.
7. Reavaliar distribuição multiempresa com evidências de uso.
