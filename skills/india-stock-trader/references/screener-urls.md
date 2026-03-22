# Screener URLs & Systematic Scanning Workflow

When scanning a universe (Nifty 50, Nifty 200, or custom), **do not rely on market recap articles for stock discovery**. Use these screener URLs to systematically filter candidates, then verify individually.

---

## Scanning Workflow (Quick Screen mode)

### Step 1: Run 3-4 screeners via web_fetch

Fetch the results page from each relevant Chartink screener below. The page will show a table of stocks matching the scan criteria. Extract ticker names from the results.

### Step 2: Cross-reference

Stocks appearing in **2+ screeners** are higher-priority candidates. Create a shortlist of 6-10 names.

### Step 3: Cross-check against the universe

If scanning Nifty 200, check shortlisted names against `references/nifty200-universe.md`. Discard any stock not in the target universe.

### Step 4: Verify each candidate individually

For each shortlisted stock (max 6), run individual web searches:
- "[TICKER] share price today" → get CMP
- "[TICKER] volume delivery percentage" → check volume quality
- "[TICKER] bulk deal [MONTH] [YEAR]" → smart money check
- "[TICKER] 52 week high low" → proximity to breakout level

### Step 5: Score and build watchlist

Apply conviction scoring from `references/conviction-scoring.md` to each verified candidate.

---

## Chartink Screener URLs

### 🔥 Custom Screeners (user-built — run these FIRST)

These screeners are purpose-built for the skill's swing/positional approach. Prioritize results from these over generic screeners.

| Screener | URL | What It Finds | How to Use Results |
|----------|-----|---------------|-------------------|
| **Medium Term Volume Gainers** | `https://chartink.com/screener/medium-term-volume-gainers` | Nifty 500 stocks with: (1) avg daily volume ≥ 2L shares (liquidity floor), (2) weekly volume > 1.5× its 20-week SMA (sustained accumulation), AND (3) daily volume > 5× its 20-day SMA (anomalous spike). The weekly + daily combo catches institutional accumulation with a climactic volume day. | ⚠️ **These stocks have already moved significantly.** Don't chase. Use for: (a) identifying WHO is being accumulated — then check if a pullback entry exists, (b) confirming stocks already on your watchlist — if a watchlisted stock appears here, conviction jumps, (c) sector discovery — if 3+ stocks from the same sector appear, that sector has institutional flow. Cross-reference with Nifty 200 universe to filter. |

**Scan logic breakdown:**
```
Universe: Nifty 500
Filter 1: Daily SMA(Daily Volume, 20) >= 200000       → liquidity floor
Filter 2: Weekly Volume > 1.5 × Weekly SMA(Weekly Vol, 20) → sustained weekly accumulation  
Filter 3: Daily Volume > 5 × Daily SMA(Daily Vol, 20)      → anomalous daily spike
```

### Primary Screeners (use these for every scan)

| Screener | URL | What It Finds |
|----------|-----|---------------|
| **Nifty 200 Breakout** | `https://chartink.com/screener/nifty-200-breakout-stocks` | Stocks in Nifty 200 breaking out of consolidation ranges |
| **Nifty 200 High Volume** | `https://chartink.com/screener/high-volume-nifty-200-stocks` | Nifty 200 stocks with unusual volume spikes — check at 9:30 AM for best results |
| **Nifty 50 Breakout** | `https://chartink.com/screener/nifty-50-breakout` | Nifty 50 stocks with 0.2%+ breakout |
| **Positive Breakout (all)** | `https://chartink.com/screener/positive-breakout-stocks` | Volume-confirmed breakouts across all stocks — filter against universe manually |
| **Approaching 52W High** | `https://chartink.com/screener/potential-52-week-high` | Stocks within striking distance of 52-week highs — prime breakout candidates |

### Secondary Screeners (use when primary results are thin)

| Screener | URL | What It Finds |
|----------|-----|---------------|
| **SMA 150 Crossover (Nifty 50)** | `https://trendlyne.com/stock-screeners/simple-moving-average/crosses-above/sma-150/today/index/NIFTY50/nifty-50/` | Nifty 50 stocks crossing above 150 SMA — trend reversal signal |
| **Volume Buzzer (daily)** | `https://chartink.com/screener/volume-shockers` | Stocks with massive volume spikes across all segments |
| **Supertrend Positive** | `https://chartink.com/screener/supertrend-positive-breakout` | Supertrend indicator flipping bullish |
| **Bullish SAR + EMA Crossover** | `https://chartink.com/screener/bullish-sar-ema-crossover-15min` | Intraday momentum confirmation (use for timing, not discovery) |

### Trendlyne Screeners

| Screener | URL | What It Finds |
|----------|-----|---------------|
| **52W High (Nifty 200)** | `https://trendlyne.com/stock-screeners/52-week-high/today/index/NIFTY200/nifty-200/` | Nifty 200 stocks hitting new 52W highs today |
| **Delivery % Analysis** | `https://trendlyne.com/equity/delivery-analysis/[STOCK_ID]/[TICKER]/` | Per-stock delivery volume data (replace STOCK_ID and TICKER) |

### NSE Direct Data

| Data | URL | What It Shows |
|------|-----|---------------|
| **52W High/Low list** | `https://www.nseindia.com/market-data/52-week-high-equity-market` | All NSE stocks at 52W highs/lows today |
| **Bulk Deals** | `https://www.nseindia.com/market-data/bulk-deal-data` | Same-day bulk deal disclosures — smart money tracking |
| **F&O Ban List** | Search "NSE F&O ban list today" | Stocks currently in F&O ban period |

---

## How to Use Chartink Results

Chartink pages render a results table. When fetching via web_fetch:

1. Look for the stock ticker symbols in the results
2. The table typically shows: Stock Name, Ticker, Close, % Change, Volume
3. If the page doesn't render (JS-heavy), fall back to web search: `site:chartink.com "nifty 200 breakout" [DATE]`
4. Chartink screeners update after market close (~4 PM IST). Results from the previous trading day are most reliable.

**Note**: Chartink free tier shows EOD (end-of-day) data. Real-time intraday scanning requires Chartink Premium. For the skill's purposes, EOD scans run after market close are sufficient for swing/positional setup discovery.

---

## Fallback: When Screeners Don't Render

If web_fetch fails on Chartink (common due to JS rendering), use this search-based fallback:

1. Web search: `"nifty 200" stocks "52 week high" today [DATE]`
2. Web search: `"nifty 200" volume breakout [DATE]`
3. Web search: `NSE bulk deals today [DATE]`
4. Web search: `top gainers nifty 200 [DATE]` → then filter for volume confirmation
5. Fetch from Trendlyne (renders better): `https://trendlyne.com/stock-screeners/...`

The key principle: **systematic discovery first, then individual verification**. Never skip straight to reading market commentary — that gives you journalist picks, not screener results.
