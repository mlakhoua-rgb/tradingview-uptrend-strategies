# Trading Strategy Design Document

## Project Overview
Create two Pine Script strategies for TradingView:
1. **Entry Scanner**: Scan stocks/crypto to select 5 high-probability uptrend candidates (80% accuracy target)
2. **Exit Manager**: Manage exits with 10% profit target or downtrend detection (80% accuracy)

## Recommended Assets (Long-term HOLD viable)
- **Crypto**: BTC (Bitcoin), ETH (Ethereum), SOL (Solana), BNB (Binance Coin)
- **Commodities**: GLD (Gold ETF), SLV (Silver ETF), GDX (Gold Miners)
- **Tech Blue Chips**: AAPL, MSFT, GOOGL, NVDA, TSLA
- **Index ETFs**: SPY, QQQ, DIA

## Entry Scanner Strategy Design

### Objective
Identify 5 assets with highest probability (80%+) of uptrend continuation over next 3-4 days.

### Multi-Indicator Confluence System

#### 1. Trend Confirmation (Weight: 30%)
- **Primary**: 50 EMA above 200 EMA (long-term bullish structure)
- **Secondary**: Price above both 50 EMA and 200 EMA
- **Tertiary**: ADX > 25 (strong trend present)
- **Score**: 3/3 conditions met = 30 points

#### 2. Momentum Analysis (Weight: 25%)
- **RSI**: Between 40-70 (not overbought, still has room)
- **MACD**: MACD line crossing above signal line (bullish momentum)
- **Stochastic**: %K crossing above %D in oversold/neutral zone (<80)
- **Score**: 3/3 conditions met = 25 points

#### 3. Volume Confirmation (Weight: 20%)
- **Volume Surge**: Current volume > 1.3x 20-day average
- **Volume Trend**: 5-day volume average > 20-day volume average
- **On-Balance Volume**: OBV trending upward (accumulation)
- **Score**: 3/3 conditions met = 20 points

#### 4. Price Action Patterns (Weight: 15%)
- **Higher Lows**: Last 3 swing lows are ascending
- **Breakout**: Price breaking above 10-day high
- **Support Hold**: Price bounced from key support (50 EMA or previous resistance turned support)
- **Score**: 2/3 conditions met = 15 points (flexible)

#### 5. Volatility & Risk (Weight: 10%)
- **ATR**: ATR increasing (volatility expansion for trend moves)
- **Bollinger Bands**: Price in upper half of bands
- **Squeeze Release**: Bollinger Bands expanding after squeeze
- **Score**: 2/3 conditions met = 10 points

### Scoring System
- **Total Possible Score**: 100 points
- **Minimum Entry Threshold**: 75 points (75% confluence)
- **High Confidence**: 85+ points
- **Select Top 5**: Rank all scanned assets, select top 5 by score

### Multi-Timeframe Validation
To achieve 80% accuracy, validate signals across multiple timeframes:
- **Daily Chart**: Primary analysis (main scoring)
- **4-Hour Chart**: Confirm momentum is building
- **Weekly Chart**: Ensure long-term trend alignment

**Bonus Points**: +5 points if all three timeframes align

### Risk Filters (Disqualifiers)
Assets are excluded if:
- Price below 200 EMA (no long-term uptrend)
- RSI > 80 (severely overbought)
- Volume < 50% of 20-day average (illiquid/dead)
- Recent death cross (50 EMA crossed below 200 EMA within 20 bars)
- Extreme volatility (ATR > 2x 50-day ATR average)

## Exit Strategy Design

### Objective
Exit positions at optimal points: 10% profit target OR early detection of downtrend reversal.

### Exit Condition 1: Profit Target (10%)
- **Simple**: Close position when price reaches 10% above entry price
- **Trailing Option**: Once 10% is reached, trail stop at 5% below highest high
- **Partial Exit**: Take 50% profit at 10%, let remaining 50% run with trailing stop

### Exit Condition 2: Downtrend Detection (80% Confidence)

#### Immediate Exit Signals (High Priority)
1. **Death Cross Formation**: 50 EMA crosses below 200 EMA
2. **MACD Bearish Divergence**: Price makes higher high, MACD makes lower high
3. **Volume Climax**: Massive volume spike (3x average) with reversal candle
4. **Break of Key Support**: Price closes below 50 EMA with increased volume

#### Early Warning Signals (Medium Priority)
1. **RSI Overbought Divergence**: RSI < 70 while price making new highs
2. **Momentum Loss**: MACD histogram declining for 3+ consecutive bars
3. **Stochastic Reversal**: %K crosses below %D in overbought zone (>80)
4. **Volume Decline**: Volume declining while price attempting new highs

#### Confirmation Signals (Combine with above)
1. **Bearish Candlestick Patterns**: Shooting star, evening star, bearish engulfing
2. **Bollinger Band Rejection**: Price rejected at upper band with reversal
3. **ADX Decline**: ADX falling below 25 (trend weakening)

### Exit Scoring System
- **Immediate Exit**: Any 1 high-priority signal = EXIT
- **Early Exit**: 2 medium-priority + 1 confirmation = EXIT
- **Cautious Exit**: 3 medium-priority signals = EXIT

### Stop Loss (Safety Net)
- **Hard Stop**: 7% below entry price (protect capital)
- **Trailing Stop**: Once in 5%+ profit, trail stop at 3% below highest high
- **Time Stop**: Exit after 10 days if no profit target hit and no clear trend

## Implementation Notes

### For Entry Scanner Script:
- Use Pine Script v5
- Scan up to 40 symbols (TradingView limit)
- Display results in table format with scores
- Alert when new high-score opportunities appear
- Update on daily bar close

### For Exit Manager Script:
- Apply to individual chart
- Track entry price (manual input or auto-detect)
- Display exit signals with priority levels
- Alert on any exit condition
- Show profit/loss percentage in real-time

### Backtesting Requirements
- Test on at least 100 historical setups
- Measure win rate, average gain, average loss
- Calculate risk-reward ratio
- Analyze performance across different market conditions
- Target: 80% win rate with 2:1 reward:risk minimum

## Expected Performance Metrics
- **Win Rate Target**: 80%+
- **Average Winner**: 10-15%
- **Average Loser**: 3-5% (tight stops)
- **Reward:Risk Ratio**: 2:1 minimum
- **Holding Period**: 3-7 days average
- **Maximum Drawdown**: <15%

## Next Steps
1. Develop Entry Scanner Pine Script
2. Develop Exit Manager Pine Script
3. Create backtesting framework
4. Test extensively on historical data
5. Refine parameters based on results
6. Document findings and recommendations
