# Pine Script Strategy & Testing Guide

**Author**: Manus AI
**Date**: Dec 11, 2025

## 1. Introduction

This document provides a comprehensive guide to the two Pine Script strategies developed for identifying high-probability uptrend opportunities and managing exits. The system is designed to be both powerful and transparent, relying on a confluence of proven technical indicators rather than "black box" machine learning predictions, which are not natively supported in Pine Script in a reliable way [1].

The two scripts provided are:

1.  `entry_scanner.pine`: A multi-symbol, multi-factor scanner that ranks up to 40 assets based on a sophisticated scoring system to identify the top 5 most promising uptrend candidates.
2.  `exit_manager.pine`: A strategy script designed for backtesting and live execution that manages trade exits based on a 10% profit target, a hard stop-loss, a dynamic trailing stop, or the detection of a potential downtrend.

> **Disclaimer**: Trading involves significant risk. This tool is for educational and informational purposes only. It is not financial advice. Past performance is not indicative of future results. Always conduct your own research and risk assessment before making any trading decisions.

---

## 2. Strategy Design & Philosophy

Achieving an "80% probability" in trading is an ambitious goal. Instead of pursuing an unattainable prediction model, this strategy focuses on **stacking probabilities** in your favor by requiring a strong consensus among indicators across different categories. This approach, known as indicator confluence, is a robust and widely-used method for increasing the reliability of trade signals [2].

### 2.1. The Entry Scanner Logic

The `entry_scanner.pine` script uses a weighted scoring system (out of 100 points) to evaluate the strength of a potential uptrend. An asset must achieve a minimum score (default is 75) to be considered a valid candidate. The score is derived from five key categories:

| Category | Weight | Description |
| :--- | :--- | :--- |
| **Trend Confirmation** | 30% | Ensures the asset is in a structurally sound long-term uptrend (e.g., 50 EMA > 200 EMA). |
| **Momentum Analysis** | 25% | Confirms that bullish momentum is currently building (e.g., MACD crossover, RSI in a healthy range). |
| **Volume Confirmation** | 20% | Validates the move with strong trading volume, indicating institutional interest and conviction. |
| **Price Action** | 15% | Looks for bullish patterns like higher lows and breakouts, confirming the market structure. |
| **Volatility** | 10% | Assesses market volatility to ensure conditions are favorable for a trend to develop (e.g., ATR expansion). |

This multi-faceted approach ensures that we are not relying on a single indicator, which can often provide false signals. The script then ranks the scanned assets and presents the **Top 5** highest-scoring candidates.

### 2.2. The Exit Manager Logic

The `exit_manager.pine` script is designed to protect capital and lock in profits. It employs a multi-pronged exit strategy:

1.  **Profit Target**: The primary goal is to exit with a **10% gain**.
2.  **Hard Stop-Loss**: A non-negotiable **7% stop-loss** from the entry price to prevent catastrophic losses.
3.  **Trailing Stop**: Once a trade is in profit (e.g., by 5%), a trailing stop activates to lock in gains while allowing the trade to continue running.
4.  **Downtrend Detection**: This is the most complex feature. It monitors for a confluence of bearish signals (e.g., bearish divergences, key support breaks, volume spikes on down moves) to provide an early warning to exit a trade before it reverses significantly.

---

## 3. Installation & Configuration

Follow these steps to set up the scripts in your TradingView account.

### 3.1. Installing the Scripts

1.  **Open Pine Editor**: In TradingView, open the "Pine Editor" tab at the bottom of your chart.
2.  **Copy & Paste**: Open the `entry_scanner.pine` file, copy its entire content, and paste it into a new, blank script in the Pine Editor.
3.  **Save Script**: Click "Save" and give the script a name (e.g., "My Entry Scanner").
4.  **Add to Chart**: Click "Add to Chart". The scanner table will appear on the right side of your screen.
5.  **Repeat for Exit Manager**: Repeat steps 2-4 for the `exit_manager.pine` script. This will be applied as a "Strategy" on your chart.

### 3.2. Configuring the Entry Scanner

-   **Symbol List**: You can customize the list of assets to scan by editing the `symbols` array in the script's code. You can add up to 40 symbols.
-   **Minimum Score**: In the script's "Settings", you can adjust the `Minimum Score for Entry` to make your criteria more or less strict.

### 3.3. Configuring the Exit Manager

-   **Entry Price**: For backtesting, leave `Manual Entry Price` at 0. For live trading, you can input your exact entry price.
-   **Risk Parameters**: Adjust the `Profit Target %`, `Hard Stop Loss %`, and `Trailing Stop %` to match your risk tolerance.
-   **Exit Sensitivity**: This setting (`Conservative`, `Medium`, `Aggressive`) controls how quickly the script will signal an exit based on the downtrend detection logic. "Aggressive" will react to weaker signals, while "Conservative" requires very strong confirmation.

---

## 4. Backtesting Framework

Extensive backtesting is critical to validate any trading strategy. The `exit_manager.pine` script is designed as a `strategy` to allow you to use TradingView's powerful **Strategy Tester**.

### 4.1. How to Backtest

1.  **Apply the Strategy**: Add the `exit_manager.pine` script to the chart of an asset you wish to test (e.g., BTC/USDT).
2.  **Open Strategy Tester**: Go to the "Strategy Tester" tab at the bottom of your chart.
3.  **Configure Settings**:
    *   **Timeframe**: Set the chart timeframe. The strategy is designed for the **Daily** timeframe but can be tested on others.
    *   **Date Range**: Select a long date range to test across different market conditions (e.g., the last 2-3 years).
    *   **Properties**: In the strategy's settings, ensure your initial capital and order size are configured correctly.
4.  **Run the Test**: The Strategy Tester will automatically run, showing you the hypothetical performance of the strategy over the selected period.

### 4.2. Key Performance Metrics to Analyze

When you review the backtesting results, focus on these key metrics:

| Metric | What it Means | Target Goal |
| :--- | :--- | :--- |
| **Net Profit** | The total profit or loss. | Positive |
| **Profit Factor** | Gross profit divided by gross loss. | > 2.0 |
| **Percent Profitable** | The percentage of trades that were winners. | > 60% (80% is the ideal target) |
| **Max Drawdown** | The largest peak-to-trough drop in equity. | < 15% |
| **Avg. Trade** | The average profit or loss per trade. | Positive |
| **Avg. # Bars in Trade** | The average holding period for a trade. | 3-10 bars (for the 3-10 day target) |

> **Important**: Run tests on multiple assets (BTC, ETH, GOOGL, etc.) and across different timeframes and market conditions (bull, bear, and sideways markets) to understand the strategy's robustness.

---

## 5. Live Trading Workflow

1.  **Run the Scanner**: On a daily basis, use the `entry_scanner.pine` indicator to identify the top 5 candidates.
2.  **Manual Review**: Do not trade blindly. Manually review the charts of the top 5 assets. Does the setup look clean? Is there any major news or event that could impact the trade?
3.  **Enter Trade**: If you decide to enter a trade, do so according to your brokerage and position sizing rules.
4.  **Apply Exit Manager**: On the chart of the asset you traded, apply the `exit_manager.pine` strategy. **Crucially, input your exact `Manual Entry Price` in the settings.**
5.  **Manage the Trade**: The script will now display your profit/loss, profit target, stop-loss, and any downtrend warnings. Use these signals to manage your trade according to your plan.

---

## 6. References

[1] Pineify. (2025, January 20). *Machine Learning Pine Script: How to Enhance Your Trading Strategies*. Retrieved from https://pineify.app/resources/blog/machine-learning-pine-script-how-to-enhance-your-trading-strategies

[2] Tradeciety. (2019, February 6). *How To Combine The Best Indicators And Avoid Wrong Signals*. Retrieved from https://tradeciety.com/how-to-choose-the-best-indicators-for-your-trading
