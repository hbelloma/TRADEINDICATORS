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

## Example Configuration
- Enable RSI, STOCHRSI, and MFI with default lengths (14).
- Set XMA guide to EMA(200) and enable volume filter with a medium threshold (1.0).
- Use `PERCENTAGE` SL/TP with 2% stop loss and 10% take profit.
- Select `WALK` risk plan for 30% max drawdown.
- Set trading period from July 17, 2010, to December 31, 2024.

## Notes
- The strategy is designed for flexibility but requires careful parameter tuning for specific markets and timeframes.
- Backtest thoroughly before deploying in live trading.
- Contact Héctor Bello (ayaxhector666@gmail.com) for questions or support.

## License
This source code is licensed under the [Mozilla Public License 2.0](https://mozilla.org/MPL/2.0/).

## Author
© Héctor Bello (ayaxhector666) for Two Level Capital.