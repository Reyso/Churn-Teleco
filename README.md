# 📊 Previsão de Churn em Empresa de Telecom

Este projeto tem como objetivo explorar, visualizar e modelar os dados de churn de uma empresa de telecomunicações utilizando a plataforma **Databricks**, com **PySpark**, **SQL** e **Seaborn/Matplotlib**.

A análise ajuda a entender os principais fatores associados ao cancelamento de clientes, com foco na geração de insights e visualizações claras.

---

## 🧰 Tecnologias Utilizadas

- 🟧 **Databricks** (ambiente unificado de dados)
- 🐍 **PySpark** (processamento de dados)
- 📊 **SQL** (consultas e agregações)
- 📈 **Seaborn / Matplotlib** (visualizações)
- 🧠 *(Opcional)*: Logistic Regression para modelagem preditiva

---

## 🔍 Análises

### Grupo 1: Chrun x (Gênero, Senioridade , Parceiro/ Cônjude e Dependentes  )
Análise da quantidade de clientes que deram **churn** (cancelaram o serviço) e **não churn** (permaneceram)

#### 🎯 Distribuição de Churn por Gênero
Observamos que não há uma influência do gênero entre os clientes que cancelaram o serviço. Haja vista o número muito próximo entre eles.
![Gráfico de churn por gênero](figs/churn_by_gender.png)
---

#### 🎯 Distribuição de Churn por Senioridade
Bem como na distribuição por gênero, não há uma significância que demonstre que pessoas mais velhas estão mais propensas a cancelar o serviço.
![Gráfico de churn por senioridade](figs/churn_by_senior.png)
---


#### 🎯 Distribuição de Churn por Cônjude
Clientes que possuem um parceiro (a) permaneceram com o serviço da empresa, um número cerca de 50% menor do que aqueles que são solteiros.
Uma demonstração que produtos multiserviços, como internet fibra, móvel, e outros serviços em um 1 só pacote para toda a família são propostas interessantes para fidelização do consumidor.

![Gráfico de churn por parceiro](figs/churn_by_partner.png)
---

#### 🎯 Distribuição de Churn por Clientes com dependentes
O cancelamento do serviço foi consideravelmente maior nos casos de clientes que não tem dependentes. Como podemos observar no gráfico abaixo, temos quase 5x mais pessoas que deixaram de ser clientes, em relação a pessoas com dependente.

![Gráfico de churn por dependentes](figs/churn_by_dep.png)
---


### 💳 Churn por Tipo de Contrato

Clientes com contratos mensais apresentaram maior tendência de cancelamento em comparação com contratos anuais ou bienais:

![Gráfico de churn por tipo de contrato](figs/churn_by_contract.png)

---

### 🌐 Churn por Tipo de Internet

Tipos de serviço de internet também influenciam a taxa de churn. Abaixo, o número de cancelamentos por categoria:

![Gráfico de churn por tipo de internet](figs/churn_by_internet.png)

---

## 📁 Estrutura do Projeto

