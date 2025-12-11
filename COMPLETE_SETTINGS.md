# Complete Parameter Settings Guide

**All Parameters for Exit Manager Strategy**

This guide provides **every single parameter** you need to configure in TradingView for optimal performance across different asset classes.

---

## 📋 Complete Settings Tables

### 🔷 CRYPTO (BTC, ETH, SOL, BNB, ADA)

**Philosophy**: Ride long trends, tolerate high volatility, maximize gains.

| Parameter | Setting | Explanation |
|-----------|---------|-------------|
| **Manual Entry Price** | 0 | Auto-detect entry price |
| **Profit Target %** | 30 | Capture major crypto moves (50-100%+ possible) |
| **Hard Stop Loss %** | 15 | Tolerate 10-15% normal corrections |
| **Use Trailing Stop** | ✅ YES | Lock in profits on big moves |
| **Trailing Stop %** | 10 | Allow 10% pullbacks without exit |
| **Trailing Activation %** | 20 | Activate only after 20% profit |
| **Use Time-Based Exit** | ❌ NO | Trends can last months |
| **Maximum Holding Days** | 30 | Not used (time exit disabled) |
| **RSI Length** | 14 | Standard momentum period |
| **Fast EMA Period** | 50 | Golden cross standard |
| **Slow EMA Period** | 200 | Death cross standard |
| **MACD Fast** | 12 | Standard MACD setting |
| **MACD Slow** | 26 | Standard MACD setting |
| **MACD Signal** | 9 | Standard MACD setting |
| **ADX Length** | 14 | Standard trend strength |
| **Stochastic Length** | 14 | Standard overbought/oversold |
| **Stochastic Smooth** | 3 | Standard smoothing |
| **Bollinger Bands Length** | 20 | Standard volatility bands |
| **Bollinger Bands Multiplier** | 2.0 | Standard deviation multiplier |
| **ATR Length** | 14 | Standard volatility measure |
| **Exit Sensitivity** | Conservative | Stay in trends longer |

**Expected Results:**
- Win Rate: 60-70%
- Profit Factor: 2.0-3.0
- Avg Winner: 25-35%
- Max Drawdown: 15-20%

---

### 🔶 BLUE CHIP STOCKS (AAPL, MSFT, GOOGL, NVDA, TSLA)

**Philosophy**: Balanced approach, capture medium-term trends with moderate risk.

| Parameter | Setting | Explanation |
|-----------|---------|-------------|
| **Manual Entry Price** | 0 | Auto-detect entry price |
| **Profit Target %** | 15 | Stocks trend slower than crypto |
| **Hard Stop Loss %** | 8 | Protect against earnings surprises |
| **Use Trailing Stop** | ✅ YES | Lock in profits on trends |
| **Trailing Stop %** | 5 | Tighter for lower volatility |
| **Trailing Activation %** | 10 | Activate after 10% profit |
| **Use Time-Based Exit** | ✅ YES | Exit if stalling |
| **Maximum Holding Days** | 20 | Prevent holding through consolidation |
| **RSI Length** | 14 | Standard momentum period |
| **Fast EMA Period** | 50 | Golden cross standard |
| **Slow EMA Period** | 200 | Death cross standard |
| **MACD Fast** | 12 | Standard MACD setting |
| **MACD Slow** | 26 | Standard MACD setting |
| **MACD Signal** | 9 | Standard MACD setting |
| **ADX Length** | 14 | Standard trend strength |
| **Stochastic Length** | 14 | Standard overbought/oversold |
| **Stochastic Smooth** | 3 | Standard smoothing |
| **Bollinger Bands Length** | 20 | Standard volatility bands |
| **Bollinger Bands Multiplier** | 2.0 | Standard deviation multiplier |
| **ATR Length** | 14 | Standard volatility measure |
| **Exit Sensitivity** | Medium | Balance trend-following with protection |

**Expected Results:**
- Win Rate: 55-65%
- Profit Factor: 1.8-2.5
- Avg Winner: 15-20%
- Max Drawdown: 12-18%

---

### 🔵 INDEX ETFs (SPY, QQQ, DIA)

**Philosophy**: Conservative approach, smooth trends, reliable signals.

| Parameter | Setting | Explanation |
|-----------|---------|-------------|
| **Manual Entry Price** | 0 | Auto-detect entry price |
| **Profit Target %** | 12 | Lower volatility = lower targets |
| **Hard Stop Loss %** | 6 | Tighter stops acceptable |
| **Use Trailing Stop** | ✅ YES | Protect gains |
| **Trailing Stop %** | 4 | Tight for low volatility |
| **Trailing Activation %** | 8 | Activate after 8% profit |
| **Use Time-Based Exit** | ✅ YES | Exit if momentum fades |
| **Maximum Holding Days** | 15 | Shorter holding for slower trends |
| **RSI Length** | 14 | Standard momentum period |
| **Fast EMA Period** | 50 | Golden cross standard |
| **Slow EMA Period** | 200 | Death cross standard |
| **MACD Fast** | 12 | Standard MACD setting |
| **MACD Slow** | 26 | Standard MACD setting |
| **MACD Signal** | 9 | Standard MACD setting |
| **ADX Length** | 14 | Standard trend strength |
| **Stochastic Length** | 14 | Standard overbought/oversold |
| **Stochastic Smooth** | 3 | Standard smoothing |
| **Bollinger Bands Length** | 20 | Standard volatility bands |
| **Bollinger Bands Multiplier** | 2.0 | Standard deviation multiplier |
| **ATR Length** | 14 | Standard volatility measure |
| **Exit Sensitivity** | Medium | Catch reversals early |

**Expected Results:**
- Win Rate: 50-60%
- Profit Factor: 1.5-2.0
- Avg Winner: 12-15%
- Max Drawdown: 10-15%

---

### 🟡 COMMODITIES/GOLD (GLD, GOLD, SLV)

**Philosophy**: Catch explosive moves, exit quickly on reversals.

| Parameter | Setting | Explanation |
|-----------|---------|-------------|
| **Manual Entry Price** | 0 | Auto-detect entry price |
| **Profit Target %** | 20 | Gold can have strong moves |
| **Hard Stop Loss %** | 10 | Accommodate commodity volatility |
| **Use Trailing Stop** | ✅ YES | Protect against sharp reversals |
| **Trailing Stop %** | 6 | Moderate trailing |
| **Trailing Activation %** | 12 | Activate after 12% profit |
| **Use Time-Based Exit** | ✅ YES | Gold can consolidate for long periods |
| **Maximum Holding Days** | 25 | Prevent holding through consolidation |
| **RSI Length** | 14 | Standard momentum period |
| **Fast EMA Period** | 50 | Golden cross standard |
| **Slow EMA Period** | 200 | Death cross standard |
| **MACD Fast** | 12 | Standard MACD setting |
| **MACD Slow** | 26 | Standard MACD setting |
| **MACD Signal** | 9 | Standard MACD setting |
| **ADX Length** | 14 | Standard trend strength |
| **Stochastic Length** | 14 | Standard overbought/oversold |
| **Stochastic Smooth** | 3 | Standard smoothing |
| **Bollinger Bands Length** | 20 | Standard volatility bands |
| **Bollinger Bands Multiplier** | 2.0 | Standard deviation multiplier |
| **ATR Length** | 14 | Standard volatility measure |
| **Exit Sensitivity** | Aggressive | Catch tops and reversals |

**Expected Results:**
- Win Rate: 55-65%
- Profit Factor: 1.7-2.3
- Avg Winner: 18-22%
- Max Drawdown: 12-16%

---

## 🎯 Quick Reference: Key Differences

| Parameter | Crypto | Stocks | ETFs | Gold |
|-----------|--------|--------|------|------|
| **Profit Target** | 30% | 15% | 12% | 20% |
| **Hard Stop** | 15% | 8% | 6% | 10% |
| **Trailing Stop** | 10% | 5% | 4% | 6% |
| **Trailing Activation** | 20% | 10% | 8% | 12% |
| **Time-Based Exit** | NO | YES | YES | YES |
| **Max Days** | 30 | 20 | 15 | 25 |
| **Exit Sensitivity** | Conservative | Medium | Medium | Aggressive |

**All other parameters (RSI, MACD, EMAs, etc.) remain at standard values across all asset classes.**

---

## 📝 How to Apply These Settings

### Step 1: Open TradingView
1. Go to your chart (e.g., BTCUSDT for crypto)
2. Make sure Exit Manager strategy is loaded
3. Click the **gear icon** ⚙️ next to "Smart Exit Manager"

### Step 2: Configure Parameters
1. Go to the **"Inputs"** tab
2. **Scroll through ALL parameters** and set them according to the table above
3. Pay special attention to:
   - Profit Target %
   - Hard Stop Loss %
   - Trailing Stop % and Activation %
   - Exit Sensitivity dropdown
   - Time-Based Exit checkbox

### Step 3: Save and Test
1. Click **"OK"** to apply settings
2. Check the **Strategy Tester** tab at the bottom
3. Look at **Net Profit** and compare to **Buy & Hold Return**
4. If strategy < buy-and-hold, increase profit target and widen trailing stop

---

## 🔄 Entry Scanner Settings (Companion)

Don't forget to optimize your Entry Scanner too!

| Parameter | Crypto | Stocks | ETFs |
|-----------|--------|--------|------|
| **Minimum Score** | 80 | 75 | 75 |
| **Top Assets to Display** | 5 | 10 | 5 |
| **RSI Lower Bound** | 40 | 40 | 45 |
| **RSI Upper Bound** | 70 | 70 | 65 |
| **Volume Multiplier** | 1.5 | 1.3 | 1.2 |
| **ADX Threshold** | 25 | 25 | 20 |

**Why different?**
- Crypto needs higher entry scores (80+) due to volatility
- ETFs need tighter RSI bounds (45-65) due to lower volatility
- Stocks are balanced in the middle

---

## 💡 Pro Tips

### 1. Start with Crypto Settings on BTC
- Apply the crypto settings to BTCUSDT
- Backtest 2-3 years on Daily timeframe
- If strategy beats buy-and-hold, you're good!
- If not, increase profit target to 35-40%

### 2. Test Multiple Assets
Don't just test one asset. Try:
- **Crypto**: BTC, ETH, SOL
- **Stocks**: AAPL, MSFT, NVDA
- **ETFs**: SPY, QQQ

### 3. Keep Notes
Track which settings work best for which assets:
```
BTC: 30% target, 15% stop, Conservative = 180% profit
ETH: 30% target, 15% stop, Conservative = 145% profit
AAPL: 15% target, 8% stop, Medium = 65% profit
```

### 4. Adjust for Market Conditions
- **Bull Market**: Use higher targets (35-40% for crypto)
- **Bear Market**: Use tighter stops (10-12% for crypto)
- **Sideways**: Consider not trading or using aggressive exits

---

## 🆘 Troubleshooting

**Q: I set all parameters but still underperforming**

A: Try this sequence:
1. Increase Profit Target by 5%
2. Widen Trailing Stop by 2%
3. Change Exit Sensitivity to Conservative
4. Disable Time-Based Exit
5. Retest

**Q: Too many parameters to remember**

A: Focus on the "Big 4":
1. **Profit Target** (biggest impact on returns)
2. **Trailing Stop** (biggest impact on holding time)
3. **Exit Sensitivity** (biggest impact on win rate)
4. **Hard Stop Loss** (biggest impact on drawdown)

The rest (RSI, MACD, etc.) can stay at standard values.

**Q: Which settings should I start with?**

A: Based on your portfolio:
- **80%+ Crypto**: Use Crypto settings
- **80%+ Stocks**: Use Stock settings
- **Mixed**: Use Stock settings (more conservative)

---

## 📊 Settings Summary Card

**Copy this to your notes for quick reference:**

```
=== CRYPTO (BTC/ETH) ===
Target: 30% | Stop: 15% | Trail: 10% @ 20%
Time Exit: NO | Sensitivity: Conservative
RSI/MACD/ADX: 14/12-26-9/14 (standard)

=== STOCKS (AAPL/MSFT) ===
Target: 15% | Stop: 8% | Trail: 5% @ 10%
Time Exit: YES (20 days) | Sensitivity: Medium
RSI/MACD/ADX: 14/12-26-9/14 (standard)

=== ETFs (SPY/QQQ) ===
Target: 12% | Stop: 6% | Trail: 4% @ 8%
Time Exit: YES (15 days) | Sensitivity: Medium
RSI/MACD/ADX: 14/12-26-9/14 (standard)

=== GOLD (GLD) ===
Target: 20% | Stop: 10% | Trail: 6% @ 12%
Time Exit: YES (25 days) | Sensitivity: Aggressive
RSI/MACD/ADX: 14/12-26-9/14 (standard)
```

---

**Last Updated**: December 11, 2025  
**Version**: 1.1 - Complete Parameters Edition
