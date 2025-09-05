 # DASHIA: Machine Learning STRATEGY

## Description
The `DASHIA` (Data Analyst and Swapper via Hawkish Intelligent Approach) Pine Script strategy, developed by H\'e9ctor Bello for Two Level Capital, is a sophisticated machine learning-based trading system designed for TradingView. It employs a Lorentzian Distance-based Approximate Nearest Neighbors (ANN) algorithm to predict price movements over a 4-bar horizon. The strategy integrates multiple technical indicators as features, including RSI, Stochastic RSI, MFI, RVI, ADX, CCI, and WaveTrend, and uses kernel regression (Rational Quadratic and Gaussian) for trend filtering. It supports customizable risk management, stop-loss (SL), and take-profit (TP) settings, with backtesting capabilities for performance evaluation.

This strategy is tailored for Bitcoin (BTC) trading but can be adapted to other assets. It emphasizes feature engineering, allowing users to select up to 10 indicators as input features, and includes filters (volatility, regime, ADX, EMA, SMA, and Stochastic KD cross) to refine trade signals. The system is designed for educational purposes and requires thorough backtesting before live use.

## Features
- **Machine Learning Model**:
  - Uses Lorentzian Distance for ANN to predict price direction (long, short, neutral) over 4 bars.
  - Supports 2\'9610 customizable features (e.g., RSI, Stochastic RSI, MFI, RVI, ADX, CCI, WaveTrend).
- **Technical Indicators**:
  - Normalized indicators for ML compatibility (RSI, Stochastic K/D, MFI, RVI, CCI, WaveTrend, ADX).
  - Kernel regression (Rational Quadratic and Gaussian) for trend detection.
- **Trade Signals**:
  - **Buy Signal**: Triggered when prediction is positive, with bullish kernel, EMA/SMA uptrend, and optional Stochastic KD crossover.
  - **Sell Signal**: Triggered when prediction is negative, with bearish kernel, EMA/SMA downtrend, and optional Stochastic KD crossunder.
- **Risk Management**:
  - Configurable risk plans: COOK (10% drawdown, x1 leverage), WALK (30%, x2\'96x5), HAWK (50%, x10\'96x100), ALLIN (100%, no limit).
  - Position sizing based on equity percentage (default: 100%) and SL.
- **Stop-Loss and Take-Profit**:
  - Methods: None, Percentage-based (default: 2% SL, 10% TP), ATR-based (default: 1x SL, 5x TP multipliers).
  - Optional trailing SL (default: 1% trail).
- **Filters**:
  - Volatility (ATR), regime (trend detection), ADX, EMA, SMA, and Stochastic KD crossover filters.
- **Backtesting**:
  - Configurable date range (default: July 17, 2010 to December 31, 2024).
  - Displays trade stats (win rate, trades, W/L ratio, early signal flips) for calibration.
- **Visualizations**:
  - Plots buy/sell signals, kernel estimates, and bar colors based on predictions.
  - Optional trade stats table and bar prediction values.

<img width="1100" height="505" alt="DASHIASTEXAMPLE" src="https://github.com/user-attachments/assets/d9f32f57-e0c9-4930-a51f-ca2d0c2bf431" />

Plot showing DASHIA strategy on a BTCUSDT chart for 1 H time-frame, we can see the Gaussian (bullish/blue, bearish/yellow curves) and Rational Quadratic (bullish/green, bearish/red curves) kernels and how its color change when bullish or bearish trends appear, also the buy (green) and sell (red) signals markers are shown, and a small chart on the upper right side showing an incode implemented backtest of 91.7%

## Backtesting
For a briefly description we shown the backtesting for 1 HOUR and 1 min charts for bullish periods, if you like to know more about the backtesting read the ArXiv: 


-**1 HOUR Backtest Results**
The 1-hour backtest covered 09 November 2021 to 30 May 2025, splitting into a bearish period (09 November 2021 to 12 January 2023, declining from $69,000 to $16,500) and a bullish period (12 January 2023 to 30 May 2025, rising to $120,000 ATH). Here we are asumming an ALLIN risk strategy unless a risk strategy is mentioned.

<img width="1097" height="542" alt="Summary1HBear0911201_120123" src="https://github.com/user-attachments/assets/e3013b52-ce00-4b79-9ac8-1b2680be2814" />

Backtesting Results on 1-Hour Chart bearish case (09/11/2021 to
12/01/2023). Placeholder for equity curve and drawdown percentage, green-
red line is for DASHIA performance and blue line for Buy and Hold strategy.

-**1 minute Backtest Results**
The Premium plan provides data for 2 weeks, but here we are using a deep
test facility which gives data up to 2 months + 1 week. For the 1-minute
backtest we use the period from 19 February 2025 to 30 May 2025 (Figure 5),
splitting into a bearish period (19 February 2025 to 13 April 2025 declining
from $98,000 to $75,000) and a bullish period (28 March 2025 to 30 May
2025 rising to $120,000 ATH) we have used deep analysis, assuming full data
acces and ALLIN risk stretegy.

<img width="1173" height="547" alt="SUM1902_1304_2025" src="https://github.com/user-attachments/assets/641898e9-a2ab-4c36-9e56-b4ef720c301b" />

Backtesting Results on 1-Minute Chart bearish case (19/02/2025 to
13/04/2025). Placeholder for equity curve and drawdown percentage, green-
red line is for DASHIA performance and blue line for Buy and Hold strategy.


## Installation
1. Copy the Pine Script code into the Pine Editor on TradingView.
2. Save the script and add it to your chart (preferably BTC/USD).
3. Configure the strategy settings via the TradingView settings menu to adjust features, filters, risk, and SL/TP.

## Usage
- **Accessing the Strategy**: Open the strategy settings in TradingView to customize:
  - **General Settings**: Source, neighbors count (default: 8), max bars back (default: 8000), feature count (default: 10).
  - **Feature Engineering**: Select indicators (e.g., STOCHK, STOCHD, RSI, ADX) and their parameters.
  - **Filters**: Enable/disable volatility, regime, ADX, EMA, SMA, and KD cross filters.
  - **Risk Management**: Choose a risk plan and equity percentage.
  - **SL/TP**: Select method (None, Percentage, ATR) and configure levels.
  - **Kernel Settings**: Adjust lookback window, regression level, and relative weighting.
- **Interpreting Signals**:
  - **Buy Signal**: Green label below bar when ML predicts upward movement, filtered by bullish conditions.
  - **Sell Signal**: Red label above bar when ML predicts downward movement, filtered by bearish conditions.
- **Backtesting**: Use TradingView\'92s strategy tester to evaluate performance. Monitor trade stats for optimization (not a replacement for full backtesting).
- **Customization**:
  - Adjust feature parameters (e.g., RSI length, Stochastic smoothing).
  - Toggle filters to refine signal frequency.
  - Modify kernel settings for trend sensitivity.
  - Experiment with SL/TP and risk settings for different market conditions.

## Parameters
| Parameter | Description | Default |
|-----------|-------------|---------|
| `source` | Input data source | `close` |
| `neighborsCount` | Number of ANN neighbors | `8` |
| `maxBarsBack` | Maximum historical bars | `8000` |
| `featureCount` | Number of ML features | `10` |
| `colorCompression` | Color scale intensity | `1` |
| `showExits` | Show exit signals | `false` |
| `useDynamicExits` | Use dynamic exits | `false` |
| `fromDate` | Backtesting start date | `July 17, 2010` |
| `toDate` | Backtesting end date | `December 31, 2024` |
| `Plan` | Risk management plan | `ALLIN` |
| `riskCapital` | Equity percentage for position sizing | `100` |
| `SLTPMethod` | SL/TP method | `NONE` |
| `stopLoss` | SL percentage | `2.0` |
| `takeProfit` | TP percentage | `10.0` |
| `slMultiplier` | SL ATR multiplier | `1.0` |
| `tpMultiplier` | TP ATR multiplier | `5.0` |
| `trailPercent` | Trailing SL percentage | `1.0` |
| `useVolatilityFilter` | Enable volatility filter | `false` |
| `useRegimeFilter` | Enable regime filter | `false` |
| `useAdxFilter` | Enable ADX filter | `false` |
| `regimeThreshold` | Regime filter threshold | `-0.1` |
| `adxThreshold` | ADX filter threshold | `20` |
| `useCrossKDFilter` | Enable KD crossover filter | `true` |
| `useEmaFilter` | Enable EMA filter | `false` |
| `emaPeriod` | EMA period | `200` |
| `useSmaFilter` | Enable SMA filter | `false` |
| `smaPeriod` | SMA period | `200` |
| `h` | Kernel lookback window | `8` |
| `x` | Kernel regression level | `25` |
| `r` | Kernel relative weighting | `8.0` |
| `lag` | Kernel lag for crossover | `2` |
| `f1_string`\'96`f10_string` | Feature indicators | `STOCHK`, `STOCHD`, `RSI`, `ADX`, `MFI`, `RVI`, `WT`, `CCI`, `RSI`, `ADX2` |
| `f1_paramA`\'96`f10_paramA` | Primary feature parameters | Varies (e.g., `14`) |
| `f1_paramB`\'96`f10_paramB` | Secondary feature parameters | Varies (e.g., `3`) |

## License
This source code is licensed under the [Mozilla Public License 2.0](https://mozilla.org/MPL/2.0/).

## Contact
For questions or support, contact H\'e9ctor Bello at [ayaxhector666@gmail.com](mailto:ayaxhector666@gmail.com).

## Notes
- **Intended Use**: Designed for educational purposes and testing on TradingView with Pine Script v5. Thoroughly backtest before live trading.
- **Asset Focus**: Optimized for Bitcoin (BTC) but adaptable to other assets.
- **Performance**: Trade stats are for calibration, not a substitute for comprehensive backtesting. Early signal flips indicate choppy markets.
- **Limitations**: The 4-bar prediction horizon is hardcoded. Dynamic exits are disabled if EMA, SMA, or kernel smoothing is used.
- **Dependencies**: No external libraries required.
- **Warnings**:
  - Test in a demo environment before live trading.
  - High leverage (e.g., HAWK, ALLIN plans) increases risk significantly.
  - Ensure feature selections are unique to avoid redundancy in ML predictions.
