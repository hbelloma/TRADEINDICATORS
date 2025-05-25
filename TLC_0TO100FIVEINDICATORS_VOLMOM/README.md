{\rtf1\ansi\ansicpg1252\cocoartf2822
\cocoatextscaling0\cocoaplatform0{\fonttbl\f0\fnil\fcharset0 Menlo-Regular;\f1\fnil\fcharset0 Menlo-Bold;\f2\fmodern\fcharset0 Courier;
}
{\colortbl;\red255\green255\blue255;\red42\green44\blue51;\red249\green249\blue249;\red219\green63\blue57;
\red14\green112\blue174;}
{\*\expandedcolortbl;;\cssrgb\c21961\c22745\c25882;\cssrgb\c98039\c98039\c98039;\cssrgb\c89412\c33725\c28627;
\cssrgb\c392\c51765\c73725;}
\margl1440\margr1440\vieww11520\viewh8400\viewkind0
\deftab720
\pard\pardeftab720\partightenfactor0

\f0\fs26 \cf2 \cb3 \expnd0\expndtw0\kerning0
\outl0\strokewidth0 \strokec2 #\cf4 \strokec4  TLC_0TO100FIVEINDICATORS_VOLMOM\cf2 \strokec2 \
\
##\cf4 \strokec4  Description\cf2 \strokec2 \
This Pine Script indicator, developed by H\'e9ctor Bello for Two Level Capital, combines five technical indicators (all scaled from 0 to 100) to generate a unified buy/sell signal based on user-selected combinations. The script's originality lies in its ability to allow users to test and combine signals from up to five indicators, enabling 32 possible combinations (2^5) through a configuration menu. This flexibility makes it a valuable tool for educational purposes, allowing users to backtest and evaluate the effectiveness (e.g., win rate) of individual or combined indicator signals.\
\
The indicators included are:\
- 
\f1\b **Momentum Indicators**
\f0\b0 :\
  - Relative Strength Index (RSI) with divergence detection\
  - Stochastic RSI (STOCH RSI)\
- 
\f1\b **Volume-Momentum Indicator**
\f0\b0 :\
  - Money Flow Index (MFI)\
- 
\f1\b **Volatility Indicators**
\f0\b0 :\
  - Relative Volatility Index (RVI)\
  - Average Directional Index (ADX)\
\
By default, the script is configured to use all five indicators, optimizing for a higher win rate but potentially reducing the number of trades.\
\
##\cf4 \strokec4  Features\cf2 \strokec2 \
- 
\f1\b **Configurable Indicator Combinations**
\f0\b0 : Enable or disable RSI, Stochastic RSI, MFI, RVI, and ADX to create custom signal conditions.\
- 
\f1\b **Buy/Sell Signals**
\f0\b0 : Generated based on the following conditions:\
  - 
\f1\b **RSI**
\f0\b0 : Signals when RSI crosses overbought (default: 70) or oversold (default: 30) levels.\
  - 
\f1\b **Stochastic RSI**
\f0\b0 : Signals on K and D line crossovers (without requiring overbought/oversold conditions in this version).\
  - 
\f1\b **MFI**
\f0\b0 : Signals when MFI crosses extreme overbought (default: 80) or oversold (default: 20) levels.\
  - 
\f1\b **RVI**
\f0\b0 : Signals based on volatility relative to overbought (default: 70) or oversold (default: 30) thresholds.\
  - 
\f1\b **ADX**
\f0\b0 : Signals when ADX crosses above a threshold (default: 50) for both buy and sell conditions.\
- 
\f1\b **RSI Divergence Detection**
\f0\b0 : Identifies regular and hidden bullish/bearish divergences with configurable lookback and range settings.\
- 
\f1\b **Moving Average Support**
\f0\b0 : Optional moving averages for RSI and RVI, with customizable types (SMA, EMA, WMA, VWMA, etc.).\
- 
\f1\b **Backtesting Support**
\f0\b0 : Evaluate win rates and trade performance for different indicator combinations using TradingView's backtesting tools.\
- 
\f1\b **Visualizations**
\f0\b0 : Plots indicators, buy/sell signals, and horizontal lines for overbought/oversold levels with customizable colors and background fills.\
\
##\cf4 \strokec4  Installation\cf2 \strokec2 \
1. Copy the provided Pine Script code into the Pine Editor on TradingView.\
2. Save the script and add it to your chart.\
3. Configure the indicator settings via the TradingView settings menu to enable/disable indicators and adjust parameters.\
\
##\cf4 \strokec4  Usage\cf2 \strokec2 \
- 
\f1\b **Accessing the Indicator**
\f0\b0 : Open the indicator settings in TradingView to customize which indicators to use, their lengths, and overbought/oversold thresholds.\
- 
\f1\b **Interpreting Signals**
\f0\b0 :\
  - 
\f1\b **Buy Signal**
\f0\b0 : Displayed as a green "B" label when the selected indicator combination meets the buy conditions.\
  - 
\f1\b **Sell Signal**
\f0\b0 : Displayed as a red "S" label when the selected indicator combination meets the sell conditions.\
- 
\f1\b **Divergence Detection**
\f0\b0 : Enable RSI divergence in settings to plot bullish (green/yellow) or bearish (red/purple) divergences.\
- 
\f1\b **Backtesting**
\f0\b0 : Use TradingView's strategy tester to analyze the win rate and performance of different indicator combinations.\
- 
\f1\b **Customization**
\f0\b0 :\
  - Adjust indicator lengths (e.g., RSI Length, Stochastic Length, etc.).\
  - Modify overbought/oversold levels and ADX threshold.\
  - Choose moving average types and lengths for RSI and RVI.\
\
##\cf4 \strokec4  Parameters\cf2 \strokec2 \
|\cf4 \strokec4  Parameter \cf2 \strokec2 |\cf4 \strokec4  Description \cf2 \strokec2 |\cf4 \strokec4  Default \cf2 \strokec2 |\
|-----------|-------------|---------|\
| `isRSI` | Enable/disable RSI | `true` |\
| `lengthRSI` | RSI calculation length | `14` |\
| `isSTOCHK` | Enable/disable Stochastic K | `true` |\
| `isSTOCHD` | Enable/disable Stochastic D | `true` |\
| `lengthStoch` | Stochastic RSI length | `14` |\
| `smoothK` | Stochastic K smoothing | `3` |\
| `smoothD` | Stochastic D smoothing | `3` |\
| `isMFI` | Enable/disable MFI | `true` |\
| `lengthMFI` | MFI calculation length | `14` |\
| `isRVI` | Enable/disable RVI | `true` |\
| `lengthRVI` | RVI calculation length | `14` |\
| `isADX` | Enable/disable ADX | `true` |\
| `adxlen` | ADX smoothing length | `14` |\
| `dilen` | ADX DI length | `14` |\
| `isRSIDiv` | Enable/disable RSI divergence | `true` |\
| `lbR` | Right bars for divergence | `5` |\
| `lbL` | Left bars for divergence | `5` |\
| `rangeUpper` | Max bars for divergence range | `60` |\
| `rangeLower` | Min bars for divergence range | `5` |\
| `overBought` | Overbought level | `70` |\
| `overSold` | Oversold level | `30` |\
| `overBoughtExt` | Extreme overbought level (MFI) | `80` |\
| `overSoldExt` | Extreme oversold level (MFI) | `20` |\
| `adxthreshold` | ADX threshold | `50` |\
| `maTypeInput` | Moving average type | `SMA` |\
\
##\cf4 \strokec4  License\cf2 \strokec2 \
This source code is licensed under the \cf5 \strokec5 [Mozilla Public License 2.0](https://mozilla.org/MPL/2.0/)\cf2 \strokec2 .\
\
##\cf4 \strokec4  Contact\cf2 \strokec2 \
For questions or support, contact H\'e9ctor Bello at \cf5 \strokec5 [ayaxhector666@gmail.com](mailto:ayaxhector666@gmail.com)\cf2 \strokec2 .\
\
##\cf4 \strokec4  Notes\cf2 \strokec2 \
- This indicator is designed for use on TradingView with Pine Script v5.\
- The script is optimized for educational purposes, allowing users to test and compare the performance of different indicator combinations.\
- The default setting uses all five indicators, which may maximize win rate but reduce trade frequency.\
- Test the indicator thoroughly in a demo environment before using it in live trading.
\f2 \
}
