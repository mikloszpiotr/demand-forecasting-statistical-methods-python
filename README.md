Demand Planning Forecasting Using Statistical Methods in Python
Project Overview
Demand planning is one of the most critical decision-making processes in supply chain management. Accurate demand forecasts directly influence inventory levels, service level performance, working capital, and production planning.
This project demonstrates how classical statistical forecasting methods can be applied to demand planning problems using Python. The goal is not to build the most complex model, but to show method understanding, model selection logic, and business interpretation—essential skills for demand planners and supply chain analytics professionals.

All demand data used in this project is synthetically generated with NumPy to simulate realistic demand behavior, including trend, seasonality, noise, and promotional effects.

What Is Demand Planning?
Demand planning is the process of estimating future customer demand in order to:

Balance inventory versus service level
Reduce stockouts and overstocks
Support production and procurement decisions
Enable reliable sales and operations planning (S&OP)

From an analytics perspective, demand planning focuses on forecasting baseline demand patterns over time, typically at SKU–location level.
Characteristics of a Good Demand Forecast
A good demand forecast must:

Capture historical demand behavior
React reasonably to changes
Remain interpretable for planners
Provide stable input for inventory and replenishment models

For this reason, statistical methods remain widely used in real supply chain environments.
Why Statistical Forecasting Methods?
Before applying machine learning or deep learning, every demand planning system should establish strong statistical baselines.
Statistical models are still heavily used in industry because they:

Are interpretable and explainable
Perform well on limited data
Are stable in operational environments
Allow planners to understand forecast behavior
Serve as benchmarks for advanced models

In many real businesses, advanced models are only accepted if they clearly outperform these classical approaches. This project focuses on those core methods.
Demand Data Simulation
Instead of using external datasets, demand is generated programmatically using NumPy.
The synthetic demand includes:

Base demand level
Linear growth trend
Seasonal patterns
Random noise
Occasional promotional spikes

This approach allows full control over demand behavior and enables clear demonstration of how different forecasting models react to various demand patterns.
Forecasting Models Included
Naive Forecast
The naive method assumes that future demand equals the last observed value.
Why it is used:

Very strong baseline
No parameters
Surprisingly difficult to beat on volatile demand

Limitations:

Cannot handle trend
Cannot handle seasonality
Reacts slowly to structural changes

Typical usage:

Baseline comparison
Highly noisy or unpredictable SKUs

Seasonal Naive Forecast
The seasonal naive method repeats the demand observed in the same period of the previous season. For example, week 10 this year is forecast as week 10 last year.
Why it is used:

Captures seasonality without optimization
Extremely intuitive for planners
Often strong for mature seasonal products

Limitations:

Ignores trend
Assumes seasonality is perfectly stable
Breaks under structural changes

Typical usage:

Retail demand
Yearly seasonal products
Benchmark for seasonal forecasting

Moving Average
The moving average forecast uses the average of the last N periods as the future forecast.
Why it is used:

Smooths short-term noise
Easy to understand
Reduces random fluctuations

Limitations:

Lags behind trend
Window size selection is subjective
Performs poorly under seasonality

Typical usage:

Stable demand patterns
Operational smoothing

Simple Exponential Smoothing (SES)
SES improves upon moving averages by assigning higher weight to recent observations. It models only the demand level.
Why it is used:

More adaptive than moving average
One tunable parameter
Widely used in classical planning systems

Limitations:

No trend modeling
No seasonality modeling
Sensitive to outliers if poorly tuned

Typical usage:

Short-term demand planning
Baseline demand estimation
Input to promotional uplift models

Holt's Linear Trend Method
Holt's method extends SES by explicitly modeling trend. The forecast consists of:

Level component
Trend component

Why it is used:

Handles growing or declining demand
Simple yet powerful extension of SES
Still interpretable for business users

Limitations:

Does not model seasonality
Trend can be distorted by promotions or stockouts
May overshoot when trend is temporary

Typical usage:

Expanding distribution
Ramp-up SKUs
Medium-term planning horizons

Model Evaluation
Forecast accuracy is evaluated using commonly applied demand planning KPIs:

sMAPE — preferred for low-demand items
MAPE — used carefully due to zero-demand issues
Forecast bias percentage — measures systematic over- or under-forecasting
RMSE — captures overall prediction error magnitude

These metrics help assess not only accuracy but also systematic over- or under-forecasting, which directly impacts inventory and service levels.
Visualization
The project includes clear visualizations showing:

Historical demand
Train and test split
Forecast comparison across models
Behavior differences between methods

Visualization is essential in demand planning, as planners must understand why a forecast behaves a certain way, not only its numerical accuracy.
Key Demand Planning Insights

No single method works best for all SKUs
Baseline methods are mandatory before advanced modeling
Seasonality and trend must be treated explicitly
Promotions and stockouts distort historical demand
Bias reduction is often more important than pure accuracy
Forecasting performance must always be interpreted together with business context

Getting Started
Requirements

Python 3.7+
NumPy
Pandas
Matplotlib / Seaborn (for visualization)
Scikit-learn (for metrics)
