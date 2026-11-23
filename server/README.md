# BurtsevWerk API

Malý server bez závislostí (Node 20+):

- `POST /api/contact` — správa z formulára príde do Telegramu.
- `POST /api/analyze` — AI expresná analýza webu (načítanie stránky + Google PageSpeed + Gemini).
- `GET /health` — stav: či sú nastavené kľúče.

## Render (Web Service)

- Root Directory: `server`
- Build Command: `echo ok`
- Start Command: `node server.js`
- Názov služby: `burtsevwerk-api` (web ju volá na `https://burtsevwerk-api.onrender.com`)

## Environment

| Premenná | Povinná | Popis |
|---|---|---|
| `GEMINI_API_KEY` | áno | kľúč z aistudio.google.com |
| `TELEGRAM_BOT_TOKEN` | áno | token od @BotFather |
| `TELEGRAM_CHAT_ID` | áno | ID chatu; ak chýba, server ho po spustení vypíše do Logs (najprv napíšte botovi /start) |
| `PAGESPEED_API_KEY` | nie | vyšší limit Google PageSpeed |
| `GEMINI_MODEL` | nie | zoznam modelov oddelený čiarkou, predvolené `gemini-3.1-flash-lite,gemini-2.5-flash` |
| `ALLOWED_ORIGINS` | nie | domény webu, predvolené burtsevwerk.eu, www.burtsevwerk.eu, burtsevwerk.onrender.com |
| `ANALYZE_PER_HOUR` / `ANALYZE_PER_DAY` | nie | limity analýz (3 za hodinu na IP, 150 za deň) |
