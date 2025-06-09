# TRADE INDICATORS IN PINESCRIPT

## Description

This is a repository for different indicators written in pinescript that runs on TradingView platforms

The pinescripts included are:
- **TLC_0TO100FIVEINDICATORS_VOLMOM**:
  This Pine Script indicator, combines five technical indicators (all scaled from 0 to 100) to generate a unified buy/sell signal based on user-selected combinations. The script's originality lies in its ability to allow users to test and combine signals from up to five indicators, enabling 32 possible combinations (2^5) through a configuration menu. This flexibility makes it a valuable tool for educational purposes, allowing users to backtest and evaluate the effectiveness (e.g., win rate) of individual or combined indicator signals.

- **TLC_0TO100FIVEINDICATORS_STRATEGY**:
  This Pine Script strategy, is designed from the indicator TLC_0TO100FIVEINDICATORS_VOLMOM for trading Bitcoin (BTC), it uses a combination of momentum and volatility indicators to generate buy and sell signals. It allows flexible configuration of indicators and risk management settings, making it adaptable to various trading styles and risk tolerances in four predefined risk levels (`COOK`, `WALK`, `HAWK`, `ALLIN`) set maximum drawdown limits (10%, 30%, 50%, 100% respectively).

- **TLC_STRATEGY_EMARSIADX**:
  This Pine Script strategy, developed by Héctor Bello for Two Level Capital, is designed for trading Bitcoin (BTC) and combines multiple technical indicators to generate buy and sell signals. The strategy leverages trend, momentum, volatility, and volume indicators to create a robust trading system. It includes configurable stop-loss (SL) and take-profit (TP) levels, either as percentage-based or ATR-based, and supports backtesting within a specified date range. The strategy is optimized for educational purposes, allowing users to test various signal combinations and evaluate their performance
  
- **DASHIA**:

