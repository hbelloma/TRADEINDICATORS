# TLC_0TO100FIVEINDICATORS_STRATEGY

This is a TradingView Pine Script strategy (`@version=5`) developed by Héctor Bello for Two Level Capital, licensed under the Mozilla Public License 2.0. The strategy, `TLC_0TO100FIVEINDICATORS_STRATEGY`, implements a trading system based on five technical indicators scaled from 0 to 100, combined with additional filters for enhanced decision-making.

## Overview

The strategy uses a combination of momentum and volatility indicators to generate buy and sell signals. It allows flexible configuration of indicators and risk management settings, making it adaptable to various trading styles and risk tolerances. The strategy supports multiple indicator combinations (2^5 = 32 possible configurations) and includes optional filters like moving averages and volume analysis.

## Features

### Indicators
The strategy incorporates five primary indicators, all scaled from 0 to 100:
1. **Relative Strength Index (RSI)**: Triggers buy/sell signals based on overbought/oversold levels, with optional divergence detection.
2. **Stochastic RSI (STOCHRSI)**: Uses K and D line crossovers to identify overbought/oversold conditions.
3. **Money Flow Index (MFI)**: A volume-momentum indicator that signals based on extreme overbought/oversold levels.
4. **Relative Volatility Index (RVI)**: Measures volatility to filter signals based on overbought/oversold thresholds.
5. **Average Directional Index (ADX)**: Assesses trend strength to filter signals based on a user-defined threshold.

### Additional Filters
- **Moving Average (XMA)**: A configurable moving average (default: EMA(100)) acts as a trend guide. Long signals are favored below the XMA, and short signals above it.
- **Volume Filter**: Uses standard deviation of volume to ensure positions are opened during periods of significant volume activity.

### Risk Management
- **Risk Plans**: Four predefined risk levels (`COOK`, `WALK`, `HAWK`, `ALLIN`) set maximum drawdown limits (10%, 30%, 50%, 100% respectively).
- **Stop Loss (SL) and Take Profit (TP)**: Configurable via percentage or ATR multiplier, with optional trailing stop functionality.
- **Position Sizing**: Quantity is calculated based on risk percentage of equity and stop loss distance.

### Customization
- All indicators can be toggled on/off, allowing 32 possible combinations.
- Parameters like indicator lengths, overbought/oversold thresholds, and moving average types are user-configurable.
- Date range inputs limit strategy execution to a specified period.

## Setup Instructions

1. **Platform**: Add the script to TradingView (Pine Script Editor).
2. **Configuration**:
   - **Strategy Action Setup**:
     - Set `From Date` and `To Date` to define the trading period.
     - Choose a risk plan (`COOK`, `WALK`, `HAWK`, `ALLIN`) to set max drawdown.
     - Adjust `Risk % of Capital` for position sizing.
   - **Stop Loss/Take Profit**:
     - Select SL/TP method (`NONE`, `PERCENTAGE`, `ATR`).
     - Configure SL/TP percentages or ATR multipliers and trailing stop options.
   - **Indicators**:
     - Toggle indicators (RSI, STOCHRSI, MFI, RVI, ADX) and their parameters (e.g., length, thresholds).
     - Enable/disable RSI divergence plotting and configure divergence parameters.
   - **Moving Average**:
     - Select MA type (`EMA`, `SMA`, `SMMA`, `WMA`, `VWMA`, `Bollinger Bands`) and length.
     - Enable/disable XMA guide for trend filtering.
   - **Volume Filter**:
     - Enable/disable volume filter and set volume thresholds (`Extra High`, `High`, `Medium`).
3. **Apply to Chart**: Add the strategy to your chart and adjust settings via the TradingView settings panel.

## Usage

- **Buy/Sell Signals**:
  - Signals are generated based on the selected indicators' conditions (e.g., crossovers/crossunders of overbought/oversold levels).
  - Filters (XMA, volume) refine signals to align with trend and volume conditions.
- **Position Management**:
  - The strategy supports pyramiding (up to 2 entries) and calculates position size based on equity and risk settings.
  - SL/TP levels are applied if enabled, with optional trailing stops.
- **Visuals**:
  - Plots SSL Channel (high/low SMAs), 100 EMA, 200 XMA, and XMA guide on the chart for trend visualization.

Here an example of the visualization on the plot of BTC 1 min chart

![PLOTTLC_0TO100FI_1min](https://github.com/user-attachments/assets/3f346036-7dac-4c51-802d-9f3800217903)

## Backtesting 
Here we get a backtesting for 1 minute chart for bullish period (12-01-2023 to 30-05-2025) and bearish period (09-11-2021 to 12-01-2023), here we take into account 4 different risk plans (ALLIN, HAWK, WALK, COOK), below the results that we get

1.-**Bullish**
- Cook:  -21% Profit, 25% (1/4) winratio, 0 Sharpe ratio and 0 Sortino ratio, in this case trades were closed by maximun drawdown reached soon
- Walk: -30% Profit, 60.47% (26/93) win ratio, -2.17 Sharpe ratio and -0.90 Sortino ratio, in this case strategy not good
- Halk: 5.24% Profit, 64.17% (352/549) win ratio, 0.125 Sharpe ratio and 0.248 Sortino ratio, in this case strategy wasn't better as buy and hold strategy 
- AllIN: -37% Profit, 63.88% (941/1473) win ration, 0.084 Sharpe ratio and 0.132 Sortino ratio, in this case strategy wasn't better as buy and hold strategy 

2.-**Bearish**
- Cook:  72.36% Profit, 69.77% (30/43) winratio, 1.687 Sharpe ratio and 0 Sortino ratio, in this case we get less trades than other and the best profit from all risk plan, (seems that been conservative on drawdown help to get beter profit), 
- Walk: 38.07% Profit, 67.39% (62/92) win ratio, 0.489 Sharpe ratio and 0.934 Sortino ratio, in this case strategy not good risk-reward ratios
- Halk: 9.97% Profit, 64.26% (151/235) win ratio, 0.181 Sharpe ratio and 0.31 Sortino ratio, here we got greater risk but lower profits
- AllIN: -32.99% Profit, 64.5% (307/476) win ration, 0.017 Sharpe ratio and 0.027 Sortino ratio, in this case we see that with non risk plan we can increase the account of at the same time we can get the accounts in negative numbers
    
For Bearish, all strategy with or without a risk plan get over the buy and hold curve, so this indicates that strategy works well as for Bearish periods but we get the best result when risk is controlled. Here I add the summary for the two backtestings with COOK and ALLIN risk plans respectively for the bearish period in 1 minute chart for BTC.

![TLC_0TO100FI_1minCOOKBear](https://github.com/user-attachments/assets/f9c04a19-b9a8-4d66-8ac0-20f98881fe70)

![TLC_0TO100FI_1minALLINBear](https://github.com/user-attachments/assets/b30c9cbf-93d0-4df8-9c48-7dbe836384c6)





## Example Configuration
- Enable RSI, STOCHRSI, and MFI with default lengths (14).
- Set XMA guide to EMA(200) and enable volume filter with a medium threshold (1.0).
- Use `PERCENTAGE` SL/TP with 2% stop loss and 10% take profit.
- Select `WALK` risk plan for 30% max drawdown.
- Set trading period from July 17, 2010, to December 31, 2025.

## Notes
- The strategy is designed for flexibility but requires careful parameter tuning for specific markets and timeframes.
- Backtest thoroughly before deploying in live trading.
- Contact Héctor Bello (ayaxhector666@gmail.com) for questions or support.

## License
This source code is licensed under the [Mozilla Public License 2.0](https://mozilla.org/MPL/2.0/).

## Author
© Héctor Bello (ayaxhector666) for Two Level Capital.
