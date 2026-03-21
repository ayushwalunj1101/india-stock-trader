# Kite MCP Integration

Zerodha's Kite MCP (Model Context Protocol) enables direct access to the user's trading account from within Claude. This dramatically enhances the skill's capabilities — instead of relying only on web searches for price data, we can pull live portfolio data, real-time quotes, and (with self-hosted setup) even place orders.

## MCP Server Details

- **Hosted (read-only)**: `https://mcp.kite.trade/mcp` — no API keys required, free
- **Self-hosted (full access)**: Requires Kite Connect API key/secret, user runs locally
- **GitHub**: https://github.com/zerodha/kite-mcp-server

## Available Capabilities

### Read Operations (hosted + self-hosted)
- **Portfolio**: Holdings, positions (open and day), P&L
- **Account**: Profile, margins (equity + commodity), fund details
- **Market Data**: Real-time quotes, LTP (Last Traded Price), instrument data
- **Orders**: Order history, trade history

### Write Operations (self-hosted only)
- **Order Placement**: Place buy/sell orders (market, limit, SL, SL-M)
- **Order Management**: Modify, cancel existing orders
- **GTT Orders**: Create/modify/cancel Good Till Triggered orders

## How to Detect Kite MCP

Check if Kite MCP tools are available in the current session. If the user has connected Kite MCP, you'll have access to tools like:
- `get_holdings` — user's portfolio holdings
- `get_positions` — current open positions
- `get_margins` — account margins
- `get_quote` / `get_ltp` — real-time stock prices
- `get_orders` — order history
- `place_order` — place a new order (self-hosted only)
- `get_instruments` — instrument list

If these tools are NOT available, fall back to web search for data and Zerodha GTT copy-paste format for execution.

## Integration with Skill Modes

### Quick Screen Mode (with Kite MCP)
1. Use `get_ltp` to fetch real-time prices for shortlisted stocks — eliminates the need for web search price verification
2. Use `get_quote` for detailed data including volume, OHLC, which may include delivery data
3. If user has holdings, cross-reference: "You already hold TATASTEEL — be aware of concentration risk"

### Full Trade Plan Mode (with Kite MCP)
1. Use `get_ltp` / `get_quote` for verified CMP — no web search needed for price
2. Use `get_margins` to check available capital for position sizing
3. Use `get_holdings` + `get_positions` to check existing exposure — flag if adding to a correlated sector
4. For order execution (self-hosted only): use `place_order` to place the trade directly after user confirms

### Risk Dashboard Mode (with Kite MCP)
This is where Kite MCP transforms the skill. Instead of the user manually listing positions:
1. `get_holdings` → fetch all holdings with average cost, P&L, quantity
2. `get_positions` → fetch all open positions with entry price, current P&L
3. `get_margins` → check available capital, used margin
4. Build the risk dashboard from LIVE data — sector concentration, correlation, total exposure, unrealized P&L

### Watchlist Maintenance (with Kite MCP)
1. `get_ltp` for each watchlisted stock — instant price updates
2. Cross-reference with `get_positions` — has the user already entered any of these?
3. Update status flags based on live prices vs. original entry/SL/target levels

## Order Execution Flow (Self-Hosted Only)

When the skill generates a trade plan and the user wants to execute:

1. **Confirm with user**: "I'll place a BUY order for 315 shares of TATAPOWER at ₹404. SL will be a separate GTT order at ₹385. Proceed?"
2. **Wait for explicit "yes"** — never auto-execute
3. **Place the order**: Use `place_order` with:
   - `tradingsymbol`: e.g., "TATAPOWER"
   - `exchange`: "NSE"
   - `transaction_type`: "BUY"
   - `quantity`: calculated from position sizing
   - `order_type`: "LIMIT" or "MARKET"
   - `price`: entry price (for LIMIT orders)
   - `product`: "CNC" (for delivery/swing trades)
4. **Place SL as GTT**: Create a GTT sell order at the stop-loss price
5. **Confirm to user**: "Order placed. Order ID: [ID]. GTT SL set at ₹385."

**Critical safety rules for order execution:**
- ALWAYS confirm with the user before placing any order
- NEVER place orders automatically based on analysis
- ALWAYS use "CNC" (Cash and Carry / delivery) product type for swing/positional trades — NOT "MIS" (intraday)
- If order fails, show the error message and suggest next steps
- After placing entry, remind user to set targets: "Entry filled. Don't forget to set your target exit."

## Setup Instructions for Users

If the user asks how to connect Kite MCP:

**For Claude.ai (web/app):**
> Kite MCP can be connected through Claude Desktop app. You'll need Node.js installed, then add the Kite MCP configuration to your Claude Desktop settings. The hosted version at `https://mcp.kite.trade/mcp` gives you read-only portfolio access with no API keys needed. For order placement, you'll need to self-host with your own Kite Connect API keys from https://developers.kite.trade.

**Quick setup (hosted, read-only):**
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

## Fallback Behavior

If Kite MCP is NOT connected:
- Use web search for all price data (with price verification rule)
- Use Zerodha GTT copy-paste format for order execution
- Ask user to manually provide holdings/positions for risk dashboard
- Note: "Connect Kite MCP for live portfolio data and real-time prices. It's free — see `https://zerodha.com/products/mcp/`"

The skill should work fully without Kite MCP — it's an enhancement, not a dependency.
