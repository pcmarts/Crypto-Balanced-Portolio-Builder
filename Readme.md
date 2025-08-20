# Crypto Portfolio by Market Cap
## Works out of the box
Simply download the HTML file, and open on the file your desktop computer. 

## Description
A single-file, client-side tool for building a **market-cap–weighted crypto portfolio** with per-asset caps.  
Fetches live data from CoinGecko, applies your constraints, and outputs a clean allocation with visuals and export options.  
No accounts. No servers. No API keys. 100% in-browser.  

---

## Why Use This?
- Build a diversified, market-cap-aligned portfolio in minutes.  
- Cap concentration risk per coin (e.g. 20%) and see how weight is redistributed.  
- Export allocations (CSV/JSON) for execution or record-keeping.  

---

## Features

### Inputs
- **Top N coins** by market cap  
- **Max weight cap (%)** per coin  
- **Portfolio value** (USD)  
- Include/exclude stablecoins  
- Custom coin exclusions  
- **Custom target allocations** with percentage weights for specific coins

### Allocation Logic
- Caps oversized weights and redistributes excess proportionally  
- Shows total % redistributed  
- **Custom targets** get exact allocations as specified (not subject to market cap weighting)
- Remaining percentage allocated to market cap weighted coins

### Results Table
- Sortable by: rank, symbol, name, price, market cap, weight %, target USD, target units  
- Market cap in compact units (M, B, T)  
- Target USD rounded to whole dollars  
- Target units:  
  - `< 1`: 4 decimal places (rounded up)  
  - `>= 1`: 3 decimal places (rounded up)  
- Inline weight bar with cap marker + yellow overlay for clipped portion  
- Coin names link to CoinGecko (new tab)  

### Visuals
- Cap effect strip with live % label + redistributed bar  
- Donut chart of allocations (hover slice highlight + synced legend focus)  

### Export
- Download CSV/JSON (respects current sort)  
- Download portfolio adjustments CSV after comparing with current holdings

### UX
- Dark, responsive UI  
- Keyboard-accessible  
- Smooth row animations  

### Custom Target Allocations
- Set specific percentage allocations for chosen coins (e.g., BTC 30%, ETH 30%)
- Custom targets receive exact allocations regardless of market cap
- Real-time calculation of remaining percentage for market cap allocation
- Prevents over-allocation with visual warnings and validation

### Current Holdings Comparison
- Upload CSV file with your current holdings (SYMBOL and AMOUNT columns)
- Compare current portfolio with target allocations
- See precise buy/sell/hold recommendations
- Calculate exact adjustment amounts and values
- Export detailed adjustment plan as CSV

### Privacy
- 100% client-side  
- Only calls CoinGecko's public API  

---

## Quick Start
1. Download this repo **or** just grab `crypto_portfolio_capped_v4.html`.  
2. Open it in any modern browser.  
3. Adjust inputs, set custom targets (optional), and click **Build Portfolio**.  
4. (Optional) Upload current holdings CSV to compare and get adjustment recommendations.
5. (Optional) Download allocations and adjustments as CSV/JSON.  

---

## How It Works (High Level)
1. Fetch Top N coins by market cap from CoinGecko.  
2. Compute baseline weights: `coin market cap / total market cap`.  
3. Apply max cap per coin; redistribute clipped weight proportionally until fully allocated.  
4. Calculate target USD + units using portfolio size.  
5. Render sortable table + visuals.  

---

## Notes & Limitations
- CoinGecko rate limits (HTTP 429) handled with simple retry/backoff.  
- Top N fetched with pagination; deduplicates symbols by highest market cap, then re-ranks.  
- All calculations are client-side — verify before trading.  
- Not financial advice.  

---

## Development
- **Stack:** HTML + CSS + Vanilla JS  
- **Single-file app:** edit `crypto_portfolio_capped_v4.html` directly  
- **Themeable:** colors in CSS `:root` variables  

---

## Attribution
- Market data from [CoinGecko Public API](https://coingecko.com)  
- Made with ❤️ by [The Marketing DAO](https://mktdao.xyz)  

---

## License
MIT — free to use, modify, and distribute.  
If you improve it, consider sharing back with the community.