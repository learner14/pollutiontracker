# Air Quality Prediction Service

This project builds a batch air quality forecasting service that predicts PM 2.5 (particulate matter) levels for the next 7 days. The system ingests data from public air quality sensors available at https://waqi.info/ and combines it with weather forecast data to generate accurate predictions.

## Overview

The air quality prediction service demonstrates a complete batch ML system with the following components:

- **Data Sources:** Public air quality sensors (PM 2.5 measurements) and weather APIs
- **Model:** XGBoost regression model trained on historical air quality and weather data
- **Features:** Historical PM 2.5 values, temperature, humidity, wind speed, pressure, and weather forecasts
- **Predictions:** 7-day air quality forecast updated regularly
- **Output:** Interactive dashboard displaying forecast with visualizations

## Architecture

The system follows a feature store-based architecture:
1. **Backfill Pipeline:** Loads historical air quality and weather data
2. **Feature Pipeline:** Computes and stores features in the feature store
3. **Training Pipeline:** Trains XGBoost model using historical features
4. **Inference Pipeline:** Generates 7-day forecasts using weather forecast data
5. **Dashboard:** Displays predictions and historical trends
