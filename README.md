# vivo_customer_churn_prediction

Projeto de **Data Science e Machine Learning em R** desenvolvido para analisar o comportamento de clientes e identificar características associadas ao **churn (cancelamento)**.

O projeto utiliza dados de clientes de telecomunicações e aplica técnicas de análise exploratória, transformação de dados e modelagem preditiva para classificação de clientes entre aqueles que permaneceram e aqueles que deixaram o serviço.

## Objetivo

O objetivo deste projeto é explorar os principais fatores relacionados ao churn e desenvolver modelos capazes de classificar clientes de acordo com a probabilidade de cancelamento.

Foram utilizados dois modelos de classificação:

* Regressão Logística
* Árvore de Decisão (CART)

## Sobre os dados

O dataset contém informações sobre clientes de serviços de telecomunicações, incluindo:

* Dados demográficos;
* Serviços de telefonia e internet;
* Serviços adicionais, como segurança, backup e suporte técnico;
* Serviços de streaming;
* Tipo de contrato;
* Método de pagamento;
* Faturamento sem papel;
* Tempo de permanência como cliente;
* Cobrança mensal;
* Cobrança total;
* Indicador de churn.

A variável-alvo do projeto é **Churn**, que indica se o cliente deixou o serviço.

### Fonte

Dataset originalmente disponibilizado no Kaggle:

[Telco Customer Churn — Kaggle](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

## Etapas do projeto

### 1. Exploração dos dados

Inicialmente foram analisadas a estrutura e as características da base utilizando funções como `glimpse()` e `summary()`.

Também foi realizada uma verificação de valores ausentes. Foram identificados valores ausentes na variável `TotalCharges`, que foram removidos para as etapas seguintes.

### 2. Análise exploratória

Foram utilizadas visualizações para investigar a distribuição das variáveis e sua relação com o churn.

Entre as análises realizadas estão:

* Boxplots de `tenure`, `MonthlyCharges` e `TotalCharges`;
* Gráficos de variáveis categóricas em relação ao churn;
* Distribuições das variáveis numéricas;
* Análise visual de possíveis outliers.

### 3. Transformação dos dados

As variáveis categóricas foram transformadas para utilização nos modelos estatísticos.

Foram criadas variáveis binárias e posteriormente utilizadas **variáveis dummy** para representar categorias como:

* Tipo de contrato;
* Serviço de internet;
* Método de pagamento;
* Serviços adicionais;
* Suporte técnico;
* Streaming.

### 4. Análise de correlação

Foi realizada uma análise de correlação entre as variáveis numéricas e binárias após a transformação dos dados.

A visualização foi feita utilizando o pacote `corrplot`.

### 5. Balanceamento da variável-alvo

Como o churn apresenta distribuição desigual entre as classes, foi realizado um balanceamento da base, selecionando uma quantidade equivalente de observações para clientes que permaneceram e clientes que deixaram o serviço.

### 6. Regressão Logística

Foi desenvolvido um modelo de **regressão logística binária** para classificação do churn.

Também foi utilizado o método **Stepwise** para avaliar a contribuição das variáveis ao modelo.

O treinamento foi realizado utilizando o pacote `caret` e validação cruzada (*cross-validation*).

### 7. Árvore de Decisão

Também foi desenvolvido um modelo de **árvore de decisão (CART)** utilizando o algoritmo `rpart`.

A árvore foi treinada utilizando validação cruzada e posteriormente visualizada com o pacote `rattle`.

### 8. Avaliação dos modelos

Os modelos foram avaliados utilizando **matriz de confusão** e métricas de classificação, permitindo analisar o desempenho dos modelos na identificação das classes de churn.

## Tecnologias e ferramentas

* **R**
* **RStudio / Google Colab**
* **tidyverse**
* **ggplot2**
* **cowplot**
* **caret**
* **corrplot**
* **rattle**
* Regressão Logística
* Árvore de Decisão (CART)

## Estrutura do projeto

```text
vivo_customer_churn_prediction/
│
├── vivo_customer_churn.R
└── README.md
```

## Principais conceitos aplicados

* Análise exploratória de dados (EDA)
* Tratamento de dados ausentes
* Análise de outliers
* Transformação de variáveis categóricas
* Variáveis dummy
* Correlação
* Balanceamento de classes
* Regressão logística
* Seleção Stepwise
* Árvore de decisão
* Validação cruzada
* Matriz de confusão
* Métricas de classificação

