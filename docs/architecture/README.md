# Arquitetura do PhotoHub

## 1. Direção arquitetural

A direção inicial é um **monólito modular com API compartilhada e aplicações frontend separadas**. Essa escolha mantém o custo operacional compatível com um projeto conduzido por uma pessoa desenvolvedora, sem abandonar separação de responsabilidades.

Stack definida:
- React + TypeScript + Vite + Tailwind CSS;
- Python + FastAPI;
- PostgreSQL;
- SQLAlchemy 2 + Alembic;
- Pytest;
- Docker Compose para ambiente local;
- GitHub Actions para CI.

As escolhas serão formalizadas em ADRs conforme a implementação começar.

## 2. Aplicações e fronteiras

- **Website:** interface pública, conteúdo comercial, portfólio e captação de leads.
- **Studio:** interface autenticada para gestão interna.
- **Client:** interface privada futura para documentos, acompanhamento e galerias.

As aplicações não devem compartilhar regras de negócio por cópias no frontend. A API é a fronteira de negócio e autorização.

## 3. Organização do backend

Organizar o backend por módulos de domínio, mantendo routers, schemas, serviços, persistência e integrações em responsabilidades distintas. Módulos candidatos:
- identidade e acesso;
- clientes e contatos;
- comercial;
- catálogo de serviços;
- propostas e contratos;
- trabalhos e projetos;
- agenda e equipe;
- financeiro operacional;
- produção e entregas;
- arquivos e integrações;
- auditoria.

Não é necessário criar um microserviço por módulo.

## 4. Persistência e arquivos

PostgreSQL será a fonte principal de dados transacionais. SQLAlchemy e Alembic serão utilizados para persistência e migrações.

Arquivos de contratos e mídia não devem ser armazenados como grandes blobs no banco por padrão. O sistema manterá metadados, permissões e referências para armazenamento apropriado. Provedor, política de backup e recuperação deverão ser documentados antes do uso operacional.

## 5. Segurança

- autenticação e autorização no backend;
- menor privilégio para usuários e integrações;
- validação de entradas e proteção contra abuso;
- segredos fora do código e dos logs;
- proteção de documentos e arquivos privados;
- trilha de auditoria para ações críticas;
- backups e restauração testados;
- revisão de privacidade e LGPD antes do piloto.

## 6. Estratégia RN-first

A primeira implantação atenderá uma operação. O sistema poderá representar marcas/frentes comerciais da RN, mas isso não equivale a multi-tenancy SaaS.

Evitar dependências que dificultem evolução futura, mas não implementar agora isolamento de dados de várias empresas, billing, onboarding SaaS, painel de assinantes ou infraestrutura distribuída.

Uma futura distribuição exigirá avaliação explícita de arquitetura, segurança, custos, suporte e requisitos legais.

## 7. Qualidade e testes

- testes unitários para regras de domínio;
- testes de integração para persistência e serviços;
- testes de API para autorização e contratos HTTP;
- testes de frontend para formulários e fluxos críticos;
- CI para lint, typecheck e testes;
- dados de demonstração fictícios e claramente identificados.

## 8. Decisões arquiteturais

Decisões relevantes devem ser registradas em docs/adr/, usando o [template](../adr/template.md). Uma decisão substituída deve permanecer no histórico, com uma nova ADR explicando a mudança.

## 9. Documentos relacionados

- [Visão do Produto](../01-visao-do-produto.md)
- [Escopo e Requisitos](../02-escopo-e-requisitos.md)
- [Modelo de Domínio](../03-modelo-de-dominio.md)
- [Fluxos Operacionais](../04-fluxos-operacionais.md)
- [Arquitetura do Ecossistema](../05-arquitetura-do-ecossistema.md)
