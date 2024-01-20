# Momentum Algorithmic-Trading 
## Description
This Algo trading strategy is designed to take advnatge of strong momentum in a volatile trending market by integrating key indicators. It utilizes the ADX to gauge trend strength, RSI for entry signals, the 50 EMA to establish trend direction, and a candlestick close beyond the previous range to suggest a potential breakout. Exit signals are triggered when the ADX returns to normal conditions, indicating a decline in momentum and a potenetial reversal. Backtesting will focus on the past two years, specifically on a volatile currency pair like Bitcoin, to assess the strategy's effectiveness. This combination of indicators aims to provide a systematic approach to momentum trading in dynamic market conditions.

The following data science concepts are used in this project
1. Feature Engineering (Creating new TA indicators)
2. Model Building (Stategy development; combining TA indicators to enhance performance of Hypothesis)
3. Model Evaluation (Evaluate strategy performance; analyze risk versus reward paramaters to decide if strategy is worth implementing)

The following technology & libraries are used in this project
1. Google Colab
2. Python
3. Pandas & Numpy (Data reading)
4. Yfinance (Data source)
5. TA-Lib (Building Strategy)
6. Vectorbt (Backtesting Strategy)

## Future Improvements
As this was my first Algorithmic trading strategy, there is a lot of room for improvement. More specifically, I would like to focus on the logic and reasoning of the parameters used in the strategy opposed to the results of the strategy itself (Expectancy, Profitability, Etc.) Some areas of improvement include:
1. Entry Signal:
   One of the biggest challenges in any trend continuatuion/momentum strategy is striking the balance between entering too early and missing the trade. While RSI served as a decent entry for this strategy, it is not limiting enough as an entry signal to filter out false breakouts nor does it offer any unique insight. For example, extreme ADX conditions are often indicative of extreme RSI conditions meaning that both oscillators are showing the same sign as there is too much of an overlap betweeen the two. For a future strategy, the overlap of these indicators could be reduced through utilizing different leading and lagging indicators to try and highlight other facets of trading such as volume and areas of support/resistance.
2. Currency Selection:
   While Bitcoin is a good representative for the entire Cryptocurrency market, it leaves room for bias in the backtesting. One potential issue is that since Bitcoin is a newer currency it is subject to more volatility and momentum-induced trends as it has not yet established extreme support and resistance levels. While they do exist, the sheer "newness" of the entire crypto market including Bitcoin leaves more doubt about the future performance of this strategy as the market conditions are bound to change significantly in the next 5-10 years. For future projects, selecting multiple currencies/assets with more historical data and thus more established regions of trading would be more indicative of future performance and ensure confidence in the strategy going forward.
3. Exit Signal:
   Similar to the entry signal, I felt that using ADX to exit a trade doesn't correlate too well with actual price action and has too much room for error. In the future, a strategy that utilizes price action in the form of either candlesticks or breaking above/below support & resistance levels could provide a more specific and accurate way of exiting the trade.
4. Multiple Active Trdaes:
   One of the biggest barriers to this strategy's success is related to entering multiple different positions off the same trend. This was a real hindrance to the overall performance and ths risk management that led to a few large drawdowns. For future strategies, I plan to implement a new condition that does not execute a trade if there is an active trade already in place.
5. Simplicity:
   Last but not least, this strategy as a whole was too specific to be comfortable trading going forward. While the logic behnd some of the ideas had potential, I believe that the combination of four separate entry conditions might have been overfitting the strategy. This could undermine its future performance capabilitites on other currencies as well as Bitcoin itself. One of the larger takeaways was that simply adding more indicators does not usually increase performance. Each indicator/condition should have a specific use case that is unique from any other indicator/condition in the same strategy.

While there is a lot to learn from, this project allowed me to use both creative and analytical thinking to try and enhance the performance of this strategy. In addition to this, learning TA-lib and vectorbt was one of the highlights of this entire project. As somebody who used to manually perform hundreds of backtests on different currency pairs, I was astonished to see the usefulness of these libraries in the creation and validation aspects of building a strategy. This was the first of many and I can't wait to apply what Ive learned in the next project.
