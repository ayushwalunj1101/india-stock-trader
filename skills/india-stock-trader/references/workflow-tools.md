# Workflow Tools

Practical workflow features that save the trader time and reduce errors.

---

## 1. Watchlist Maintenance

When a user has an existing watchlist (from a previous session or provided as a list), the skill can update it.

**"Update my watchlist" workflow:**
1. For each stock on the watchlist, search for current price
2. Check if the setup is still valid:
   - Did it hit SL? → Remove, mark as "Stopped out"
   - Did it hit Target? → Remove, mark as "Target hit"
   - Did the setup trigger? → Update status to "Active"
   - Is the setup still pending? → Update CMP, check if levels still make sense
   - Has the setup deteriorated? → Remove, explain why (e.g., "broke below support, setup invalid")
3. Output an updated watchlist with status flags

**Status flags:**
- 🟢 **Active** — trade triggered, currently in the position
- 🟡 **Pending** — setup not yet triggered, still valid
- 🔴 **Stopped out** — hit SL, trade failed
- ✅ **Target hit** — reached target, trade successful
- ❌ **Invalidated** — setup broke down before triggering
- 🔄 **Updated** — levels revised based on new price action

**Example output:**
```
## Watchlist Update — 22 March 2026

| Stock | Status | Original Entry | CMP | Notes |
|-------|--------|---------------|-----|-------|
| JSWSTEEL | 🟡 Pending | ₹1,140-1,170 | ₹1,175 | Near entry zone. Setup still valid. |
| TATASTEEL | ❌ Invalidated | ₹192-200 | ₹185 | Broke below ₹190 support. Remove. |
| TECHM | 🟢 Active | ₹1,320 | ₹1,365 | +3.4% in trade. Trail SL to ₹1,310. |
```

---

## 2. News & Event Risk Flagging

Proactively flag known risk events that could impact trade setups. Search for these when building any trade plan or watchlist.

**Events to flag:**
- **Earnings dates** — binary risk event. Flag if within 14 days.
- **RBI monetary policy** — impacts banks, NBFCs, rate-sensitive stocks. Flag dates.
- **Budget / fiscal announcements** — impacts infrastructure, defence, agriculture sectors.
- **Geopolitical events** — currently Iran-Israel tensions impacting oil, energy, defence stocks.
- **F&O expiry weeks** — increased volatility, wider swings. Monthly expiry (last Thursday) is particularly volatile.
- **Index rebalancing** — Nifty 50 / Nifty Next 50 additions/removals cause forced buying/selling.
- **Global events** — US Fed meetings, US jobs data, China PMI — impact sentiment broadly.

**How to flag:**
- In trade plans: Add a "Risk Calendar" section listing upcoming events within the trade's expected holding period.
- In watchlists: Add a "⚠️" flag next to stocks with upcoming events.

**Example:**
```
## Risk Calendar (next 2 weeks)
- March 27: F&O monthly expiry — expect volatility
- April 1: RBI MPC meeting — rate decision impacts financials
- April 10-15: Q4 earnings season begins — IT companies report first
- Ongoing: Iran-Israel tensions — oil/energy/defence stocks volatile
```

---

## 3. Position Sizing Calculator

When the user asks for position sizing, don't just show the formula — present it as a clear, interactive-feeling breakdown.

**Format:**
```
## Position Sizing

Capital: ₹3,00,000
Risk appetite: 2% per trade = ₹6,000 max loss
Conviction score: 7.5/10 (B-grade) → adjusted risk: 1.5% = ₹4,500

| Parameter | Value |
|-----------|-------|
| Entry price | ₹404 |
| Stop loss | ₹385 |
| SL distance | ₹19 (4.7%) |
| Max shares (2% risk) | 315 shares |
| Max shares (adjusted 1.5%) | 236 shares |
| Capital deployed | ₹95,344 (31.8% of capital) |
| Capital remaining | ₹2,04,656 |

Recommended: Buy **236 shares** at ₹404 (B-grade conviction → 1.5% risk)
```

**If the user hasn't shared capital:** Ask once: "What's your trading capital? I need this to calculate position sizes. If you'd rather not share, I'll just give you levels without quantities."

---

## 4. Risk Dashboard

When the user has multiple active positions, provide a portfolio-level risk view.

**Trigger:** User says "how's my portfolio looking", "check my positions", "risk check", or provides a list of active trades.

**Dashboard format:**
```
## Risk Dashboard — 22 March 2026

### Active Positions
| Stock | Entry | CMP | P&L | SL | Risk Left | Sector |
|-------|-------|-----|-----|-----|-----------|--------|
| JSWSTEEL | ₹1,155 | ₹1,170 | +1.3% | ₹1,100 | ₹70 (6%) | Metal |
| TECHM | ₹1,320 | ₹1,365 | +3.4% | ₹1,270 | ₹95 (7%) | IT |
| TATAPOWER | ₹404 | ₹410 | +1.5% | ₹385 | ₹25 (6%) | Power |

### Portfolio Health
- **Total deployed**: ₹2,85,000 / ₹5,00,000 (57%)
- **Open P&L**: +₹8,200 (+2.9%)
- **Max portfolio risk** (if all SLs hit): -₹18,500 (-3.7% of capital)
- **Sector concentration**: Metal 35%, IT 33%, Power 32% — well diversified
- **Correlation risk**: Metal and Power may move together in risk-off — 67% of portfolio exposed

### Alerts
- ⚠️ TECHM earnings approaching April 15 — consider booking partial profits
- ✅ No F&O expiry this week
- ⚠️ 67% of portfolio in cyclical sectors — vulnerable to macro sell-off
```

**Correlation check (simplified):**
Flag when 2+ positions are in the same sector or when sectors tend to move together:
- Metal + Mining = correlated
- IT services stocks = correlated
- Banks + NBFCs = correlated
- Power + Energy = correlated
- Pharma + FMCG = defensive, correlated

If portfolio is concentrated in correlated sectors, note: "High correlation risk — if [sector] sells off, multiple positions get hit simultaneously. Consider diversifying into uncorrelated sectors."

---

## 5. Order Execution Format (Zerodha-Ready)

Since there's no Zerodha MCP integration yet, format the trade plan's execution details as a ready-to-copy order instruction. This minimizes the user's effort when placing the order manually.

**Format for GTT (Good Till Triggered) order on Zerodha:**
```
## Quick Order — Zerodha GTT Format

Stock: TATAPOWER (NSE)
Order type: GTT — Single

BUY trigger:
  Trigger price: ₹402
  Limit price: ₹405
  Quantity: 315

SELL (Stop Loss) trigger:
  Trigger price: ₹385
  Limit price: ₹383
  Quantity: 315

SELL (Target 1) trigger:
  Trigger price: ₹417
  Limit price: ₹415
  Quantity: 157 (50%)

Note: After Target 1 hits, manually update SL to ₹402 (entry) for remaining 158 shares.
```

**For other brokers:** Adapt the format — Groww uses a different GTT interface, Angel One has bracket orders. If the user mentions their broker, format accordingly. Default to Zerodha format since it's the most popular in India.

**Future-proofing:** If a Zerodha/Kite Connect MCP becomes available, the skill should be ready to directly place orders through it. The data is already structured — it just needs an API call layer.

---

## 6. Recommendation Tracking Spreadsheet

When the user wants to track the skill's past recommendations, generate or update an xlsx file with this structure:

**Columns:**
| Column | Description |
|--------|-------------|
| Date | Date of recommendation |
| Stock | NSE ticker |
| Setup Type | Breakout / Support bounce / Pullback etc. |
| Entry Zone | Recommended entry range |
| Actual Entry | Where the user actually entered (filled by user) |
| SL | Stop loss level |
| T1 | Target 1 |
| T2 | Target 2 |
| Score | Conviction score at time of recommendation |
| Grade | A / B / C |
| Status | Pending / Active / Hit T1 / Hit T2 / Stopped Out / Invalidated |
| Exit Price | Actual exit price (filled by user or checked via search) |
| P&L % | Calculated from actual entry to exit |
| Days Held | Trading days from entry to exit |
| Notes | Any context — why it worked/failed |

**When generating the scorecard**, calculate:
- Overall hit rate (T1 reached / total triggered)
- Hit rate by grade (A vs B vs C)
- Average win % vs average loss %
- Win/loss ratio (avg win / avg loss)
- Expectancy = (win rate × avg win) - (loss rate × avg loss)
- Best and worst trades

**Key insight generation:** After 10+ tracked trades, the skill should identify patterns:
- "A-grade setups are hitting T1 at 80% — your edge is clearly in high-conviction trades"
- "B-grade setups are only 40% — consider skipping B-grades or half-sizing them"
- "Metal sector picks are 5/5 — your sector reads are strong there"
- "Support bounce setups are 1/4 — breakout entries are working better for you"

This feedback loop is what separates traders who improve from those who repeat mistakes.
