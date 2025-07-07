# Análise Exploratória de Dados (EDA) - Telecom Churn

## 1. Introdução
The Telco customer churn data contains information about a fictional telco company that provided home phone and Internet services to 7043 customers in California in Q3. It indicates which customers have left, stayed, or signed up for their services.

---

## 2. Dados Utilizados

*(Você pode complementar com as informações da base e variáveis aqui.)*

---

## 3. Análises Univariadas

### 3.1 - Distribuição do Churn
![Churn Distribution](figs/percent_churn_total.png)

Aproximadamente 26.6% dos clientes cancelaram o serviço.  
Aqui apresenta-se um desbalanceamento na quantidade da amostra de usuários. A quantidade de cancelamentos é bem menor que a quantidade de não cancelamentos.

---

### 3.2 - Distribuição de Tempo de Contrato (Tenure)
![Tenure Distribution](figs/tenure_distribution.png)

Analisando a frequência dos valores de tempo de contrato, a figura sugere uma distribuição bimodal. Os maiores números de tempo de contrato concentram-se nos primeiros e nos últimos 6 meses deste recorte de tempo da base de dados.

No entanto, observa-se que os clientes com menos tempo de contrato são a maioria. Precisamos investigar se esses clientes também representam um maior número de cancelamentos (Churn).

![Tenure Churn_by_tenure](figs/prop_churn_tenure.png)

De fato, mais de 50% dos clientes que possuem tempo de contrato de 0 a 6 meses cancelaram o serviço. Isso destaca que um menor tempo de contrato é um elemento importantíssimo para construir um perfil de risco.

---

### 3.3 - Distribuição de Cobrança Total (TotalCharges)
![TotalCharges Distribution](figs/dist_totalcharges.png)

A distribuição é assimétrica, concentrada em clientes com baixas cobranças acumuladas.

![TotalCharges Distribution](figs/prop_churn_totalcharges.png)

Segmentando o total gasto pelo cliente (TotalCharges) em 4 intervalos, observamos que o maior número de cancelamento de serviço ocorre na faixa de menor valor de até $1000. O que é perfeitamente compreensível, uma vez que clientes com menos tempo de contrato tendem a cancelar o serviço e o montante arrecadado pela empresa tende a ser menor.

---

### 3.4 - Distribuição de Cobrança Mensal (MonthlyCharges)
![MonthlyCharges Distribution](figs/monthlycharges.png)

Muitos clientes pagam tarifas mensais moderadas, mas existem planos com tarifas mais elevadas.

![MonthlyCharges Distribution](figs/media_tenure_monthlycharges.png)

Apesar dos clientes da faixa de gastos totais até $1000 serem maioria na base de dados analisada, eles possuem as menores médias de tempo de contrato e de pagamento mensal, cerca de 10.1 meses e $48/mês, respectivamente. 

Ao contrário dos clientes da faixa $4000+, que possuem as maiores médias de tempo de contrato e de pagamento mensal. Além disso, aproximadamente 85% desses clientes não cancelaram o serviço.

---

## Grupo 1 - Churn vs (Gender | SeniorCitizen | Partner | Dependents)

### 1.1 - Churn vs Gênero
![Churn vs Gender](figs/churn_by_gender.png)

Há um balanceamento na amostra de clientes do sexo feminino e masculino.

---

### 1.2 - Churn vs Idosos (SeniorCitizen)
![Churn vs SeniorCitizen](figs/churn_by_senior.png)

Temos um número muito pequeno de clientes idosos, cerca de 1142. No entanto, cerca de 41% deles cancelaram o serviço com a empresa, o que é uma porcentagem significativa diante do número total desse público.

---

### 1.3 - Churn vs Parceiros (Partner)
![Churn vs Partner](figs/churn_by_partner.png)

Clientes que possuem parceiros(as) têm menos cancelamentos em comparação com aqueles que vivem sozinhos.

---

### 1.4 - Churn vs Dependentes
![Churn vs Dependents](figs/churn_by_dep.png)

Semelhante ao caso dos parceiros, os casos de cancelamento são maiores para aqueles clientes que não têm dependentes.

---

## Grupo 2 - Churn vs (PhoneService | MultipleLines | InternetService | StreamingTV | StreamingMovies)

### 2.1 - Churn vs Serviço de telefonia (PhoneService)
![Churn vs PhoneService](figs/churn_by_phone.png)

Um número expressivo de clientes, 90% (6352 clientes), possui serviço de telefonia. Destes clientes, 36.5% cancelaram o serviço por algum motivo.

---

### 2.2 - Churn vs Multiplas Linhas (MultipleLines)
![Churn vs MultipleLines](figs/churn_by_MultipleLines.png)

Cerca de 42.2% (2667) dos clientes possuem múltiplas linhas disponíveis em suas residências. É interessante notar que ter ou não múltiplas linhas apresenta um número muito semelhante de cancelamento, o que sugere que isto pode não ser um fator determinante para o rompimento de contrato.

---

### 2.3 - Churn vs Serviços de internet (InternetService)
![Churn vs InternetService](figs/churn_by_internet.png)

Entre os 3096 clientes que assinam o serviço de internet por fibra óptica, observamos um elevado número de cancelamentos, cerca de 40% (1297 clientes).

---

### 2.4 - Churn vs Streaming de TV
![Churn vs StreamingTV](figs/churn_by_streamingtv.png)

O serviço de streaming de TV por assinatura apresenta proporção equivalente de cancelamento entre aqueles que possuem e não possuem o serviço adicional no seu plano, cerca de 30% a 33% de taxa de cancelamento, respectivamente.

---

### 2.5 - Churn vs Streaming de Filmes
![Churn vs StreamingMovies](figs/churn_by_streaming_movies.png)

O comportamento é semelhante para aqueles que adicionaram serviço de filmes no plano: entre 30% a 34% de taxa de cancelamento, respectivamente, para quem possui e quem não possui o serviço.

---

## Grupo 3 - Churn vs (OnlineSecurity | OnlineBackup | DeviceProtection | TechSupport)

### 3.1 - Churn vs Serviço de Segurança Online (OnlineSecurity)
![Churn vs OnlineSecurity](figs/churn_by_security.png)

Clientes que não possuem pacote de segurança online, como VPN e gerenciador de senhas, têm um número considerável de cancelamentos em comparação com os clientes que possuem o serviço.  
Oferecer diferentes pacotes de proteção na web pode ser uma forma de mitigar o churn.

---

### 3.2 - Churn vs Serviço de Backup (OnlineBackup)
![Churn vs OnlineBackup](figs/churn_by_onlinebk.png)

Semelhante ao caso anterior, o número de churn mais que dobra (de 523 para 1233) nos casos de clientes que não possuem serviço de backup de proteção de dados.

---

### 3.3 - Churn vs Serviço de Proteção para Dispositivos (DeviceProtection)
![Churn vs DeviceProtection](figs/churn_by_deviceprotection.png)

Mais uma vez, podemos observar o dobro de casos de cancelamento entre clientes que não possuem proteção adicional em relação aos que possuem este serviço no pacote.

---

### 3.4 - Churn vs Suporte Técnico (TechSupport)
![Churn vs TechSupport](figs/churn_by_techsupport.png)

Entre os clientes que não possuem suporte técnico adequado, há um crescimento expressivo no número de churn: de 310 para 1446, resultando em um aumento de 366.45% nos casos de cancelamento.

---

## Grupo 4 - Churn vs (Contract | PaperlessBilling | PaymentMethod)

### 4.1 - Churn vs Método de Pagamento
![Churn vs payment](figs/percent_churn_by_paymentmethod.png)

Majoritariamente, os clientes que optam pelo método de pagamento com cheque eletrônico apresentam a maior taxa de cancelamento (57.3%), contrastando com o débito automático no cartão de crédito (12.4%).  
Os métodos automáticos representam maior fidelização do cliente e, consequentemente, maior tempo de contrato e menor taxa de cancelamento.

---

### 4.2 - Churn por Tipo de Contrato
![Churn vs Tenure](figs/churn_by_contract.png)

Como visto anteriormente por meio de diferentes análises, o churn é significativamente maior entre clientes com pouco tempo de contrato.

---

## 5 - Perfis de Risco.

Será necessário oferecer opções de serviços que incentivem maior tempo de contrato e benefícios de proteção de dados e segurança online como estratégia para retenção de clientes.
