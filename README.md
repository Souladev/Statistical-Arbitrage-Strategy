# Statistical-Arbitrage-Strategy
This is a Statistical Arbitrage Strategy implemented in Pine Script (version 5) for TradingView, designed to identify trading opportunities by analyzing the relationship between two assets using statistical methods

# Overview 
The strategy, titled "Statistical Arbitrage Strategy - Clean Signals", uses a combination of linear regression and Nadaraya-Watson kernel regression to model the relationship between two assets (e.g., BTCUSD as the primary asset and ETHUSD as the secondary asset). It generates buy and sell signals based on deviations in the price relationship, aiming to exploit temporary mispricings. The strategy includes customizable inputs for lookback periods, thresholds, and risk management levels, and it visualizes signals, trends, and key price levels on the chart.

# How It Works
1/ Modeling the Relationship: The strategy uses linear regression to establish a baseline relationship between two assets (e.g., BTCUSD and ETHUSD). It then refines this model with non-linear adjustments using the Nadaraya-Watson estimator.
2/ Identifying Mispricings: By analyzing residuals (deviations from the model), the strategy detects when the secondary asset is significantly undervalued (buy signal) or overvalued (sell signal) relative to the primary asset.
3/Trade Execution: Signals are generated based on threshold crossings, with clear entry, stop-loss, and take-profit levels displayed on the chart.

Trend Context: The strategy provides trend direction to help traders understand the broader market context, visualized through background colors.

# Trend Analysis
The strategy identifies the trend of the combined_fit (the combined linear and non-linear model):
Uptrend: When combined_fit is rising over 2 bars (ta.rising(combined_fit, 2)).
Downtrend: When combined_fit is falling over 2 bars (ta.falling(combined_fit, 2)).
Sideways: When neither an uptrend nor downtrend is detected.
Trends are visualized using background colors:
Uptrend: Light blue background.
Downtrend: Light red background.
Sideways: Light gray background.
Use Cases

# Statistical Arbitrage: Ideal for trading pairs of correlated assets (e.g., BTCUSD and ETHUSD) to exploit temporary price divergences.
Customizable Trading: Users can adjust lookback periods, thresholds, and risk levels to suit their trading style or asset pair.
Visual Feedback: The strategy provides clear visual cues (arrows, labels, and background colors) for entry/exit points and trend direction, making it user-friendly for traders.

# Limitations
Market Assumptions: Assumes a stable statistical relationship between the two assets, which may break down during extreme market conditions.
Parameter Sensitivity: The strategy's performance depends on the choice of length, threshold, bandwidth, tp_level, and sl_level. Users should backtest and optimize these parameters.
Execution: The script defines signals but does not execute trades automatically; users must act on the signals manually or integrate with a trading platform.
Data Dependency: Relies on accurate price data for both assets, which may be affected by exchange-specific differences or data lags.
# How to Use
Add to TradingView: Copy the Pine Script code into TradingView’s Pine Editor and apply it to a chart (e.g., BTCUSD).
Configure Inputs:
Set the secondary asset ticker (e.g., ETHUSD).

# Summary 
This strategy combines robust statistical methods with clear visualizations, making it a powerful tool for traders interested in statistical arbitrage across correlated assets.
Adjust length, threshold, bandwidth, tp_level, and sl_level as needed.
Interpret Signals:
Look for green "BUY" arrows for long opportunities and red "SELL" arrows for short opportunities.
Check the labels for entry, stop-loss, and take-profit levels.
Monitor background colors for trend context (blue for uptrend, red for downtrend, gray for sideways).
Backtest and Optimize: Use TradingView’s strategy tester to evaluate performance and fine-tune parameters.
