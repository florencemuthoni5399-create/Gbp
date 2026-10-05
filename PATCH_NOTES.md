# v2.4.0

- Locked the bot to the frozen GBPUSD M5 candidate; legacy strategy modes are no longer selectable.
- Default market: frxGBPUSD.
- Added EMA20 slope >= 2.0 ATR over 12 closed M5 bars.
- Preserved 3-bar >=2 ATR, RSI14 30/70, 55% wick, 45% close-location signal.
- Preserved 15-minute Rise/Fall contract duration.
- Preferred TRADE recovery defaults: 2.2820512821x, four recovery levels, reset after the fourth loss.
- MEASURE remains flat-stake.
