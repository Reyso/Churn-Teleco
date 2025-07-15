# 📞 Projeto de Previsão de Churn - Telco Customer Churn

**Objetivo**: Prever a rotatividade de clientes (churn) em uma empresa de telecomunicações usando XGBoost com dados processados no Databricks.

---

## 🛠️ Fluxo de Dados (Databricks)
| Camada       | Processamento                          |
|--------------|----------------------------------------|
| **Bronze**   | Dados brutos ingeridos da fonte        |
| **Silver**   | Tratamento de valores nulos/missing    |
| **Gold**     | Pré-processamento para ML:             |
|              | - Label Encoding & Binary Encoding     |
|              | - One-Hot Encoding                     |

![Data Pipeline](figs_/data_split.png)

---

## 🔍 Análise e Seleção de Features
- **Correlação com Target**: Identificação das variáveis numéricas mais relacionadas ao churn 

![Data Pipeline](figs_/corr_churn.png)

- **Teste Qui-Quadrado**: Filtragem estatística para selecionar apenas features com maior significância (p-valor > 20)
![Feature Selection](figs_/qui2.png)

---

## ⚙️ Modelagem
### Pipeline de Pré-processamento

