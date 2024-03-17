# iBurguer

## O que é iBurguer?
Em suma, a plataforma **iBurguer** é uma solução abrangente que aborda os desafios operacionais da lanchonete **Byte Burguer**, oferecendo uma solução integrada de **gerenciamento de pedidos**, **autoatendimento**, **gestão de clientes**, **cardápio digital** entre outras coisas. Essas funcionalidades não apenas melhoram a eficiência operacional, mas também proporcionam uma experiência aprimorada para os clientes e oportunidades de crescimento para o negócio.

<p align="center">
  <img width="100%" src="https://github.com/FIAP-G04/.github/blob/main/images/iburguer.png" alt="iBurguer">
</p>

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

```POST /api/customers``` <br>Registra um cliente;

```GET /api/customers/{cpf}``` <br>Autentica o cliente a partir do CPF;

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
