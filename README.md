# Stock Price Time-Series Analysis (Python & Pandas)

An end-to-end exploratory data analysis of 5 years of daily stock trading data using Python, Pandas, and Matplotlib — covering data cleaning, feature engineering, time-series analysis, and visualization.

## Overview

This project analyzes **1,254 days** of historical daily stock data (July 2021 – July 2026), transforming raw, uncleaned price data into actionable insights on price trends, volatility, and trading activity.

| Metric | Value |
|---|---|
| Trading days analyzed | 1,254 |
| Date range | Jul 6, 2021 – Jul 2, 2026 |
| Total price growth | +117% |
| Up days ("green" days) | 54% |
| Average daily volume | 65.3M shares |

## Objectives

- Clean and structure raw price data for analysis
- Engineer time-based and statistical features (returns, moving averages, volatility)
- Identify pricing trends, seasonal patterns, and volume spikes
- Visualize price action, trend, and performance over time

## Dataset

Daily OHLC (Open, High, Low, Close) price and trading volume data, sourced as a CSV export. Raw fields:

`Date | Close/Last | Volume | Open | High | Low`

Note: raw price fields were formatted as text with currency symbols (e.g. `$308.63`) and required cleaning before analysis.

## Tools & Libraries

- **Python 3** (Jupyter Notebook)
- **pandas** — data cleaning, transformation, aggregation
- **matplotlib** — visualization

## Methodology

### 1. Data Cleaning
- Stripped `$` symbols from price columns and cast to `float64`
- Converted `Date` from text to `datetime64`, sorted chronologically
- Validated there were no missing or null values

### 2. Feature Engineering
| Feature | Description |
|---|---|
| `Daily_Change` / `Daily_Return_%` | Day-over-day price change, in $ and % |
| `Daily_Range` | High minus Low, a proxy for intraday volatility |
| `MA_7` / `MA_30` | 7-day and 30-day rolling moving averages |
| `Volatility_7` | 7-day rolling standard deviation of daily returns |
| `Year`, `Month`, `Day_of_Week` | Extracted date components for grouping |
| Monthly Returns | Month-over-month % change in closing price |

### 3. Exploratory & Time-Series Analysis
- Filtering and sorting (e.g., highest-volume days, "green" vs "red" days)
- Grouped aggregations (average close/volume by year and month)
- Rolling averages to smooth short-term noise and surface the underlying trend
- Volatility tracking to flag periods of elevated risk

### 4. Visualization
- Closing price trend over the full period
- Trading volume trend
- Price vs. 7-day moving average overlay
- Daily and monthly returns distribution

## Key Findings

- **Consistent multi-year uptrend** — average closing price rose every year, from ~$153 (2021) to ~$274 (2026 YTD)
- **Accelerating growth** in the most recent years relative to earlier in the period
- **Elevated volatility cluster in April 2025** — daily swings of +15% / -9% within days of each other, coinciding with unusually high trading volume
- **Volume spikes correlate with sharp price moves**, consistent with news/earnings-driven trading activity
