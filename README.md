# TradingView Pine scripts — Ivan Labrie

Source backups of my open-source TradingView indicators.

TradingView hid a number of my publications in an automated moderation sweep in August 2026. Hidden
scripts return 404 to anyone but me, which means every link ever shared to them is dead — including
links I'd sent to people who were mid-setup. This repo exists so the code has a home that doesn't
depend on one platform's moderation queue.

## What's here

`scripts/` — 26 Pine files. Filenames prefixed with an 8-character code are the TradingView script ID
for that publication.

Most of these are old. Sixteen of them predate Pine versioning entirely (no `//@version` line), and
several are small experiments I wrote between 2014 and 2017 and never revisited. They're published as
they were written, not cleaned up for display. A rewrite to Pine v6 is in progress; when it lands it
will go into the existing TradingView publications rather than new ones.

The exceptions, which are current and written in Pine v6:

- `expected-move-bands.pine` — the options-implied expected move, plotted as bands at ±1 and ±2 sigma
  around price, anchored to the open of each week or month and held flat across the period. Pulls VIX
  for equities and Deribit DVOL for crypto, and falls back to a realized-vol estimate (marked "est")
  when no IV series exists for the symbol. Pairs with `vol-premium-gauge.pine`.
- `cot-commercial-extreme.pine` — commercial hedger net positioning as a multi-year percentile, with
  the bottom tell: commercials covering en masse rather than adding is what marks a major low.
- `crypto-cot-cohorts.pine` — the same CFTC cohort data for crypto futures, published as an honest
  viewer rather than a signal. The commercial-hedger read does not transfer to bitcoin, and the script
  is built to show you why.
- `buyers-sellers-trapped.pine` — flags a bar that spikes beyond the prior bar's true range and then
  closes back inside it, trapping the traders who chased the extension. Original concept from 2017.
- `regime-compass.pine` — a risk-on to crisis regime read composed from volatility, trend and momentum.
- `vol-premium-gauge.pine` — implied minus realized volatility, with a Parkinson-based fallback when no
  IV series is available for the symbol.

## Using them

Copy the file contents into the Pine Editor and add to chart. If something doesn't compile, open an
issue — several of these are old enough that Pine has moved under them.

Free to fork and adapt.

---

Ivan Labrie · [TradingView](https://www.tradingview.com/u/IvanLabrie/) · [ivanlabrie.netlify.app](https://ivanlabrie.netlify.app/)
