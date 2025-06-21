# Financial Mathematics Project: Interest Rate Modeling, Hybrid Forecasting, and Trading Strategy Backtesting

Project Overview

This project combines financial mathematics theory with machine learning to model South Korean interest rates, predict bond prices based on this model, and backtest the performance of a resulting trading strategy.

Using real-world CD (91-day) rates and 5-year Korean Treasury Bond (KTB) yields from the Bank of Korea ECOS API, this project calibrates the Hull-White interest rate model. It then employs a hybrid approach, using a LightGBM machine learning model to correct the theoretical limitations of the analytical model. Finally, a trading strategy based on the developed predictive model is formulated and its effectiveness is validated through backtesting on historical data.