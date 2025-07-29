# TechChallenge4


# 📈 Previsão de Preço de Ações com LSTM - AMZN

Este projeto tem como objetivo prever o preço de fechamento das ações da Amazon (AMZN) utilizando redes neurais LSTM (Long Short-Term Memory), uma técnica de Deep Learning bastante eficaz para séries temporais.

---

## 🧠 Tecnologias Utilizadas

- Python
- Pandas, Numpy
- Matplotlib
- scikit-learn
- TensorFlow / Keras
- yfinance (para download dos dados históricos)
- Flask + Ngrok (para servir a API)

---

## 📦 Etapas do Projeto

### 1. Coleta de Dados
- Fonte: Yahoo Finance via `yfinance`
- Período: De 2018-01-01 a 2024-07-01
- Coluna utilizada: `Close` (preço de fechamento diário)

### 2. Pré-processamento
- Normalização dos dados com `MinMaxScaler`
- Janela deslizante de 60 dias para construção das amostras de entrada (X) e saída (y)

### 3. Modelo LSTM
- Arquitetura:
  - LSTM (50 unidades, retorno de sequência)
  - LSTM (50 unidades)
  - Dense (1 saída)
- Otimizador: Adam
- Loss: Mean Squared Error
- Treinamento: 20 épocas, batch size 32
- Separação: 80% treino / 20% validação

### 4. Avaliação
- Métricas:
  - **MAE** (Erro Médio Absoluto): `2.6658`
  - **RMSE** (Raiz do Erro Quadrático Médio): `3.4898`
- Visualização do gráfico de preço real vs previsto

### 5. Salvamento do Modelo
- O modelo final é salvo como `lstm_model.h5`
- O scaler usado é salvo como `scaler.save`

---

## 🚀 API Flask com Ngrok

Foi criada uma API com Flask para receber 60 valores de preços anteriores e retornar o próximo valor previsto.

