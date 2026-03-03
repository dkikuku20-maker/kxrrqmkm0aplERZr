# Smart Bitcoin Trading Agent

## Project Overview

This project implements a rule-based Bitcoin trading system designed to operate with minimal human supervision.

The objective of this assignment was not to build a hedge fund strategy, but to demonstrate:

- Hybrid trading strategy design (DCA + Swing)
- Volatility-based stop-loss using ATR
- Portfolio-level risk management
- Risk metrics calculation (Maximum Drawdown, Sharpe Ratio)
- Basic automation using Telegram notifications

The system uses real historical Bitcoin price data and simulates trading decisions.

---

# System Architecture

The trading system consists of the following components:

1. Data download using Yahoo Finance (yfinance)
2. Data cleaning and preprocessing
3. Dollar-Cost Averaging (DCA) base strategy
4. Swing trading layer with ATR-based stop-loss
5. Portfolio-level drawdown safeguard
6. Risk metrics evaluation
7. Telegram notification integration

This structure demonstrates both trading logic and system-level thinking.

---

# Strategy Design

## 1. Dollar-Cost Averaging (DCA)

The system buys $500 worth of Bitcoin whenever the price drops 3% from the last DCA buy.

Purpose:
- Reduce emotional decision-making
- Accumulate Bitcoin gradually during market dips
- Lower average cost over time

---

## 2. Swing Trading (Short-Term Layer)

The system opens small short-term trades when simple trend conditions are met.

Each swing trade includes a volatility-based stop-loss:

Stop-Loss = Entry Price − (ATR × k)

Where:
- ATR = Average True Range (market volatility)
- k = configurable multiplier

Purpose:
- Capture short-term market movements
- Adapt stop-loss distance to volatility
- Avoid fixed-percentage stops

---

# Risk Management

## Portfolio-Level Safeguard

If total portfolio value drops 25% from its highest value:

- The system pauses new trades
- Stop-loss exits are still allowed

This prevents excessive losses during major market crashes.

---

## Maximum Drawdown

Maximum drawdown measures the largest peak-to-trough decline during the simulation.

This helps evaluate worst-case loss exposure.

---

## Sharpe Ratio

Sharpe Ratio measures risk-adjusted return.

It compares:

- Average returns
- Versus return volatility

This helps evaluate performance stability.

---

# Data Source

Bitcoin historical data is downloaded using:

- yfinance (Yahoo Finance API)
- Daily and 30-minute candle intervals

This allows realistic backtesting using real market data.

---

# Installation Requirements

Install required Python packages:

```bash
pip install pandas numpy yfinance matplotlib requests
