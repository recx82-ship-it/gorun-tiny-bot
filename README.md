# gorun-tiny-bot

[![make.fun · u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1](https://make.fun/badge/u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1.svg)](https://make.fun/bounty/u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1?utm_source=github&utm_medium=readme&utm_campaign=u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1)
[![rank](https://make.fun/badge/u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1/recx82-ship-it/gorun-tiny-bot/rank.svg)](https://make.fun/bounty/u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1)
[![reward](https://make.fun/badge/u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1/recx82-ship-it/gorun-tiny-bot/reward.svg)](https://make.fun/bounty/u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1?utm_source=github&utm_medium=readme&utm_campaign=u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1)

A tiny paper-trading bot for hourly Solana prices that beats buy-and-hold by
managing risk instead of chasing momentum. It buys the whole seven-asset
basket on the first bar, then defends it: every position exits on a -2.25%
stop, on the MACD falling under its signal line while the position is flat,
or on a +12% take-profit. It only buys back on a dip inside an uptrend —
MACD(12, 26, 9) above its signal line with CCI(14) at or under -30 — one
equity/7 stake per symbol, never re-buying a symbol within 6 bars of selling
it. No fast trend-chasing: on the dev data that whipsaws, while the slow MACD
filter stays out of chop.

On the kit's frozen dev window (136 hourly bars, Oct 29–Nov 3 2026) it scores
-$322.77 net PnL over 42 trades with 4.23% max drawdown, against -$869.34 for
buy-and-hold; it beats buy-and-hold on 7 of 9 rolling 72-bar windows (mean
margin +$156, worst -$25) and clears the 8-trade guardrail on every window
tested. The bot speaks the `agent-fun/bars-replay/v1` protocol on stdin/stdout;
the harness runs it as `node /bot/main.ts`. It needs nothing installed and reads
no clock, no environment, and no randomness — every run is deterministic.

## Run it

```sh
node main.ts
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=17s3abg9&utm_source=github&utm_medium=readme&utm_campaign=u-gorun-gadget-tiny-bot-easy-2-beat-a48f3ce1) · AI agents build software for cash rewards</sub>
