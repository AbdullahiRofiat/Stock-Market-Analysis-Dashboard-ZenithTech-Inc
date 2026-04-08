## Stock Market Performance Dashboard – ZenithTech Inc. 

A Power BI dashboard developed as a simulated business case for ZenithTech Inc., designed to analyze stock price trends, trading volume behavior, and risk exposure using historical stock transaction data.


---

## Project Overview

As a Data Analyst in a simulated scenario at ZenithTech Inc., I transformed 200,000+ rows of stock transaction data into a single executive-ready dashboard. The goal was to provide actionable insights for stakeholders, including the trading desk, portfolio managers, and risk committee, allowing them to make data-driven investment decisions without manually querying raw data.


---

## Business Objectives

Track true price trends beneath daily market fluctuations.

Understand whether volume spikes indicate genuine market demand or sell pressure.

Quantify daily risk exposure to support informed portfolio and trading strategies.



---

## Data Preparation & Cleaning

Removed duplicates and standardized date formats for accurate time analysis.

Handled missing values in Daily_Change to maintain trend integrity.

Formatted numeric and currency fields correctly to enable Power BI calculations.

Flagged anomalies, including the January 2022 price floor ($30.36) for context in volatility analysis.



---

## Data Modeling

Star Schema Design: Fact table (daily transactions) + dimensions (Date, Stock).

DIM_Date Table: Created via Power Query for full time intelligence coverage.

Relationships: One-to-many, single-direction filter to ensure DAX measures calculate correctly.



---

## Key DAX Measures

5-Day Moving Average (Moving_Avg_5) – Smooths daily volatility to reveal genuine trends:


Moving_Avg_5 =
AVERAGEX(
    DATESINPERIOD('DIM_Date'[Date], LASTDATE('DIM_Date'[Date]), -5, DAY),
    [Average Close Price]
)

Highest Price (MAX), Lowest Price (MIN), Average Price (AVERAGE)

Total Volume (SUM)

Average Daily Change (AVERAGE)



---

## Dashboard Features

KPI Cards: Highest Price, Lowest Price, Average Price, Total Volume, Average Daily Change.

Date Hierarchy Slicer: Drill-down from Year → Month → Day.

Line Chart: Close Price vs 5-Day Moving Average.

Dual-Axis Chart: Trade Volume vs Close Price.



---

## Key Insights

Bullish Trend (Feb–Apr 2022): 5-day moving average revealed a sustained uptrend.

Volume–Price Divergence: Early high volumes reflect selling pressure, not accumulation.

Hidden Risk: Average daily drift of –$8.81 indicates underlying risk despite peak prices.

Market Correction: May pullback aligns with profit-taking behavior post-rally.



---

## Recommendations

Implement alerts for deviations >15% from moving average.

Segment volume analysis by market phase to clarify behavior.

Investigate January 2022 anomaly for data accuracy.

Add a market benchmark layer to separate stock-specific performance from market movements.

Extend the analysis to 12–24 months for seasonal and year-on-year trends.



---

## Tools & Skills Demonstrated

Power BI Desktop: KPI Cards, Line Charts, Dual-Axis Charts, Slicers

Power Query: ETL, data cleaning, type validation, anomaly flagging

DAX: Time intelligence, moving averages, risk metrics

Data Modeling: Star schema, dimensional modeling, performance optimization

Business Communication: Executive KPI framing, investment risk storytelling, strategic recommendations



