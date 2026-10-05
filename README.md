# SynthTrade Pro v2.4.0 — Frozen GBPUSD Candidate

This package contains one trading strategy only: the frozen GBPUSD M5 exhaustion/reversal candidate. Previous strategy modes are no longer selectable.

## Frozen strategy
- Market: `frxGBPUSD`
- Timeframe: 5-minute wall-clock candles
- 3-bar move: >= 2.0 ATR(14)
- RSI: Wilder RSI(14), CALL <30 / PUT >70
- Wick ratio: >=55%
- Close-location ratio: >=45%
- EMA20 slope over previous 12 closed M5 bars: >= +2.0 ATR
- Entry: next M5 candle/open execution path after signal candle
- Contract: Rise/Fall (CALL/PUT)
- Duration: 15 minutes

The frozen strategy parameters are not exposed as alternate strategy modes or tuning controls.

## Recovery
TRADE mode defaults to the preferred tested recovery configuration: base stake $1, multiplier 2.2820512821, maximum 4 recovery levels. After the fourth consecutive loss, the sequence resets to base stake and the normal cooldown applies. MEASURE mode always uses flat stake.

## Safety
`BOT_MODE=MEASURE` is the default and the account default is demo. Historical research is not a guarantee of future profitability. Review live demo results before considering real funds.

The existing measurement/quote-aware TRADE lock remains in place.

## Run
1. Node.js 18+
2. Copy `.env.example` to `.env`
3. Set `DERIV_APP_ID` and `DERIV_API_TOKEN`
4. Keep `DERIV_ACCOUNT_TYPE=demo`
5. `npm ci`
6. `npm start`

`STRATEGY_MODE` is intentionally not used in v2.4.0.
