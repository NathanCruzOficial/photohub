# PhotoHub

**PhotoHub** é um ecossistema de software para negócios de fotografia e audiovisual. Será desenvolvido primeiro para uso real na **RN Foto & Mídia**, com qualidade de engenharia e documentação profissional.

A visão contempla três aplicações conectadas por uma API:
1. **PhotoHub Website** — site público, portfólio e captação de solicitações.
2. **PhotoHub Studio** — gestão interna de clientes, comercial, contratos, serviços, projetos, agenda, financeiro e produção.
3. **PhotoHub Client** — área privada para documentos, acompanhamento, seleção e entrega de imagens. Etapa futura.

> **Status:** descoberta, modelagem e documentação fundacional. Ainda não há funcionalidades de produto implementadas.

## Estratégia

O PhotoHub será validado inicialmente em uma única operação: RN Foto & Mídia. O objetivo imediato é resolver problemas reais, aproveitar os aprendizados do ERP/site anterior e construir um projeto de portfólio demonstrável.

A arquitetura deverá evitar bloqueios desnecessários a uma distribuição futura. Isso **não** significa implementar agora uma plataforma SaaS: multi-tenancy completo, planos, cobrança recorrente, onboarding comercial, suporte e operação de clientes externos estão fora do MVP.

## Aplicações

| Aplicação | Responsabilidade | Prioridade |
|---|---|---|
| Website | Apresentar a RN, divulgar serviços e receber solicitações | Após o núcleo do Studio |
| Studio | Controlar a operação interna e os dados do negócio | **Produto principal do MVP** |
| Client | Expor dados, documentos e galerias autorizadas ao cliente | Futuro |

O Website capta e encaminha leads; o Studio executa os processos internos; o Client oferecerá acesso restrito ao cliente. Nenhuma interface acessará diretamente o banco de dados.

## Escopo do MVP

- Clientes, contatos e histórico.
- Leads, atendimento, propostas e orçamentos.
- Catálogo de serviços, pacotes e adicionais.
- Contratos e documentos.
- Trabalhos/projetos, tarefas, responsáveis e prazos.
- Agenda operacional.
- Controle financeiro básico.
- Acompanhamento de produção e entrega por status e referências a arquivos externos.
- Usuários, permissões, histórico e auditoria.

O MVP não pretende substituir contabilidade, editar mídia, hospedar bibliotecas massivas de fotos ou oferecer uma galeria profissional completa.

## Stack definida

| Camada | Tecnologia |
|---|---|
| Frontend | React, TypeScript, Vite e Tailwind CSS |
| Backend/API | Python e FastAPI |
| Banco de dados | PostgreSQL |
| ORM e migrações | SQLAlchemy 2 e Alembic |
| Testes | Pytest |
| CI | GitHub Actions |
| Ambiente local | Docker Compose |

As escolhas serão registradas em ADRs e poderão ser revistas com justificativa técnica.

## Arquitetura inicial

A proposta é um **monólito modular**, com API compartilhada e aplicações frontend separadas no mesmo repositório. Os módulos de domínio devem refletir os processos do negócio, não apenas entidades técnicas. Essa abordagem reduz a complexidade operacional para uma pessoa desenvolvedora e mantém limites claros.

## Documentação

| Documento | Descrição |
|---|---|
| [Visão do Produto](docs/01-visao-do-produto.md) | Estratégia RN-first e visão das três aplicações |
| [Escopo e Requisitos](docs/02-escopo-e-requisitos.md) | Módulos, prioridades e critérios do MVP |
| [Modelo de Domínio](docs/03-modelo-de-dominio.md) | Conceitos e relacionamentos |
| [Fluxos Operacionais](docs/04-fluxos-operacionais.md) | Jornada de atendimento, contratação e entrega |
| [Arquitetura do Ecossistema](docs/05-arquitetura-do-ecossistema.md) | Aplicações, API e fronteiras técnicas |
| [Referências de Mercado](docs/06-referencias-de-mercado.md) | Plataformas para análise comparativa |
| [Arquitetura](docs/architecture/README.md) | Princípios e organização técnica |
| [ADR Template](docs/adr/template.md) | Modelo de decisões arquiteturais |

## Princípios de engenharia

- Resolver primeiro um problema operacional real.
- Separar Website, Studio e Client por responsabilidade.
- Manter regras de negócio no backend e módulos coesos.
- Proteger dados pessoais, contratos, finanças e imagens.
- Testar regras e fluxos críticos.
- Documentar API, instalação, operação e decisões.
- Não implementar complexidade SaaS antes de validar a necessidade.
- Manter o status do README fiel ao que realmente está implementado.

## Roadmap

1. Descoberta dos processos da RN e revisão do ERP/site anterior.
2. Requisitos, modelo de domínio e arquitetura.
3. Backend e PhotoHub Studio.
4. Website comercial integrado ao funil do Studio.
5. Integrações e automações selecionadas.
6. Portal do cliente e galerias.
7. Qualidade, segurança, implantação e demonstração pública.

## Portfólio

O repositório é público e voltado também à avaliação técnica por recrutadores. Deve demonstrar levantamento de requisitos, modelagem, arquitetura, APIs, desenvolvimento frontend/backend, testes, segurança, documentação e evolução incremental.

Screenshots e demonstrações serão adicionados quando existirem funcionalidades reais para apresentar.
