# TLC_STRATEGY_EMARSIADX

## Description
This Pine Script strategy, developed by Héctor Bello for Two Level Capital, is designed for trading Bitcoin (BTC) and combines multiple technical indicators to generate buy and sell signals. The strategy leverages trend, momentum, volatility, and volume indicators to create a robust trading system. It includes configurable stop-loss (SL) and take-profit (TP) levels, either as percentage-based or ATR-based, and supports backtesting within a specified date range. The strategy is optimized for educational purposes, allowing users to test various signal combinations and evaluate their performance.

The indicators used include:
- **Trend Indicators**:
  - Exponential Moving Averages (EMAs) with customizable lengths
  - SSL Channel (based on moving averages of highs and lows)
  - Volume-Weighted Average Price (VWAP)
- **Momentum Indicators**:
  - Relative Strength Index (RSI) with divergence detection
  - Stochastic RSI
  - Money Flow Index (MFI)
- **Volatility Indicators**:
  - Relative Volatility Index (RVI)
  - Average Directional Index (ADX)
  - Average True Range (ATR) (optional filter)
- **Volume Indicators**:
  - Volume Oscillator
  - Volume Heatmap (based on standard deviation)

The strategy's buy and sell conditions are based on a combination of Stochastic RSI crossovers, RSI, MFI, RVI, and ADX, with optimal performance noted on 3-minute and 5-minute timeframes (e.g., 80% win rate on 3-minute and 87.5% on 5-minute with specific settings).

## Features
- **Configurable Indicators**: Customize EMA lengths, SSL channel, RSI, Stochastic RSI, MFI, RVI, ADX, and volume settings.
- **Buy/Sell Signals**: Generated based on:
  - Stochastic RSI crossovers (K and D lines)
  - RSI below 30 (buy) or above 70 (sell)
  - MFI below 20 (buy) or above 80 (sell)
  - RVI below 70 (buy) or above 30 (sell)
  - ADX above 50 (for both buy and sell)
- **Stop-Loss and Take-Profit**:
  - Optional SL/TP settings, configurable as percentage-based (default: 5% SL, 100% TP) or ATR-based (default: 1x SL, 5x TP multipliers).
- **RSI Divergence Detection**: Identifies regular and hidden bullish/bearish divergences with configurable lookback and range settings.
- **Volume Filtering**: Uses a volume heatmap to filter signals based on standard deviation thresholds.
- **Backtesting Support**: Configurable date range for backtesting (default: July 17, 2010 to December 31, 2024).
- **Visualizations**: Plots SSL channel, EMAs, and buy/sell signals on the chart with customizable colors.

## Installation
1. Copy the provided Pine Script code into the Pine Editor on TradingView.
2. Save the script and add it to your BTC chart.
3. Configure the strategy settings via the TradingView settings menu to adjust indicators, SL/TP, and date ranges.

## Usage
- **Accessing the Strategy**: Open the strategy settings in TradingView to customize indicator parameters, SL/TP settings, and backtesting date range.
- **Interpreting Signals**:
  - **Buy Signal**: Triggered when `bullishCross` conditions are met (e.g., Stochastic RSI crossover, RSI < 30, MFI < 20, RVI < 70, ADX > 50).
  - **Sell Signal**: Triggered when `bearishCross` conditions are met (e.g., Stochastic RSI crossunder, RSI > 70, MFI > 80, RVI > 30, ADX > 50).
- **Backtesting**: Use TradingView's strategy tester to evaluate performance across different timeframes and indicator combinations. Optimal settings include:
  - 3-minute timeframe: ~80% win rate, 5 operations, 8.227 factor gain.
  - 5-minute timeframe: ~87.5% win rate, 8 operations, 9.5 factor gain (with pyramiding = 2: 90%, 11 operations, 13 factor gain).
- **Customization**:
  - Adjust EMA lengths (fast, golden, slow, 100, 200).
  - Enable/disable SL/TP and choose between percentage or ATR-based methods.
  - Modify volume thresholds and ATR filter settings.
  - Configure RSI divergence parameters for enhanced signal accuracy.

## Parameters
| Parameter | Description | Default |
|-----------|-------------|---------|
| `offset` | Plot offset | `0` |
| `maTypeInput` | Moving average type | `SMA` |
| `fromDate` | Backtesting start date | `July 17, 2010` |
| `toDate` | Backtesting end date | `December 31, 2024` |
| `SLTPistaken` | Enable/disable SL/TP | `false` |
| `SLTPviaPerc` | Use percentage-based SL/TP | `false` |
| `stopLoss` | SL percentage | `5` |
| `takeProfit` | TP percentage | `100` |
| `SLTPviaATR` | Use ATR-based SL/TP | `false` |
| `slMultiplier` | SL ATR multiplier | `1.0` |
| `tpMultiplier` | TP ATR multiplier | `5.0` |
| `emaLength` | EMA guide length | `100` |
| `sslen` | SSL channel length | `5` |
| `length` | RSI/RVI/ADX length | `14` |
| `volumeLength` | Volume MA length | `400` |
| `lbR` | Right bars for RSI divergence | `1` |
| `lbL` | Left bars for RSI divergence | `3` |
| `rangeUpper` | Max bars for divergence range | `60` |
| `rangeLower` | Min bars for divergence range | `3` |
| `fastLength` | Fast EMA length | `13` |
| `goldenLength` | Golden EMA length | `21` |
| `slowLength` | Slow EMA length | `48` |
| `smoothK` | Stochastic K smoothing | `3` |
| `smoothD` | Stochastic D smoothing | `3` |
| `thresholdExtraHigh` | Extra high volume threshold | `4.0` |
| `thresholdHigh` | High volume threshold | `2.5` |
| `thresholdMedium` | Medium volume threshold | `1.0` |
| `adxlen` | ADX smoothing length | `14` |
| `dilen` | ADX DI length | `14` |
| `overSold` | RSI oversold level | `30` |
| `overBought` | RSI overbought level | `70` |
| `useATRFilter` | Enable ATR filter | `false` |
| `minATRLength` | Minimum ATR length | `1` |
| `maxATRLength` | Maximum ATR length | `10` |

## License
This source code is licensed under the [Mozilla Public License 2.0](https://mozilla.org/MPL/2.0/).

## Contact
For questions or support, contact Héctor Bello at [ayaxhector666@gmail.com](mailto:ayaxhector666@gmail.com).

## Notes
- This strategy is designed for use on TradingView with Pine Script v5 and is tailored for Bitcoin (BTC).
- The script includes commented-out backtesting results for various signal combinations, indicating optimal performance on 3-minute and 5-minute timeframes.
- The commented `pyramiding`, `default_qty_type`, and `initial_capital` settings suggest potential for position sizing but are currently disabled.
- Test the strategy thoroughly in a demo environment before using it in live trading.
- Some commented signal conditions provide insights into alternative configurations tested by the author, which can be explored for further optimization.
