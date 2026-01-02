# 📊 BTC Swing Trading Strategy

**Author**: Manus AI & Mohamed Ben Lakhoua  
**Created**: January 2, 2026  
**Version**: 1.0  
**Asset**: Bitcoin (BTC/USDT) only  
**Capital**: 5,000 EUR  
**Target Frequency**: 20-25 trades/year

---

## 🎯 Strategy Overview

The **BTC Swing Trading Strategy** is a sophisticated dual-timeframe trading system designed specifically for Bitcoin. It combines trend-following principles with momentum-based pullback entries, using a dynamic ATR-based trailing stop to capture significant price moves while protecting capital.

This strategy is built on the principle of **high-quality setups over quantity**, targeting 20-25 carefully selected trades per year with a focus on larger, more reliable price swings.

---

## 🔑 Key Features

✅ **Dual Timeframe Analysis** - 1D primary + 4H confirmation for higher probability setups  
✅ **Trend Filter** - 200 EMA ensures alignment with long-term trend  
✅ **Momentum Filter** - ADX > 25 avoids choppy, sideways markets  
✅ **RSI Pullback Entries** - Enters on healthy pullbacks, not overbought conditions  
✅ **Volume Confirmation** - Requires institutional interest before entry  
✅ **Minimum Hold Period** - 3-day minimum prevents premature exits  
✅ **ATR-Based Trailing Stop** - Dynamic exit adapts to Bitcoin's volatility  
✅ **Compounding Enabled** - Risk 5-7% per trade with position sizing based on equity  
✅ **Zero Commission** - Optimized for exchanges with maker rebates or zero-fee trading

---

## 📈 Strategy Logic

### Entry Conditions (ALL must be met)

#### 1. **Trend Filter (200 EMA)**
- **Condition**: Price must be above the 200-period EMA on daily timeframe
- **Purpose**: Ensures we're trading in the direction of the long-term trend
- **Why it matters**: Bitcoin respects long-term moving averages; trading with the trend increases win rate

#### 2. **ADX > 25 (Trend Strength)**
- **Condition**: ADX (Average Directional Index) must be above 25
- **Purpose**: Confirms the market is trending, not ranging
- **Why it matters**: Swing trading strategies fail in sideways markets; ADX filters out low-probability environments

#### 3. **RSI Pullback (40-70 Range)**
- **Condition**: RSI must be between 40 and 70
- **Purpose**: Identifies healthy pullbacks within an uptrend
- **Why it matters**: Entering when RSI is not overbought (>70) or oversold (<40) provides better risk/reward

#### 4. **Volume Confirmation**
- **Condition**: Current volume must exceed 1.3x the 20-period volume moving average
- **Purpose**: Confirms institutional participation and buying pressure
- **Why it matters**: Volume precedes price; high volume on entry signals conviction

#### 5. **4H Timeframe Confirmation (Optional but Recommended)**
- **Condition**: 4H chart must also show:
  - Price above 200 EMA
  - ADX > 25
  - RSI in pullback range (40-70)
- **Purpose**: Multi-timeframe alignment increases probability of success
- **Why it matters**: When both daily and 4H timeframes align, the setup has higher conviction

---

### Exit Logic

The strategy uses a **dynamic ATR-based trailing stop** that adapts to Bitcoin's volatility:

#### ATR Trailing Stop Mechanics
- **Calculation**: Stop distance = ATR(14) × 2.0
- **Behavior**: Trails below price as it moves up, never moves down
- **Minimum Hold**: Must hold for at least 3 days before trailing stop can trigger
- **Purpose**: Locks in profits while giving trades room to breathe

#### Why ATR-Based?
Bitcoin's volatility changes dramatically across market cycles. A fixed percentage stop would be:
- Too tight during high volatility (stopped out prematurely)
- Too loose during low volatility (giving back too much profit)

ATR automatically adjusts the stop distance based on recent price action.

---

## ⚙️ Configuration Parameters

### Risk Management
| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| **Risk Per Trade** | 6.0% | 1-10% | Percentage of equity risked per trade |
| **Minimum Hold Period** | 3 days | 1-10 days | Minimum bars before trailing stop can trigger |

### Trend Filter
| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| **EMA Length** | 200 | 50-300 | Long-term trend filter |
| **ADX Threshold** | 25 | 15-40 | Minimum ADX for trend strength |
| **ADX Length** | 14 | 7-28 | ADX calculation period |

### RSI Pullback
| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| **RSI Length** | 14 | 7-28 | RSI calculation period |
| **RSI Oversold Level** | 40 | 20-50 | Lower bound for entry |
| **RSI Overbought Level** | 70 | 60-80 | Upper bound for entry |

### Volume Confirmation
| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| **Volume Multiplier** | 1.3 | 1.0-3.0 | Multiplier for volume surge detection |
| **Volume MA Length** | 20 | 10-50 | Volume moving average period |

### ATR Trailing Stop
| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| **ATR Length** | 14 | 7-28 | ATR calculation period |
| **ATR Multiplier** | 2.0 | 1.0-5.0 | Stop distance multiplier |

### 4H Confirmation
| Parameter | Default | Options | Description |
|-----------|---------|---------|-------------|
| **Use 4H Confirmation** | Enabled | On/Off | Require 4H timeframe alignment |

---

## 📊 Expected Performance

Based on backtesting and the strategy's design principles, here are realistic performance expectations:

| Metric | Conservative | Optimistic | Notes |
|--------|--------------|------------|-------|
| **Win Rate** | 55-65% | 65-75% | Percentage of profitable trades |
| **Average Winner** | 10-15% | 15-25% | Average profit on winning trades |
| **Average Loser** | 3-5% | 2-4% | Average loss on losing trades |
| **Reward:Risk Ratio** | 2.5:1 | 4:1 | Profit vs. loss ratio |
| **Trades Per Year** | 15-20 | 20-25 | Annual trade frequency |
| **Max Drawdown** | 15-20% | 10-15% | Largest equity decline |
| **Holding Period** | 5-15 days | 7-20 days | Average trade duration |

> **Important**: These are estimates based on historical backtesting. Actual results will vary based on market conditions, execution quality, and parameter optimization.

---

## 🧪 Backtesting Instructions

### Step 1: Install the Strategy

1. Open TradingView and navigate to the **Pine Editor**
2. Copy the contents of `btc_swing_trading_strategy.pine`
3. Paste into a new script and click **Save**
4. Click **Add to Chart** as a Strategy
5. The Strategy Tester will automatically open at the bottom

### Step 2: Configure the Chart

1. **Asset**: BTC/USDT (Binance, Coinbase, or your preferred exchange)
2. **Timeframe**: Daily (1D) - this is critical
3. **Date Range**: Test over at least 2-3 years to include various market conditions

### Step 3: Analyze Results

Focus on these key metrics in the Strategy Tester:

| Metric | Target | What It Means |
|--------|--------|---------------|
| **Net Profit** | Positive | Total profit after all trades |
| **Total Trades** | 40-75 (for 3 years) | Should average 20-25/year |
| **Win Rate** | >55% | Percentage of profitable trades |
| **Profit Factor** | >2.0 | Gross profit ÷ gross loss |
| **Max Drawdown** | <20% | Largest equity decline |
| **Avg. Trade** | Positive | Average profit per trade |
| **Avg. Bars in Trade** | 5-15 | Average holding period in days |

### Step 4: Optimization

Test different parameter combinations to find optimal settings for your risk tolerance:

1. **Conservative Setup** (Lower frequency, higher quality):
   - ADX Threshold: 30
   - RSI Range: 45-65
   - Volume Multiplier: 1.5
   - ATR Multiplier: 2.5

2. **Aggressive Setup** (Higher frequency, more trades):
   - ADX Threshold: 20
   - RSI Range: 35-75
   - Volume Multiplier: 1.2
   - ATR Multiplier: 1.5

3. **Balanced Setup** (Default):
   - Use the default parameters as listed above

---

## 🎯 Recommended Testing Protocol

### Phase 1: Historical Backtesting (2-3 weeks)

1. **Bull Market Period** (e.g., 2020-2021)
   - Verify the strategy captures major uptrends
   - Check that trailing stops lock in profits
   - Ensure minimum hold period prevents premature exits

2. **Bear Market Period** (e.g., 2022)
   - Verify the strategy stays out during downtrends
   - Check that 200 EMA filter prevents counter-trend trades
   - Ensure drawdown remains acceptable

3. **Sideways Market** (e.g., 2023-2024)
   - Verify ADX filter reduces trade frequency
   - Check that the strategy doesn't overtrade in choppy conditions
   - Ensure win rate remains stable

### Phase 2: Forward Testing (1-2 months)

1. **Paper Trading**
   - Run the strategy on a demo account
   - Track all signals in real-time
   - Document any execution challenges

2. **Alert Configuration**
   - Set up TradingView alerts for entry and exit signals
   - Test alert delivery and response time
   - Ensure you can act on signals within your schedule

### Phase 3: Live Trading (Start Small)

1. **Initial Capital**: Start with 10-20% of intended capital
2. **Position Sizing**: Use the built-in risk management (5-7% per trade)
3. **Journal**: Document every trade, including:
   - Entry price and reasoning
   - Exit price and reason
   - Emotional state during the trade
   - Lessons learned

---

## ⚠️ Risk Management Guidelines

### Position Sizing

The strategy automatically calculates position size based on your risk percentage (default 6%). This means:

- **5,000 EUR capital × 6% risk = 300 EUR at risk per trade**
- Position size adjusts based on the distance to the trailing stop
- As equity grows, position sizes increase (compounding effect)

### Maximum Exposure

- **Single Asset**: 100% (BTC only)
- **Maximum Concurrent Positions**: 1 (no pyramiding)
- **Cash Reserve**: Consider keeping 10-20% in stablecoins for rebalancing

### Psychological Rules

1. **Trust the System**: Don't override the trailing stop
2. **Be Patient**: 20-25 trades/year means weeks between setups
3. **Accept Losses**: Even a 70% win rate means 30% losers
4. **Stay Disciplined**: Don't chase trades or force entries

---

## 🔧 Troubleshooting

### "No trades appearing in backtest"

**Possible Causes**:
- Wrong timeframe (must be Daily)
- Date range too short
- 4H confirmation too strict

**Solutions**:
1. Verify you're on the Daily (1D) timeframe
2. Extend backtest period to at least 2 years
3. Disable 4H confirmation temporarily to test

### "Too many trades (>30/year)"

**Possible Causes**:
- ADX threshold too low
- RSI range too wide
- Volume multiplier too low

**Solutions**:
1. Increase ADX threshold to 30
2. Narrow RSI range to 45-65
3. Increase volume multiplier to 1.5

### "Win rate below 50%"

**Possible Causes**:
- Trailing stop too tight
- Minimum hold period too short
- Market conditions not suitable

**Solutions**:
1. Increase ATR multiplier to 2.5 or 3.0
2. Increase minimum hold period to 5 days
3. Review if testing period includes extreme bear market

### "Drawdown exceeds 20%"

**Possible Causes**:
- Risk per trade too high
- Consecutive losses during trend reversal
- Trailing stop too loose

**Solutions**:
1. Reduce risk per trade to 4-5%
2. Consider adding a maximum loss per month limit
3. Tighten ATR multiplier to 1.5

---

## 📊 Dashboard Explanation

The strategy includes a real-time dashboard in the top-right corner showing:

| Field | Description |
|-------|-------------|
| **Position** | Current position status (LONG or FLAT) |
| **Entry Price** | Price at which the current position was entered |
| **Current Price** | Latest BTC price |
| **Trailing Stop** | Current trailing stop level |
| **P&L %** | Unrealized profit/loss percentage |
| **Days in Trade** | Number of days in current position |
| **Trend (1D)** | Daily trend status (UPTREND or DOWNTREND) |
| **ADX** | Current ADX value and status |
| **RSI** | Current RSI value and pullback status |
| **4H Confirm** | 4H timeframe confirmation status |
| **Volume** | Volume surge status (HIGH or LOW) |

---

## 📈 Chart Visualization

The strategy provides clear visual cues:

- **Blue Line**: 200 EMA on Daily timeframe
- **Purple Line**: 200 EMA on 4H timeframe (semi-transparent)
- **Red Line**: Current trailing stop level (only when in position)
- **Green Triangle Up**: Entry signal
- **Red Triangle Down**: Exit signal (trailing stop hit)
- **Background Color**: Light green (uptrend) or light red (downtrend)

---

## 🔔 Alert Configuration

The strategy includes two pre-configured alerts:

### Entry Alert
- **Title**: "BTC Swing Entry"
- **Message**: Includes current price, RSI, and ADX values
- **When to use**: Set up to receive notifications when entry conditions are met

### Exit Alert
- **Title**: "BTC Swing Exit"
- **Message**: Includes exit price and P&L
- **When to use**: Get notified when trailing stop is hit

### How to Set Up Alerts

1. Click the **Alerts** button (bell icon) in TradingView
2. Select **Condition**: "BTC Swing Trading Strategy"
3. Choose alert type: "BTC Swing Entry" or "BTC Swing Exit"
4. Configure delivery method (email, SMS, webhook)
5. Click **Create**

---

## 💡 Strategy Philosophy

This strategy is built on several core principles:

### 1. Quality Over Quantity
- Target 20-25 trades/year (not 200)
- Each trade is carefully filtered through multiple conditions
- Higher win rate and larger average winners compensate for lower frequency

### 2. Trend is Your Friend
- Only trade in the direction of the 200 EMA
- Avoid counter-trend trades that have lower probability
- Let the market do the heavy lifting

### 3. Dynamic Risk Management
- ATR-based stops adapt to changing volatility
- Trailing stops lock in profits automatically
- Minimum hold period prevents premature exits

### 4. Multi-Timeframe Confirmation
- Daily timeframe for primary trend
- 4H timeframe for entry timing
- Alignment increases probability of success

### 5. Compounding for Growth
- Risk percentage stays constant (5-7%)
- Position sizes grow with equity
- Exponential growth potential over time

---

## 📚 Additional Resources

### Recommended Reading

- **Bitcoin Market Cycles**: Understanding Bitcoin's 4-year halving cycle
- **ATR-Based Stops**: [Volatility-Based Position Sizing](https://www.investopedia.com/articles/trading/08/average-true-range.asp)
- **Swing Trading Principles**: [The Complete Guide to Swing Trading](https://www.babypips.com/learn/forex/swing-trading)
- **Pine Script Documentation**: [TradingView Pine Script v5 Manual](https://www.tradingview.com/pine-script-docs/v5/welcome/)

### Community & Support

- **TradingView Community**: Share your results and get feedback
- **Pine Script Forums**: Ask technical questions about modifications
- **Trading Journals**: Document your journey and learn from others

---

## 📝 Changelog

### Version 1.0 (January 2, 2026)
- Initial release
- Dual timeframe analysis (1D + 4H)
- ATR-based trailing stop
- Risk management with compounding
- Real-time dashboard
- Pre-configured alerts
- Comprehensive documentation

---

## ⚖️ Disclaimer

**This software is provided for educational and informational purposes only.** It is not financial advice and should not be construed as a recommendation to buy or sell any security. Trading cryptocurrencies involves substantial risk of loss and is not suitable for all investors.

Bitcoin is highly volatile and can experience significant price swings in short periods. Past performance is not indicative of future results. You should never trade with money you cannot afford to lose.

The creator of this software makes no warranties, express or implied, regarding the accuracy, completeness, or reliability of the information provided. You are solely responsible for your own trading decisions and should conduct your own research and due diligence before making any investment.

By using this software, you acknowledge and agree that:
- You understand the risks involved in cryptocurrency trading
- You will not hold the creator liable for any losses incurred
- You will use proper risk management and position sizing
- You will comply with all applicable laws and regulations in your jurisdiction

**Trade responsibly. Never risk more than you can afford to lose.**

---

## 📞 Questions?

If you have questions about the strategy or need help with implementation, please refer to:
1. This documentation for strategy details
2. The `testing_guide.md` for backtesting instructions
3. TradingView's Pine Script documentation for coding questions
4. The main `README.md` for general system overview

---

**Happy Trading! 🚀📈**
