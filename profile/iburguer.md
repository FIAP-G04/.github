# iBurguer
- [O que é iBurguer?](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#o-que-%C3%A9-ibuguer)
- [Funcionalidades](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#funcionalidades)
  - [Gestão de Cardápio](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#gest%C3%A3o-de-card%C3%A1pio)
  - [Gestão de Clientes](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#gest%C3%A3o-de-clientes)
  - [Carrinho de Compras](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#carrinho-de-compras)
  - [Pagamento](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#pagamento)
  - [Gestão de Pedidos](https://github.com/FIAP-G04/.github/blob/main/profile/iburguer.md#pedidos)
- [Visão Geral da Arquitetura](#)
  - [Diagrama de Contexto](#)
  - [Diagrama de Container](#)
- [Estrutura de Persistência de Dados](#)
- [Arquitetura de Aplicação](#)
- [Tecnologias Utilizadas](#)
- [Considerações de Escalabilidade e Desempenho](#)
- [Fluxo de Implantação e CI/CD](#)
- [Infraestrutura na AWS usando Terraform](#)
  
## O que é iBurguer?
Em suma, a plataforma **iBurguer** é uma solução abrangente que aborda os desafios operacionais da lanchonete **Byte Burguer**, oferecendo uma solução integrada de **gerenciamento de pedidos**, **autoatendimento**, **gestão de clientes**, **cardápio digital** entre outras coisas. Essas funcionalidades não apenas melhoram a eficiência operacional, mas também proporcionam uma experiência aprimorada para os clientes e oportunidades de crescimento para o negócio.

## Funcionalidades
Seguem abaixo a lista de funcionalidades expostas na API:

### Gestão de Cardápio
O primeiro passo para a execução da API é o preenchimento do cardápio com itens que podem ser adicionados ao pedido. 

```POST /api/menu/products``` <br>Inclui um item no cardápio;

```PUT /api/menu/products``` <br>Atualiza um item do cardápio;

```DELETE /api/menu/products``` <br>Remove um item do cardápio;

```PATCH /api/menu/products/enabled``` <br>Habilita um item do cardápio;

```PATCH /api/menu/products/disabled``` <br>Desabilita um item do cardápio;

```GET /api/menu/products/{category}``` <br>Obtem todos os itens do cardápio a partir de uma determinada categoria;

### Gestão de Clientes

O próximo passo é o registro dos clientes que farão os pedidos na lanchonete. Para esse fim são disponibilizados os seguintes endpoints:

```POST /api/customers/signup``` <br>Registra um cliente;

```POST /api/customers/signin``` <br>Autentica o cliente a partir do CPF;

### Carrinho de Compras

Havendo um cardápio definido com itens e um cliente cadastrado buscando pelos mesmos, é necessário que um carrinho seja criado para o cliente. Isso pode ser feito através do endpoint:

```POST /api/carts``` <br>Cria carrinho a partir do identificador do cliente cadastrado;

Em seguida, os itens do carrinho podem ser gerenciados através dos seguintes endpoints:

```POST /api/carts/{shoppingCartId}/item``` <br>Adiciona um item do menu ao carrinho de compras através de seu ID;

```PATCH /api/carts/{shoppingCartId}/item/{cartItemId}/increment``` <br>Incrementa a quantidade de um determinado item do carrinho através de seu ID;

```PATCH /api/carts/{shoppingCartId}/item/{cartItemId}/decrement``` <br>Decrementa a quantidade de um determinado item do carrinho através de seu ID;

```DELETE /api/carts/{shoppingCartId}/item/{cartItemId}``` <br>Remove um determinado item do carrinho através de seu ID;

```PATCH /api/carts/{shoppingCartId}/clear``` <br>Limpa o carrinho de compras;

### Pagamento

Após o carrinho de compras possuir todos os itens que o cliente deseja pedir, é necessário prosseguir para o pagamento:

```POST /api/checkout/cart/{shoppingCartId}``` <br>Cria um pagamento para um carrinho de compras existente;

Após a criação de um pagamento, o gerenciamento de seu *status* pode ser feito pelos seguintes endpoints:

```GET /api/checkout/{paymentId}/status``` <br>Retorna o *status* atual do pagamento;

```PUT /api/checkout/{paymentId}/confirm``` <br>Webhook que confirma o pagamento;

```PUT /api/checkout/{paymentId}/refuse``` <br>Webhook que recusa o pagamento;

### Pedidos

Após a criação de um pagamento, o pedido referente ao mesmo é criado. O seguinte endpoint pode ser utilizado para verificar todos os pedidos:

```GET /api/orders``` <br>Retorna os pedidos em uma lista paginada;

Após a confirmação do pagamento, o mesmo é enviado para a fila de pedidos. A seguir estão os endpoints utilizados para gerenciá-lo até sua finalização:

```GET /api/orders/queue``` <br>Retorna a fila de pedidos, com os pedidos em *status* Pronto, Em Preparação e Finalizado;

```PATCH /api/orders/{orderId}/start``` <br>Confirma o pedido, passando o mesmo para o *status* Em Preparação. 

```PATCH /api/orders/{orderId}/complete``` <br>Indica que o pedido foi preparado pela cozinha, passando o mesmo para o *status* Pronto;

```PATCH /api/orders/{orderId}/deliver``` <br>Indica que o pedido foi recebido pelo cliente, passando o mesmo para o *status* Finalizado;

```PATCH /api/orders/{orderId}/cancel``` <br>Cancela um pedido;

## Visão Geral da Arquitetura
Nesta seção utilizaremos o diagrama C4 para representar algumas visões de arquitetura da plataforma **iBurguer**.

### Diagrama de Contexto
Nesta perspectiva, o diagrama de contexto mostra o **iBurguer** e os sistemas externos com os quais ele interage, como o **Mercado Pago**. Isso ajuda a entender o ambiente geral em que o sistema está inserido e os limites do sistema.

<p align="center">
  <img width="85%" src="https://github.com/FIAP-G04/.github/blob/main/images/diagrama-de-contexto.png?raw=true" alt="Diagrama de Contexto">
</p>

### Diagrama de Container
Aqui, a plataforma iBurguer é dividida em contêineres, que podem ser aplicativos, serviços da web, bancos de dados, etc. Cada contêiner é representado como uma caixa e mostra as relações de dependência entre eles.

<p align="center">
  <img width="85%" src="https://github.com/FIAP-G04/.github/blob/main/images/diagrama-de-container.png?raw=true" alt="Diagrama de Container">
</p>

## Estrutura de Persistência de Dados

## Arquitetura de Aplicação

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
- [Terraform](https://www.terraform.io/)
- [Github Actions](https://github.com/features/actions)
- [K6](https://k6.io/)

## Considerações de Escalabilidade e Desempenho

## Fluxo de Implantação e CI/CD

## Infraestrutura na AWS usando Terraform
