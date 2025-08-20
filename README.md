# Analise De Teste ABC
Este projeto traz a resolução de um case técnico que solicita uma análise de teste ABC de alguns datasets. Todos os dados são fictícios e foram gerados pela empresa responsável pelo case técnico. A análise abrange desde o comportamento de clientes até o desempenho de categorias e informações sobre regiões com maior percentual de venda, oferecendo insights valiosos para tomadas de decisão estratégicas.

## 🧰 Tecnologias Utilizadas
- Python ([pandas](https://pandas.pydata.org/), [pandasql](https://pypi.org/project/pandasql/), [matplotlib](https://matplotlib.org/))
- Jupyter Notebook

##  📁 Fontes de Dados
Os dados utilizados são oriundos de um dataset ficcional e incluem:

- clientes.csv
- produtos.csv
- pedidos.csv
- itens_pedidos.csv


`Clientes.csv`
  Este arquivo contém informações detalhadas sobre os clientes cadastrados na plataforma.
  
| Coluna    | Descrição | Tipo  |
|----------|-------|-------|
| cliente_id    |  Identificador único de cada cliente.     | INTEGER
| nome    | O nome completo do cliente.    | STRING
| email  | O endereço de e-mail único do cliente.  | STRING
| data_cadastro  | A data em que o cliente se registrou na plataforma.  | DATE
|  cidade  | A cidade de residência do cliente.  | STRING.
|  estado  |A sigla do estado de residência do cliente (por exemplo, SP, RJ).  |  STRING
| grupo  | Esta coluna indica o grupo de um Teste A/B ao qual o cliente foi designado (A para o grupo de controle e B para a variante).  | STRING.

`Produtos.csv`
Este arquivo armazena os detalhes de todos os produtos que estão disponíveis para venda.


| Coluna        | Descrição | Tipo |
|---------------|-----------|------|
| produto_id    | Identificador único de cada produto. | INTEGER |
| nome_produto  | O nome completo do produto. | STRING |
| descricao     | Uma breve descrição do produto. | STRING |
| preco         | O preço unitário de venda do produto. | NUMERIC ou BIGNUMERIC |
| categoria     | A categoria à qual o produto pertence (por exemplo, Eletrônicos, Roupas, Alimentos). | STRING |

---

`Pedidos.csv`
Este arquivo registra as informações principais de cada pedido realizado pelos clientes.

| Coluna        | Descrição | Tipo |
|---------------|-----------|------|
| pedido_id     | Identificador único de cada pedido. | INTEGER |
| cliente_id    | O identificador do cliente que fez o pedido. Este campo serve como chave estrangeira, ligando ao `cliente_id` na tabela **clientes.csv**. | INTEGER |
| data_pedido   | A data e a hora exatas em que o pedido foi efetuado. | TIMESTAMP |
| status        | O status atual do pedido (por exemplo, Pendente, Processando, Enviado, Entregue, Cancelado). | STRING |
| valor_total   | O valor monetário total do pedido, incluindo todos os itens. | NUMERIC ou BIGNUMERIC |

---


`itens_pedido.csv`
Este arquivo detalha cada item individual que compôe um pedido Um único pedido pode ter um ou mais itens.

| Coluna        | Descrição | Tipo |
|---------------|-----------|------|
| item_id       | Identificador único de cada item dentro de um pedido específico. | INTEGER |
| pedido_id     | O identificador do pedido ao qual este item pertence. Chave estrangeira ligando ao `pedido_id` da tabela **pedidos.csv**. | INTEGER |
| produto_id    | O identificador do produto que foi comprado. Chave estrangeira ligando ao `produto_id` da tabela **produtos.csv**. | INTEGER |
| quantidade    | A quantidade do produto específico incluída neste item do pedido. | INTEGER |
| preco_unitario | O preço unitário do produto no momento em que a compra foi realizada (pode diferir do preço atual da tabela produtos). | NUMERIC ou BIGNUMERIC |
| subtotal      | O subtotal monetário para este item do pedido (quantidade × preco_unitario). | NUMERIC ou BIGNUMERIC |

📂 Estrutura do projeto:
- ├── Notebook/
 - │   └── Teste.ipynb
- ├── Datasets/
 - │   └── *.csv

## 📌 Principais Análises Realizadas

- Qual grupo teve o desempenho mais rentável?
- O estado influencia no valor das vendas?
- Qual o faturamento por estado?
- Qual o faturamento por cidade?
- A categoria do produto influencia no status do pedido?
- Qual a categoria mais vendida?
- Número de pedidos CONFIRMADOS, CANCELADOS e PENDENTES
