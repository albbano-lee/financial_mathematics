# Financial Mathematics Project: Interest Rate Modeling, Hybrid Forecasting, and Trading Strategy Backtesting

Project Overview

This project combines financial mathematics theory with machine learning to model South Korean interest rates, predict bond prices based on this model, and backtest the performance of a resulting trading strategy.

Using real-world CD (91-day) rates and 5-year Korean Treasury Bond (KTB) yields from the Bank of Korea ECOS API, this project calibrates the Hull-White interest rate model. It then employs a hybrid approach, using a LightGBM machine learning model to correct the theoretical limitations of the analytical model. Finally, a trading strategy based on the developed predictive model is formulated and its effectiveness is validated through backtesting on historical data.

# Project Workflow

1. Data Collection & Preprocessing:

    1-1. Fetch CD (91-day) and 5-year KTB yield data from the BOK ECOS API.
    1.2 Create a daily time-series by forward-filling (ffill) missing data for weekends and holidays.

2. Hull-White Model Calibration:

    2-1.Estimate Hull-White parameters a and
sigma using Maximum Likelihood Estimation (MLE).
    2-2. Derive the time-varying mean-reversion level
theta(t) directly from the data to apply to the model.

3. Theoretical Pricing & Error Calculation:
    
    3-1. Calculate the theoretical price of a 5-year KTB using the analytical solution of the calibrated Hull-White model.

    3-2. Compute the price_error (the difference between the actual market price and the theoretical price), which becomes the target for the machine learning model.

4. Error Prediction via Machine Learning:

    4-1. Train a LightGBM model to predict the next day's price error.

    4-2. Optimize model performance by tuning hyperparameters with GridSearchCV.

    4-3. Final Predicted Price = Hull-White Theoretical Price + LightGBM Predicted Error.

5. Forecasting & Trading Simulation:

    Use the trained hybrid model to forecast 5-year KTB prices for the period of June 2025 – December 2026.

6. Backtesting & Performance Analysis:

    6-1. Execute a simple trading strategy during the test period (Jan 2024 – May 2025) based on the model's price predictions.

    6-2. Calculate cumulative returns and visually compare the strategy's performance against a baseline Buy-and-Hold strategy.

# Key Results & Visualizations

# How to use

1. Install Dependencies

pip install pandas requests numpy scipy matplotlib lightgbm scikit-learn

2. Get API Key

API_KEY = "YOUR_API_KEY" # Replace with your actual key