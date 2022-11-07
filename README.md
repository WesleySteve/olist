# Olist

## Objetivo
- O objetivo deste projeto é apresentar as etapas do processo completo de ETL (Extract Transform Load) ou Extração Transformação e Carga dos dados, com o foco em respoder perguntas de negócio.

## Etapas do projeto
- 1  [x] Problema do negócio
- 2  [x] Perguntas de negócio
- 3  [x] Coleta de dados
- 4  [x] Modelo de dados transacional
- 5  [x] Conhecendo os dados
- 6  [x] Modelagem do data warehouse
- 7  [x] Representação do processo de ETL
-   7.1 [x] Etapa 1 Carga dos arquivos .csv no banco de dados OLTP
-   7.2 [x] Etapa 2 Carga dos dados do OLTP para STAGING
-   7.3 [x] Etapa 3 Limpeza e transformações carregando no Data Warehouse
-   7.4 [x] Etapa 4 Apresentação dos Resultados
  -   7.1 [x] Etapa 1 Carga dos arquivos .csv no banco de dados OLTP
  -   7.2 [x] Etapa 2 Carga dos dados do OLTP para STAGING
  -   7.3 [x] Etapa 3 Limpeza e transformações carregando no Data Warehouse
  -   7.4 [x] Etapa 4 Apresentação dos Resultados
- 8  [x] Configurando docker-compose
- 9  [x] Carga full dos arquivos.csv para o banco transacional (oltp)
- 10 [x] Carga full na staging area
- 11 [] Realizando limpeza e transformações da staging carregando 
        no data warehouse
- 12 [] Carga incremental diaria dos dados na staging area
- 13 [] Realizando limpeza e transformações diarias e carregando no data warehouse
- 14 [] Apresentando os resultados
- 15 [] Tecnicas utilizadas

### Problema de negócio
- O gestor deseja saber algumas informações sobre como está a saúde de sua empresa.

### Perguntas de negócio
- [] Quantos produtos por pedido
- [] Quais os top 10 produtos mais vendem
- [] Quais os top 10 produtos menos vendem
- [] Quais são as top 10 vendedores que mais vendem
- [] Quais são as top 10 vendedores que menos vendem
- [] Quais são as top 10 clientes que mais compram
- [] Quais são as top 10 clientes que menos compram
- [] Quantos produtos foram cancelados
- [] Quantos produtos foram entregues
- [] Quais os tipos de pagamento existentes
- [] Quantos vendedores estão cadastrados por estado
- [] Quantos clientes estão cadastrados por estado
- [] Quais os tipos de pagamentos cadastrados
- [] Quais os tipos de pagamentos mais frequentes
- [] Quais os tipos de pagamentos menos frequentes
- [] Quais os top 10 pagamentos efetudos mais caros
- [] Quais os top 10 pagamentos efetudos mais baratos
- [] Quais os top 10 estados que realizam mais pedidos
- [] Quais os top 10 estados que realizam menos pedidos
- [] Qual o faturamento total das vendas
- [] Qual o faturamento de vendas por ano
- [] Qual o faturamento de vendas por mes
- [] Qual o faturamento de vendas por dia
- [] Qual o faturamento de vendas por produto
- [] Qual o faturamento de compras por cliente
- [] Qual o faturamento de vendas por vendedor
- [] Quais os top 10 fretes mais caros
- [] Quais os top 10 fretes mais baratos
- [] Qual o estado que mais compra
- [] Qual o estado que menos compra
- [] Qual o estado que mais vende
- [] Qual o estado que menos vende

### Coleta de dados
- Nesta etapa foi feito a extração dos dados diponibilizados no Kaggle.
- link: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

### Modelo de dados transacional
- Imagem disponivel no link acima

![modelo transacional](docs/modelagem/modelo-transacional.png)

### Conhecendo os dados
- Nesta etapa foi realizado uma analise dos dados, para enter como será desenvolvido o modelo dimensional que terá como foco responder as perguntas de negócio, sem que atrapalhe as operações diarias do sistema transacional.

### Modelagem do data warehouse
- Nesta etapa foi desenhado o modelo dimencional que irá atender as **perguntas de negócio**

![modelo dimencional](docs/modelagem/dw.png)

### Representação do processo de ETL
- Nesta etapa podemos visualizar uma representação do processo de ETL completo que será realizado.

#### Etapa 1 Carga dos arquivos .csv no banco de dados OLTP

![processo etl etapa 1](docs/processoETL/processoETL-etapa1.png)

#### Etapa 2 Carga dos dados do OLTP para STAGING

![processo etl etapa 2](docs/processoETL/processoETL-etapa2.png)

#### Etapa 3 Limpeza e transformações carregando no Data Warehouse

![processo etl etapa 3](docs/processoETL/processoETL-etapa3.png)

#### Etapa 4 Apresentação dos Resultados

![processo etl etapa 4](docs/processoETL/processoETL-etapa4.png)


### Configurando docker-compose
- Nesta etapa foi adicionado um arquivo **docker-compose.yml** com as configurações dos bancos de dados que serão utilizados.
- O serviço de oltp será responsável por armazenar as tabelas do banco de dados transacional, que serão carregados dos arquivos .csv que foram obtidos já em etapas anterios.
- O serviço de dw será responsável por armazenar as tabelas do banco de daaos analitico, que serão carregados com a extração dos dados que estão no banco de dados transacional.


### Carga full dos arquivos.csv para o banco transacional (oltp)
- Nesta etapa será adicionado imagens do processo de ETL realizado utilizando a ferramenta Pentaho (data integration)

#### Explicação do processo
- Inicia com o job Start oltp full
  - Ele chama a primeira **Transform**
    - A Transform realiza o seu processo
- O **Job** recebe o resultado da **Transform**
  - O job chama a proxima **Transform**
    - E segue este processo até que o Job chame todas as Transforms

##### **Job Start oltp full**

![Job Start oltp full](docs/processoETL/oltp/jobOltp.png)

##### **Transform geolocation**

![Transform geolocation oltp full](docs/processoETL/oltp/transformOltpGeolocation.png)

##### **Transform sellers**

![Transform sellers oltp full](docs/processoETL/oltp/transformOltpSellers.png)

##### **Transform customers**

![Transform customers oltp full](docs/processoETL/oltp/transformOltpCustomers.png)

##### **Transform products**

![Transform products oltp full](docs/processoETL/oltp/transformOltpProducts.png)

##### **Transform payments**

![Transform payments oltp full](docs/processoETL/oltp/transformOltpPayments.png)

##### **Transform orders**

![Transform orders oltp full](docs/processoETL/oltp/transformOltpOrders.png)

##### **Transform order_items**

![Transform order_items oltp full](docs/processoETL/oltp/transformOltpOrderItems.png)


## Tecnicas utilizadas
- No item 5 Conhecendo os dados da **Etapas do projeto**
  - Foi utilzado a biblioteca **pandas** para fazer as analises dos dados.
- No item 6 Modelagem do data warehouse da **Etapas do projeto**
  - Foi utilizado o software SQL Power Archtect para o desenvolvimento da modelagem do data warehouse.
- No item 7 Repesentação do processo de ETL da **Etapas do projeto**
  - Foi utilizado o programa **LibreOffice Draw** e **Paint** para o desenvolvimento do desenho arquitetural do processo completo.
  - No items 8 Configurando docker-compose da **Etapa do projeto**
    - Foi utilizado um arquivo.yml com as definições dos bancos de dados utilizados no processo de armazenamento dos dados.
  - No item 9 Carga full dos arquivos.csv para o banco transacional (oltp)
    - Foi utilizado a ferramenta **Pentaho (data integration)** para fazer as manipulações necessarias para gerar o banco de dados transacional.
- No item 10 Carga full na staging area
    - Foi utilizado a ferramenta **Pentaho (data integration)** para fazer as manipulações necessarias para gerar o banco de dados staging.