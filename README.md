# O PROJETO

- este é uma api para foruns com o objetivo de aplicar DDD na prática - desenvolvido pelo curso de node da rocketseat

# TEORIA

## Design de Software

- se refere à criação intencional e organizada de sistemas de software, com o objetivo de satisfazer necessidades específicas dos usuários, cumprir requisitos de qualidade e de performance, e garantir a manutenibilidade do código.

## DDD (Domain Driven Design - design dirigido a dominio)

- https://efficient-sloth-d85.notion.site/Gloss-rio-DDD-3a81b4df36d348a299ccbc53f38a1665
- **é uma abordagem de design de software** que se concentra na modelagem do domínio da aplicação, visando representar as regras e conceitos de negócios do mundo real.
- desenhar a aplicação, ou seja, como iremos converter o problema do nosso cliente em algo palpavel, um software que resolver o problema
- A principal diferença é que o Design de Software se concentra na arquitetura geral do sistema, enquanto o DDD enfatiza a modelagem do domínio.

### Dominio

- Domain Expects

  - conversar com quem domina a area do produto.

- Linguagem ubiqua

  - linguagem universal onde todos que estão envolvidos entendam

- entities - entidades

  - pessoas, unidades (eu, alunos, usuários,professores )

- casos de uso

  - verbos que conectam varias entidades (um professor dar aulas para alunos- aulas é um caso de uso)

- Value Object

  - campos que tem suas proprias regras de negocios => \domain\forum\enterprise\entities\value-objects

#### subDominios

- teoria: eles são independentes entre si. (é paralelo a ideia de microserviço)

  tipos de subdominios

- Core: o que é fundamental parao sistema funcionar
- Supporting: dar suporte para o core funcionar
- Generic: é necessário mas não fundamental

#### Domain events

- Domain Events, que é uma técnica utilizada para lidar com a comunicação e ações entre domínios na arquitetura de software.
- Publish/Subscribe. exemplo: src\core\events\domain-events.spec.ts e src\domain\notification\application\subscribers

### patterns

- Aggregates (faz parte do DDD)

  - um conjunto de entidades que são manipuladas ao mesmo tempo e elas juntas compoe algo maior que é aquilo que chamamos de aggregates.
  - exemplo: questions -> anexos = a questions e o anexos são salvos juntos, nascem juntos - src\domain\forum\enterprise\entities\answer.ts

- Watched Lists (faz parte do DDD)

  - lista observada. Ela permite termos mais informações de uma lista de um agregado(ex: order -> orderItens[]). Com ele sabemos se os itens foram removidos, adicionados ou atualizados
  - exemplo: src\domain\forum\enterprise\entities\question-attachment-list.ts

## Clean Architecture (arquitetura limpa)

- diferente do DDD que não fala de como estruturar o projeto e implementar, mas de como transformar problemas do mundo real em software. O clean architecture fala de estrutura de código e projeto.
- https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html

- fluxo de desenvolvimento

  - domain: implementar começando do coração da aplicação sem ainda pensar nas conexões externas
    - entity -> use-cases -> repositories
      - sempre já fazer os testes dos casos de uso

## patterns

### Functional Error Handling

- uso: src\core\either.ts
