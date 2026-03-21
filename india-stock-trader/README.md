# india-stock-trader

The first India-specific stock trading skill for AI agents. Built for swing and positional traders on NSE/BSE.

## What it does

A comprehensive trading assistant that helps Indian equity traders screen stocks, build trade plans, manage risk, and execute trades — all through natural language.

**Two modes:**
- **Quick Screen** — "scan Nifty 50 for breakout setups" → outputs a scored watchlist with entry/SL/target levels
- **Full Trade Plan** — "give me a trade plan for TATASTEEL, capital 5 lakhs" → complete analysis with conviction score, position sizing, safety checks, and ready-to-execute Zerodha GTT format

**Brief or detailed** — asks about multiple stocks, get a compact quick take. Ask about one stock, get the full deep dive. You control the depth.

## Key features

**Analysis & screening**
- Breakout/breakdown pattern detection with volume-price confirmation
- Delivery % analysis — filters out fake breakouts driven by intraday speculation
- Conviction scoring (0-10) with 8 weighted parameters — replaces gut feel with objective grades
- Relative strength ranking vs Nifty and sector
- Weekly + daily timeframe alignment check
- Sector rotation radar — prioritizes stocks in leading sectors
- Unusual volume detection (3x+ average) cross-referenced with delivery data
- Bulk/block deal tracking — smart money signal detection

**Risk management**
- SL-based position sizing with conviction-adjusted risk %
- India VIX integration — auto-adjusts sizing and conviction thresholds based on market volatility
- Portfolio heat monitoring — caps total risk at 6-8% of capital across all positions
- Gap risk awareness with stock beta, slippage buffers on entry and SL
- Position scaling framework — pyramid into winners while keeping risk constant

**India-specific**
- Circuit limit checks before every recommendation
- ASM/GSM surveillance detection — flags restricted stocks
- F&O ban period warnings
- Operator activity / pump-and-dump detection (7-point red flag checklist)
- T+1 settlement awareness, weekend gap risk flagging
- Budget, RBI policy, F&O expiry week patterns encoded

**Execution & tracking**
- Zerodha Kite MCP integration — live prices, portfolio data, and direct order placement
- Ready-to-copy Zerodha GTT order format (works without MCP too)
- Watchlist maintenance with status tracking (active/pending/stopped out/target hit)
- Recommendation scorecard — tracks past picks, calculates hit rates by grade, identifies what's working

## Install

**Claude.ai / Claude app:**

Download the `.skill` file from [Releases](../../releases) → Settings → Customize → Skills → Upload

**Claude Code / skills.sh:**

```bash
npx skills add YOUR_USERNAME/india-stock-trader
```

**Kite MCP (optional, recommended):**

Connect your Zerodha account for live prices and portfolio data — free, no API keys needed with the hosted version.

```json
{
  "mcpServers": {
    "kite": {
      "command": "npx",
      "args": ["mcp-remote", "https://mcp.kite.trade/mcp"]
    }
  }
}
```

More details: [zerodha.com/products/mcp](https://zerodha.com/products/mcp/)

## Sample outputs

### Quick Screen
```
| Stock     | Setup        | CMP     | Entry      | SL    | T1    | T2    | R:R  | Del% | Score    | Timeframe   |
|-----------|-------------|---------|------------|-------|-------|-------|------|------|----------|-------------|
| JSWSTEEL  | Breakout    | ₹1,170  | 1,140-1,170| 1,100 | 1,225 | 1,285 | 1:2.6| 44%  | 7.5 (B) | Positional  |
| TATASTEEL | Support     | ₹198    | 192-200    | 185   | 210   | 216   | 1:1.4| 38%  | 6.5 (B) | Swing       |
```

### Conviction Scorecard
```
| Parameter         | Score    | Detail                              |
|-------------------|----------|-------------------------------------|
| Volume            | 1.5/1.5  | 3.8x avg volume ✅                  |
| Delivery %        | 0.5/1.0  | 38% — acceptable but not strong     |
| Price vs MAs      | 1.5/1.5  | Above both 50 & 200 DMA ✅          |
| Sector momentum   | 1.0/1.0  | Metal sector leading ✅              |
| R:R ratio         | 0.75/1.5 | 1:1.6 — decent but below 1:2       |
| Relative strength | 1.0/1.0  | Outperforming Nifty ✅               |
| Weekly-Daily      | 0.75/1.0 | Weekly bullish, daily recovering    |
| Earnings          | 0.5/0.5  | Q4 results May 2026 — safe ✅       |
```

### Zerodha GTT Format
```
BUY trigger ₹1,140 / limit ₹1,145 / qty 86
SL trigger ₹1,100 / limit ₹1,097 / qty 86
T1 trigger ₹1,225 / limit ₹1,220 / qty 43 (50%)
```

## Who this is for

Swing and positional traders (2 days to 4 weeks holding period) who trade Indian equities on NSE/BSE. Works best for traders who:

- Analyze markets on weekends/evenings and plan trades for the week ahead
- Want a systematic, risk-first framework instead of gut-feel trading
- Already follow the market but need disciplined entry/exit/sizing rules
- Use Zerodha (Kite MCP integration) or any other Indian broker (GTT copy-paste format)

**Not for:** Intraday/scalping, options trading, mutual fund analysis, long-term investing (6+ months), or non-Indian markets.

## Skill structure

```
india-stock-trader/
├── SKILL.md                              — Main skill (453 lines)
└── references/
    ├── conviction-scoring.md             — 8-parameter weighted scoring rubric
    ├── advanced-filters.md               — RS ranking, MTF check, gaps, earnings, sectors
    ├── alpha-and-edge.md                 — Unusual volume, block deals, VIX, gap risk, scaling
    ├── india-mechanics.md                — Circuits, ASM/GSM, F&O ban, operators, T+1
    ├── kite-mcp.md                       — Zerodha Kite MCP integration & order execution
    └── workflow-tools.md                 — Watchlist, risk dashboard, position sizing, GTT format
```

## Disclaimer

This is a technical analysis framework, not financial advice. It does not guarantee profits. Always do your own research and manage your risk. The creator is not a SEBI-registered research analyst. Past patterns don't guarantee future results.

## License

MIT
