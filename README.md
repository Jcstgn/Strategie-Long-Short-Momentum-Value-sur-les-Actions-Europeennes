# Python Project : Long/Short Momentum/Value Strategy on European Stocks
## Project Overview

This project implements a Long/Short strategy combining two classic factors: Momentum and Value. The goal is to select European stocks for simultaneous long and short portfolios, then compare the strategy’s performance against major stock indices (e.g., S&P 500, CAC 40, DAX).

The strategy is rebalanced monthly, using historical returns and Price-to-Book (P/B) ratios. At each rebalance, a global score is assigned to each stock to determine if it should be bought (long) or sold short (short).

## Methodology
The project follows a three-step approach to implement the strategy:

### 1. Data Loading & Cleaning
- The data (monthly returns, P/B ratios) is sourced from DATA.xlsx.
- Missing values for certain stocks (e.g., BNP PARIBAS, SOCIETE GENERALE SA) are replaced with zero or other suitable methods.
- DataFrames are filtered to keep only dates after March 2008.

### 2. Score Calculation
 - **Momentum Score**: Based on the standard deviation of a 12-month rolling average of returns, excluding the most recent month.
 - **Value Score**: Derived from the standard deviation of the P/B ratio (or an inverted P/B if you wish to capture the “value” effect more directly).
 - **Global Score**: The arithmetic mean of each stock’s Momentum Score and Value Score.
   
### 3. Portfolio Formation
- **Long Portfolio**: The top 15 stocks with the highest Global Scores.
- **Short Portfolio**: The bottom 15 stocks with the lowest Global Scores.

### 4. Portfolio Construction & Rebalancing
- Portfolios are weighted proportionally to the absolute values of their Global Scores.
- Capital is split equally: 50% in long positions and 50% in short positions.
- Each month, weights are updated (rebalanced), and capital is recalculated based on the monthly returns.

### 5. Performance Analysis
- The net capital is computed as Long Portfolio Capital – Short Portfolio Capital.
- A cumulative performance chart is generated and compared to major benchmark indices (S&P 500, CAC 40, DAX, etc.) via the yfinance library.

## Data Source
The data for this strategy comes from the `DATA.xlsx` file, which contains:

 - Monthly returns for European stocks.
 - Price-to-Book ratios for each stock.

## Installation
1. Load the dataset file `DATA.xlsx` in the main project directory.
2. Run the main Jupyter Notebook file to execute the analysis

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Contact
For any questions or feedback, please reach out:

Email: julie.castagnon@edu.devinci.fr

Linkedin: Julie Castagnon

GitHub: https://github.com/Jcstgn
