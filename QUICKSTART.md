# ⚡ Quick Start Guide - 5 Minutes to Trading

## 🎯 What You're Installing

You're installing **TWO separate scripts**:

| Script | Type | What It Does | Where It Goes |
|--------|------|--------------|---------------|
| **entry_scanner.pine** | Indicator | Scans 40 assets, shows top 5 opportunities | Table on chart |
| **exit_manager.pine** | Strategy | Manages exits with profit targets & stop losses | Signals on chart + Strategy Tester |

---

## 📋 Installation in 3 Steps

### Step 1: Install Entry Scanner (2 minutes)

```
1. TradingView → Pine Editor → Click "+" (New Script)
2. Delete everything
3. Copy ALL of entry_scanner.pine
4. Paste into editor
5. Click "Save" → Name it "Entry Scanner"
6. Click "Add to Chart"
```

**✅ You should see**: A table on the right showing ranked symbols with scores

---

### Step 2: Install Exit Manager (2 minutes)

```
1. Pine Editor → Click "+" AGAIN (New Script - don't reuse!)
2. Delete everything
3. Copy ALL of exit_manager.pine
4. Paste into editor
5. Click "Save" → Name it "Exit Manager"
6. Click "Add to Chart"
```

**✅ You should see**: Buy/sell arrows on chart + Strategy Tester tab opens

---

### Step 3: Customize Your Symbols (1 minute)

**For Entry Scanner:**
1. Click the **gear icon** next to "Entry Scanner"
2. Scroll to find the symbol list (or edit the code directly)
3. Add your favorite assets in format: `"EXCHANGE:SYMBOL"`

**Examples:**
- Crypto: `"BINANCE:BTCUSDT"`, `"BINANCE:ETHUSDT"`
- Stocks: `"NASDAQ:AAPL"`, `"NASDAQ:TSLA"`
- Forex: `"FX:EURUSD"`, `"FX:GBPUSD"`

---

## 🚀 Your First Trade Setup

### Daily Routine:

**Morning (5 minutes):**
1. Open TradingView with Entry Scanner active
2. Check the Top 5 ranked assets in the table
3. Look for scores **≥ 75** (good) or **≥ 85** (strong)

**Before Entering:**
1. Open the chart of the top-ranked asset
2. Apply the Exit Manager strategy
3. Check the backtest results in Strategy Tester
4. If win rate > 60%, consider entering

**After Entering:**
1. Keep Exit Manager on the chart
2. Monitor the info table (top right) for:
   - Current P&L %
   - Downtrend risk level
   - Exit signals
3. Exit when:
   - ✅ 10% profit target hit
   - 🛑 7% stop loss hit
   - ⚠️ Downtrend detected

---

## 🎨 What You'll See

### Entry Scanner Display:
```
┌─────┬──────────┬───────┬──────────┐
│Rank │ Symbol   │ Score │ Signal   │
├─────┼──────────┼───────┼──────────┤
│  1  │ BTCUSDT  │ 87.5  │ 🔥 STRONG│
│  2  │ ETHUSDT  │ 82.0  │ ✅ GOOD  │
│  3  │ AAPL     │ 78.5  │ ✅ GOOD  │
│  4  │ MSFT     │ 76.0  │ ✅ GOOD  │
│  5  │ SPY      │ 74.0  │ ⚠️ WEAK  │
└─────┴──────────┴───────┴──────────┘
```

### Exit Manager Display:
- **Green arrows** ⬆️ = Entry signals
- **Red arrows** ⬇️ = Exit signals
- **Lines on chart**:
  - White dashed = Entry price
  - Green dotted = Profit target
  - Red dotted = Stop loss
  - Orange solid = Trailing stop (when active)

---

## ⚙️ Recommended Settings

### For Conservative Traders:
- Minimum Score: **80**
- Profit Target: **12%**
- Stop Loss: **5%**
- Exit Sensitivity: **Conservative**

### For Moderate Traders (Default):
- Minimum Score: **75**
- Profit Target: **10%**
- Stop Loss: **7%**
- Exit Sensitivity: **Medium**

### For Aggressive Traders:
- Minimum Score: **70**
- Profit Target: **8%**
- Stop Loss: **8%**
- Exit Sensitivity: **Aggressive**

---

## 🎓 Learning Path

**Week 1: Paper Trading**
- Install both scripts
- Watch the signals
- Don't trade real money yet
- Take notes on what works

**Week 2: Backtesting**
- Test on BTC, ETH, AAPL
- Analyze win rates
- Adjust parameters
- Find your comfort zone

**Week 3: Small Positions**
- Start with 1-2% of capital per trade
- Follow the signals strictly
- Keep a trading journal
- Review weekly

**Week 4+: Scale Up**
- If win rate > 60%, increase position size
- Max 5 concurrent positions
- Never risk more than 2% per trade
- Maintain discipline

---

## 🆘 Troubleshooting

| Problem | Solution |
|---------|----------|
| "Two declaration statements" error | You pasted both scripts in one editor - create TWO separate scripts |
| No table showing | Check if Entry Scanner is actually added to chart (look in indicator list) |
| No signals on chart | Exit Manager needs time to calculate - wait for a few bars or scroll back |
| "Symbol not found" | Check symbol format: must be "EXCHANGE:SYMBOL" (e.g., "BINANCE:BTCUSDT") |
| Script too slow | Reduce number of symbols in the scanner (max 40, try 20 first) |

---

## 📱 Mobile Usage

Both scripts work on TradingView mobile app:
1. Install scripts on desktop first
2. Open TradingView mobile app
3. Go to your chart
4. Tap "Indicators" → "My Scripts"
5. Select "Entry Scanner" or "Exit Manager"

---

## ✅ Success Checklist

After 5 minutes, you should have:

- [x] Entry Scanner showing top 5 ranked assets
- [x] Exit Manager showing signals and Strategy Tester
- [x] Both scripts saved and working without errors
- [x] Understanding of what each script does
- [x] Ready to start paper trading

---

**🎉 Congratulations!** You're ready to start using the system. Remember: Start with paper trading, backtest extensively, and never risk more than you can afford to lose.

**Next Steps:**
- Read `testing_guide.md` for backtesting instructions
- Read `README.md` for full documentation
- Join TradingView community to share results

**Happy Trading! 🚀**
