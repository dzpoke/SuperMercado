📄 Documentação do Dataset – Supermercado

Este documento descreve a estrutura do dataset "Supermercado", contendo informações de vendas de diversos produtos em diferentes lojas e clientes. O modelo segue o padrão estrela, facilitando análises no Power BI.

1️⃣ Estrutura do Dataset

O dataset é composto por uma tabela fato e quatro tabelas dimensão, conforme detalhado abaixo:

📌 Tabela Fato: Fato_Vendas
Esta tabela contém os registros das transações realizadas no supermercado.

Nome do Campo	Tipo de Dado	Descrição
ID_Venda	Inteiro	Identificador único de cada venda.
Data_Venda	Data	Data em que a venda foi realizada. (Relacionada à Dim_Tempo).
ID_Produto	Inteiro	Chave estrangeira referenciando a Dim_Produto.
ID_Loja	Inteiro	Chave estrangeira referenciando a Dim_Loja.
ID_Cliente	Inteiro	Chave estrangeira referenciando a Dim_Cliente.
Quantidade_Vendida	Inteiro	Quantidade de unidades vendidas do produto.
Preço_Unitário	Decimal	Preço unitário do produto no momento da venda.
Desconto	Decimal	Valor do desconto aplicado à venda.
Total_Venda	Decimal	Valor total da venda após descontos. *(Cálculo: Quantidade_Vendida * Preço_Unitário - Desconto) *

📌 Tabelas Dimensão
Estas tabelas contêm informações detalhadas sobre cada entidade no processo de venda.

📂 Dimensão Produto: Dim_Produto Armazena os detalhes dos produtos vendidos.

Nome do Campo	Tipo de Dado	Descrição
ID_Produto	Inteiro	Identificador único do produto.
Nome_Produto	Texto	Nome do produto.
Categoria	Texto	Categoria à qual o produto pertence (Ex: Alimentos, Bebidas).
Marca	Texto	Marca do produto.
Fornecedor	Texto	Nome do fornecedor responsável pelo produto.
Preço_Base	Decimal	Preço base do produto antes de qualquer desconto.
Unidade de Medida	Texto	Unidade de venda (Kg, L, Unidade).

📂 Dimensão Loja: Dim_Loja Armazena os detalhes das lojas onde as vendas ocorreram.

Nome do Campo	Tipo de Dado	Descrição
ID_Loja	Inteiro	Identificador único da loja.
Nome_Loja	Texto	Nome da loja.
Cidade	Texto	Cidade onde a loja está localizada.
Estado	Texto	Estado onde a loja está localizada.
País	Texto	País onde a loja está localizada.
Tamanho_Loja	Texto	Classificação do tamanho da loja (Pequena, Média, Grande).

📂 Dimensão Cliente: Dim_Cliente Contém informações sobre os clientes que realizaram compras.

Nome do Campo	Tipo de Dado	Descrição
ID_Cliente	Inteiro	Identificador único do cliente.
Nome_Cliente	Texto	Nome do cliente.
Gênero	Texto	Gênero do cliente (Masculino/Feminino).
Faixa_Etária	Texto	Grupo etário do cliente (Ex: 18-24, 25-34).
Frequência_Compra	Texto	Classificação da frequência de compras (Baixa, Média, Alta).
Tipo_Cliente	Texto	Classificação do cliente (Novo, Regular, VIP).

📂 Dimensão Tempo: Dim_Tempo Facilita análises temporais ao fornecer granularidade de tempo.

Nome do Campo	Tipo de Dado	Descrição
Data	Data	Chave primária, representa um dia específico.
Ano	Inteiro	Ano da data.
Mês	Inteiro	Número do mês (1-12).
Trimestre	Inteiro	Trimestre do ano (1-4).
Semana	Inteiro	Número da semana no ano.
Dia da Semana	Texto	Nome do dia da semana (Ex: Segunda-feira).
Feriado	Texto	Indica se a data é um feriado (Sim/Não).
2️⃣ Relações Entre as Tabelas
O modelo segue o padrão estrela, onde a Fato_Vendas se relaciona com as tabelas dimensão por meio das chaves primárias/estrangeiras.


3️⃣ Possíveis Análises e KPIs
Com base neste dataset, é possível criar diversos relatórios e dashboards no Power BI, como:

📊 Vendas por Categoria e Produto
📍 Vendas por Região (Cidade, Estado, País)
🛒 Comportamento dos Clientes (Frequência de Compra, Tipo de Cliente)
📆 Vendas por Período (Mês, Trimestre, Dia da Semana, Feriado)
💰 Média de Preço por Produto e Loja
🔥 Produtos Mais Vendidos
📈 Impacto de Descontos no Total de Vendas

