# Modelo de Domínio — PhotoHub

- **Status:** conceitual e sujeito a validação
- **Referência:** [Escopo e Requisitos](./02-escopo-e-requisitos.md)

## 1. Objetivo

Identificar os principais conceitos do negócio antes de definir tabelas, relacionamentos físicos ou modelos de código.

Este documento descreve um vocabulário inicial. Não é um esquema definitivo de banco de dados.

## 2. Conceitos principais

| Conceito | Descrição |
|---|---|
| Cliente | Pessoa ou organização que contrata ou solicita serviços |
| Contato | Meio ou pessoa de contato associada a um cliente |
| Oportunidade | Possibilidade comercial em atendimento ou negociação |
| Serviço | Modalidade oferecida pelo negócio |
| Proposta | Condições comerciais apresentadas ao cliente |
| Trabalho | Serviço confirmado que será executado |
| Evento | Ocorrência ou compromisso associado a um trabalho |
| Membro da equipe | Pessoa que participa de atividades operacionais |
| Documento | Arquivo ou registro documental associado ao processo |
| Pagamento | Registro de valor previsto, recebido ou pendente |
| Etapa de produção | Fase do fluxo de execução de um trabalho |
| Entrega | Registro da disponibilização do resultado ao cliente |
| Atividade | Ação, tarefa ou interação registrada no histórico |

## 3. Relacionamentos conceituais

- Um cliente pode possuir vários contatos.
- Um cliente pode possuir várias oportunidades.
- Uma oportunidade pertence a um cliente.
- Uma oportunidade pode originar uma proposta.
- Uma proposta aceita pode originar um trabalho.
- Um cliente pode possuir vários trabalhos.
- Um trabalho pode envolver um ou mais serviços, conforme regra a validar.
- Um trabalho pode possuir eventos, documentos, pagamentos e atividades.
- Um trabalho pode possuir etapas de produção e registros de entrega.
- Membros da equipe podem participar de vários trabalhos.

## 4. Fluxo conceitual

~~~mermaid
flowchart TD
    A[Cliente] --> B[Oportunidade]
    B --> C[Proposta]
    C --> D{Aceita?}
    D -->|Sim| E[Trabalho]
    D -->|Não| F[Encerrada ou em negociação]
    E --> G[Planejamento]
    G --> H[Execução e produção]
    H --> I[Entrega]
    E --> J[Documentos e pagamentos]
    E --> K[Histórico de atividades]
~~~

## 5. Estados candidatos

Os estados abaixo são exemplos para discussão. Os estados finais devem ser definidos por processo e não apenas por conveniência técnica.

**Oportunidade**
- nova;
- em atendimento;
- aguardando retorno;
- em negociação;
- ganha;
- perdida.

**Trabalho**
- aguardando confirmação;
- confirmado;
- agendado;
- em execução;
- em produção;
- aguardando entrega;
- concluído;
- cancelado.

## 6. Cuidados de modelagem

- Não confundir cliente com contato.
- Não confundir oportunidade comercial com trabalho confirmado.
- Não armazenar arquivos grandes diretamente no banco sem uma decisão arquitetural específica.
- Preservar histórico de alterações importantes.
- Evitar apagar registros necessários para auditoria ou histórico comercial.
- Definir regras para cancelamentos, reagendamentos e alterações de valores.
- Considerar fuso horário, datas e horários de eventos.
- Definir limites de acesso a dados pessoais e financeiros.

## 7. Questões para validação

1. O cliente será sempre uma pessoa física ou também poderá ser uma empresa?
2. Um evento pode ter vários contratos, pagamentos ou entregas?
3. Como representar serviços adicionais contratados depois da proposta?
4. A equipe será cadastrada por empresa?
5. Um mesmo usuário poderá participar de mais de uma empresa?
6. A seleção de fotos será controlada internamente ou integrada a uma ferramenta externa?

## 8. Próxima revisão

Após validar os fluxos reais, este documento poderá evoluir para diagrama ER, glossário de domínio, regras de negócio, modelos de dados e contratos de API.
