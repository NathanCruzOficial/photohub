# PhotoHub

**PhotoHub** é uma proposta de plataforma de gestão para negócios de fotografia e audiovisual. O objetivo é organizar o fluxo operacional desde o primeiro contato com o cliente até a execução e entrega do serviço.

O projeto parte de necessidades observadas em uma operação real de fotografia e audiovisual e será desenvolvido de forma incremental, com foco em requisitos claros, arquitetura sustentável, segurança, testes e integrações.

> **Status:** fase de descoberta e documentação. As funcionalidades, tecnologias e decisões arquiteturais ainda estão em definição.

## Objetivos

- Centralizar clientes, contatos e oportunidades comerciais.
- Organizar serviços, ensaios, eventos e trabalhos.
- Acompanhar contratos, pagamentos, produção e entregas.
- Reduzir tarefas manuais e retrabalho.
- Disponibilizar uma API documentada para integrações e automações.
- Manter histórico, controle de acesso e proteção dos dados.

## Escopo inicial

| Área | Objetivo |
|---|---|
| Clientes e contatos | Manter dados e histórico de relacionamento |
| Comercial | Acompanhar oportunidades, propostas e negociações |
| Serviços e trabalhos | Organizar serviços contratados e eventos |
| Agenda e equipe | Planejar datas, responsáveis e compromissos |
| Documentos | Relacionar contratos e documentos aos trabalhos |
| Financeiro operacional | Acompanhar valores acordados e pagamentos |
| Produção e entrega | Controlar etapas, prazos e disponibilização dos materiais |
| Integrações | Permitir comunicação com ferramentas externas |

O escopo é preliminar e será validado antes da implementação.

## Tecnologias

As tecnologias ainda não foram escolhidas. A seleção será documentada após a análise dos requisitos, restrições operacionais e alternativas técnicas. Não há stack ou infraestrutura declarada como definitiva nesta fase.

## Documentação

| Documento | Descrição |
|---|---|
| [Visão do Produto](docs/01-visao-do-produto.md) | Problema, público, objetivos e princípios |
| [Escopo e Requisitos](docs/02-escopo-e-requisitos.md) | Áreas funcionais e requisitos candidatos |
| [Modelo de Domínio](docs/03-modelo-de-dominio.md) | Conceitos e relacionamentos do negócio |
| [Arquitetura](docs/architecture/README.md) | Princípios e tópicos de arquitetura |
| [ADR Template](docs/adr/template.md) | Modelo para registrar decisões arquiteturais |

## Princípios de engenharia

- Separação de responsabilidades e baixo acoplamento.
- Código legível, testável e documentado.
- Segurança e privacidade desde o desenho.
- API consistente e documentada.
- Testes automatizados para regras e fluxos críticos.
- Integrações resilientes e observáveis.
- Decisões técnicas registradas e justificadas.
- Evolução incremental baseada em validação.

## Estado do projeto

1. [x] Repositório inicial criado.
2. [x] Documentação fundacional em elaboração.
3. [ ] Validar processos e requisitos com usuários.
4. [ ] Definir MVP e critérios de aceitação.
5. [ ] Avaliar arquitetura e stack.
6. [ ] Implementar a primeira fatia funcional.
7. [ ] Automatizar testes e verificações de qualidade.
8. [ ] Documentar API, implantação e operação.

## Contexto e propósito

O PhotoHub também funciona como projeto de engenharia de software, permitindo demonstrar levantamento de requisitos, modelagem de domínio, decisões arquiteturais, desenvolvimento, testes, segurança, documentação e manutenção.

As necessidades do negócio orientam o produto; as práticas de engenharia orientam como ele será construído.

## Contribuição e evolução

Durante a fase inicial, mudanças de escopo e decisões relevantes devem ser registradas na documentação. Decisões arquiteturais importantes devem utilizar o modelo de [Architecture Decision Record](docs/adr/template.md).
