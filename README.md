# Modelo Preditivo para Previsão de Evasão de Clientes (Churn Rate)

## 📌 Descrição do Projeto
Este projeto acadêmico de Business Analytics e Machine Learning foi desenvolvido na Universidade de São Paulo (USP) dentro da disciplina RAD2810 (Análise de Dados para Gestão de Negócios). O principal objetivo foi analisar o comportamento de clientes e construir modelos de classificação capazes de prever a evasão de consumidores (churn) em serviços de assinatura, apoiando estratégias de retenção de clientes.

## 📊 Abordagem e Etapas Técnicas
* **Análise Exploratória de Dados (EDA):** Extração de estatísticas descritivas multivariadas e distribuições via Boxplots. Foi identificado que a variável de tempo de contrato (*tenure*) possui a correlação mais expressiva com a taxa de cancelamento.
* **Modelagem Preditiva com Machine Learning:** Implementação, treinamento e teste de três algoritmos supervisionados em linguagem R: Regressão Logística, Árvore de Decisão e Random Forest.
* **Avaliação de Performance:** Utilização de Matrizes de Confusão para cálculo rigoroso de métricas de **Acurácia** e **F1-Score**.
* **Diagnóstico de Overfitting:** Avaliação crítica da variância de performance entre as etapas de treino e teste, resultando na escolha da Regressão Logística como o modelo mais robusto e estável para produção corporativa.

## 🛠️ Tecnologias e Ferramentas Utilizadas
* **Linguagem:** R (ecossistema `tidymodels`)
* **Formatos de Dados:** Excel, CSV, Arquivos de Texto Estruturados
* **Competências de Apoio:** Ciência da Informação (Estruturação de dados, Governança e Relatórios via Quarto)

---

## 📈 Dados Obtidos e Resultados Técnicos

### 1. Estatísticas Descritivas (Amostra Inicial)
* **tenure (meses):** Média global de 32.37 meses (churn=0: 37.56 meses | churn=1: 17.97 meses)
* **MonthlyCharges (US$):** Média global de $65.30 (churn=0: $60.80 | churn=1: $76.28)
* **TotalCharges (US$):** Média global de $2323.94 (churn=0: $2567.24 | churn=1: $1556.60)
* *Variável mais indicada para prever Churn:* **Tenure** (Tempo de permanência do cliente)

### 2. Resultados dos Modelos de Machine Learning (Treino vs. Teste)

* **Regressão Logística:**
  * Acurácia (Treino / Teste): 0.7996 / 0.7913
  * F1-Score (Treino / Teste): 0.5907 / 0.5689
  * Variância (Acurácia / F1): 0.0083 / 0.0218

* **Árvore de Decisão:**
  * Acurácia (Treino / Teste): 0.9951 / 0.7321
  * F1-Score (Treino / Teste): 0.9908 / 0.4807
  * Variância (Acurácia / F1): 0.2630 / 0.5101

* **Random Forest:**
  * Acurácia (Treino / Teste): 0.9951 / 0.7648
  * F1-Score (Treino / Teste): 0.9909 / 0.5198
  * Variância (Acurácia / F1): 0.2303 / 0.4711

### 3. Conclusão da Modelagem
A **Regressão Logística** foi selecionada como o melhor modelo para o problema de negócio devido ao seu equilíbrio estável entre treino e teste (baixíssima variância). Os modelos baseados em árvores (Árvore de Decisão e Random Forest) sofreram um sobreajuste severo (*overfitting*), apresentando excelente performance na base de treino, mas queda acentuada na base de testes.

