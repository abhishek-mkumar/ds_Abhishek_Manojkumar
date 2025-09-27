# ds_Abhishek_Manojkumar

Google Colab link : https://colab.research.google.com/drive/1CqGiCuefdIfDs3fIh7Y5ApdEqK1PWr0E?usp=sharing

# Trader Performance vs Market Sentiment Analysis

This repository explores the relationship between trader performance and Bitcoin market sentiment using historical trading data from Hyperliquid and the Fear & Greed Index. The goal is to uncover patterns in trading behavior and profitability under different market conditions.

## Datasets

1. **Trader Historical Data**
   - Source: Hyperliquid platform
   - Key columns:
     - `Coin` – Trading pair
     - `Execution Price` – Price at which trade executed
     - `Size USD` – Trade size in USD
     - `Closed PnL` – Profit or loss from the trade
     - `Side` – Buy or Sell
     - `Fee` – Transaction fee
     - `Timestamp IST` – Trade timestamp

2. **Bitcoin Market Sentiment**
   - Source: Fear & Greed Index
   - Key columns:
     - `date` – Daily timestamp
     - `value` – Numeric sentiment score (0–100)
     - `classification` – Sentiment category (Extreme Fear, Fear, Neutral, Greed, Extreme Greed)

## Methodology

1. **Data Cleaning & Preprocessing**
   - Converted timestamps to datetime objects.
   - Extracted date from trader timestamps to align with daily sentiment.
   - Merged trader data with Fear & Greed Index on the date column (left join).

2. **Exploratory Data Analysis**
   - Trader dataset:
     - Average and total trade sizes, PnL, and fees.
     - Distribution of buy/sell trades.
   - Sentiment dataset:
     - Counts of each sentiment class.
     - Average numeric value per class.

3. **Analysis**
   - **PnL vs Sentiment:** Evaluated average and total profit/loss per sentiment.
   - **Trade Size vs Sentiment:** Compared average trade sizes across sentiment classes.
   - **Buy/Sell vs Sentiment:** Counted buy vs sell trades per sentiment.
   - **Fees vs Sentiment:** Summed fees to assess trading activity.
   - **Win/Loss Ratio:** Calculated percentage of profitable trades per sentiment.

4. **Visualization**
   - Bar charts, boxplots, and line charts to visualize trade performance and sentiment trends.

## Key Insights

- **Trader Profitability:**
  - Highest average PnL per trade occurs in **Extreme Greed**.
  - Lowest profitability occurs during **Extreme Fear**.
- **Trade Sizes:**
  - Traders take larger positions during **Fear**, likely buying the dip.
  - Smaller trades occur in **Extreme Fear**, indicating risk aversion.
- **Buy/Sell Behavior:**
  - More **BUY trades** in Extreme Fear.
  - More **SELL trades** in Greed and Extreme Greed.
- **Fees & Activity:**
  - Fees are highest during volatile sentiment extremes (Extreme Fear/Extreme Greed), showing increased trading activity.
- **Win/Loss Ratio:**
  - Win rates are lowest in Extreme Fear (~40%) and highest in Extreme/Greed (~60%).

## Conclusion

The analysis highlights how trader behavior and profitability are influenced by market sentiment. Traders tend to trade cautiously during Fear phases and aggressively during Greed phases. Extreme Fear is associated with lower win rates, while Extreme Greed yields the highest per-trade profitability.  

These insights can inform trading strategies, risk management, and decision-making under different market conditions.

## Tools & Libraries

- Python (Pandas, NumPy)
- Matplotlib & Seaborn for visualization
