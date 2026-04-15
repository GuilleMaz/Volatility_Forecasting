# 📈 Volatility Forecasting & Options Pricing: A Quantitative Approach

![Python](https://img.shields.io/badge/python-3.9+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![XGBoost](https://img.shields.io/badge/XGBoost-Latest-green.svg)
![Financial-Engineering](https://img.shields.io/badge/Financial-Engineering-gold.svg)

Este proyecto desarrolla un motor cuantitativo avanzado para la predicción de la **Volatilidad Realizada (RV)** del ETF **SPY (S&P 500)** y su aplicación directa en el **Pricing de Opciones Financieras** mediante el modelo de Black-Scholes. 

El núcleo del proyecto consiste en comparar y ensamblar modelos econométricos tradicionales con arquitecturas modernas de Machine Learning y Deep Learning para identificar ineficiencias en el mercado de opciones.

## 🎯 Objetivos
* Predecir la volatilidad anualizada del SPY con alta precisión.
* Comparar el rendimiento de modelos **GARCH**, **LSTM**, **Transformers** y **XGBoost**.
* Utilizar métricas financieras asimétricas como **QLIKE** para evaluar la gestión del riesgo.
* Calcular el "Precio Justo" (Fair Value) de opciones Call/Put y detectar oportunidades de arbitraje estadístico (*Mispricing*).

---

## 🏗️ Estructura del Proyecto (Notebooks)

### 📓 1. Data Engineering & EDA
* Extracción de datos históricos del SPY vía `yfinance`.
* Cálculo de Log-Returns y Volatilidad Realizada (Target).
* Feature Engineering: Indicadores técnicos (RSI, MACD) y análisis de efectos ARCH/GARCH.
* Pruebas de estacionariedad (ADF Test).

### 📓 2. Modelo Estadístico - GARCH
* Implementación de un modelo **GARCH(1,1)** como *baseline* institucional.
* Análisis de residuos y persistencia de la volatilidad.
* Generación de *Rolling Forecast* para evaluación out-of-sample.

### 📓 3. Deep Learning - LSTM & Transformers
* Implementación de redes **LSTM** para capturar dependencias secuenciales.
* Arquitectura **Transformer** con mecanismos de **Multi-Head Attention** para identificar shocks de mercado.
* Prevención de *Data Leakage* mediante escalado dinámico (fit solo en train).

### 📓 4. Machine Learning - XGBoost
* Ingeniería de variables rezagadas (*Lags*) de volatilidad y retornos.
* Entrenamiento con *Early Stopping* y análisis de **Feature Importance** (interpretabilidad).

### 📓 5. Evaluación y Comparación de Modelos
* Consolidación de predicciones de todos los modelos.
* Cálculo de métricas de error: **RMSE**, **MAE** y **QLIKE** (específica para volatilidad).

### 📓 6. Pricing de Opciones (Black-Scholes)
* Implementación de la fórmula de Black-Scholes para opciones europeas.
* Simulación de estrategia de trading: Precio de Mercado vs. Precio Justo (XGBoost).
* Visualización del "Edge" (ventaja) y generación de señales de compra/venta de primas.

---

## 📊 Principales Conclusiones

1.  **Dominio de XGBoost:** El modelo basado en árboles demostró la mayor capacidad de reacción ante picos súbitos de volatilidad, superando a las redes neuronales en métricas RMSE y QLIKE.
2.  **Robustez de GARCH:** A pesar de su simplicidad, GARCH se mantuvo como un excelente regulador de "reversión a la media", siendo el segundo mejor modelo.
3.  **Captura de Ineficiencias:** El análisis de *Mispricing* reveló ventanas de oportunidad donde el mercado sobrevalora las opciones por inercia histórica (pánico), permitiendo estrategias de venta de volatilidad altamente rentables.

---

