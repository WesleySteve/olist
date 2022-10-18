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
- 7  [] Repesentação do processo de ETL
- 8  [] Carga full dos arquivos.csv para o banco transacional (oltp)
- 9  [] Carga inical no data warehouse
- 10 [] Realizando limpeza e transformações iniciais
- 11 [] Carga incremental diaria dos dados
- 12 [] Realizando limpeza e transformações do dia
- 13 [] Apresentando os resultados

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

### Repesentação do processo de ETL
