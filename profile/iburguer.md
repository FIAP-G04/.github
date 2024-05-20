# iBurguer
- [O que é iBurguer?](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#o-que-%C3%A9-ibuguer)
- [Funcionalidades](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#funcionalidades)
  - [Gestão de Cardápio](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#gest%C3%A3o-de-card%C3%A1pio)
  - [Gestão de Clientes](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#gest%C3%A3o-de-clientes)
  - [Carrinho de Compras](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#carrinho-de-compras)
  - [Pagamento](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#pagamento)
  - [Gestão de Pedidos](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#pedidos)
- [Visão Geral da Arquitetura](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#vis%C3%A3o-geral-da-arquitetura)
  - [Diagrama de Container](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#diagrama-de-container)
  - [Diagrama de Sequência do processo de SignUp](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#diagrama-de-sequ%C3%AAncia-do-processo-de-signup)
  - [Diagrama de Sequência do processo de SignIn](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#diagrama-de-sequ%C3%AAncia-do-processo-de-signin)
- [Estrutura de Persistência de Dados](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#estrutura-de-persist%C3%AAncia-de-dados)
  - [RDS - Amazon Relational Database Service](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#rds---amazon-relational-database-service)
  - [Dados do Cliente](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#dados-de-cliente)
- [Tecnologias Utilizadas](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#tecnologias-utilizadas)
- [Fluxo de Implantação e CI/CD](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#fluxo-de-implanta%C3%A7%C3%A3o-e-cicd)
- [Infraestrutura na AWS usando Terraform](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#infraestrutura-na-aws-usando-terraform)
  
## O que é iBurguer?
Em suma, a plataforma **iBurguer** é uma solução abrangente que aborda os desafios operacionais da lanchonete **Byte Burguer**, oferecendo uma solução integrada de **gerenciamento de pedidos**, **autoatendimento**, **gestão de clientes**, **cardápio digital** entre outras coisas. Essas funcionalidades não apenas melhoram a eficiência operacional, mas também proporcionam uma experiência aprimorada para os clientes e oportunidades de crescimento para o negócio.

## Funcionalidades
<p align="center">
  <img width="100%" src="https://github.com/FIAP-G04/.github/blob/main/images/fiap-subdominios.png" alt="Diagrama de Container">
</p>

Seguem abaixo a lista de funcionalidades expostas na API:

### Gestão de Cardápio
O primeiro passo para a execução da API é o preenchimento do cardápio com itens que podem ser adicionados ao pedido. 

```POST /api/menu/items``` <br>Inclui um item no cardápio;

```PUT /api/menu/items/{id}``` <br>Atualiza um item do cardápio;

```DELETE /api/menu/items/{id}``` <br>Remove um item do cardápio;

```PATCH /api/menu/items/{id}/enabled``` <br>Habilita um item do cardápio;

```PATCH /api/menu/items/{id}/disabled``` <br>Desabilita um item do cardápio;

```GET /api/menu/items/{category}``` <br>Obtem todos os itens do cardápio a partir de uma determinada categoria;

```GET /api/menu/items/{id}``` <br>Obtem os dados de um item do cardápio;

### Gestão de Clientes

O próximo passo é o registro dos clientes que farão os pedidos na lanchonete. Para esse fim são disponibilizados os seguintes endpoints:

```POST /api/customers/signup``` <br>Registra um cliente;

```POST /api/customers/signin``` <br>Autentica o cliente a partir do CPF;

### Carrinho de Compras

Havendo um cardápio definido com itens e um cliente cadastrado buscando pelos mesmos, é necessário que um carrinho seja criado para o cliente. Isso pode ser feito através do endpoint:

```POST /api/carts``` <br>Cria carrinho a partir do identificador do cliente cadastrado;

Em seguida, os itens do carrinho podem ser gerenciados através dos seguintes endpoints:

```POST /api/carts/{shoppingCartId}/items``` <br>Adiciona um item do menu ao carrinho de compras através de seu ID;

```PATCH /api/carts/{shoppingCartId}/items/{cartItemId}/incremented``` <br>Incrementa a quantidade de um determinado item do carrinho através de seu ID;

```PATCH /api/carts/{shoppingCartId}/items/{cartItemId}/decremented``` <br>Decrementa a quantidade de um determinado item do carrinho através de seu ID;

```DELETE /api/carts/{shoppingCartId}/items/{cartItemId}``` <br>Remove um determinado item do carrinho através de seu ID;

```PATCH /api/carts/{shoppingCartId}/checkout``` <br>Gera o QRCode de Pagamento e também o pedido do cliente;

### Pagamento

Após a criação de um pagamento, o gerenciamento de seu *status* pode ser feito pelos seguintes endpoints:

```POST /api/payments``` <br>Gera QrCode no Mercado Pago e registra um pagamento no status de pendente no banco de dados;

```PUT /api/payments/{idd}/confirmed``` <br>Webhook que confirma o pagamento;

```PUT /api/payments/{id}/refused``` <br>Webhook que recusa o pagamento;

### Pedidos

Após a criação de um pagamento, o pedido referente ao mesmo é criado. O seguinte endpoint pode ser utilizado para verificar todos os pedidos:

```GET /api/orders``` <br>Retorna os pedidos em uma lista paginada;

Após a confirmação do pagamento, o mesmo é enviado para a fila de pedidos. A seguir estão os endpoints utilizados para gerenciá-lo até sua finalização:

```GET /api/orders/queue``` <br>Retorna a fila de pedidos, com os pedidos em *status* Pronto, Em Preparação e Finalizado;

```PATCH /api/orders/{id}/started``` <br>Confirma o pedido, passando o mesmo para o *status* Em Preparação. 

```PATCH /api/orders/{id}/completed``` <br>Indica que o pedido foi preparado pela cozinha, passando o mesmo para o *status* Pronto;

```PATCH /api/orders/{id}/delivered``` <br>Indica que o pedido foi recebido pelo cliente, passando o mesmo para o *status* Finalizado;

```PATCH /api/orders/{id}/canceled``` <br>Cancela um pedido;

## Visão Geral da Arquitetura
Nesta seção utilizaremos o diagrama C4 para representar algumas visões de arquitetura da plataforma **iBurguer**.

### Diagrama de Container
Dividimos o iBurguer em cinco subdomínios distintos, e a separação dos microsserviços seguiu a mesma lógica. Como resultado, temos os seguintes microsserviços:

- Menu API => Gestão de Cardápio
- Shopping Cart API => Carrinho de compras
- Ordering API => Gestão de Pedidos
- Payments API => Gestão de Pagamentos
- SignIn Function => Autenticação do cliente
- SignUp Function => Registro do cliente

<p align="center">
  <img width="96%" src="https://github.com/FIAP-G04/.github/blob/main/images/iburguer-macro-architecture.png" alt="Diagrama de Container">
</p>

### Diagrama de Sequência do processo de SignUp
Este diagrama visa mostrar o passo à passo do processo de registro de um cliente utilizando a plataforma **Amazon Cognito**.

<p align="center">
  <img width="85%" src="https://github.com/FIAP-G04/.github/blob/main/images/signup-diagram.png" alt="Diagrama de Sequência">
</p>

### Diagrama de Sequência do processo de SignIn
Este diagrama visa mostrar o passo à passo do processo de autenticação do cliente utilizando a plataforma **Amazon Cognito**.

<p align="center">
  <img width="85%" src="https://github.com/FIAP-G04/.github/blob/main/images/signin-diagram.png" alt="Diagrama de Sequência">
</p>

## Estrutura de Persistência de Dados
Decidimos armazenar os dados do **Cliente** diretamente no **Amazon Cognito** e manter os contextos de **Cardápio**, **Pedido**, **Pagamento** e **Carrinho** no **Amazon Relational Database Service**, como parte da estratégia para atender aos requisitos da **FASE 3** do **Tech Challenge**, que exige a separação do contexto do **Cliente** do monolito.

A criação da estrutura de tabelas no RDS foi feito através de Migrations do .NET.

### Gestão de Cardápio
Para o armazenamento do cenário de Cardápio Digital, optamos pela utilização do MongoDB devido a várias características chave que ele possui. Ele oferece um modelo de dados flexível, permitindo fácil alteração de esquemas sem migrações complexas. Sua capacidade de escalabilidade horizontal garante que o sistema suporte um crescimento significativo e mantenha alta performance em operações de leitura e escrita. O MongoDB também permite o armazenamento eficiente de dados complexos com estruturas aninhadas e arrays de forma nativa.

Além disso, o MongoDB assegura alta disponibilidade e confiabilidade através da replicação e tolerância a falhas. Ferramentas avançadas de administração e um robusto ecossistema de suporte facilitam a gestão e manutenção do banco de dados. Essas características combinadas tornam o MongoDB uma opção ideal para um cardápio digital, oferecendo flexibilidade, escalabilidade e desempenho superior.

Segue um exemplo da estrutura de dados armazenada no banco de dados referente a um item do cardápio:
```json
{
   "id": "082d3640-34a1-48e2-9b1d-ae93cf5bce80",
   "name":"Batata Frita",
   "description":"Batata frita deliciosa e crocante",
   "price":"10.0"
   "category":1,
   "preparationTime":3,
   "enabled":true,
   "createdAt":"1716160618861",
   "updatedAt":"1716160618861",
   "images":[
      "http://img.url.com"
   ]
}
```

### Carrinho de Compras
O Redis é ideal para armazenar dados de carrinhos de compras devido à sua performance rápida, já que é um banco de dados em memória, proporcionando leituras e escritas instantâneas. Suas estruturas de dados ricas e flexíveis permitem armazenar e manipular eficientemente os itens do carrinho. Além disso, Redis oferece persistência transitória com expiração automática de chaves, ideal para gerenciar sessões de carrinho. Sua capacidade de escalabilidade e clusterização facilita a gestão de grandes volumes de dados e usuários simultâneos. Redis também é fácil de integrar com diversas linguagens e frameworks, tornando a implementação rápida e eficiente. 

Segue um exemplo da estrutura de dados armazenada no banco de dados referente a um carrinho de compra:
```json
{
   "Id":"209fb1d8-8b00-4d67-a8dd-4cf80a5ccefc",
   "CustomerId":"3fa85f64-5717-4562-b3fc-2c963f66afa6",
   "Closed":false,
   "CreatedAt":"2024-05-19T22:54:06.860262-03:00",
   "UpdatedAt":"2024-05-19T22:56:38.400384-03:00",
   "Items":[
      {
         "CartItemId":"aaeded25-ea11-423b-922b-0f50c80f6de1",
         "Product":{
            "ProductId":"ab59d5ca-0275-4a15-b065-4da640358138",
            "Name":"Sorvete de Chocolate",
            "Type":"Dessert",
            "Price":10.0
         },
         "Quantity":2,
         "UnitPrice":10.0
      }
   ],
}
```

<p align="center">
  <img width="600" src="https://github.com/FIAP-G04/.github/blob/main/images/mer.png" alt="Modelo de Dados">
</p>

### Dados de Cliente
Os dados de cliente estão sendo armazenados no próprio Amazon Cognito.

<p align="center">
  <img width="120" src="https://github.com/FIAP-G04/.github/blob/main/images/customer.png" alt="Dados de Cliente">
</p>

## Tecnologias Utilizadas
Esse projeto está utilizando as seguintes tecnologias até o momento:

- [C#](https://learn.microsoft.com/pt-br/dotnet/csharp/)
- [.NET 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
- [PostgreSQL](https://www.postgresql.org/)
- [Docker](https://www.docker.com/)
- [Kubernetes](https://kubernetes.io/pt-br/)
- [Helm](https://helm.sh/)
- [Swagger](https://swagger.io/)
- [Amazon Relational Database Service](https://aws.amazon.com/pt/rds/)
- [Amazon Cognito](https://aws.amazon.com/pt/pm/cognito/)
- [AWS Lambda](https://aws.amazon.com/pt/pm/lambda/)
- [Amazon API Gateway](https://aws.amazon.com/pt/api-gateway/)
- [Amazon Elastic Kubernetes Service](https://aws.amazon.com/pt/eks/)
- [Amazon S3](https://aws.amazon.com/pt/s3/)
- [Terraform](https://www.terraform.io/)
- [Github Actions](https://github.com/features/actions)
- [K6](https://k6.io/)

## Fluxo de Implantação e CI/CD
Até o momento foram criados **2 repositórios** contendo código fonte e **3 repositórios** de infraestrutura como código (IaC). Todos os repositórios possuem pipelines de CI e CD utilizando GitHub Actions.

- [**iburguer-onboarding:**](https://github.com/FIAP-G04/iburguer-onboarding) Representa o código fonte das **2 lambdas functions** **SignIn** (Identificação do Cliente) e **SignUp** (Registro do Cliente)
- [**iburguer-api:**](https://github.com/FIAP-G04/iburguer-api) Representa a API do monolito que é publicado no Kubernetes.

## Infraestrutura na AWS usando Terraform
Optamos pela utilização da AWS com provisionamento da infraestrutura como código (IaC) através do Terraform utilizando um pipeline do GitHub Actions para executá-lo. Dividimos a criação do ambiente nos seguintes repositórios:

- [**iburguer-eks:**](https://github.com/FIAP-G04/iburguer-eks) Provisiona toda infraestrutura Kubernetes no serviço **Amazon Elastic Kubernetes Service**.
- [**iburguer-auth:**](https://github.com/FIAP-G04/iburguer-auth) Contém toda infraestrura para o processo de **SignIn** e **SignUp** como **AWS Lambdas**, **Amazon Cognito**, **Amazon API Gateway**.
- [**iburguer-rds:**](https://github.com/FIAP-G04/iburguer-rds) Provisiona o banco de dados **PostgreSQL** no **Amazon Relational Database Service**.
