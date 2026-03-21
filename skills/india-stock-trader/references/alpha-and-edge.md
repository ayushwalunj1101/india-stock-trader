# Alpha Generation

Features that go beyond standard technical analysis to provide an informational edge. These are the difference between "well-organized free knowledge" and "insights you can't easily get elsewhere."

---

## 1. Unusual Volume Detection

Standard volume analysis asks "is volume above average?" That's table stakes. Unusual volume detection asks "is this volume *statistically anomalous*?"

**Framework:**
- **Normal**: Volume within 1 standard deviation of 20-day average → business as usual
- **Elevated**: 1.5-2x average → worth noting but not unusual
- **Unusual**: 2-3x average → something is happening. Smart money may be accumulating/distributing.
- **Anomalous**: 3x+ average → this is a signal. Combined with delivery % analysis, this can reveal institutional activity before it shows up in shareholding data.

**How to search:**
- "[STOCK] volume today vs average" or check stock pages on Trendlyne/Tickertape which show volume relative to average
- For anomalous volume, also check: "[STOCK] bulk deal today NSE" — bulk deals are disclosed same day and reveal who's buying/selling

**Interpretation matrix:**

| Volume | Delivery % | Price Move | Signal |
|--------|-----------|------------|--------|
| 3x+ | >50% | Up | 🟢 Strong accumulation — institutional buying likely |
| 3x+ | >50% | Down | 🔴 Strong distribution — institutions exiting |
| 3x+ | <25% | Up | ⚠️ Speculative pump — don't trust the move |
| 3x+ | <25% | Down | ⚠️ Panic selling by speculators — may reverse |
| 3x+ | 30-50% | Flat/Small | 🟡 Churning — ownership changing hands. Watch next 2-3 days for direction. |

**In trade plans**, when unusual volume is detected:
> "⚡ Unusual volume: 3.2x average with 48% delivery. This suggests genuine institutional interest, not just speculative churn. The volume pattern adds conviction to this breakout."

---

## 2. Bulk & Block Deal Tracking

NSE discloses bulk deals (>0.5% of shares traded by a single entity) and block deals (large negotiated trades in a special window) on the same day. This is as close to "smart money tracking" as retail traders can get in Indian markets.

**How to find:**
- Search "NSE bulk deals today [DATE]" or "[STOCK] bulk deal"
- Check NSE website: nseindia.com → Market Data → Bulk/Block Deals
- Trendlyne and Moneycontrol also aggregate bulk/block deal data

**What to look for:**
- **Known institutional buyers** (mutual funds, FIIs, insurance companies) buying in bulk → bullish signal
- **Promoter buying** → very strong signal (they know the company best)
- **Promoter selling** → caution, especially if >1% stake
- **PE/VC funds exiting** → they're taking profits. Short-term negative, may create buying opportunity on dip
- **Multiple bulk buys over several days** → sustained accumulation. More reliable than a single bulk deal.

**How to use:**
- When analyzing a stock for a trade plan, always search for recent bulk/block deals (last 30 days)
- If a major institution bought in bulk recently AND the stock is setting up technically → conviction boost
- If promoter sold a large block recently → caution flag, even if the technical setup looks good
- Add to trade plan: "Recent block deal: [Institution] bought 2.5 lakh shares at ₹1,150 on March 15. Smart money is positioned long."

---

## 3. Sector-Stock Divergence Analysis

When a stock moves opposite to its sector, it's an anomaly worth investigating. Divergences often precede trend changes.

**Types of divergences:**

**Bullish divergence (stock weak, sector strong):**
- The sector index is rallying but one stock in the sector is flat or down
- Could mean: stock-specific bad news (temporary) OR the stock is about to catch up
- If fundamentals are fine and the weakness is just price-based → potential mean-reversion buy
- Example: Nifty Metal +5% this week but HINDALCO -2% → HINDALCO may be a laggard catch-up play

**Bearish divergence (stock strong, sector weak):**
- The sector is falling but one stock is holding up or rising
- Could mean: stock has genuine relative strength OR it hasn't sold off yet and will catch up to the downside
- If the stock has strong RS over 1+ months → it's a genuine leader, prioritize for longs
- If the stock just hasn't reacted yet → be cautious, it may drop later

**How to screen for divergences:**
- Compare "[SECTOR] index performance this week" with individual stock performance
- Stocks that diverge from sector by >3% in either direction are worth flagging
- Combine with delivery % and volume to distinguish genuine divergence from noise

**In watchlists**, add a divergence flag:
> "📊 Divergence: HINDALCO -2.8% while Nifty Metal +3.5% — laggard catch-up potential if ₹480 support holds"

---

## 4. Historical Pattern Context

While the skill can't run backtests in real-time, it can provide context about how similar setups have historically played out in Indian markets.

**Patterns with known Indian market tendencies:**

**Breakouts in Nifty 50 stocks:**
- Large cap breakouts from multi-week bases have a higher success rate (65-70% in trending markets) than mid/small cap breakouts (~50-55%)
- Volume confirmation (>1.5x avg) improves success rate by ~10%
- Breakouts that hold for 3 days without retesting the breakout level have ~75% probability of reaching Target 1

**Support bounces:**
- Stocks bouncing from 200 DMA with volume have historically had a 60%+ success rate for a 3-5% move
- Double bottom patterns at 52W lows work better in sectors that are turning (sector rotation) vs sectors in structural decline

**Earnings gap-ups:**
- Post-earnings gap-ups in Indian markets tend to sustain for 3-5 days if accompanied by >2x average volume and >40% delivery
- Gap-ups on poor delivery (<25%) often fill within a week

**Market regime impact:**
- When Nifty is above its 200 DMA: long setups have ~65% hit rate
- When Nifty is below 200 DMA: long setups drop to ~45% hit rate. This alone should adjust conviction scores.
- When India VIX is above 20: all setups have lower probability. Widen SLs by 20% or reduce position sizes.

**How to use:**
- In trade plans, add a "Historical context" line referencing relevant pattern statistics
- Example: "Historical context: Breakouts from 3+ week bases in Nifty 50 stocks with 2x+ volume have a ~70% success rate in trending markets. Current market is below 200 DMA, which reduces base rate to ~50%."
- This is not a guarantee — it's context that helps the trader calibrate expectations.

---

## 5. India VIX Integration

India VIX (Volatility Index) measures the market's expectation of near-term volatility. It's derived from Nifty option prices.

**VIX levels and what they mean for swing trading:**

| VIX Range | Market State | Swing Trading Implication |
|-----------|-------------|--------------------------|
| Below 12 | Complacent | Low volatility. Breakouts may lack momentum. Tight range trading. |
| 12-15 | Normal | Good environment for swing trading. Standard SLs and sizing. |
| 15-20 | Elevated | Increased volatility. Widen SLs by 10-15%. Reduce position sizes to B-grade levels. |
| 20-25 | High fear | Difficult for longs. Counter-trend bounces are sharp but short-lived. Only A-grade setups. |
| Above 25 | Panic | Stay mostly cash. Only trade if you have exceptional conviction. Gaps and whipsaws are common. |

**How to check:**
- Search "India VIX today" — it's prominently displayed on NSE and all market platforms
- Also check VIX trend — a falling VIX from high levels is bullish (fear receding), rising VIX from low levels is cautionary

**How to integrate:**
- Check VIX before building any watchlist or trade plan
- State it in market context: "India VIX at 18.5 — elevated. Recommending tighter position sizes (B-grade risk even for A-grade setups)."
- If VIX > 20, add a blanket warning: "⚠️ VIX above 20 — volatility is high. All position sizes should be reduced. Expect wider intraday swings and potential gap moves."

---

## 6. Gap Risk & Slippage Management

### Gap Risk
Indian markets can gap significantly overnight due to global cues (US markets, Asia open), geopolitical events, or company-specific news.

**Gap risk factors:**
- Stocks with high beta (>1.3) gap more than low-beta stocks
- Stocks near earnings dates have higher gap risk
- Global events (US Fed, geopolitical flare-ups) cause correlated gaps across all stocks
- Friday positions carry extra gap risk (2 days of potential news before Monday open)

**How to handle:**
- Note beta in trade plans: "Beta: 1.46 — this stock amplifies market moves. A 2% Nifty gap = ~3% gap in TATAPOWER."
- For high-beta stocks, factor gap risk into SL: "SL at ₹385 (4.7% from entry). However, in a gap-down scenario, actual exit may be at ₹378-380."
- Before long weekends: "⚠️ Long weekend ahead (3 days without trading). Consider booking partial profits or tightening SLs."

### Slippage
The difference between your intended entry/exit price and the actual fill price.

**Slippage factors in Indian markets:**
- **Liquid stocks (Nifty 50)**: Slippage is minimal — ₹0.5-2 for limit orders, ₹2-5 for market orders
- **Mid caps**: ₹2-5 slippage on limit orders, ₹5-15 on market orders
- **Small caps / low volume**: Slippage can be ₹10-50+ — significant impact on R:R
- **Breakout entries**: Higher slippage because many traders are buying at the same level. ₹5-10 above the breakout level is common.
- **SL exits**: In fast moves, SL-Market orders can execute 1-3% below the trigger price

**How to handle:**
- Factor slippage into R:R calculations: "Entry at ₹402. With ~₹3-5 slippage, effective entry may be ₹405-407. R:R adjusted from 1:1.6 to ~1:1.4."
- For SL orders: "SL trigger at ₹385 with limit at ₹383 (₹2 buffer for execution). In a fast move, actual exit may be ₹380-383."
- For illiquid stocks: "⚠️ Average daily volume is low. Slippage may be significant — use limit orders only, avoid market orders."

---

## 7. Maximum Portfolio Heat Rule

The single most important rule for surviving as a swing trader.

**Portfolio heat** = sum of risk-to-SL across all open positions, as a percentage of total capital.

**Example:**
- Position 1: Risking ₹6,000 (2% of ₹3L capital)
- Position 2: Risking ₹4,500 (1.5%)
- Position 3: Risking ₹6,000 (2%)
- **Total portfolio heat: ₹16,500 (5.5%)**

**Rules:**
- **Maximum portfolio heat: 6-8% of total capital.** Never exceed this regardless of how many A-grade setups you see.
- If portfolio heat is already at 6%, the next trade must either be very small or you must close/reduce an existing position.
- In high VIX environments (>20), reduce max heat to 4-5%.

**How to integrate:**
- In the risk dashboard, always calculate and display portfolio heat
- When suggesting a new trade, check: "Adding this trade would bring portfolio heat to 7.2% — approaching maximum. Consider half-sizing this position."
- If portfolio heat exceeds 8%: "⚠️ Portfolio heat at 9.5% — overexposed. Do not add new positions. Consider reducing the weakest trade."

---

## 8. Position Scaling (Adding to Winners)

One of the most powerful techniques in swing trading — but also one of the most misused. The goal is to add size to trades that are proving you RIGHT, turning a good trade into a portfolio-maker.

### When to Scale In

**Only add to a winning position when ALL of these conditions are met:**
1. The stock has moved at least 3% in your favor from entry
2. The stock has held above the breakout level for 3+ trading days (not a one-day spike)
3. Volume on the move remains healthy (not declining)
4. The original thesis is intact — nothing has changed fundamentally
5. Your portfolio heat can absorb the additional risk

**Do NOT scale in when:**
- The stock is approaching Target 1 (you're chasing the move, not building it)
- Volume is declining on the advance (momentum fading)
- The broader market has deteriorated since your entry (Nifty selling off, VIX spiking)
- You're already at maximum portfolio heat
- You're averaging down on a losing position — this is NOT scaling, this is denial

### How to Scale

**The pyramid method** — each add is smaller than the previous position:
- **Initial entry**: Full size per conviction score (e.g., 300 shares at ₹400)
- **First add (after +3-5%)**: 50% of initial size (150 shares at ₹412-420)
- **Second add (after +7-10%)**: 25% of initial size (75 shares at ₹430-440) — rare, only for exceptional movers

**Total maximum: 175% of original position size** (100% + 50% + 25%)

### SL Adjustment After Scaling

When you add to a position, your average cost goes up and your SL must be recalculated:

```
## Position Scaling Example

Initial: 300 shares @ ₹400 = ₹1,20,000 (SL ₹385)
Add 1:  150 shares @ ₹415 = ₹62,250
Combined: 450 shares @ avg ₹405 = ₹1,82,250

New SL: Move up to ₹398 (below the pullback low after the breakout held)
New risk: 450 × (₹405 - ₹398) = ₹3,150 (was ₹4,500 on initial entry)

Key: Your risk has actually DECREASED even though position size increased,
because the stock's move in your favor allows a tighter structural SL.
```

**The golden rule of scaling**: After adding, your total risk (position size × SL distance) should be EQUAL TO OR LESS THAN your initial risk. If adding increases your total risk, the add is too aggressive — reduce the add size or tighten the SL.

### How to Present in Trade Plans

When a stock has already been recommended and the user asks about adding:

```
## Scale-In Opportunity: JSWSTEEL

Original entry: ₹1,155 (March 20) | Original SL: ₹1,100
Current price: ₹1,195 (+3.5% from entry)
Days held: 5 | Volume: Sustained above average ✅

Scale-in eligible: ✅ (moved 3%+, held 3+ days, volume healthy, thesis intact)

Recommended add: 50% of original size at ₹1,190-1,200
New combined avg: ~₹1,170
New SL: ₹1,155 (moved up from ₹1,100 — original entry becomes new floor)
New total risk: Same as before (₹ amount risk unchanged despite larger position)

Portfolio heat check: Current 5.2% → after add 5.8% → ✅ within limits
```

### What NOT to Do

- **Never "average down"** — adding to a losing position is not scaling, it's increasing risk on a trade that's proving you wrong. The skill should explicitly reject requests to add to positions that are below entry price: "The stock is below your entry. Adding here is averaging down, not scaling. If the thesis is still valid, hold your original position with your original SL. If the thesis has changed, consider exiting."
- **Never scale into a stock approaching a major resistance** — you're adding size right where sellers are likely to appear.
- **Never scale more than twice** — the pyramid method caps at 175% of original size. Beyond that, you're overconcentrated in a single stock.
