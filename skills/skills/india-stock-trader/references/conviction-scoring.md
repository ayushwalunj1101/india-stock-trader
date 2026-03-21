# Conviction Scoring System

A weighted checklist that produces a score out of 10 for any trade setup. This replaces subjective "High/Medium/Low" conviction labels with an objective, repeatable framework.

## Scoring Rubric (10 points total)

| # | Parameter | Weight | Score | How to Evaluate |
|---|-----------|--------|-------|-----------------|
| 1 | **Volume Confirmation** | 1.5 pts | 0 / 0.75 / 1.5 | 0 = below average volume. 0.75 = 1-1.5x avg volume. 1.5 = above 1.5x avg volume on breakout/bounce day |
| 2 | **Delivery %** | 1.0 pt | 0 / 0.5 / 1.0 | 0 = below 25%. 0.5 = 25-40%. 1.0 = above 40% |
| 3 | **Price vs Moving Averages** | 1.5 pts | 0 / 0.75 / 1.5 | 0 = below both 50 & 200 DMA. 0.75 = above one MA. 1.5 = above both 50 & 200 DMA |
| 4 | **Sector Momentum** | 1.0 pt | 0 / 0.5 / 1.0 | 0 = sector underperforming Nifty. 0.5 = sector in line with Nifty. 1.0 = sector outperforming Nifty |
| 5 | **Risk:Reward Ratio** | 1.5 pts | 0 / 0.75 / 1.5 | 0 = R:R below 1:1.5. 0.75 = R:R between 1:1.5 and 1:2. 1.5 = R:R above 1:2 |
| 6 | **Relative Strength (vs Nifty)** | 1.0 pt | 0 / 0.5 / 1.0 | 0 = stock falling more than Nifty. 0.5 = in line. 1.0 = outperforming Nifty in last 1 month |
| 7 | **Weekly-Daily Alignment** | 1.0 pt | 0 / 0.5 / 1.0 | 0 = weekly and daily trends conflict. 0.5 = one is neutral. 1.0 = both weekly and daily trends agree (e.g., both bullish) |
| 8 | **Proximity to Earnings** | 0.5 pt | 0 / 0.5 | 0 = earnings within 2 weeks (risk event). 0.5 = no earnings nearby or already reported |

**Total: 10 points**

## Interpretation

| Score | Label | Action |
|-------|-------|--------|
| 8-10 | **A-grade setup** | Full position size. High conviction — all key parameters aligned. |
| 6-7.5 | **B-grade setup** | Reduced position (50-75% of normal size). Most parameters support, but some gaps. |
| 4-5.5 | **C-grade setup** | Small pilot position only (25-50% of normal size). Speculative. |
| Below 4 | **No trade** | Setup doesn't meet minimum quality bar. Skip or add to watchlist and wait for improvement. |

## How to Present

In watchlists, add a "Score" column with the number and grade letter:

| Stock | ... | Score | ...
|-------|-----|-------|----
| JSWSTEEL | ... | 7.5/10 (B) | ...

In full trade plans, show the complete scorecard:

```
## Conviction Score: 7.5/10 (B-grade)

| Parameter | Score | Detail |
|-----------|-------|--------|
| Volume | 1.5/1.5 | 3.8x avg volume ✅ |
| Delivery % | 0.5/1.0 | 38% — acceptable but not strong |
| Price vs MAs | 1.5/1.5 | Above both 50 & 200 DMA ✅ |
| Sector momentum | 1.0/1.0 | Metal sector leading ✅ |
| R:R ratio | 0.75/1.5 | 1:1.6 — decent but below 1:2 |
| Relative strength | 1.0/1.0 | Outperforming Nifty last month ✅ |
| Weekly-Daily align | 0.75/1.0 | Weekly bullish, daily recovering |
| Earnings proximity | 0.5/0.5 | Q4 results May 2026 — safe ✅ |
```

## Position Sizing by Score

The conviction score directly influences position sizing:

- **A-grade (8-10)**: Risk up to 2% of capital per trade
- **B-grade (6-7.5)**: Risk 1-1.5% of capital
- **C-grade (4-5.5)**: Risk max 0.5-1% of capital
- **Below 4**: No trade

**VIX Modifier** — apply after scoring:
- VIX below 15: No change — use score as-is
- VIX 15-20: Downgrade one tier (A → B sizing, B → C sizing)
- VIX above 20: Downgrade two tiers (A → C sizing). Only A-grade setups are tradeable.
- VIX above 25: No new trades regardless of score

**Market Regime Modifier:**
- Nifty above 200 DMA: No change — bullish regime supports long setups
- Nifty below 200 DMA: Subtract 1 point from the score — long setups have lower base rate (~45% vs ~65%)
- This means a 7.0 score in a bearish regime becomes 6.0 — still B-grade, but at the lower end

These modifiers ensure you're automatically conservative when conditions are against you, without needing to manually override every trade.
