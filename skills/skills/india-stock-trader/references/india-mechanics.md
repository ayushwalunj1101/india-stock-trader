# Indian Market Mechanics

Critical India-specific rules and quirks that affect swing trading. These aren't optional knowledge — ignoring them can turn a winning setup into a trapped position.

---

## 1. Circuit Limits

NSE/BSE impose daily price bands on stocks. Once hit, trading halts in that direction.

**Circuit bands**: 2%, 5%, 10%, or 20% — varies by stock. F&O stocks typically don't have circuit limits (they have dynamic price bands instead).

**Why it matters for swing traders:**
- If you're long and the stock hits **upper circuit**, you can't buy more — but that's fine, your position is profitable
- If you're long and the stock hits **lower circuit**, you **cannot sell**. Your SL becomes useless. You're locked in until circuit opens or next day.
- Stocks that hit lower circuit often gap down further the next day as trapped sellers rush to exit

**How to handle:**
- Before entering any non-F&O stock, check its circuit limit band. Search "[STOCK] circuit limit NSE" or check NSE website.
- If a stock's SL is more than half the circuit band away from CMP, it's relatively safe. If SL is close to the circuit limit, gap risk is high.
- Flag in trade plans: "⚠️ Circuit limit: ±10%. SL at ₹385 is 4.7% below entry — within circuit band, SL should execute normally."
- For stocks with 5% circuit limits, swing trading is risky — a single bad day can lock you in.

---

## 2. T+1 Settlement

India moved to T+1 settlement in January 2023. Shares are credited to your demat account one trading day after purchase.

**What this means for swing traders:**
- If you buy on Monday, shares settle on Tuesday. You can sell on Monday itself (BTST — Buy Today Sell Tomorrow is allowed), but it's treated differently by brokers.
- Short selling in delivery (CNC) is NOT possible — you can only sell what you own.
- If you buy on Friday, settlement happens on Monday. Weekend risk is real — news over the weekend can gap the stock.

**How to handle:**
- For Friday entries, note: "Weekend risk applies — 2 days of potential news events before next trading session."
- Don't recommend buying before long weekends or holidays unless the setup is very strong (A-grade conviction).

---

## 3. ASM / GSM Framework

SEBI's Additional Surveillance Measures (ASM) and Graded Surveillance Measures (GSM) are applied to stocks showing unusual price/volume activity.

**ASM stages:**
- Stage 1: Trade-to-trade (no intraday), 100% margin
- Stage 2: Additional 20% margin, price band reduced to 5%
- Stage 3: Additional 40% margin, price band reduced to 5%
- Stage 4: Additional 60% margin, price band reduced to 2%

**GSM stages**: Similar escalation with even stricter restrictions.

**Why it matters:**
- ASM/GSM stocks have reduced circuit limits — your SL may not execute
- 100% margin means no leverage — full capital required upfront
- Trade-to-trade means you MUST take delivery — no intraday exit possible
- These stocks are often flagged because of operator manipulation

**How to handle:**
- Before recommending any mid/small cap stock, search "[STOCK] ASM GSM status NSE"
- If a stock is under ASM/GSM: **Do not recommend for swing trading.** Flag it: "⚠️ Under ASM Stage [X] — restricted trading, reduced circuits, likely operator activity. Avoid."
- Even if a stock recently exited ASM/GSM, treat with caution for 2-4 weeks — the conditions that triggered surveillance may still be in play.

---

## 4. F&O Ban Period

When open interest in a stock's F&O contracts crosses 95% of the Market Wide Position Limit (MWPL), the stock enters the F&O ban period.

**What happens:**
- No new F&O positions can be created (only existing positions can be squared off)
- This forces F&O traders to either hold or close positions
- Cash market trading continues normally, but price action becomes erratic as F&O positions unwind

**Why it matters for swing traders:**
- Stocks in F&O ban often show unusual volatility — wild intraday swings that don't follow normal technical patterns
- Delivery volumes may spike artificially as F&O traders convert positions
- The stock can whipsaw violently and then normalize once ban is lifted

**How to handle:**
- Search "[STOCK] F&O ban today" or check NSE's daily F&O ban list
- If a stock is in F&O ban: **Flag prominently.** "⚠️ Currently in F&O ban — expect erratic price action. Consider waiting until ban is lifted before entering."
- Some traders specifically trade F&O ban stocks for volatility — but that's a different strategy, not standard swing trading.

---

## 5. Operator Activity / Pump-and-Dump Warnings

In Indian markets, some mid/small cap stocks are manipulated by "operators" — coordinated groups that artificially inflate prices to dump on retail traders.

**Red flags to watch for:**
- Sudden 20%+ move in a stock with no fundamental catalyst or news
- Volume spike from near-zero average to 10x+ in a single day
- Very low delivery percentage (<15%) despite huge volume — pure speculation
- Stock price moving up in a straight line for multiple days without any pullback
- The company's fundamentals don't justify the move (tiny revenue, no earnings growth, obscure business)
- Stock is micro/small cap with market cap below ₹2,000 Cr and very low institutional holding
- Multiple social media/Telegram tips about the same stock simultaneously

**How to handle:**
- If a stock shows 3+ of the above red flags: "⚠️ Possible operator activity — avoid. The breakout may be manufactured."
- Stick to Nifty 200 / large-mid cap universe for reliable setups. Only venture into small caps if the user specifically asks and understands the risk.
- Delivery % is your best friend here — operators generate volume through intraday churn, so delivery % is typically very low (<20%) on pump days.

---

## 6. Budget & RBI Policy Patterns

Certain Indian events create recurring sector-level patterns that experienced traders exploit.

**Union Budget (February):**
- Infrastructure, defence, railways, agriculture stocks rally 2-4 weeks before budget on anticipation
- "Buy the rumor, sell the news" — many of these stocks correct after budget regardless of actual announcements
- FMCG/consumer stocks may react to duty changes on raw materials

**RBI Monetary Policy (bi-monthly):**
- Banks, NBFCs, housing finance stocks are most sensitive
- Rate cut expectation → banks rally into the announcement
- Hawkish surprise → sharp sell-off in rate-sensitives
- The market usually prices in the expected decision — the reaction is to the SURPRISE element

**F&O Expiry (last Thursday of month):**
- Increased volatility, especially in the last 2-3 days
- Option writers drive price toward max pain (the strike where most options expire worthless)
- Swing traders should be cautious about entering new positions in expiry week — let the noise settle

**Quarter-end / FY-end (March):**
- Mutual funds engage in window dressing — buying/selling to make portfolios look good
- Tax-loss harvesting in March can create artificial selling pressure in beaten-down stocks
- FY-end flows can distort price action

**How to handle:**
- When building a trade plan, check if any of these events fall within the expected holding period
- Flag in the Risk Calendar section: "RBI MPC on April 1 — HDFCBANK and other banks may see event-driven volatility"
- Don't fight event-driven flows — if budget/RBI is within your holding period, either enter after the event or size down.
