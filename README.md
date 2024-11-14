# Long/Short Momentum/Value Strategy on European Stocks
## Project Overview

This project aims to replicate a Long/Short Momentum/Value Strategy on European stocks, as described in the provided data and methodology. The strategy combines two well-known factors—momentum and value—to select stocks for long and short positions in the European equity market. 

The strategy is rebalanced monthly and utilizes historical return and Price-to-Book (P/B) ratios for stock selection.

## Methodology
The project follows a three-step approach to implement the strategy:

### 1. Stock Scoring
 - **Momentum Score** : Calculated as the centered standard deviation of the average monthly returns over the past 12 months, excluding the most recent month.

 - **Value Score** : Calculated as the centered standard deviation of the Price-to-Book (P/B) ratio, measured at the end of the previous month.

 - **Global Score** : Each stock's global score is the arithmetic mean of its momentum and value scores.

### 2. Portfolio Formation
 - **Long Portfolio**: Composed of the top 15 stocks with the highest global scores.
 - **Short Portfolio**: Composed of the bottom 15 stocks with the lowest global scores.

### 3. Portfolio Construction
Both the long and short portfolios are weighted proportionally to the absolute values of their respective global scores.
The strategy invests 100% in both the long and short portfolios.

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
