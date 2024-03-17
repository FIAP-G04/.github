# Domain Discovery 💡
Está seção ....

## Visão geral do problema
A lanchonete de bairro Byte Burguer, que inicialmente se destacou pelo sucesso, agora enfrenta uma série de desafios operacionais devido à falta de automação e sistemas essenciais para o atendimento ao cliente e a gestão do negócio. 

Primeiramente, a lanchonete Byte Burguer enfrenta dificuldades significativas devido à falta de um sistema de gerenciamento de pedidos. A anotação manual de pedidos e sua comunicação à cozinha são propensas a erros e confusão. Isso resulta em atrasos na preparação e na entrega dos pedidos, bem como na possibilidade de pedidos serem perdidos ou mal interpretados. A insatisfação dos clientes devido a pedidos incorretos prejudica a reputação do estabelecimento e causa prejuízos financeiros.

A falta de um sistema de autoatendimento também impacta negativamente a lanchonete. A ausência dessa  opção torna o processo de pedido mais demorado, resultando em filas longas e clientes insatisfeitos devido aos tempos de espera prolongados. Além disso, a falta de automação na escolha de itens e no pagamento online de pedidos limita a flexibilidade e a comodidade para os clientes.

A inexistência de um sistema de controle de estoque é outra preocupação crítica. Sem um sistema automatizado para rastrear o consumo de ingredientes, a lanchonete corre o risco de desperdiçar alimentos devido a pedidos errados, causando prejuízos financeiros significativos. Além disso, a falta de controle de estoque pode levar a escassez de ingredientes e itens, afetando a qualidade e a oferta de produtos aos clientes.

A falta de um sistema de cadastramento de clientes impede que a lanchonete colete dados valiosos para o negócio. A  ausência  de informações sobre os hábitos de consumo dos clientes impede a criação de estratégias de marketing direcionadas e personalizadas, bem como a notificação de clientes sobre campanhas promocionais e ofertas exclusivas.

Outro desafio é a ausência de um cardápio digital acessível de qualquer lugar. A falta dessa facilidade impede que os clientes naveguem pelos itens do cardápio, façam escolhas e até mesmo pré-encomendem refeições antes de chegarem à lanchonete.

Por fim, a lanchonete enfrenta o de-safio de não possuir um sistema para coletar avaliações de clientes e reclama-ções. A ausência de um mecanismo para feedback do cliente dificulta a avaliação da satisfação do cliente e a resolução de problemas em tempo hábil.

Em resumo, a lanchonete está enfrentando uma série de desafios operacionais devido à falta de sistemas de automação e gestão. Para garantir o sucesso contínuo do negócio, é essencial investir em sistemas de gerenciamento de pedidos, sistemas de autoatendimento, sistemas de controle de estoque, sistemas de cadastramento de clientes e análise de dados, cardápio digital e sistemas de avaliação da experiência do cliente. Essas melhorias não apenas aumentarão a eficiência operacional, mas também proporcionarão uma experiência aprimorada para os clientes e oportunidades de crescimento para a lanchonete.

## Análise do cenário atual (AS-IS)
Atualmente, nós disponibilizamos aos nossos clientes um cardápio dividido em 4 seções: lanches, acompanhamentos, bebidas e sobremesas. Este cardápio é apresentado em formato físico ao cliente e inclui todos os detalhes relevantes sobre os produtos, como nome, descrição, preço e imagem. A gestão dessas informações é de responsabilidade do gerente da lanchonete que as revisa mensalmente através de um arquivo word. 

Quando o cliente já sabe o que deseja pedir, ele começa a fazer o seu pedido selecionando entre lanches, acompanhamentos, bebidas e sobremesas, sendo que cada categoria que compõe o pedido é opcional. 

Após a seleção dos itens, o atendente do caixa registra o pedido do cliente em um papel e lhe informa em voz alta um resumo do pedido e o valor total a ser pago. Após a confirmação, o cliente efetua o pagamento do pedido e aguarda a confirmação da transação. Uma vez que o pagamento é confirmado, o atendente do caixa entrega ao cliente um comprovante de pagamento e um código que representa o número do pedido, que será usado posteriormente para a retirada, quando o mesmo estiver pronto. 

Em seguida, o atendente do caixa adiciona o papel com o resumo do pedido à fila da cozinha. Cada pedido que entra na cozinha é colocado em uma fila de preparação. Na cozinha, cada categoria de produto - lanches, acompanhamentos, bebidas e sobremesas - é tratada por um profissional especializado, que, após a conclusão, entrega o produto pronto ao atendente de entrega. 

O atendente de entrega é responsável por montar o pedido que será entregue ao cliente e gerenciar a retirada de cada um dos pedidos. O pedido é organizado da mesma maneira: a bebida fica no centro, o lanche de um lado e os acompanhamentos e sobremesas com o logotipo da empresa voltado para o cliente. Isso mantém o peso equilibrado e facilita o manuseio.

Após a montagem do pedido, o atendente de entrega anuncia em voz alta o número do pedido que está pronto, permitindo que o cliente vá até o balcão e retire seu pedido. O cliente apresenta o código de retirada e recebe o seu pedido completo. Por sua vez, o atendente de entrega coloca o papel com o resumo do pedido em uma urna de pedidos entregues.

## Decomposição da visão do Domain Expert
Nesta seção, através da aplicação da metodologia do Domain Storytelling, iremos ex-plorar os cenários cruciais e os atores centrais que desempenham papéis fundamentais nas narrativas compartilhadas pelo Domain Expert.

### Atores
Analisando os relatos do Domain Expert, 5 atores foram identificados na visão geral do cenário atual:

<p align="center">
  <img width="680" src="https://github.com/FIAP-G04/.github/assets/5951374/0f0a5bb4-735e-4ab6-b103-590f319eb15f" alt="Nosso Grupo">
</p>

### Cenários
Avaliando a narrativa do **Domain Expert**, identificamos três cenários distintos que representam grande parcela do escopo do problema:

- O primeiro cenário diz respeito à etapa em que o cliente faz seu pedido.
- O segundo cenário aborda o momento em que o pedido é recebido na cozinha e posteriormente entregue ao cliente.
- Por fim, o terceiro cenário descreve o processo de gerenciamento das infor-mações do cardápio.

A seguir iremos ilustrar na abordagem **Domain Storytelling** de cada um dos cenários.

#### Realizar um Pedido
Antes de exibir a representação pictográfica da abordagem de **Domain Storytelling** para o cenário em que o cliente conclui com êxito um pedido em uma lanchonete, é necessário introduzir algumas premissas e observações referentes ao cenário em questão:

- Premissas:
  - O cliente já sabe quais produtos quer pedir;
  - Todos os produtos escolhidos pelo cliente estão disponíveis para venda;
  - A transação de pagamento foi bem sucedida;
  - Não há desistência do pedido, pelo cliente, em nenhum momento;

- Observações:
  - O lanche, acompanhamento, bebida e sobremesa são opcionais no combo;
 
<p align="center">
  <img style="width:98%" src="xxx.png" alt="Realizar um Pedido">
</p>

#### Preparação e Retirada do Pedido
 Esse contexto abrange todo o processo, desde o momento em que o pedido é re-cebido na cozinha, passando pela sua preparação e chegando até a retirada pelo cliente. Abaixo, apresentam-se algumas premissas e observações relacionadas a esse cenário:

- Premissas:
  - O atendente da cozinha só disponibiliza um item do pedido ao atendente de entrega quando está pronto;
  - Cada pedido da fila é atendido de maneira sequencial;
  - O atendente de entrega só avisa o cliente quando todos os itens do pedido estão prontos;
  - O cliente retirará o pedido quando for avisado;

<p align="center">
  <img style="width:98%" src="xxx.png" alt="Preparação e Retirada do Pedido">
</p>

## Mapeamento de Domínios e Subdomínios


## Análise de Subdomínios no cenário TO-BE


## Análise estratégica dos Subdomínios


## Visão geral da solução


## Dicionário de linguagem ubíqua


## Event Storming
