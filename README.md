# Projeto 01 – Análise de Vendas (Power BI)

##  Objetivo do Projeto

Analisar dados de vendas para entender o desempenho comercial da empresa, identificar padrões de compra, avaliar a performance de vendedores e analisar o comportamento de vendas por região, produto e canal.

O projeto foca em responder perguntas estratégicas como:

* “A operação está saudável?”
* “Quem realmente gera resultado?”
* “Estamos crescendo com qualidade ou só volume?”
* “Onde estamos ganhando ou perdendo margem?”

---

##  Ferramentas

* **Power BI**
* **Excel**
* **Power Query**
* **DAX**

---

##  Dataset

Base de dados fictícia contendo informações de vendas: produtos, vendedores, regiões, clientes e métodos de pagamento.

### Principais colunas

* `Product_ID` → identificador do produto vendido
* `Sale_Date` → data da venda
* `Sales_Rep` → vendedor responsável pela venda
* `Region` → região onde a venda ocorreu
* `Sales_Amount` → valor total da venda
* `Quantity_Sold` → quantidade de produtos vendidos
* `Product_Category` → categoria do produto
* `Unit_Cost` → custo unitário do produto
* `Unit_Price` → preço unitário de venda
* `Customer_Type` → tipo de cliente (novo ou recorrente)
* `Discount` → percentual de desconto aplicado
* `Payment_Method` → forma de pagamento
* `Sales_Channel` → canal de venda (online ou loja física)

---

##  Estrutura do Dashboard

###  Aba 1 — Visão Executiva (Executive Summary)

**Objetivo:** Responder rápido “A operação está saudável?”  
**Visualizações:**

* Cards: Receita Líquida, Custo Total, Lucro Total, Margem (%), Quantidade Total
* Linha do tempo: Receita Líquida e Lucro Total
* Barras: Receita por Região e por Categoria de Produto

**Insight:**

> A operação apresenta crescimento de receita ao longo do tempo, mas a lucratividade varia entre regiões e categorias, indicando oportunidades de otimização.

**Storytelling:**

> Esta visão geral permite acompanhar os principais indicadores da operação, incluindo receita, custo e margem.

---

###  Aba 2 — Performance Comercial

**Objetivo:** Descobrir “Quem realmente traz resultado?”  
**Visualizações:**

* Barras: Receita e Lucro por Vendedor
* Funil: Lucro por Categoria de Produto
* Barras: Receita por Canal de Vendas
* Medida DAX: `Ranking Vendedor = RANKX(ALL('vendas'[Sales_Rep]), [Receita Líquida], , DESC)`

**Insight:**

> Nem sempre os vendedores com maior volume de vendas são os mais lucrativos, mostrando diferença de eficiência comercial.

**Storytelling:**

> Esta aba mostra a performance de vendedores e canais, permitindo identificar quem gera valor real para o negócio.

---

###  Aba 3 — Clientes

**Objetivo:** Avaliar “Estamos crescendo com qualidade ou só volume?”  
**Visualizações:**

* Cards: Clientes Novos, Clientes Recorrentes, % Novos, % Recorrentes
* Pizza: Distribuição por tipo de cliente
* Barras: Distribuição por região x tipo de cliente

**Insight:**

> A proporção entre clientes novos e recorrentes indica o equilíbrio entre aquisição e retenção.

**Storytelling:**

> Avaliamos o comportamento dos clientes, identificando estabilidade e previsibilidade de receita.

---

###  Aba 4 — Eficiência e Rentabilidade

**Objetivo:** Descobrir “Onde estamos ganhando ou perdendo margem?”  
**Visualizações:**

* Cards: Preço Médio, Custo Médio, Desconto Médio
* Barras: Preço, Custo e Margem por Categoria
* Dispersão: Preço x Custo, tamanho da Receita Líquida, legenda Categoria

**Insight:**

> Diferenças entre preço e custo mostram oportunidades de melhoria de margem por categoria.

**Storytelling:**

> Esta aba analisa a eficiência operacional, permitindo identificar produtos com maior potencial de rentabilidade.

---

##  Insights Gerais

* Regiões com maior volume de vendas
* Vendedores mais eficientes
* Produtos mais lucrativos
* Impacto do canal de venda nas receitas
* Comportamento de clientes novos vs recorrentes

---

##  Imagens do Dashboard

![Visão Executiva](./imagens/dashprints/01_Analise_Geral.png)
![Performance Comercial](./imagens/dashprints/02_Performance_Comercial.png)
![Clientes](./imagens/dashprints/03_Clientes.png)
![Eficiência e Rentabilidade](./imagens/dashprints/04_Eficiencia.png)