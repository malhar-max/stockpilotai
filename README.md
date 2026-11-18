# StockPilot AI — prototype

A responsive, static frontend prototype for an Indian stock research and paper-trading education platform.

## Run locally
Open `index.html` in a modern browser. No build step is required.

## Included
- Stock symbol lookup with clearly labelled demo reference values
- Intraday / swing / long-term timeframe selector
- Screenshot upload preview (not AI image interpretation yet)
- Editable sample price, RSI and ATR inputs
- Transparent illustrative scenario levels
- Responsive dashboard UI

## Important limitations
This is NOT a live trading system or an investment adviser. Prices and chart art are demo-only. The scenario math is intentionally labelled illustrative and must not be used to place trades. No broker integration or order execution exists.

## Production implementation plan
1. Select an NSE/BSE market-data vendor and obtain written rights for storage, display, derived data and redistribution.
2. Build a backend (FastAPI or Next.js server routes) to fetch and timestamp data; never put vendor/API secrets in browser code.
3. Calculate indicators server-side from validated OHLCV data (RSI, ATR, MACD, SMA/EMA, volume, support/resistance).
4. Add corporate actions, trading sessions, symbol mapping, liquidity checks and stale-data detection.
5. Add screenshot vision on the server. Extract only visible facts, label OCR confidence, and cross-check against provider data.
6. Use an LLM only to explain structured calculations and risks; it must not invent prices or targets. Return WAIT/INSUFFICIENT DATA when evidence is incomplete or contradictory.
7. Backtest and paper-trade any strategy with realistic brokerage, taxes, slippage and survivorship-bias controls.
8. Add authentication, rate limiting, upload validation, private object storage, audit logs and deletion controls.
9. Obtain Indian securities-law advice before offering personalized recommendations or commercial advisory features. Keep this educational and simulated until properly reviewed.

## Suggested production stack
- Frontend: Next.js + TypeScript
- Backend: FastAPI / Python
- Database: Neon PostgreSQL
- AI: OpenAI API (server-side only)
- Hosting: Vercel + Render
- Storage/security: private object storage and Cloudflare
- Charts: TradingView Lightweight Charts (check applicable licence)
