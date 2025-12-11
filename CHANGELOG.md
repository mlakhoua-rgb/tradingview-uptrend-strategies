# Changelog

All notable changes to the TradingView Uptrend Strategies project.

---

## [1.1.0] - 2025-12-11

### ✅ Fixed
- **Upgraded to Pine Script v6** - Both scripts now use the latest version instead of outdated v5
- **Fixed `request.security()` error** - Replaced dynamic loop with individual security calls (Pine Script v5/v6 limitation)
- **Fixed consistency warnings** - Extracted `ta.crossover()` calls to be called on each calculation
- **Improved code quality** - Removed all Pine Script compiler warnings

### 🔧 Changed
- Entry scanner now scans **20 fixed symbols** instead of dynamic array (technical limitation)
- Crossover functions now calculated at global scope for consistency
- Default display changed from "Top 5" to "Top 20" assets

### 📝 Technical Details

**Entry Scanner Changes:**
- Changed from `//@version=5` to `//@version=6`
- Replaced loop-based `request.security()` with 20 individual calls:
  ```pine
  s1 = request.security("BINANCE:BTCUSDT", timeframe.period, calcScore())
  s2 = request.security("BINANCE:ETHUSDT", timeframe.period, calcScore())
  // ... etc
  ```
- Extracted `ta.crossover()` calls from conditional blocks
- Fixed MACD and Stochastic crossover consistency warnings

**Exit Manager Changes:**
- Changed from `//@version=5` to `//@version=6`
- Extracted crossover calculations to separate variables:
  ```pine
  bool goldenCross = ta.crossover(ema50, ema200)
  bool macdCross = ta.crossover(macdLine, signalLine)
  ```
- All `ta.crossunder()` and `ta.crossover()` now called consistently

### 🎯 Assets Tracked (Entry Scanner)
1. BTCUSDT, ETHUSDT, SOLUSDT, BNBUSDT (Crypto)
2. ADAUSDT, DOGEUSDT (Crypto)
3. GOLD, GLD (Commodities)
4. AAPL, MSFT, GOOGL, NVDA, TSLA (Tech Stocks)
5. META, AMZN, AMD, AVGO (Tech Stocks)
6. SPY, QQQ, DIA (Index ETFs)

---

## [1.0.0] - 2025-12-11

### 🎉 Initial Release

**Features:**
- Multi-factor entry scanner with 100-point scoring system
- Smart exit manager with profit targets and downtrend detection
- Comprehensive documentation and testing guides
- GitHub repository with private access

**Components:**
- `entry_scanner.pine` - Scans and ranks assets by uptrend probability
- `exit_manager.pine` - Manages exits with multiple strategies
- `README.md` - Complete usage guide
- `testing_guide.md` - Backtesting framework
- `strategy_design.md` - Technical documentation
- `INSTALLATION.md` - Step-by-step installation
- `QUICKSTART.md` - 5-minute quick start guide

---

## Known Limitations

### Pine Script Constraints
- **Symbol limit**: Maximum 20 symbols due to `request.security()` limitations
- **No dynamic loops**: Symbols must be hardcoded as individual calls
- **Bar close updates**: Scanner only updates when bar closes (not real-time intraday)
- **No true ML**: Pine Script doesn't support machine learning - uses indicator confluence instead

### Workarounds
- To add/change symbols, manually edit the script and add new `request.security()` lines
- For real-time scanning, use lower timeframes (1-minute, 5-minute)
- For more than 20 symbols, create multiple scanner scripts

---

## Upgrade Instructions

### From v1.0.0 to v1.1.0

1. **Delete old scripts** in TradingView Pine Editor
2. **Pull latest from GitHub**:
   ```bash
   git pull origin main
   ```
3. **Copy updated scripts** to TradingView
4. **Save and add to chart**

No settings changes required - all parameters remain compatible.

---

## Future Enhancements (Planned)

- [ ] Multi-timeframe analysis integration
- [ ] Custom symbol input via settings (if Pine Script allows)
- [ ] Additional exit strategies (Fibonacci levels, support/resistance)
- [ ] Performance analytics dashboard
- [ ] Webhook integration for automated trading

---

## Support

For issues or questions:
1. Check `INSTALLATION.md` for common errors
2. Review `QUICKSTART.md` for usage tips
3. Read `testing_guide.md` for backtesting help
4. Open an issue on GitHub (private repo)

---

**Last Updated**: December 11, 2025
