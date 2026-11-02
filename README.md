# MarketPulse India — website MVP

A mobile-friendly Streamlit news dashboard for Indian and global markets. It collects configured RSS feeds, deduplicates stories in SQLite, optionally analyses new stories using OpenAI, and displays summaries, sentiment, impact scores, affected symbols (when identified), filters and source links.

## Run locally
1. Install Python 3.10+.
2. Extract this ZIP and open a terminal in the folder.
3. Create a virtual environment:
   - Windows: `py -m venv .venv` then `.venv\\Scripts\\activate`
   - macOS/Linux: `python3 -m venv .venv` then `source .venv/bin/activate`
4. Install: `pip install -r requirements.txt`
5. Copy `.env.example` to `.env`. AI key is optional. Keep secrets private.
6. Run: `streamlit run app.py`
7. Open the local address shown (usually http://localhost:8501).

## Hosting
For a public URL, deploy to Streamlit Community Cloud or a small VPS. For a private dashboard, add authentication or use a private VPS/VPN. Keep API keys in the hosting provider's secrets manager. SQLite needs persistent storage for reliable history.

## Feeds
Configured feeds: NSE announcements, SEBI, US Federal Reserve, ECB and Bank of England. RSS coverage and refresh speed vary. Check current feed URLs and publisher reuse terms. This MVP fetches when you click the button; no guaranteed instant breaking-news delivery. Add licensed providers only through authorised feeds/APIs.

## AI and safety
Without OPENAI_API_KEY the app uses a basic keyword classifier. With a key, new stories are analysed with the configured OpenAI model. AI output is not a verified fact or buy/sell instruction. Verify original disclosures. This app does not show live prices or place trades.

## Next upgrades
Scheduled refresh, login/password, WhatsApp alerts, watchlists, read-only Kite quotes, market-price widgets and more licensed news sources.
