# Advanced Technical Filters

Additional analysis layers to apply on top of the core price-volume-structure framework. Use these when the user asks for deeper analysis, or proactively apply them in Full Trade Plan mode.

---

## 1. Relative Strength Ranking

Relative strength (RS) measures how a stock is performing compared to a benchmark (Nifty 50) or its sector index. Stocks with high RS tend to outperform — they fall less in corrections and lead in recoveries.

**How to assess:**
- Search for "[STOCK] vs Nifty 50 performance 1 month" or compare the stock's % change vs Nifty's % change over the same period
- A stock that's down 5% when Nifty is down 9% is showing strong relative strength
- A stock that's up while its sector is down is showing exceptional RS

**RS categories:**
- **Strong RS**: Stock outperforming Nifty by 5%+ over last month — prioritize for longs
- **Neutral RS**: Stock moving roughly in line with Nifty — acceptable but not exciting
- **Weak RS**: Stock underperforming Nifty — avoid for longs, possible short candidate

**In watchlists**, add a simple RS flag: ✅ (outperforming), ➡️ (in line), ❌ (underperforming)

---

## 2. Multiple Timeframe Check (Weekly + Daily Alignment)

The most reliable setups occur when the weekly and daily timeframes agree. A daily breakout in a stock that's also bullish on the weekly chart has much higher probability than one where the weekly is bearish.

**Framework:**
1. **Weekly trend**: What's the bigger picture? Uptrend (higher highs/lows), downtrend (lower highs/lows), or sideways?
2. **Daily setup**: What's the actionable trigger? Breakout, support bounce, pullback entry?

**Alignment matrix:**

| Weekly | Daily | Trade? |
|--------|-------|--------|
| Bullish | Bullish breakout | ✅ Best setup — trend + trigger aligned |
| Bullish | Pullback to support | ✅ Good — buying dip in uptrend |
| Sideways | Breakout from range | ⚠️ OK — but watch for false breakouts |
| Bearish | Bullish bounce | ❌ Counter-trend — risky, reduce size |
| Bearish | Bearish breakdown | 🔻 Short setup (if user trades shorts) |

**In trade plans**, state the weekly-daily alignment explicitly:
> "Weekly: Bullish (higher highs/lows, above 20 WMA). Daily: Breakout above ₹1,170 with volume. Alignment: ✅ Both bullish — high probability setup."

---

## 3. Gap Analysis

Gaps (price jumps between one day's close and the next day's open) reveal urgency — they signal that buyers or sellers couldn't wait for the open.

**Types of gaps relevant for swing trading:**

- **Breakaway gap**: Stock gaps up/down out of a consolidation range on high volume. This is often the start of a new trend. Actionable — trade in the direction of the gap.
- **Continuation gap**: Occurs mid-trend, confirms momentum. Less actionable as a standalone entry but confirms existing positions.
- **Exhaustion gap**: Occurs after a long run, often on climactic volume. This is a warning sign — the trend may be ending.

**How to use gaps:**
- **Gap-up + volume + breakout** = strong bullish signal. Enter on the gap day or next-day pullback.
- **Gap-up but fills within the day** = weak signal. The gap was rejected — avoid.
- **Gap-down to support** = potential panic selling. If it holds support on high volume, could be a reversal setup.

**Search for**: "[STOCK] gap up today NSE" or check "stocks that gapped up today NSE" for screening.

---

## 4. Earnings Calendar Alert

Earnings dates create binary risk events — the stock can gap 5-15% either way. For swing traders, this is important to know BEFORE entering.

**Rules:**
- If earnings are within 7 days: **Flag it prominently** in the trade plan. State: "⚠️ Earnings on [DATE] — this creates event risk. The stock could gap significantly. Consider reducing position size or waiting until after results."
- If earnings are within 14 days: **Note it** as upcoming risk. State: "Earnings approaching on [DATE]. Factor this into holding period."
- If earnings just passed (within 7 days ago): **Note the reaction**. Was it positive or negative? How did volume behave?

**How to find earnings dates:**
- Search for "[STOCK] next earnings date 2026" or "[STOCK] quarterly results date"
- TradingView, Tickertape, and Trendlyne typically show the next earnings date on stock pages

**In watchlists**, add a column or flag:
- "Earnings: May 22" or "⚠️ Earnings in 5 days" or "✅ No earnings nearby"

---

## 5. Sector Rotation Radar

Sector context tells you whether you're swimming with or against the current. A great stock in a weak sector will underperform a mediocre stock in a strong sector.

**How to assess sector rotation:**

1. Search for "Nifty sectoral indices performance today" or "sector heatmap NSE today"
2. Identify which sectors are leading (green) and lagging (red) over the last 1 week and 1 month
3. Compare the stock's sector performance vs Nifty

**Sector strength tiers:**
- **Leading sectors** (outperforming Nifty by 2%+ over 1 month): Prioritize stock picks from these sectors
- **In-line sectors** (±2% of Nifty): Acceptable — stock-specific factors matter more here
- **Lagging sectors** (underperforming Nifty by 2%+): Avoid for longs unless stock has exceptional relative strength

**In trade plans**, add a one-line sector context:
> "Sector: Nifty Metal (+3.5% this week, outperforming Nifty). Sector momentum supports this trade."

**Sector rotation cycle (simplified):**
- Early recovery: IT, Financials
- Mid-cycle: Auto, Capital Goods, Infrastructure
- Late-cycle: Metals, Energy, Commodities
- Defensive: FMCG, Pharma, Utilities

This is a rough guide — Indian markets don't always follow textbook cycles, but it helps contextualize sector moves.
