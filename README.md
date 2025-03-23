# Weather Trend Forecasting Project

**Project Name**: Weather Trend Forecasting (Basic)  
**Part of**: Company PM Accelerator Program  
**Objective**: Predict next-day temperature (°C) using historical weather data with Ridge Regression.  

---

## Table of Contents
- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Installation](#installation)
- [Dataset](#dataset)
- [Usage](#usage)
- [Model Details](#model-details)
- [Results](#results)
- [Limitations](#limitations)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Project Overview
This project demonstrates a basic implementation of weather trend forecasting using Ridge Regression. The goal is to predict the next day's temperature (°C) based on historical weather data, including features like wind speed, precipitation, humidity, and pressure. The code is designed for the **Company PM Accelerator Program** to showcase data cleaning, exploratory analysis, and regression modeling.

---

## Key Features
- **Data Cleaning**: Filters 12 core weather features from raw data.
- **Exploratory Analysis**: Visualizes temperature and precipitation trends.
- **Time-Shifted Target**: Creates a target variable for next-day temperature prediction.
- **Ridge Regression Model**: Trains and evaluates a linear model with regularization.
- **Model Evaluation**: Reports Mean Absolute Error (MAE) and visualizes predictions vs. actuals.

---

## Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-company/pm-accelerator-weather-forecasting.git
   cd pm-accelerator-weather-forecasting
 **Install Dependencies:**
    pandas==1.3.5
    scikit-learn==1.0.2
    matplotlib==3.5.1
2. **Dataset**
    Source: GlobalWeatherRepository.csv (not included in this repository for licensing       reasons).
    Required Columns:
            latitude (used as index in the code)
            temperature_celsius, temperature_fahrenheit
            wind_mph, wind_kph, wind_degree
            pressure_mb, pressure_in
            precip_mm, precip_in
            humidity, visibility_km, visibility_miles

    Place the dataset in the root directory before running the code
3.  **Usage**
    1. Data Preparation
          Ensure the dataset is named GlobalWeatherRepository.csv and placed in the project root.
          Run the Jupyter notebook or Python script to load and preprocess data:             weather = pd.read_csv("GlobalWeatherRepository.csv", index_col="latitude")
    2. Exploratory Analysis
          Generate plots for temperature and precipitation trends:  core_weather[["temperature_celsius", "temperature_fahrenheit"]].plot()
plt.savefig("temperature_trends.png")  # Export for reporting
    3. Train the Model
          Split data into training/testing sets and train the Ridge Regression model:
            reg = Ridge(alpha=0.1)
            reg.fit(train[prediction_parameters], train["target"])
    4. Evaluate Predictions
          Calculate MAE and visualize results:
              predictions = reg.predict(test[prediction_parameters])
              print(f"MAE: {mean_absolute_error(test['target'], predictions)}")
              combined.plot().figure.savefig("predictions_vs_actuals.png")
4.  **Model Details**
        Model Details
            Algorithm: Ridge Regression (L2 regularization).
            Features: 12 weather parameters (e.g., humidity, wind speed).
            Train-Test Split:
                Initial: First 35 rows for training, rows 36+ for testing.
                Validation: First 10 rows for training, rows 11+ for testing (in core_predictions function).
5.  **Results**
        **Mean Absolute Error (MAE):** 8.585383009399957
             Example: MAE ~8.5 degree celcius (lower is better).
        **Visualizations:**
              **Temperature Trends**
    ![image](https://github.com/user-attachments/assets/b4839c1e-3025-4d68-ab8d-758291e13e5f)
              **Precipitation Trends**
![image](https://github.com/user-attachments/assets/ce053c99-e9c3-4352-9d60-a34e4ba7d961)
              **Predictions vs. Actuals (predictions_vs_actuals.png).**
![image](https://github.com/user-attachments/assets/630305c4-10c8-4e1b-b68b-c23c7988cf3a)

6.  **Future Improvements**
      Data:
          Use datetime index for proper time-series analysis.
          Add data imputation and normalization.
      Model:
          Test ARIMA, LSTM, or Gradient Boosting.
          Implement cross-validation.
      Evaluation:
          Track RMSE and R² metrics.
7.  **Contact**
   For questions or feedback, contact:
      Name: Abhishek Sharma
      Email: abhisharma5sept2004@gmail.com
      Slack: PM Accelerator
