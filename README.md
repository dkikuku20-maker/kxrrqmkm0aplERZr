# Introduction: Bitcoin Hybrid Trading System (DCA + ATR)

In this notebook, we will walk through building a complete rule-based Bitcoin trading system using real market data.

This project is inspired by real-world fintech trading systems that must operate continuously, manage risk, and make decisions automatically.

The one-sentence summary of this project is:

Design a hybrid Bitcoin trading system that accumulates during price drops, manages short-term trades using volatility-adjusted stop-loss rules, and protects capital using portfolio-level safeguards.

This is not a machine learning prediction task.

Instead, this is a systematic decision-engine design problem.

We are building a disciplined system that makes consistent decisions based on rules.

## Project Objective

The goal of this system is to answer one main question:

How can we grow a Bitcoin portfolio while controlling downside risk in a volatile market?

To solve this, we design a hybrid system with two components:

1. Dollar Cost Averaging (DCA)
   - Accumulate Bitcoin when price drops.
   - Long-term capital growth logic.

2. ATR-Based Swing Trading
   - Enter short-term trades.
   - Use volatility-based stop-loss protection.

The system operates on 30-minute market updates and continuously evaluates:

- Portfolio value
- Risk exposure
- Stop-loss conditions
- Trade opportunities

## Trading System Workflow

Although this is not a machine learning model, it follows a structured pipeline similar to ML workflows.

The general structure of our trading system is:

1. Data collection and formatting
2. Data validation and cleaning
3. Feature engineering (volatility indicators)
4. Strategy design (DCA + Swing logic)
5. Risk management implementation
6. Performance evaluation
7. Reporting and monitoring

Just like machine learning pipelines, trading systems are iterative.

We may adjust:

- Risk parameters
- Stop-loss multiplier
- DCA percentage triggers
- Swing entry conditions

based on performance results.

This is not a one-pass system.
It evolves through testing and refinement.
