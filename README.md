# EMBRAPII - Teste para Analista de Dados Sênior

Este projeto consiste em um teste de previsão estatística e de modelagem de séries temporais para a avaliação de métricas de projetos da **EMBRAPII**.

---

## Descrição Geral

- **Objetivo**: Prever indicadores relacionados a projetos e contratos, como:
  1. **Novos Projetos Contratados**  
  2. **Valor de Projetos Contratados**  
  3. **Projetos Concluídos**  

- **Modelos Utilizados**:
  - Regressão Linear (OLS) com variáveis de lag (autorregressivas)  
  - Rede Neural (Multilayer Perceptron - MLP) com variáveis de lag  

---

## Estrutura do Projeto

1. **Leitura e Pré-Processamento**  
   - Leitura de dados em formato Excel, ajustes de formatação (por exemplo, datas e valores monetários em formato brasileiro).  
   - Criação de colunas derivadas: data, `time_idx`, `lag1_...`, etc.  
   - Divisão em conjunto de treino (80%) e teste (20%).  

2. **Modelagem**  
   - **OLS** (com e sem variáveis de lag)  
   - **Rede Neural** (com e sem variáveis de lag)  
   - Métrica principal: **MAPE** (Mean Absolute Percentage Error)  

3. **Previsões Futuras**  
   - Geração de um período futuro de 12 meses,  
   - Alimentação das mesmas features (ex.: `time_idx`, `lag1`, etc.),  
   - Plot dos resultados (histórico vs. futuro) para cada variável-alvo.  

4. **Escalonamento (Opcional)**  
   - Exemplo de normalização (0 a 1) para a variável `valor_projetos_contratados` e posterior inversão ao final.  

---

**Pré-requisitos**:
   - Python 3.9+ (preferencialmente)  
   - Bibliotecas principais: `pandas`, `numpy`, `matplotlib`, `statsmodels`, `scikit-learn`, etc.

---

## Interpretação dos Resultados

- **MAPE** indica a porcentagem média de erro em relação ao valor real. MAPE menor sugere melhor adequação do modelo aos dados.  
- Nos exemplos internos, a Regressão Linear (OLS) obteve erros menores para algumas variáveis, enquanto a Rede Neural eventualmente pode capturar padrões mais complexos, mas possivelmente requer um conjunto de dados maior ou tuning de hiperparâmetros.

---

## Contato

- **Autor**: Lucas Moreira Gomes
- **LinkedIn**: [lucasmoreirag](https://www.linkedin.com/in/lucasmoreirag/)
