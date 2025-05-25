# TLC_0TO100FIVEINDICATORS_VOLMOM

## Description
This Pine Script indicator, developed by Héctor Bello for Two Level Capital, combines five technical indicators (all scaled from 0 to 100) to generate a unified buy/sell signal based on user-selected combinations. The script's originality lies in its ability to allow users to test and combine signals from up to five indicators, enabling 32 possible combinations (2^5) through a configuration menu. This flexibility makes it a valuable tool for educational purposes, allowing users to backtest and evaluate the effectiveness (e.g., win rate) of individual or combined indicator signals.

The indicators included are:
- **Momentum Indicators**:
  - Relative Strength Index (RSI) with divergence detection
  - Stochastic RSI (STOCH RSI)
- **Volume-Momentum Indicator**:
  - Money Flow Index (MFI)
- **Volatility Indicators**:
  - Relative Volatility Index (RVI)
  - Average Directional Index (ADX)

By default, the script is configured to use all five indicators, optimizing for a higher win rate but potentially reducing the number of trades.

## Features
- **Configurable Indicator Combinations**: Enable or disable RSI, Stochastic RSI, MFI, RVI, and ADX to create custom signal conditions.
- **Buy/Sell Signals**: Generated based on the following conditions:
  - **RSI**: Signals when RSI crosses overbought (default: 70) or oversold (default: 30) levels.
  - **Stochastic RSI**: Signals on K and D line crossovers (without requiring overbought/oversold conditions in this version).
  - **MFI**: Signals when MFI crosses extreme overbought (default: 80) or oversold (default: 20) levels.
  - **RVI**: Signals based on volatility relative to overbought (default: 70) or oversold (default: 30) thresholds.
  - **ADX**: Signals when ADX crosses above a threshold (default: 50) for both buy and sell conditions.
- **RSI Divergence Detection**: Identifies regular and hidden bullish/bearish divergences with configurable lookback and range settings.
- **Moving Average Support**: Optional moving averages for RSI and RVI, with customizable types (SMA, EMA, WMA, VWMA, etc.).
- **Backtesting Support**: Evaluate win rates and trade performance for different indicator combinations using TradingView's backtesting tools.
- **Visualizations**: Plots indicators, buy/sell signals, and horizontal lines for overbought/oversold levels with customizable colors and background fills.

![TLC_0TO100FIVEINDICATORS_VOLMOM](https://github.com/user-attachments/assets/c3f103ad-72a0-4960-88d0-d8079b1b9c1a)


## Installation
1. Copy the provided Pine Script code into the Pine Editor on TradingView.
2. Save the script and add it to your chart.
3. Configure the indicator settings via the TradingView settings menu to enable/disable indicators and adjust parameters.

## Usage
- **Accessing the Indicator**: Open the indicator settings in TradingView to customize which indicators to use, their lengths, and overbought/oversold thresholds.
- **Interpreting Signals**:
  - **Buy Signal**: Displayed as a green "B" label when the selected indicator combination meets the buy conditions.
  - **Sell Signal**: Displayed as a red "S" label when the selected indicator combination meets the sell conditions.
- **Divergence Detection**: Enable RSI divergence in settings to plot bullish (green/yellow) or bearish (red/purple) divergences.
- **Backtesting**: Use TradingView's strategy tester to analyze the win rate and performance of different indicator combinations.
- **Customization**:
  - Adjust indicator lengths (e.g., RSI Length, Stochastic Length, etc.).
  - Modify overbought/oversold levels and ADX threshold.
  - Choose moving average types and lengths for RSI and RVI.

## Parameters
| Parameter | Description | Default |
|-----------|-------------|---------|
| `isRSI` | Enable/disable RSI | `true` |
| `lengthRSI` | RSI calculation length | `14` |
| `isSTOCHK` | Enable/disable Stochastic K | `true` |
| `isSTOCHD` | Enable/disable Stochastic D | `true` |
| `lengthStoch` | Stochastic RSI length | `14` |
| `smoothK` | Stochastic K smoothing | `3` |
| `smoothD` | Stochastic D smoothing | `3` |
| `isMFI` | Enable/disable MFI | `true` |
| `lengthMFI` | MFI calculation length | `14` |
| `isRVI` | Enable/disable RVI | `true` |
| `lengthRVI` | RVI calculation length | `14` |
| `isADX` | Enable/disable ADX | `true` |
| `adxlen` | ADX smoothing length | `14` |
| `dilen` | ADX DI length | `14` |
| `isRSIDiv` | Enable/disable RSI divergence | `true` |
| `lbR` | Right bars for divergence | `5` |
| `lbL` | Left bars for divergence | `5` |
| `rangeUpper` | Max bars for divergence range | `60` |
| `rangeLower` | Min bars for divergence range | `5` |
| `overBought` | Overbought level | `70` |
| `overSold` | Oversold level | `30` |
| `overBoughtExt` | Extreme overbought level (MFI) | `80` |
| `overSoldExt` | Extreme oversold level (MFI) | `20` |
| `adxthreshold` | ADX threshold | `50` |
| `maTypeInput` | Moving average type | `SMA` |

## License
This source code is licensed under the [Mozilla Public License 2.0](https://mozilla.org/MPL/2.0/).

## Contact
For questions or support, contact Héctor Bello at [ayaxhector666@gmail.com](mailto:ayaxhector666@gmail.com).

## Notes
- This indicator is designed for use on TradingView with Pine Script v5.
- The script is optimized for educational purposes, allowing users to test and compare the performance of different indicator combinations.
- The default setting uses all five indicators, which may maximize win rate but reduce trade frequency.
- Test the indicator thoroughly in a demo environment before using it in live trading.
