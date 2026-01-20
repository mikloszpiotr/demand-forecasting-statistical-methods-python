# Demand Planning Forecasting Using Statistical Methods in Python

## Project Overview

Demand planning is one of the most critical decision-making processes in supply chain management. Accurate demand forecasts directly influence inventory levels, service level performance, working capital, and production planning.

This project demonstrates how **classical statistical forecasting methods** can be applied to demand planning problems using Python. The objective is not to build the most complex model, but to demonstrate:

- Method understanding  
- Model selection logic  
- Business interpretation of forecasts  

These are essential skills for demand planners and supply chain analytics professionals.

All demand data used in this project is **synthetically generated using NumPy** to simulate realistic demand behavior, including trend, seasonality, noise, and promotional effects.

---

## What Is Demand Planning

Demand planning is the process of estimating future customer demand in order to:

- Balance inventory versus service level  
- Reduce stockouts and overstocks  
- Support production and procurement decisions  
- Enable reliable Sales & Operations Planning (S&OP)  

From an analytics perspective, demand planning focuses on forecasting **baseline demand patterns over time**, typically at **SKU–location level**.

A good demand forecast must:

- Capture historical demand behavior  
- React reasonably to changes  
- Remain interpretable for planners  
- Provide stable input for inventory and replenishment models  

For this reason, statistical forecasting methods remain widely used in real supply chain environments.

---

## Why Statistical Forecasting Methods

Before applying machine learning or deep learning, every demand planning system should establish **strong statistical baselines**.

Statistical models are still heavily used in industry because they:

- Are interpretable and explainable  
- Perform well on limited data  
- Are stable in operational environments  
- Allow planners to understand forecast behavior  
- Serve as benchmarks for advanced models  

In many organizations, advanced models are accepted only if they **clearly outperform classical statistical approaches**.

This project focuses on those core methods.

---

## Demand Data Simulation

Instead of using external datasets, demand data is generated programmatically using NumPy.

The synthetic demand includes:

- Base demand level  
- Linear growth trend  
- Seasonal patterns  
- Random noise  
- Occasional promotional spikes  

This approach allows full control over demand behavior and enables clear demonstration of how different forecasting models respond to various demand patterns.

---

## Forecasting Models Included

### 1. Naive Forecast

The naive method assumes that future demand equals the last observed value.

This model is simple but extremely important in practice, as it often serves as the **minimum performance benchmark**.

**Why it is used:**
- Very strong baseline  
- No parameters  
- Surprisingly difficult to beat on volatile demand  

**Limitations:**
- Cannot handle trend  
- Cannot handle seasonality  
- Reacts slowly to structural changes  

**Typical usage:**
- Baseline comparison  
- Highly noisy or unpredictable SKUs  

---

### 2. Seasonal Naive Forecast

The seasonal naive method repeats demand from the same period in the previous season.

Example:  
Week 10 this year = Week 10 last year.

**Why it is used:**
- Captures seasonality without optimization  
- Extremely intuitive for planners  
- Often strong for mature seasonal products  

**Limitations:**
- Ignores trend  
- Assumes seasonality is perfectly stable  
- Breaks under structural changes  

**Typical usage:**
- Retail demand  
- Yearly seasonal products  
- Benchmark for seasonal forecasting  

---

### 3. Moving Average

The moving average forecast uses the average of the last *N* periods.

**Why it is used:**
- Smooths short-term noise  
- Easy to understand  
- Reduces random fluctuations  

**Limitations:**
- Lags behind trend  
- Window size selection is subjective  
- Performs poorly under seasonality  

**Typical usage:**
- Stable demand patterns  
- Operational smoothing  

---

### 4. Simple Exponential Smoothing (SES)

SES improves upon moving averages by assigning higher weight to recent observations.  
It models **only the demand level**.

**Why it is used:**
- More adaptive than moving average  
- One tunable parameter  
- Widely used in classical planning systems  

**Limitations:**
- No trend modeling  
- No seasonality modeling  
- Sensitive to outliers if poorly tuned  

**Typical usage:**
- Short-term demand planning  
- Baseline demand estimation  
- Input to promotional uplift models  

---

### 5. Holt’s Linear Trend Method

Holt’s method extends SES by explicitly modeling trend.

The forecast consists of:
- Level component  
- Trend component  

**Why it is used:**
- Handles growing or declining demand  
- Simple yet powerful extension of SES  
- Remains interpretable for business users  

**Limitations:**
- Does not model seasonality  
- Trend can be distorted by promotions or stockouts  
- May overshoot when trend is temporary  

**Typical usage:**
- Expanding distribution  
- Ramp-up SKUs  
- Medium-term planning horizons  

---

## Model Evaluation

Forecast accuracy is evaluated using commonly applied demand planning KPIs:

- **sMAPE** (preferred for low-demand items)  
- **MAPE** (used carefully due to zero-demand issues)  
- **Forecast Bias (%)**  
- **RMSE**  

These metrics help assess not only accuracy, but also **systematic over- or under-forecasting**, which directly impacts inventory and service levels.

---

## Visualization

The project includes clear visualizations showing:

- Historical demand  
- Train–test split  
- Forecast comparison across models  
- Behavioral differences between methods  

Visualization is critical in demand planning, as planners must understand **why** a forecast behaves a certain way — not only its numerical accuracy.

---

## Key Demand Planning Insights

- No single forecasting method works best for all SKUs  
- Baseline methods are mandatory before advanced modeling  
- Seasonality and trend must be handled explicitly  
- Promotions and stockouts distort historical demand  
- Bias reduction is often more important than pure accuracy  

In real-world environments, forecasting performance must always be interpreted together with **business context**, not metrics alone.

---

## Technologies Used

- Python  
- NumPy  
- Pandas  
- Matplotlib / Seaborn  
- Statsmodels  

---

## Business Relevance

This project mirrors real demand planning workflows used in:

- FMCG  
- Retail  
- Manufacturing  
- Distribution and logistics  

It emphasizes **interpretability, stability, and decision support**, which are core requirements in professional supply chain forecasting systems.

---

