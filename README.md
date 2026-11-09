# Doji Indicator (Pine Script v5)

A TradingView indicator that detects **Doji** candlesticks on any chart and marks them with a label, a highlighted background and an alert condition.

A Doji forms when the open and close of a candle are almost equal. It signals indecision between buyers and sellers and is often watched as a possible reversal or pause in the trend.

## Detection logic

| Rule | Condition |
| --- | --- |
| Small body | `body ≤ 5% of the candle range` |
| Balanced shadows | upper and lower shadows are of similar length |
| Not a Dragonfly / Gravestone | excludes candles whose upper or lower shadow is shorter than the body |

The average body size is tracked with a 14-period EMA, and labels are placed using the 30-period ATR so they don't overlap the candles.

## Features

- "D" label under every detected Doji, with an explanatory tooltip
- Grey background highlight on Doji bars
- `alertcondition` — create a TradingView alert for "New Doji pattern detected"
- Configurable label colour

## Usage

1. Open TradingView → **Pine Editor**.
2. Paste the contents of [`doji.pine`](doji.pine).
3. Click **Add to chart**.
4. Optional: right-click the indicator → **Add alert** to get notified on new Dojis.

## Related

- [backtest-lab](https://github.com/ariaesm/backtest-lab) — a Python engine that detects the same pattern (and others) and backtests strategies built on it.

## Credits

The detection rules follow the Doji definition used in TradingView's built-in candlestick pattern library, packaged here as a standalone v5 indicator.
