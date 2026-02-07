# Air Quality Dashboard

Air quality forecasting service that predicts PM 2.5 (particulate matter) levels for the next 7 days. It gets updated once every day.
Regression model is trained on historical air quality and weather data and is monitoted against predicted and real data.

# The air quality prediction


{% include air-quality.html %}

![Forecast](./air-quality/img/pm25_forecast.png)


# Model Performance Monitoring

Predictions vs Outcomes

![Hindcast](./air-quality/img/pm25_hindcast_1day.png)

## Architecture

The system follows a feature store based architecture:
1. **Feature backfill Pipeline:** Loads historical air quality and weather data
2. **Feature Pipeline:** Computes and stores features in the feature store
3. **Training Pipeline:** Trains XGBoost model using historical features
4. **Inference Pipeline:** Generates 7-day forecasts using weather forecast data
5. **Dashboard:** Displays predictions and historical trends

| Dynamic Data  | Prediction Problem | User Interface  |  Monitoring |
| ------------- |:-------------:| ------------:| ------------:|
| aqicn.org and open-meteo.com | Air Quality Forecasting | [Github Pages](./air-quality) | [Hindcasts](./air-quality) |