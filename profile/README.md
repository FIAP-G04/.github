# Tech Challenge FIAP - 4SOAT 👋
Os repositórios desta organização têm como objetivo principal o desenvolvimento do **Tech Challenge** da **Pós-Graduação em Software Architecture** da **FIAP**, realizado pelo grupo **G04**, composto por:

<p align="center">
  <img width="100%" src="https://github.com/FIAP-G04/.github/blob/main/images/nosso-grupo.png?raw=true" alt="Nosso Grupo">
</p>

## Domain Discovery
- [Visão Geral do Problema](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#vis%C3%A3o-geral-do-problema)
- [Análise do Cenário Atual (AS-IS)](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#an%C3%A1lise-do-cen%C3%A1rio-atual-as-is)
- [Decomposição da Visão do Domain Expert](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#decomposi%C3%A7%C3%A3o-da-vis%C3%A3o-do-domain-expert)
  - [Atores](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#atores)
  - [Cenários](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#cen%C3%A1rios)
    - [Realizar um Pedido](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#realizar-um-pedido)
    - [Preparação e Retirada do Pedido](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#prepara%C3%A7%C3%A3o-e-retirada-do-pedido)
    - [Revisar Informações do Cardápio](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#revisar-informa%C3%A7%C3%B5es-do-card%C3%A1pio) 
- [Mapeamento de Domínios e Subdomínios](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#mapeamento-de-dom%C3%ADnios-e-subdom%C3%ADnios)
  - [Core Domains](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#core-domains)
  - [Supporting Domains](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#supporting-domains)
  - [Generic Domains](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#generic-domains)
- [Análise de Subdomínios no Cenário TO-BE](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#an%C3%A1lise-de-subdom%C3%ADnios-no-cen%C3%A1rio-to-be)
- [Análise Estratégica dos Subdomínios](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#an%C3%A1lise-estrat%C3%A9gica-dos-subdom%C3%ADnios)
- [Visão Geral da Solução](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#vis%C3%A3o-geral-da-solu%C3%A7%C3%A3o)
  - [Módulo de Autoatendimento](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#m%C3%B3dulo-de-autoatendimento)
  - [Módulo de Acompanhamento de Pedido](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#m%C3%B3dulo-de-acompanhamento-de-pedido)
  - [Módulo de Gestão de Cardápio](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#m%C3%B3dulo-de-gest%C3%A3o-de-card%C3%A1pio)
- [Dicionário de Linguagem Ubíqua](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#dicion%C3%A1rio-de-linguagem-ub%C3%ADqua)
- [Event Storming](https://github.com/FIAP-G04/.github/blob/main/profile/Domain-Discovery.md#event-storming)

# iBurguer
- [O que é iBurguer?](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#o-que-%C3%A9-ibuguer)
- [Funcionalidades](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#funcionalidades)
  - [Gestão de Cardápio](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#gest%C3%A3o-de-card%C3%A1pio)
  - [Gestão de Clientes](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#gest%C3%A3o-de-clientes)
  - [Carrinho de Compras](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#carrinho-de-compras)
  - [Gestão de Pagamentos](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#pagamento)
  - [Gestão de Pedidos](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#pedidos)
- [Visão Geral da Arquitetura](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#vis%C3%A3o-geral-da-arquitetura)
  - [Cenário Monolítico](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#cen%C3%A1rio-monol%C3%ADtico)
  - [Cenário em Microsserviços](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#cen%C3%A1rio-em-microsservi%C3%A7os)
  - [Diagrama de Sequência do processo de SignUp](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#diagrama-de-sequ%C3%AAncia-do-processo-de-signup)
  - [Diagrama de Sequência do processo de SignIn](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#diagrama-de-sequ%C3%AAncia-do-processo-de-signin)
- [Estrutura de Persistência de Dados](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#estrutura-de-persist%C3%AAncia-de-dados)
  - [Gestão de Cardápio](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#gest%C3%A3o-de-card%C3%A1pio-1)
  - [Carrinho de Compras](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#carrinho-de-compras-1)
  - [Gestão de Pedidos](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#gest%C3%A3o-de-pedidos)
  - [Gestão de Pagamentos](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#gest%C3%A3o-de-pagamentos)
  - [Dados do Cliente](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#dados-de-cliente)
- [Políticas de Resiliência](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#pol%C3%ADticas-de-resili%C3%AAncia)
- [Tecnologias Utilizadas](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#tecnologias-utilizadas)
- [Fluxo de Implantação e CI/CD](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#fluxo-de-implanta%C3%A7%C3%A3o-e-cicd)
- [Infraestrutura na AWS usando Terraform](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#infraestrutura-na-aws-usando-terraform)

## Vídeos
- [Fase 2](https://youtu.be/QVkNK2sfK38)
- [Fase 3](https://youtu.be/Xz4LOV8k-Mo)
- [Fase 4](https://youtu.be/Xz4LOV8k-Mo)
