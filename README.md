# hyperliquid-sentiment-analysis.ipynb
Python-based exploratory analysis of 200k+ Hyperliquid trades merged with Bitcoin Fear &amp; Greed Index to study sentiment-driven trading behavior and profitability patterns.

# Hyperliquid Trader Behavior vs Market Sentiment Analysis

## Objective
The goal of this project is to analyze how Bitcoin market sentiment (Fear/Greed index) relates to trader behavior and performance on Hyperliquid.  
The analysis investigates whether sentiment regimes affect profitability, trade frequency, and position sizing.

---

## Datasets

1. Bitcoin Fear & Greed Index  
Columns: date, classification, value  

2. Hyperliquid Historical Trader Data  
Includes trade execution details such as account, symbol, execution price, side, timestamp, position size, and realized PnL.

---

## Methodology

1. Data Cleaning
- Loaded both datasets using pandas
- Checked missing values and duplicates
- Converted timestamps to datetime
- Extracted daily date from trade timestamps

2. Data Alignment
- Merged trade data with sentiment data using daily date as the key

3. Feature Engineering
Created behavioral metrics including:
- trade outcome indicators
- buy/sell ratios
- long/short exposure indicators
- absolute trade size (risk proxy)

4. Aggregations
Analysis performed at two levels:
- Trade level
- Trader-day level

Metrics analyzed:
- average trade PnL
- win rate
- trade frequency
- position size

---

## Key Insights

### 1. Extreme Greed produces the highest average trade profitability
Extreme Greed sentiment shows the strongest average realized PnL per closed trade.  
This suggests trend-following conditions may allow traders to capture larger directional moves.

### 2. Fear periods are associated with larger position sizes
Average trade size is highest during Fear regimes.  
This indicates traders may increase exposure when markets decline, possibly attempting dip-buying strategies.

### 3. Higher returns during Fear may reflect higher risk exposure
Although Fear days show strong PnL results, they also exhibit larger trade sizes.  
This suggests improved profitability may partially come from increased risk-taking rather than improved trade timing.

---

## Strategy Recommendations

1. Reduce position size during Fear markets  
Higher volatility and larger trade sizes indicate increased risk exposure.

2. Favor momentum trading during Extreme Greed  
Trend continuation appears more likely during strongly bullish sentiment.

3. Monitor trading activity during strong sentiment regimes  
High trading frequency may indicate emotional or reactive trading behavior.

---

## Limitations

- The dataset does not include leverage information.
- True drawdown cannot be calculated without full account equity history.
- Long/short indicators are approximated using direction fields.

---

## How to Run

1. Install dependencies

pip install pandas numpy matplotlib seaborn

2. Open the notebook

analysis.ipynb

3. Run cells sequentially to reproduce the analysis.
