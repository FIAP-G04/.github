# Domain Discovery 💡

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

## Visão Geral do Problema
<p align="center">
  <img width="100%" src="https://github.com/FIAP-G04/.github/blob/main/images/byte-burguer.png" alt="Byte Burguer">
</p>

A lanchonete de bairro Byte Burguer, que inicialmente se destacou pelo sucesso, agora enfrenta uma série de desafios operacionais devido à falta de automação e sistemas essenciais para o atendimento ao cliente e a gestão do negócio. 

Primeiramente, a lanchonete Byte Burguer enfrenta dificuldades significativas devido à falta de um sistema de gerenciamento de pedidos. A anotação manual de pedidos e sua comunicação à cozinha são propensas a erros e confusão. Isso resulta em atrasos na preparação e na entrega dos pedidos, bem como na possibilidade de pedidos serem perdidos ou mal interpretados. A insatisfação dos clientes devido a pedidos incorretos prejudica a reputação do estabelecimento e causa prejuízos financeiros.

A falta de um sistema de autoatendimento também impacta negativamente a lanchonete. A ausência dessa  opção torna o processo de pedido mais demorado, resultando em filas longas e clientes insatisfeitos devido aos tempos de espera prolongados. Além disso, a falta de automação na escolha de itens e no pagamento online de pedidos limita a flexibilidade e a comodidade para os clientes.

A inexistência de um sistema de controle de estoque é outra preocupação crítica. Sem um sistema automatizado para rastrear o consumo de ingredientes, a lanchonete corre o risco de desperdiçar alimentos devido a pedidos errados, causando prejuízos financeiros significativos. Além disso, a falta de controle de estoque pode levar a escassez de ingredientes e itens, afetando a qualidade e a oferta de produtos aos clientes.

A falta de um sistema de cadastramento de clientes impede que a lanchonete colete dados valiosos para o negócio. A  ausência  de informações sobre os hábitos de consumo dos clientes impede a criação de estratégias de marketing direcionadas e personalizadas, bem como a notificação de clientes sobre campanhas promocionais e ofertas exclusivas.

Outro desafio é a ausência de um cardápio digital acessível de qualquer lugar. A falta dessa facilidade impede que os clientes naveguem pelos itens do cardápio, façam escolhas e até mesmo pré-encomendem refeições antes de chegarem à lanchonete.

Por fim, a lanchonete enfrenta o de-safio de não possuir um sistema para coletar avaliações de clientes e reclama-ções. A ausência de um mecanismo para feedback do cliente dificulta a avaliação da satisfação do cliente e a resolução de problemas em tempo hábil.

Em resumo, a lanchonete está enfrentando uma série de desafios operacionais devido à falta de sistemas de automação e gestão. Para garantir o sucesso contínuo do negócio, é essencial investir em sistemas de gerenciamento de pedidos, sistemas de autoatendimento, sistemas de controle de estoque, sistemas de cadastramento de clientes e análise de dados, cardápio digital e sistemas de avaliação da experiência do cliente. Essas melhorias não apenas aumentarão a eficiência operacional, mas também proporcionarão uma experiência aprimorada para os clientes e oportunidades de crescimento para a lanchonete.

## Análise do Cenário Atual (AS-IS)
Atualmente, nós disponibilizamos aos nossos clientes um cardápio dividido em 4 seções: lanches, acompanhamentos, bebidas e sobremesas. Este cardápio é apresentado em formato físico ao cliente e inclui todos os detalhes relevantes sobre os produtos, como nome, descrição, preço e imagem. A gestão dessas informações é de responsabilidade do gerente da lanchonete que as revisa mensalmente através de um arquivo word. 

Quando o cliente já sabe o que deseja pedir, ele começa a fazer o seu pedido selecionando entre lanches, acompanhamentos, bebidas e sobremesas, sendo que cada categoria que compõe o pedido é opcional. 

Após a seleção dos itens, o atendente do caixa registra o pedido do cliente em um papel e lhe informa em voz alta um resumo do pedido e o valor total a ser pago. Após a confirmação, o cliente efetua o pagamento do pedido e aguarda a confirmação da transação. Uma vez que o pagamento é confirmado, o atendente do caixa entrega ao cliente um comprovante de pagamento e um código que representa o número do pedido, que será usado posteriormente para a retirada, quando o mesmo estiver pronto. 

Em seguida, o atendente do caixa adiciona o papel com o resumo do pedido à fila da cozinha. Cada pedido que entra na cozinha é colocado em uma fila de preparação. Na cozinha, cada categoria de produto - lanches, acompanhamentos, bebidas e sobremesas - é tratada por um profissional especializado, que, após a conclusão, entrega o produto pronto ao atendente de entrega. 

O atendente de entrega é responsável por montar o pedido que será entregue ao cliente e gerenciar a retirada de cada um dos pedidos. O pedido é organizado da mesma maneira: a bebida fica no centro, o lanche de um lado e os acompanhamentos e sobremesas com o logotipo da empresa voltado para o cliente. Isso mantém o peso equilibrado e facilita o manuseio.

Após a montagem do pedido, o atendente de entrega anuncia em voz alta o número do pedido que está pronto, permitindo que o cliente vá até o balcão e retire seu pedido. O cliente apresenta o código de retirada e recebe o seu pedido completo. Por sua vez, o atendente de entrega coloca o papel com o resumo do pedido em uma urna de pedidos entregues.

## Decomposição da Visão do Domain Expert
Nesta seção, através da aplicação da metodologia do Domain Storytelling, iremos ex-plorar os cenários cruciais e os atores centrais que desempenham papéis fundamentais nas narrativas compartilhadas pelo Domain Expert.

### Atores
Analisando os relatos do Domain Expert, 5 atores foram identificados na visão geral do cenário atual:

<p align="center">
  <img width="680" src="https://github.com/FIAP-G04/.github/assets/5951374/0f0a5bb4-735e-4ab6-b103-590f319eb15f" alt="Nosso Grupo">
</p>

| Atores | Descrição |
|--------|-----------|
| Cliente | Quem efetua um pedido na lanchonete com os itens desejados. |
| Atendente de Caixa | Encarregado de registrar o pedido do cliente, calcular o valor total e receber o pagamento correspondente. |
| Atendente de Cozinha | São especialistas na elaboração dos itens do pedido do cliente. Cada atendente de cozinha é designado a um grupo específico de preparação, como lanches, acompanhamentos, bebidas ou sobremesas. Sua responsabilidade inclui a preparação e disponibilização do item pronto ao atendente de entrega. |
| Atendente de Entrega | Responsável por montar os itens do pedido em uma bandeja e gerenciar as entregas aos clientes. Após a entrega do pedido, o atendente registra a retirada de cada pedido. |
| Gerente | Responsável por gerenciar os produtos apresentados no cardápio aos clientes. |

### Cenários
Avaliando a narrativa do **Domain Expert**, identificamos três cenários distintos que representam grande parcela do escopo do problema:

- O primeiro cenário diz respeito à etapa em que o cliente faz seu pedido.
- O segundo cenário aborda o momento em que o pedido é recebido na cozinha e posteriormente entregue ao cliente.
- Por fim, o terceiro cenário descreve o processo de gerenciamento das infor-mações do cardápio.

A seguir iremos ilustrar na abordagem **Domain Storytelling** de cada um dos cenários.

#### Realizar um Pedido
Antes de exibir a representação pictográfica da abordagem de **Domain Storytelling** para o cenário em que o cliente conclui com êxito um pedido em uma lanchonete, é necessário introduzir algumas premissas e observações referentes ao cenário em questão:

- **Premissas:**
  - O cliente já sabe quais produtos quer pedir;
  - Todos os produtos escolhidos pelo cliente estão disponíveis para venda;
  - A transação de pagamento foi bem sucedida;
  - Não há desistência do pedido, pelo cliente, em nenhum momento;

- **Observações:**
  - O lanche, acompanhamento, bebida e sobremesa são opcionais no combo;
 
<p align="center">
  <img style="width:98%" src="https://github.com/FIAP-G04/.github/blob/main/images/realizar-pedido-as-is.png" alt="Realizar um Pedido">
</p>

#### Preparação e Retirada do Pedido
 Esse contexto abrange todo o processo, desde o momento em que o pedido é re-cebido na cozinha, passando pela sua preparação e chegando até a retirada pelo cliente. Abaixo, apresentam-se algumas premissas e observações relacionadas a esse cenário:

- **Premissas:**
  - O atendente da cozinha só disponibiliza um item do pedido ao atendente de entrega quando está pronto;
  - Cada pedido da fila é atendido de maneira sequencial;
  - O atendente de entrega só avisa o cliente quando todos os itens do pedido estão prontos;
  - O cliente retirará o pedido quando for avisado;

<p align="center">
  <img width="95%" src="https://github.com/FIAP-G04/.github/blob/main/images/preparacao-e-retirada-do-pedido-as-is.png" alt="Preparação e Retirada do Pedido">
</p>

#### Revisar Informações do Cardápio
Esse cenário se desenha devido à necessidade de atualização dos produtos disponíveis e das informações apresentadas aos clientes, incluindo elementos como nome, descrição, preço e imagens. A seguir, ressaltamos algumas premissas e considerações relacionadas a essa situação:

- **Premissas:**
  - O cardápio digital é um simples documento editável que possibilita o gerente alterar as informações dos produtos.
  - O cardápio é disponibilizado através de cópias impressas acessíveis aos clientes que estão dentro da lanchonete.

<p align="center">
  <img width="95%" src="https://github.com/FIAP-G04/.github/blob/main/images/revisar-informacoes-do-cardapio-as-is.png" alt="Revisar Informações do Cardápio">
</p>


## Mapeamento de Domínios e Subdomínios
Um domínio se refere a uma esfera de conhecimento ou atividade no mundo real que abrange um espaço de problema específico. Esse domínio possui sua própria linguagem, conceitos, regras e práticas que o tornam únicos. No contexto do Tech Challenge o nosso domínio é uma Lanchonete Fast Food.

Por outro lado, um subdomínio é uma subdivisão ou área menor de conhecimento ou atividade dentro de um domínio mais amplo. Os subdomínios representam uma granularização desse espaço de problema e podem se concentrar em tópicos ou aspectos específicos dentro do domínio principal. Isso ajuda a organizar e categorizar o conhecimento de forma mais detalhada e específica. Desta forma, entendemos que o Domínio da Lanchonete Fast Food possui os seguintes subdomínios:

<p align="center">
  <img width="90%" src="https://github.com/FIAP-G04/.github/blob/main/images/subdominios-as-is.png" alt="Subdomínios AS-IS">
</p>

### Core Domains
Os domínios principais **(Core Domains)** são aqueles que estão no cerne do negócio e geralmente são os mais complexos e específicos, dos quais temos **Gestão de Cardápio** e **Gerenciamento de Pedidos**.

- **Gestão de Cardápio:** Responsável por definir os produtos oferecidos na lanchonete fast food, além de seus preços, ingredientes, categorias, promoções e variações. Faz parte do Core Domain, visto que é de extrema importância para o funcionamento eficiente da lanchonete.

- **Gerenciamento de Pedidos:** Este subdomínio lida com a criação, preparação, acompanhamento, montagem e retirada dos pedidos dos clientes. Este é um **Core Domain**, pois lida diretamente com a funcionalidade central do negócio, ou seja, a criação e gestão de pedidos dos clientes. Devido a sua complexidade, poderíamos subdivídi-lo em 3 subdomínios: 

  - **Solicitação do Pedido:** Compreende o conjunto de etapas envolvidas na criação de um pedido, no qual o cliente faz sua solicitação ao atendente de caixa.
    
  - **Preparação do Pedido:** É todo o processo de preparação dos itens do pedido pelos atendentes de cozinha.
    
  - **Montagem & Retirada do Pedido:** Refere-se ao procedimento que inclui a mon-tagem dos itens do pedido por parte do atendente de entrega e a subsequente retirada do pedido pelo cliente.

### Supporting Domains

Os domínios de suporte **(Supporting Domains)** são aqueles que oferecem suporte direto às operações principais do negócio, mas não são a parte central do mesmo. Eles ajudam a impulsionar as vendas, a atrair clientes ou simplesmente garantir o funcionamento dos Core Domains. Considerando o contexto da lanchonete fast food, temos 2 subdomínios: **Gestão de Estoque** e **Marketing & Promoções**.

- **Gestão de Estoque:** Gerencia o estoque de ingredientes, as quantidades disponíveis e as encomendas de ingredientes. Embora seja um domínio importante, ele está mais voltado para dar suporte às operações principais, como garantir que os ingredientes estejam disponíveis para os pedidos. Portanto, pode ser considerado um **Supporting Domai**n. Se fossemos detalhar esse subdomínio, provavelmente teríamos mais atores envolvidos no contexto. Além disso poderíamos subdividir esse subdomínio em **3** outros **subdomínios**:

  - **Gestão de Fornecedores:** Faz referência aos mais diversos fornecedores de ingredientes utilizados pela lanchonete.

  - **Controle de Estoque:** É o processo de entrada e saída de ingredientes do estoque, controlando a sua disponibilidade e quantidade existente.

  - **Compra:** Refere-se ao processo de compra de ingredientes junto aos fornecedores.

- **Marketing & Promoções:** Este subdomínio gerencia campanhas de marketing, promoções, cupons e programas de fidelidade. Ele é responsável por um conjunto ações que visam a atração de clientes e a maximização das vendas.

### Generic Domains

Os domínios genéricos **(Generic Domains)** são geralmente aqueles que não são exclusivos para o negócio e podem ser compartilhados com outros domínios de negócio. No contexto da lanchonete fast food, podemos considerar os possíveis subdomínios: **Atendimento ao Cliente**, **Pagamento**, **Financeiro** e **Recursos Humanos**.

- **Atendimento ao Cliente:** Responsável pela gestão de reclamações, feedback do cliente e a satisfação do cliente, que por sua vez, são considerados aspectos comuns em todos os tipos de negócio.

- **Pagamento:** Responsável pelos processos de pagamento, faturamento e transações financeiras. Embora seja de extrema importância para a lanchonete fast food, é uma funcionalidade comum a muitos tipos de negócios.

- **Financeiro:** A gestão financeira tem papel fundamental para a saúde e sustentabilidade de qualquer negócio, e a lanchonete não é exceção. Através deste subdomínio, a empresa pode acompanhar seus custos, margens de lucro, impostos e outras informações financeiras críticas para tomada de decisão.

- **Recursos Humanos:** Este subdomínio desempenha um papel fundamental na gestão da equipe que trabalha na lanchonete, assegurando que haja pessoal adequado para todas as tarefas diárias. Sua responsabilidade principal consiste em garantir que a lanchonete esteja em conformidade com todas as regulamentações trabalhistas, proporcionando um ambiente de trabalho seguro e produtivo para seus funcionários. Isso é alcançado por meio do recrutamento e capacitação de profissionais apropriados.


## Análise de Subdomínios no Cenário TO-BE
Na primeira parte deste documento abordamos o cenário AS-IS e os problemas existentes, sendo mapeadas as seguintes necessidades de investimento:

- Gestão de pedidos 
- Autoatendimento
- Controle de estoque
- Gerenciamento de clientes 
- Cardápio digital 
- Feedback & Reclamações do cliente. 

Diante das questões mencionadas, observamos que a necessidade de gestão de pedidos pode ser atendida por meio do subdomínio identificado no cenário atual (AS-IS) conhecido como Gerenciamento de Pedidos. No entanto, com o objetivo de satisfazer a demanda por autoatendimento e simplificar o subdomínio de **Gerenciamento de Pedidos**, decidimos dividir este em dois novos subdomínios: **Carrinho de Compra** e **Acompanhamento de Pedidos**.

O **Carrinho de Compra** diz respeito ao processo em que os clientes solicitam pedidos de forma autônoma em uma lanchonete. Por sua vez, o **Acompanhamento de Pedidos** abrange todas as etapas do ciclo de vida de um pedido, incluindo recebimento, preparação e retirada por parte do cliente.

No que diz respeito aos problemas de controle de estoque, cardápio digital e feedback e reclamações dos clientes, já identificamos subdomínios correspondentes no cenário atual (AS-IS), que são **Gestão de Estoque**, **Gestão de Cardápio** e **Atendimento ao Cliente**, respectivamente.

Além disso, é necessário criar um novo subdomínio denominado **Gerenciamento de Clientes**, uma vez que, no cenário atual (AS-IS), não existe um meio de coletar dados dos clientes nem de acompanhar seus históricos de compras e relacionamento com a lanchonete.

Desta forma, temos os seguintes subdomínios definidos no cenário TO-BE:

<p align="center">
  <img width="90%" src="https://github.com/FIAP-G04/.github/blob/main/images/subdominios-to-be.png" alt="Subdomínios TO-BE">
</p>

## Análise Estratégica dos Subdomínios
Dado o cenário TO-BE dos novos subdomínios e as necessidades mapeadas no contexto do problema, podemos analisar de forma estratégica qual a melhor abordagem para solucionar cada uma das necessidades. Essas estratégias vão desde o desenvolvimento de soluções própria e personalizadas até a contratação de serviços ou aquisição de softwares de terceiros.

Para esta análise, iremos abordar apenas os subdomínios envolvidos nas necessidades mencionadas no contexto do problema. Iremos considerar 2 aspectos: **Complexidade do Modelo** e **Diferenciação para o negócio**.

<p align="center">
  <img width="680" src="https://github.com/FIAP-G04/.github/blob/main/images/core-domain-charts.png" alt="Core Domain Charts">
</p>

A visão acima, do **Core Domain Chart**, nos ajuda a visualizar a importância estratégica de cada subdomínio tem no modelo de negócios e permite identificarmos onde o **ROI** esperado é maior e merecem o maior foco. Desta forma, podemos concluir que:

O subdomínio **Pagamento** é caracterizado por uma complexidade significativa, mas que oferece um valor de diferenciação relativamente baixo para o negócio, o que nos leva a concluir que a utilização de um serviço de terceiros é a opção mais recomendada, como por exemplo: **Mercado Pago**. 

O subdomínio de **Atendimento ao Cliente** está situado no quadrante de baixa complexidade, mas também apresenta baixa diferenciação de valor para o negócio. Temas como feedback, reclamações e satisfação do cliente são considerados elementos comuns em todos os tipos de negócios, o que nos leva a sugerir a adoção de soluções prontas disponíveis no mercado.

A **Gestão de Estoque**, por sua vez, apresenta uma complexidade de nível intermediário, uma vez que é desafiador medir com precisão a alocação de ingredientes em cada um dos pedidos, tornando o desenvolvimento dessa solução um pouco mais complicada. Entretanto existe um valor razoável de diferenciação ao negócio, visto que a existência de um sistema desses possibilitaria a redução de desperdício financeiro para o Byte Burguer. Desta forma, poderíamos implementar uma solução customizada para atender esta necessidade, porém consideramos que a mesma teria menos prioridade de investimento que as demais.

Por outro lado, o subdomínio **Gerenciamento de Clientes** ofereceria benefícios substanciais para o negócio, uma vez que o conhecimento aprofundado dos clientes permitiria a criação de campanhas personalizadas e o fornecimento de atendimento personalizado. A coleta de dados de consumo dos clientes poderia gerar inúmeros insights valiosos para o negócio. Dado seu caráter de baixa complexidade e alto potencial de ganhos, é altamente recomendável investir em uma solução para o gerenciamento de clientes.

Já os subdomínios **Gestão de Cardápio**, **Carrinho de Compras** e **Acompanhamento de Pedidos** possuem complexidades diferentes, mas todos possuem alto valor de diferenciação para o negócio. Tal fato nos leva a recomendar investimento prioritário em soluções customizadas que atendam essas necessidades.

## Visão Geral da Solução
Nesta seção, apresentaremos uma visão geral da solução proposta para atender às necessidades descritas na primeira parte deste documento. Aqui, exploraremos em detalhes cada um dos componentes que constituem a plataforma **iBurguer**. 

### Módulo de Autoatendimento
Este módulo permite que os clientes efetuem seus pedidos, personalizem seus combos e efetuem o pagamento sem a necessidade de interação direta com um atendente de caixa. Inicialmente, um totem de autoatendimento será disponibilizado dentro da lanchonete para que os clientes possam interagir diretamente com a plataforma **iBurguer**. No entanto, futuramente, também será lançado um aplicativo móvel e uma página web que permitirá aos clientes fazerem seus pedidos diretamente por meio de seus smartphones. Este módulo oferece as seguintes funcionalidades:

- Listagem dos itens do cardápio;
- Pesquisar itens do cardápio por categoria.
- Visualizar informações detalhadas dos itens no cardápio, incluindo nome, descrição, preço e fotos.
- Adicionar itens do cardápio ao carrinho de compras, com a opção de selecionar a quantidade desejada.
- Pré-visualização do resumo do pedido antes de confirmar a compra.
- Realização do pagamento por meio de um QRCode.
- Emissão de um código para retirada do pedido.
  
 A seguir, ilustraremos através da abordagem **Domain Storytelling**, uma demonstração do processo de realização de um pedido. Para este cenário, utilizaremos as seguintes premissas e observações para detalhar o cenário:

- **Premissas:**
  - Nenhum problema ocorreu na geração do QRCode com o Mercado Pago;
  - A transação de pagamento foi bem sucedida;
  - Não há desistência do pedido pelo cliente em nenhum momento;

- **Observações:**
  - O lanche, acompanhamento, bebida e sobremesa são opcionais no combo;
  - Se o cliente optar por não se identificar, ele tem a opção de pular a etapa de identificação e acessar o sistema como anônimo.
  - Apenas pessoas com o perfil de gerente podem acessar essa funcionalidade

<p align="center">
  <img width="95%" src="https://github.com/FIAP-G04/.github/blob/main/images/realizar-pedido-to-be.png" alt="Realizar um Pedido TO-BE">
</p>

### Módulo de Acompanhamento de Pedido
Este módulo é encarregado de gerenciar o ciclo de vida do pedido, desde o momento em que é recebido após a compra, passando pela etapa de preparação, até a conclusão e entrega do pedido ao cliente.

O processo começa logo após a confirmação do pagamento, que, como resultado, registra o pedido como **"Recebido"** na fila da cozinha. Quando um membro da equipe de cozinha começa a preparar o pedido, o status é atualizado para **"Em Preparação"** pelo atendente de cozinha. À medida que cada item do pedido é preparado, o atendente de entrega monta o pedido na bandeja e atualiza o status para **"Pronto"** quando todos os itens do pedido estão concluídos. Como resultado, o sistema envia uma notificação para os painéis de acompanhamento do status do pedido, informando ao cliente que o pedido está pronto para ser retirado.

Os painéis de acompanhamento do pedido são monitores que exibem o status de cada pedido e uma estimativa de tempo para a conclusão do pedido. Essa estimativa é calculada com base no tempo médio necessário para preparar cada produto e também na fila de pedidos na cozinha.

Quando o pedido está pronto, o cliente se dirige ao balcão e apresenta o código de retirada do pedido. O atendente de entrega então entrega o pedido ao cliente e atualiza o status do pedido para **"Finalizado"**.

A seguir, ilustraremos o processo de preparação e retirada de um pedido através da abordagem **Domain Storytelling**. Para este cenário, utilizaremos as seguintes premissas e observações para detalhar o cenário:

- **Premissas:**
  - O atendente da cozinha só disponibiliza o item do pedido ao atendente de entrega quando está pronto;
  - Cada pedido da fila é atendido de maneira sequencial;
  - O atendente de entrega só avisa o cliente quando todos os itens do pedido estão prontos;
  - O cliente retirará o pedido quando for avisado;
 
<p align="center">
  <img width="95%" src="https://github.com/FIAP-G04/.github/blob/main/images/preparacao-e-retirada-do-pedido-to-be.png" alt="Acompanhamento de Pedidos TO-BE">
</p>


### Módulo de Gestão de Cardápio
Visando atender a necessidade de facilitar a gestão das informações do catálogo e torná-lo acessível ao cliente de qualquer lugar, propomos a criação da funcionalidade de gestão de cardápio dentro da plataforma **iBurguer**. Segue abaixo o mapeamento do **Domain Storytelling** referente a funcionalidade.

- **Premissas:**
  - O gerente já precisa estar logado no sistema.
  - O cliente consegue visualizar o cardápio que fica pública para qualquer pessoa visualizar.

- **Observações:**
  - A ação de revisar engloba o escopo de inclusão, alteração, inativação e ativação de um produto do cardápio.
  - Apenas pessoas com o perfil de gerente podem acessar essa funcionalidade

<p align="center">
  <img width="65%" src="https://github.com/FIAP-G04/.github/blob/main/images/revisar-informacoes-do-cardapio-to-be.png" alt="Gestão de Cardápio TO-BE">
</p>

## Dicionário de Linguagem Ubíqua
Segue abaixo um conjunto de palavras que compõem o dicionário de **linguagem ubíqua** ao contexto da lanchonete fast food **Byte Burguer**:

| Termos | Definição |
|--------|-----------|
| Totem de Autoatendimento | Uma estação eletrônica na lanchonete onde os clientes podem fazer seus pedidos e efetuar o pagamento sem a necessidade de interagir com um atendente. |
| Cardápio Digital | Uma tela sensível ao toque no totem de autoatendimento que exibe as opções de menu e permite aos clientes selecionar os itens desejados. |
| Lanche Principal | O lanche principal é o prato principal da refeição como sanduíches e hambúrgueres. Podem haver opções de carne, frango e vegetarianas ou veganas, como hambúrgueres de legumes.  |
| Acompanhamentos | Os acompanhamentos são alimentos que complementam o lanche principal. Os acompanhamentos típicos incluem batatas fritas, onion rings, nuggets de frango, saladas entre outros. Os clientes podem escolher entre diferentes acompanhamentos para criar uma refeição personalizada. |
| Bebidas | As bebidas são líquidos que acompanham a refeição como: refrigerantes, água, chá gelado e sucos. |
| Sobremesa | As sobremesas são itens doces que os clientes podem adicionar à sua refeição ou desfrutar após o lanche principal. Disponibilizamos Sobremesas como: sorvetes, tortas, cookies, brownies e milkshakes. |
| Combo | Uma refeição que inclui lanche principal, acompanhamento, bebida e sobremesa não sendo obrigatório nenhum deles. |
| QR Code | Um código de barras bidimensional que pode ser escaneado com um smartphone para realizar o pagamento do pedido. |
| Código de Retirada | É um código de 6 dígitos alfanuméricos que deve ser apresentado para retirar o pedido. |
| Código do Pedido | É um código sequencial utilizado pelos clientes para acompanhamento do status do pedido. |
| Carrinho de Compras | O carrinho de compras é uma representação virtual que contém os itens selecionados pelo cliente para compra. Ele é usado para revisar e confirmar os itens antes de prosseguir para o pagamento |
| Checkout | O checkout é a etapa final do processo de compra, onde o cliente confirma os itens em seu carrinho de compras, fornece informações de pagamento e finaliza o pedido. É o momento em que a transação é concluída e o cliente se prepara para receber os produtos ou refeições. |
| Pedido | Um pedido refere-se à seleção de itens feita pelo cliente no cardápio da  lanchonete. Isso pode incluir lanches principais, bebidas, acompanhamentos e sobremesas.  |
| Pagamento | O pagamento é a ação de quitar o valor total do pedido. Atualmente os clientes podem pagar com QR Code. |
| Pedido Aguardando Pagamento | Esta é a fase inicial após a seleção dos itens do cardápio e a adição ao carrinho de compras. O pedido aguardando pagamento indica que o cliente ainda não efetuou o pagamento, e a transação não foi concluída. Os itens ainda não foram preparados. |
| Pedido Confirmado | Após o pagamento bem sucedido, o pedido é confirmado. Isso significa que a lanchonete recebeu o pagamento e encaminhou para a fila de atendimento da cozinha. |
| Pedido em Preparação | Nesta fase, a lanchonete está ocupada preparando os itens do pedido. Os alimentos estão sendo cozidos, montados e embalados para atender ao pedido do cliente. |
| Pedido Pronto | Quando os itens do pedido estão todos prontos e estão disponíveis para serem retirados. |
| Pedido Retirado | Após a notificação de que o pedido está pronto, o cliente pode retirar os itens do pedido. Isso geralmente envolve pegar a comida no balcão de retirada ou na área de retirada designada no estabelecimento. |
| Cliente | Quem efetua um pedido na lanchonete com os itens desejados. |
| Atendente de Caixa | Encarregado de registrar o pedido do cliente, calcular o valor total e receber o pagamento correspondente. |
| Atendente da Cozinha | São especialistas na elaboração dos itens do pedido do cliente. Cada atendente de cozinha é designado a um grupo específico de preparação, como lanches, acompanhamentos, bebidas ou sobremesas. Sua responsabilidade inclui a preparação e disponibilização do item pronto ao atendente de entrega. |
| Atendente de Entrega | Responsável por montar os itens do pedido em uma bandeja e gerenciar as entregas aos clientes. Após a entrega do pedido, o atendente registra a retirada de cada pedido. |
| Gerente | Responsável por gerenciar os produtos apresentados no cardápio aos clientes. |
| Mercado Pago | É uma plataforma de serviços financeiros e pagamentos online desenvolvida pelo Mercado Livre. |

## Event Storming
