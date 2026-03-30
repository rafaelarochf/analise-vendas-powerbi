# Projeto 01 – Análise de Vendas (Power BI)

## 1️⃣ Objetivo do Projeto
Este dashboard foi desenvolvido para analisar o desempenho comercial da empresa, permitindo uma visão clara sobre a saúde financeira da operação. Ele responde perguntas estratégicas e auxilia na tomada de decisão:

* **A operação está saudável?** – Monitoramento de Receita vs. Lucro.
* **Quem realmente gera resultado?** – Performance de vendas e vendedores.
* **Estamos crescendo com qualidade?** – Equilíbrio entre Clientes Novos e Recorrentes.
* **Onde ganhamos ou perdemos margem?** – Eficiência de Preço e Custo por Categoria.

> 💡 **Resumo de impacto:** Permite identificar produtos estratégicos, apoiar decisões de precificação e maximizar a lucratividade através de análise de margem.

---

## 2️⃣ Dataset
Os dados utilizados são fictícios, estruturados para análise de performance em varejo.
* **Período:** 01/2023 a 12/2023 
* **Volume:** ~10.000 registros

| Fonte de Dados | Descrição |
| :--- | :--- |
| **vendas.csv** | Tabela fato com transações, produtos, clientes, vendedores e custos. |
| **Medidas** | Tabela de medidas DAX (Receita, Lucro, Margem %, Ticket Médio). |
| **dCalendario** | Tabela de dimensão de tempo para análise MoM e inteligência de datas. |

---

## 3️⃣ Limpeza e Transformação de Dados (ETL)
Processo realizado no **Power Query**:
1.  **Padronização:** Tipos de dados ajustados para Moeda e Percentual.
2.  **Tratamento de colunas:** Cálculo de descontos aplicado para refletir a Receita Líquida real.
3.  **Modelagem:** Estrutura em *Star Schema* para otimização de performance.
4.  **Criação de métricas:** Desenvolvimento de 23 medidas DAX para suporte aos visuais.

---

## 4️⃣ Métricas e DAX (Principais Destaques)
Das 23 medidas criadas, estas são as fundamentais para a gestão do negócio:

| Medida | Descrição Técnica | Impacto no Negócio |
| :--- | :--- | :--- |
| **02 Receita Líquida** | `SUM(Sales_Amount) - Descontos` | Faturamento real disponível após deduções. |
| **05 Margem (%)** | `DIVIDE([Lucro Total], [Receita Líquida], 0)` | Eficiência da operação (lucratividade relativa). |
| **20 Variação % Receita** | `DIVIDE([Receita Atual] - [Receita Mês Ant.], [Receita Mês Ant.])` | Análise de crescimento mensal (MoM). |
| **21 Ticket Médio** | `DIVIDE([Receita Líquida], [Quantidade Total], 0)` | Valor médio gasto por pedido/cliente. |
| **23 Var. % Clientes Novos** | `Calcula a variação da base de novos entrantes` | Mede a eficácia da aquisição de mercado. |

---

## 5️⃣ Visualizações e Insights

###  Visão Executiva
* **Visual:** Cards com indicadores de variação e linhas de tendência.
* **Insight:** A operação apresenta crescimento constante, mas a lucratividade oscila entre regiões, sugerindo oportunidades de otimização logística.

###  Performance Comercial
* **Visual:** Ranking de vendedores com **Tooltips Personalizados**.
* **Insight:** Vendedores com maior volume nem sempre possuem a melhor margem; o dashboard destaca quem gera valor real.

###  Análise de Clientes
* **Visual:** Gráficos de rosca e barras comparativas.
* **Insight:** Base equilibrada (~50% novos / ~50% recorrentes), indicando sucesso tanto na prospecção quanto na fidelização.

###  Eficiência e Rentabilidade
* **Visual:** Gráfico de dispersão e análise de Preço Médio.
* **Insight:** A categoria **Food** é o "carro-chefe", possuindo o maior ticket médio aliado à maior margem unitária.

---

## 6️⃣ Conclusão / Takeaways
* **Produtos:** Foco na categoria Food para expansão, devido à alta rentabilidade.
* **Vendas:** Treinamento focado em "Upsell" para vendedores de alto volume mas baixo ticket médio.
* **Canais:** Potencial de investimento no canal Online para ganho de escala com custos menores.

---

## 7️⃣ Como Abrir o Dashboard
1.  Baixe e instale o [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
2.  Clone este repositório:
    ```bash
    git clone [https://github.com/rafaelarochf/analise-vendas-powerbi](https://github.com/rafaelarochf/analise-vendas-powerbi)
    ```
3.  Abra o arquivo `.pbix` localizado na pasta `dashboard`.
4.  Explore os filtros de **Ano, Mês, Região e Produto** para interagir com os dados.

## Imagens do Dashboard

###  Visão Executiva
![Visão Geral](imagens/dashprints/01_Analise_Geral.png)

###  Performance Comercial
![Performance Comercial](imagens/dashprints/02_Performance_Comercial.png)

###  Análise de Clientes
![Clientes](imagens/dashprints/03_Clientes.png)

###  Eficiência e Rentabilidade
![Eficiência](imagens/dashprints/04_Eficiencia.png)

---
📌 *Projeto desenvolvido por **Rafaela** para portfólio de Análise de Dados.*