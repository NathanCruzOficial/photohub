# Modelo de Domínio — PhotoHub

- **Status:** conceitual e sujeito à validação operacional
- **Referência:** [Escopo e Requisitos](./02-escopo-e-requisitos.md)

## 1. Objetivo

Definir vocabulário de negócio e relacionamentos antes de criar tabelas e classes. Este documento não é um esquema físico definitivo. O modelo deve representar a operação da RN Foto & Mídia, contemplando frentes comerciais de fotografia e audiovisual que compartilham clientes e gestão operacional.

## 2. Conceitos do negócio

| Conceito | Responsabilidade |
|---|---|
| Operação/Empresa | Organização que utiliza o sistema na implantação inicial |
| Marca/Frente comercial | Identidade pública ou linha de serviço, como RN Fotografia e RN Audiovisual |
| Usuário | Pessoa autenticada que utiliza o Studio |
| Papel/Permissão | Define o que um usuário pode visualizar e executar |
| Cliente | Pessoa ou organização que solicita/contrata serviços |
| Contato | Pessoa ou canal de comunicação associado ao cliente |
| Lead | Solicitação ou oportunidade recebida por qualquer canal |
| Serviço | Modalidade oferecida, como ensaio, evento ou produção audiovisual |
| Pacote | Composição comercial de itens, entregáveis e condições |
| Adicional | Item opcional associado a pacote ou proposta |
| Proposta | Oferta comercial com itens, valores, validade e condições |
| Contrato | Instrumento que registra condições acordadas |
| Trabalho | Serviço confirmado que será executado |
| Projeto | Organização operacional do trabalho em etapas e tarefas |
| Tarefa | Atividade com responsável, prazo e estado |
| Evento/Compromisso | Ocorrência agendada relacionada ao trabalho |
| Membro/Fornecedor | Pessoa que participa da execução |
| Documento | Arquivo ou registro relacionado ao processo |
| Parcela | Valor previsto para pagamento em determinada data |
| Pagamento | Registro de valor recebido e sua conciliação operacional |
| Ativo de mídia | Referência a arquivo, pasta, galeria ou lote de mídia |
| Etapa de produção | Fase de seleção, edição e revisão |
| Entrega | Registro de materiais disponibilizados ao cliente |
| Atividade/Auditoria | Registro de ação ou alteração relevante |

## 3. Relacionamentos conceituais

- Uma operação pode possuir várias marcas ou frentes comerciais.
- Uma marca pode oferecer vários serviços e pacotes.
- Um cliente pode possuir vários contatos, leads e trabalhos.
- Um lead possui origem e pode ser associado a um cliente.
- Um lead pode originar propostas durante a negociação.
- Uma proposta aceita pode originar contrato e trabalho.
- A proposta deve preservar itens e condições apresentados, mesmo que o catálogo seja alterado depois.
- Um trabalho pode incluir vários serviços, eventos, documentos, parcelas, tarefas e entregas.
- Um projeto organiza etapas e tarefas de um trabalho.
- Membros da equipe e fornecedores podem participar de vários trabalhos.
- Ativos de mídia podem estar relacionados a etapas de produção ou entregas.
- Atividades registram alterações relevantes nas entidades do domínio.

## 4. Fluxo conceitual

~~~mermaid
flowchart TD
    A[Website, WhatsApp, indicação ou contato manual] --> B[Lead]
    B --> C[Cliente e atendimento]
    C --> D[Proposta e orçamento]
    D --> E{Aceita?}
    E -->|Não| F[Negociação ou encerramento]
    E -->|Sim| G[Contrato]
    G --> H[Trabalho / Projeto]
    H --> I[Agenda e equipe]
    H --> J[Tarefas e execução]
    J --> K[Produção e revisão]
    K --> L[Entrega]
    H --> M[Parcelas e pagamentos]
    B --> N[Histórico e auditoria]
    G --> N
    H --> N
~~~

## 5. Estados candidatos

Estados finais e transições devem ser definidos por processo e manter histórico.

**Lead:** novo; em atendimento; aguardando informações; orçamento em preparação; proposta enviada; em negociação; ganho; perdido.

**Proposta:** rascunho; enviada; aceita; recusada; expirada; substituída. Estados como visualizada só devem existir se houver evidência técnica confiável.

**Contrato:** rascunho; aguardando assinatura; assinado; cancelado; encerrado.

**Trabalho:** aguardando formalização; confirmado; agendado; em execução; em produção; aguardando aprovação/seleção; aguardando entrega; concluído; cancelado.

**Pagamento:** previsto; pendente; parcialmente pago; pago; atrasado; cancelado; estornado.

Os estados podem variar por modalidade, mas não devem criar fluxos duplicados sem justificativa.

## 6. Cuidados de modelagem

- Cliente e contato são conceitos diferentes.
- Lead e cliente não são sinônimos.
- Proposta deve manter snapshot dos itens e valores apresentados.
- Contrato e trabalho têm ciclos de vida diferentes.
- Um trabalho pode ter várias datas, equipes ou entregas.
- Preços e regras comerciais devem ser configuráveis.
- Arquivos grandes devem ficar em armazenamento apropriado; o banco guarda metadados e referências.
- Documentos e galerias precisam de controle de acesso por cliente e trabalho.
- Datas de eventos devem considerar fuso horário.
- Alterações críticas devem ser auditáveis.

## 7. RN-first e possibilidade futura de multiempresa

Na primeira implantação, o sistema atenderá uma única operação da RN. A existência de duas frentes comerciais públicas (RN Fotografia e RN Audiovisual) não significa que sejam dois tenants separados.

O domínio pode representar marcas ou unidades comerciais dentro da operação, compartilhando clientes, equipe e gestão. Não será implementado agora o isolamento completo de múltiplas empresas numa mesma instância. Uma evolução para multi-tenancy exigirá ADR, revisão de autorização, migração de dados e testes específicos de isolamento.

## 8. Questões para validação

1. O cliente pode ser pessoa física ou jurídica?
2. Uma contratação pode reunir fotografia e audiovisual?
3. Um trabalho pode ter várias datas e locais?
4. Quais etapas variam por ensaio, evento, casamento e produção audiovisual?
5. Como representar adicionais contratados depois da proposta?
6. Como versionar contratos e propostas alterados?
7. Quais membros da equipe precisam de acesso ao Studio?
8. Quais informações o cliente poderá consultar no portal futuro?
9. A seleção de fotos será própria ou feita por ferramenta externa?

## 9. Próxima revisão

Após inventariar o ERP/site anterior e validar os fluxos da RN, evoluir este documento para glossário, diagrama ER, regras de negócio e contratos de API.
