# 📥 Installation Guide - Step by Step

## ⚠️ Important: Install Each Script Separately!

Each Pine Script file must be installed as a **separate script** in TradingView. You cannot paste both scripts into the same editor window.

---

## 🔧 Step-by-Step Installation

### Part 1: Install the Entry Scanner

1. **Open TradingView** and go to any chart
2. **Click on "Pine Editor"** tab at the bottom of the screen
3. **Click the "+" icon** or "New" to create a new blank script
4. **Delete all default code** in the editor
5. **Open the file** `entry_scanner.pine` from this repository
6. **Copy the ENTIRE contents** of `entry_scanner.pine`
7. **Paste it** into the Pine Editor (replacing everything)
8. **Click "Save"** and name it something like "My Entry Scanner"
9. **Click "Add to Chart"** - You should see a table appear on the right side showing ranked assets

✅ **Success**: You should see a scoring table with symbols and their scores!

---

### Part 2: Install the Exit Manager

1. **In the Pine Editor, click the "+" icon again** to create a NEW script (don't reuse the previous one!)
2. **Delete all default code** in the new editor
3. **Open the file** `exit_manager.pine` from this repository
4. **Copy the ENTIRE contents** of `exit_manager.pine`
5. **Paste it** into the Pine Editor
6. **Click "Save"** and name it something like "My Exit Manager"
7. **Click "Add to Chart"** - This will add it as a Strategy
8. **The Strategy Tester** tab will automatically open at the bottom

✅ **Success**: You should see buy/sell signals on your chart and performance metrics in the Strategy Tester!

---

## 🎯 Quick Test

### Test the Entry Scanner:
1. Make sure it's applied to your chart
2. Look at the table on the right side
3. You should see symbols ranked by score (e.g., BTCUSDT: 82.5)
4. The top 5 highest scores are your best opportunities

### Test the Exit Manager:
1. Apply it to a chart (e.g., BTCUSDT on Daily timeframe)
2. Look at the Strategy Tester tab at the bottom
3. You should see:
   - Number of trades
   - Win rate percentage
   - Profit/loss metrics
   - Entry and exit points marked on the chart

---

## 🐛 Common Errors & Solutions

### Error: "Scripts must contain one declaration statement"
**Cause**: You pasted both scripts into the same editor window  
**Solution**: Create TWO separate scripts - one for entry_scanner.pine, one for exit_manager.pine

### Error: "Script execution exceeded time limit"
**Cause**: Scanning too many symbols or complex calculations  
**Solution**: Reduce the number of symbols in the `symbols` array in entry_scanner.pine

### Error: "Undeclared identifier"
**Cause**: Copy/paste didn't capture the entire script  
**Solution**: Make sure you copied from the very first line (`//@version=5`) to the last line

### Error: "No data for this symbol"
**Cause**: One of the symbols in the scanner doesn't exist or has wrong format  
**Solution**: Check the symbol names in the `symbols` array - they should be in format "EXCHANGE:SYMBOL" (e.g., "BINANCE:BTCUSDT")

---

## 📝 Customization After Installation

### For Entry Scanner:
1. Click the **gear icon** (Settings) next to the script name
2. Adjust:
   - `Minimum Score for Entry` (default: 75)
   - `Number of Top Assets to Display` (default: 5)
   - Indicator parameters (RSI, MACD, etc.)

### For Exit Manager:
1. Click the **gear icon** (Settings) next to the strategy name
2. Adjust:
   - `Profit Target %` (default: 10%)
   - `Hard Stop Loss %` (default: 7%)
   - `Exit Sensitivity` (Conservative/Medium/Aggressive)

---

## 🎬 Video Tutorial Alternative

If you prefer visual instructions, search YouTube for:
- "How to add Pine Script indicator to TradingView"
- "How to add Pine Script strategy to TradingView"

The process is the same for any Pine Script code.

---

## ✅ Verification Checklist

After installation, you should have:

- [ ] Entry Scanner showing a table with ranked symbols
- [ ] Exit Manager showing buy/sell signals on chart
- [ ] Strategy Tester tab showing performance metrics
- [ ] No error messages in Pine Editor
- [ ] Both scripts saved with descriptive names

---

## 🆘 Still Having Issues?

If you're still encountering errors:

1. **Check the Pine Script version**: Make sure the first line is `//@version=5`
2. **Copy from raw files**: Use the "Raw" button on GitHub to copy the code
3. **Clear and retry**: Delete everything in Pine Editor and start fresh
4. **Check for hidden characters**: Copy to a plain text editor first, then to Pine Editor

---

**Need more help?** Check the `README.md` and `testing_guide.md` for detailed usage instructions!
