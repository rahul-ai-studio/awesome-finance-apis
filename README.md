# Awesome Free Finance APIs [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

> Curated list of free/freemium APIs for banking, capital markets, FX, and derivatives data. Every fintech developer needs this.

Stop paying for market data you don't need yet. This list is for developers who want to **ship first, pay later** — every API here has a free tier you can hit with `curl` in under 60 seconds. No sales calls, no enterprise contracts.

**40+ APIs** across 8 categories, personally verified, with real rate limits and honest limitations.

---

## Contents

- [Try it right now](#try-it-right-now)
- [Why this list?](#why-this-list)
- [How to use this list](#how-to-use-this-list)
- [Banking \& Open Banking](#banking--open-banking)
- [Equities \& ETFs](#equities--etfs)
- [Fixed Income \& Credit](#fixed-income--credit)
- [FX \& Crypto](#fx--crypto)
- [Derivatives \& Options](#derivatives--options)
- [Macro \& Economic Data](#macro--economic-data)
- [Alternative \& Sentiment Data](#alternative--sentiment-data)
- [Market Infrastructure \& Reference Data](#market-infrastructure--reference-data)
- [Getting Started Quickly](#getting-started-quickly)
- [Caveats \& Compliance](#caveats--compliance)
- [Roadmap / Ideas](#roadmap--ideas)
- [Contributing](#contributing)

---

## Try it right now

Don't take our word for it — paste these into your terminal. No API key needed for any of them.

**Get today's EUR/USD rate:**

```bash
curl -s https://api.frankfurter.app/latest?from=EUR&to=USD | python3 -m json.tool
```

**Fetch US GDP data from the World Bank:**

```bash
curl -s "https://api.worldbank.org/v2/country/US/indicator/NY.GDP.MKTP.CD?format=json&per_page=5" | python3 -m json.tool
```

**Look up Apple's FIGI identifier:**

```bash
curl -s -X POST "https://api.openfigi.com/v3/mapping" \
  -H "Content-Type: application/json" \
  -d '[{"idType":"TICKER","idValue":"AAPL","exchCode":"US"}]' | python3 -m json.tool
```

**Get Bitcoin price from CoinGecko:**

```bash
curl -s "https://api.coingecko.com/api/v3/simple/price?ids=bitcoin&vs_currencies=usd,eur,gbp" | python3 -m json.tool
```

> These all work. Right now. For free. The rest of this list has 40+ more like them.

---

## Why this list?

Financial data APIs are everywhere, but finding ones with genuinely usable free tiers is surprisingly hard. Most "free" offerings bury rate limits, hide asset coverage gaps, or require enterprise contracts for anything beyond a demo. This list cuts through the noise.

**Who this is for:**

- **Fintech developers** building MVPs or prototypes.
- **Quants & algo traders** who need data for backtesting without a Bloomberg terminal.
- **Data scientists** exploring financial datasets.
- **Students & hobbyists** learning about markets programmatically.

## How to use this list

Each entry follows a consistent format:

- **Name** — linked to docs or homepage.
- **Description** — what the API provides, in one sentence.
- **Best for** — the primary use case where it shines.
- **Free tier** — what you get without paying.
- **Limitations** — constraints worth knowing upfront.

Browse by category, or jump to [Getting Started Quickly](#getting-started-quickly) for curated starter stacks.

---

## Banking & Open Banking

APIs for account aggregation, payment initiation, transaction data, and PSD2/open-banking sandbox environments.

- [**Plaid Sandbox**](https://plaid.com/docs/sandbox/) — Account linking, transaction, and balance APIs used by thousands of fintech apps.
  - **Best for:** Prototyping account aggregation and personal-finance apps.
  - **Free tier:** Sandbox environment with unlimited test calls; 100 live Items in development.
  - **Limitations:** Production use requires a paid plan. Live credentials are US/Canada/UK/EU focused.

- [**TrueLayer Sandbox**](https://truelayer.com/docs/) — Open-banking API providing account, balance, and transaction access across UK and European banks.
  - **Best for:** PSD2-compliant open-banking prototypes in the UK/EU.
  - **Free tier:** Full sandbox with mock bank connections; free live tier available with limited volume.
  - **Limitations:** Live coverage is primarily UK and EU. Production pricing is per-API-call.

- [**Tink Sandbox**](https://docs.tink.com/) — Open-banking platform (Visa-owned) supporting account aggregation and payment initiation across Europe.
  - **Best for:** European multi-bank aggregation and payment initiation prototypes.
  - **Free tier:** Sandbox environment with test data; free to start building.
  - **Limitations:** Production requires commercial agreement. Coverage varies by country.

- [**MX Platform**](https://docs.mx.com/) — Financial data aggregation, transaction enrichment, and account verification.
  - **Best for:** Transaction categorization and financial wellness app prototyping.
  - **Free tier:** Sandbox with synthetic data and full API access.
  - **Limitations:** Live data access requires a paid plan. US/Canada focused.

- [**Yapily Sandbox**](https://docs.yapily.com/) — Open-banking connectivity API supporting account info and payments across European banks.
  - **Best for:** Multi-country European open-banking integrations.
  - **Free tier:** Sandbox access; free application tier for early-stage startups.
  - **Limitations:** Production volume pricing applies. Coverage is Europe-centric.

## Equities & ETFs

APIs for stock quotes, historical prices, fundamentals, and ETF data.

- [**Alpha Vantage**](https://www.alphavantage.co/documentation/) — Broad financial data API covering stocks, forex, crypto, and technical indicators.
  - **Best for:** Low-frequency backtesting and learning projects.
  - **Free tier:** 25 requests/day with a free API key.
  - **Limitations:** Tight daily rate limit on free plan. Intraday data limited to recent months.

- [**Finnhub**](https://finnhub.io/docs/api) — Real-time stock prices, company fundamentals, and alternative data (earnings, filings, ESG).
  - **Best for:** Real-time quote monitoring and fundamental screening.
  - **Free tier:** 60 calls/minute; real-time US quotes via WebSocket.
  - **Limitations:** Some endpoints (institutional ownership, advanced estimates) are premium only.

- [**Twelve Data**](https://twelvedata.com/docs) — Time-series stock, forex, and crypto data with 100+ technical indicators built in.
  - **Best for:** Technical analysis workflows and charting applications.
  - **Free tier:** 800 calls/day; 8 calls/minute.
  - **Limitations:** End-of-day data only for some exchanges on the free tier. Limited to 5,000 rows per request.

- [**Marketstack**](https://marketstack.com/documentation) — Intraday and historical stock data for 70+ exchanges worldwide.
  - **Best for:** Global equity coverage for international stock screeners.
  - **Free tier:** 100 requests/month; end-of-day data.
  - **Limitations:** Free plan is HTTP only (no HTTPS). Intraday data requires a paid plan.

- [**Polygon.io**](https://polygon.io/docs) — Comprehensive US market data including ticks, trades, quotes, and aggregates.
  - **Best for:** Tick-level US equities and options research.
  - **Free tier:** Basic plan provides 5 API calls/minute and delayed data; 2 years of end-of-day history.
  - **Limitations:** Real-time and full-depth data require paid plans. Free tier is quite limited in throughput.

- [**IEX Cloud**](https://iexcloud.io/documentation) — US-focused stock quotes, financials, and market data from IEX exchange.
  - **Best for:** US equity dashboards and lightweight stock apps.
  - **Free tier:** Pay-as-you-go with free monthly credit (subject to change — check current plans).
  - **Limitations:** Credit-based pricing model can be confusing. International data is limited.

- [**Financial Modeling Prep**](https://site.financialmodelingprep.com/developer/docs) — Stock fundamentals, financial statements, DCF models, and screening data.
  - **Best for:** Fundamental analysis, financial-statement scraping, and stock screening.
  - **Free tier:** 250 requests/day; access to core financial statements and quote endpoints.
  - **Limitations:** Some bulk endpoints and international data are premium. Historical data depth varies.

- [**Tiingo**](https://www.tiingo.com/documentation/general/overview) — End-of-day and intraday US stock data, plus news and crypto feeds.
  - **Best for:** Daily backtesting with clean, adjusted historical data going back decades.
  - **Free tier:** 1,000 requests/hour; 50 concurrent WebSocket connections for IEX real-time.
  - **Limitations:** Intraday data coverage is IEX exchange only on free tier. No international equities.

- [**Stooq**](https://stooq.com/) — Free historical end-of-day data for global equities, indices, and bonds (CSV download).
  - **Best for:** Bulk historical data downloads for offline analysis.
  - **Free tier:** Free CSV downloads; no API key required.
  - **Limitations:** No REST API — data is downloaded via URL-constructed CSV links. No real-time data.

## Fixed Income & Credit

APIs for bond prices, yields, credit ratings, and fixed-income analytics.

- [**FRED API (Federal Reserve Economic Data)**](https://fred.stlouisfed.org/docs/api/fred/) — 800,000+ economic and financial time series from the St. Louis Fed, including Treasury yields, credit spreads, and interest rates.
  - **Best for:** US Treasury yields, interest rate curves, credit spreads, and macro-fixed-income analysis.
  - **Free tier:** 120 requests/minute with a free API key.
  - **Limitations:** Data is observational (rates, yields, spreads) — no individual bond pricing or CUSIP-level data.

- [**Quandl / Nasdaq Data Link**](https://docs.data.nasdaq.com/) — Curated financial and economic datasets including yield curves, credit data, and corporate bond indices.
  - **Best for:** Sourcing structured fixed-income datasets for quantitative research.
  - **Free tier:** Several free datasets (FRED-sourced, Wiki, community tables); API access with a free key.
  - **Limitations:** Premium datasets (individual bond pricing, structured products) are paid. Free datasets can be limited in freshness.

- [**OpenFIGI**](https://www.openfigi.com/api) — Maps trading symbols and identifiers (ISIN, CUSIP, SEDOL, ticker) to Bloomberg FIGI codes.
  - **Best for:** Resolving bond and security identifiers across systems.
  - **Free tier:** 25,000 mapping requests/day without an API key; 250,000/day with a key.
  - **Limitations:** Provides identifier mapping only — no pricing or analytical data.

- [**ECB Data Portal API**](https://data.ecb.europa.eu/help/api/overview) — Euro area yield curves, interest rate statistics, and monetary data from the European Central Bank.
  - **Best for:** Euro-denominated yield curves and ECB policy rate data.
  - **Free tier:** Fully free; no API key required.
  - **Limitations:** European data only. SDMX format can be complex to parse.

## FX & Crypto

APIs for foreign exchange rates, currency conversion, and cryptocurrency market data.

### Foreign Exchange

- [**Exchange Rates API (exchangerate.host / exchangerate-api.com)**](https://exchangerate.host/) — Simple JSON API for historical and current FX rates sourced from ECB and other providers.
  - **Best for:** Currency conversion and historical FX rate lookups.
  - **Free tier:** Varies by provider — exchangerate.host offers free access; exchangerate-api.com offers 1,500 requests/month free.
  - **Limitations:** Rates are typically daily snapshots (no intraday tick data). Source is often ECB reference rates.

- [**Frankfurter**](https://www.frankfurter.app/docs/) — Open-source API for current and historical FX rates published by the ECB.
  - **Best for:** Simple currency conversion with no API key required.
  - **Free tier:** Completely free and open-source; self-hostable.
  - **Limitations:** ECB reference rates only (updated daily around 16:00 CET). No weekends/holidays. ~30 currencies.

- [**Open Exchange Rates**](https://docs.openexchangerates.org/) — FX rates for 170+ currencies with hourly updates.
  - **Best for:** Multi-currency apps needing broad coverage.
  - **Free tier:** 1,000 requests/month; hourly updates; USD base only.
  - **Limitations:** Free plan restricts base currency to USD. Historical data requires a paid plan.

- [**Currencyapi.com**](https://currencyapi.com/docs/) — Real-time and historical exchange rates for 150+ currencies.
  - **Best for:** Lightweight currency conversion for SaaS applications.
  - **Free tier:** 300 requests/month.
  - **Limitations:** Low free-tier volume. Some historical endpoints require paid access.

- [**RealMarketAPI**](https://realmarketapi.com/docs/) — REST API for market data across gold, forex, crypto, and stocks.
  - **Best for:** Applications that need basic spot quotes across multiple asset classes from one API and can work within the 60-instrument free-tier limit.
  - **Free tier:** 5,000 requests/month.
  - **Limitations:** Only 60 instruments exists. Historical data requires a paid plan.

### Cryptocurrency

- [**CoinGecko API**](https://docs.coingecko.com/reference/introduction) — Comprehensive crypto data: prices, market cap, volume, exchanges, and DeFi metrics for 10,000+ coins.
  - **Best for:** Broad crypto market data and portfolio tracking.
  - **Free tier:** ~30 calls/minute (Demo plan with free API key); historical data included.
  - **Limitations:** Rate limits can be tight under heavy usage. No WebSocket on the free plan.

- [**CoinMarketCap API**](https://coinmarketcap.com/api/documentation/v1/) — Crypto prices, market cap rankings, exchange listings, and metadata.
  - **Best for:** Market-cap-weighted crypto rankings and metadata.
  - **Free tier:** 10,000 calls/month; basic plan.
  - **Limitations:** Historical data is limited on free tier. Some endpoints (DEX data, advanced metrics) are paid.

- [**Binance Public API**](https://binance-docs.github.io/apidocs/spot/en/) — Real-time and historical market data for all Binance-listed trading pairs.
  - **Best for:** Crypto algo trading, real-time order book and candle data.
  - **Free tier:** Public market data endpoints are free; no API key needed for read-only data.
  - **Limitations:** Trading endpoints require account and key. Rate limits are IP-based (1,200 requests/minute for most endpoints).

- [**Kraken REST API**](https://docs.kraken.com/api/) — Market data, OHLC, order book, and trade history for Kraken-listed pairs.
  - **Best for:** Crypto market data from a regulated exchange with fiat pairs.
  - **Free tier:** Public endpoints are free; no key required.
  - **Limitations:** Only covers Kraken-listed pairs. Rate limits apply per-tier.

- [**Messari API**](https://messari.io/api) — Crypto asset profiles, quantitative metrics, and market data with editorial research.
  - **Best for:** Fundamental crypto research and asset profiling.
  - **Free tier:** Free tier with access to asset profiles, metrics, and basic market data.
  - **Limitations:** Time-series and advanced features require a paid plan.

## Derivatives & Options

APIs for options chains, implied volatility, futures data, and derivatives analytics.

- [**CBOE Delayed Quotes**](https://www.cboe.com/delayed_quotes/) — Delayed options and volatility data from CBOE, including VIX and options chains.
  - **Best for:** Exploring CBOE-listed options and volatility indices.
  - **Free tier:** Delayed data freely accessible on the website; limited programmatic access.
  - **Limitations:** Not a formal REST API — requires scraping or third-party wrappers. Data is delayed (typically 15 min).

- [**Tradier**](https://documentation.tradier.com/) — US options and equities brokerage API with market data including options chains.
  - **Best for:** Options chain data and paper trading for US markets.
  - **Free tier:** Sandbox (paper trading) with full API access; delayed market data is free.
  - **Limitations:** Real-time data and live trading require a funded brokerage account. US markets only.

- [**Polygon.io Options**](https://polygon.io/docs/options) — US options data including contracts, aggregates, and snapshots.
  - **Best for:** Historical US options data for research and backtesting.
  - **Free tier:** Included in Polygon's basic free plan (5 calls/min, delayed data).
  - **Limitations:** Full historical options data and real-time feeds require paid plans.

- [**Deribit Public API**](https://docs.deribit.com/) — Crypto derivatives exchange offering options and futures on BTC and ETH.
  - **Best for:** Crypto options and futures market data (order books, volatility surfaces).
  - **Free tier:** Public market data is free; WebSocket supported.
  - **Limitations:** Only covers Deribit-listed instruments (BTC, ETH). Trading requires an account.

- [**CME Group Datamine (Samples)**](https://www.cmegroup.com/market-data/datamine-api.html) — Sample historical data from CME for futures and options.
  - **Best for:** Exploring CME futures/options data structure and building parsers.
  - **Free tier:** Free sample datasets available for download.
  - **Limitations:** Full production data requires a commercial license. Samples are limited in scope and date range.

## Macro & Economic Data

APIs for GDP, inflation, employment, central bank rates, and other economic indicators.

- [**FRED API**](https://fred.stlouisfed.org/docs/api/fred/) — The gold standard for US economic data — 800,000+ series including GDP, CPI, employment, interest rates, and more.
  - **Best for:** Any US macro analysis, economic research, or rate modeling.
  - **Free tier:** 120 requests/minute; full historical data for all series.
  - **Limitations:** Primarily US-focused. Some series have publication lag.

- [**World Bank Open Data API**](https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation) — Development indicators for 200+ countries: GDP, trade, population, poverty, education, and more.
  - **Best for:** Cross-country macro comparisons and emerging-market research.
  - **Free tier:** Completely free; no API key required.
  - **Limitations:** Data frequency is typically annual or quarterly. Can lag by 1–2 years for some countries.

- [**IMF Data API**](https://datahelp.imf.org/knowledgebase/articles/667681-using-json-restful-web-service) — International Financial Statistics, Balance of Payments, Government Finance Statistics, and other IMF datasets.
  - **Best for:** Sovereign debt analysis, balance-of-payments research, and international macro comparisons.
  - **Free tier:** Completely free; no API key required.
  - **Limitations:** SDMX/JSON format. Some datasets have multi-month publication lag.

- [**BLS API (Bureau of Labor Statistics)**](https://www.bls.gov/developers/) — US labor market data: employment, unemployment, CPI, PPI, wages, and productivity.
  - **Best for:** US employment and inflation research.
  - **Free tier:** V2 API with registration: 500 queries/day; up to 20 years of data per request.
  - **Limitations:** US labor data only. V1 (no key) has stricter limits (25 series, 10 years).

- [**ECB Statistical Data Warehouse**](https://data.ecb.europa.eu/help/api/overview) — Euro area monetary, financial, and economic statistics.
  - **Best for:** Euro-area macro indicators, monetary aggregates, and balance-of-payments.
  - **Free tier:** Fully free; no key required.
  - **Limitations:** SDMX format. Euro area / EU focus.

- [**DBnomics**](https://db.nomics.world/docs/api) — Aggregator providing a unified API to access data from 80+ statistical institutions (FRED, ECB, Eurostat, OECD, etc.).
  - **Best for:** One-stop access to multiple global macro databases through a single API.
  - **Free tier:** Completely free; no API key required.
  - **Limitations:** Aggregator — data freshness depends on the upstream provider. Some series may have gaps.

## Alternative & Sentiment Data

APIs for news feeds, social sentiment, ESG scores, and other non-traditional data sources.

- [**NewsAPI**](https://newsapi.org/docs) — Search and retrieve live news articles from 150,000+ sources worldwide.
  - **Best for:** News-driven trading signals and media monitoring.
  - **Free tier:** 100 requests/day; articles up to 1 month old.
  - **Limitations:** Free plan is for development only (not production). Results are delayed by 1 hour on the free tier.

- [**Finnhub News & Sentiment**](https://finnhub.io/docs/api/company-news) — Company news, market news, and basic sentiment indicators integrated into the Finnhub API.
  - **Best for:** Combining market data and news in a single API.
  - **Free tier:** Included in Finnhub's free plan (60 calls/min).
  - **Limitations:** Sentiment analysis is basic. Deep NLP features are premium.

- [**GNews API**](https://gnews.io/docs/v4) — News search API with topic and keyword filtering across multiple languages.
  - **Best for:** Multi-language financial news monitoring.
  - **Free tier:** 100 requests/day; 10 articles per search.
  - **Limitations:** Low article count per query on free tier. No sentiment scoring built in.

- [**Reddit API**](https://www.reddit.com/dev/api/) — Access posts and comments from financial subreddits (r/wallstreetbets, r/investing, etc.).
  - **Best for:** Retail sentiment analysis and meme-stock tracking.
  - **Free tier:** 100 requests/minute with OAuth; free for non-commercial use.
  - **Limitations:** Requires OAuth setup. Terms of service restrict commercial use without agreement.

- [**Unusual Whales API**](https://docs.unusualwhales.com/) — Options flow, dark pool data, and political trading tracker.
  - **Best for:** Options flow sentiment and unusual activity monitoring.
  - **Free tier:** Limited free access; some endpoints available without subscription.
  - **Limitations:** Most detailed data requires a paid subscription.

- [**ESG Enterprise**](https://www.esgenterprise.com/esg-analytics/esg-api/) — ESG risk ratings and scores for publicly traded companies.
  - **Best for:** Integrating ESG scores into screening or portfolio construction.
  - **Free tier:** Limited free tier available (check current offering).
  - **Limitations:** Coverage and data depth increase with paid plans.

## Market Infrastructure & Reference Data

APIs for instrument identifiers, exchange calendars, symbology, and other reference data.

- [**OpenFIGI**](https://www.openfigi.com/api) — Bloomberg's open symbology mapping service: map tickers, ISINs, CUSIPs, and SEDOLs to FIGI identifiers.
  - **Best for:** Cross-referencing security identifiers across data systems.
  - **Free tier:** 25,000 requests/day (no key); 250,000/day (with free key).
  - **Limitations:** Mapping only — no pricing or fundamental data.

- [**Exchangeratesapi.io / ISO Currency Data**](https://www.six-group.com/en/products-services/financial-information/data-standards.html) — ISO 4217 currency codes and metadata maintained by SIX.
  - **Best for:** Currency code reference data and standardization.
  - **Free tier:** ISO standard lists are freely published.
  - **Limitations:** Static reference data — no live rates.

- [**trading_calendars / exchange_calendars**](https://github.com/gerrymanoim/exchange_calendars) — Open-source Python library providing trading calendars for 50+ global exchanges.
  - **Best for:** Knowing when markets are open, including half-days and holidays.
  - **Free tier:** Fully open source (Apache 2.0).
  - **Limitations:** Python library, not a REST API. Calendar accuracy depends on community maintenance.

- [**SEC EDGAR API**](https://www.sec.gov/search#/dateRange=custom&startdt=2024-01-01&enddt=2024-12-31) — Full-text search and structured data for SEC filings (10-K, 10-Q, 8-K, 13-F, etc.).
  - **Best for:** US public company filings, insider transactions, and institutional holdings.
  - **Free tier:** Completely free; rate limit of 10 requests/second (must include User-Agent header).
  - **Limitations:** US-listed companies only. Raw filings require parsing (XBRL/HTML).

- [**SEC EDGAR Full-Text Search API**](https://efts.sec.gov/LATEST/search-index?q=) — Search through the full text of SEC filings.
  - **Best for:** Keyword-based search across SEC filings for due diligence and research.
  - **Free tier:** Free; same rate limit as EDGAR (10 req/sec with User-Agent).
  - **Limitations:** US filings only. Results are filing excerpts — full document retrieval is a separate call.

- [**GLEIF API**](https://www.gleif.org/en/lei-data/gleif-api) — Legal Entity Identifier (LEI) lookup and entity reference data.
  - **Best for:** KYC, entity resolution, and counterparty identification.
  - **Free tier:** Completely free; no key required.
  - **Limitations:** LEI data only — no market or financial data.

---

## Getting Started Quickly

Not sure where to begin? Here are a few starter stacks for common use cases.

### Retail Algo Trading Starter Stack

Build a simple equity trading bot or screener:

| Need | API | Why |
|---|---|---|
| Daily stock prices | [Alpha Vantage](https://www.alphavantage.co/) or [Tiingo](https://www.tiingo.com/) | Clean historical data; enough for daily strategies |
| Real-time quotes | [Finnhub WebSocket](https://finnhub.io/) | Free real-time US stock quotes |
| Fundamentals | [Financial Modeling Prep](https://financialmodelingprep.com/) | Financial statements and ratios |
| News sentiment | [Finnhub News](https://finnhub.io/) | Company news integrated with market data |
| Paper trading | [Tradier Sandbox](https://documentation.tradier.com/) | Full brokerage API in sandbox mode |

### FX Backtesting Starter Stack

Backtest a currency strategy with historical data:

| Need | API | Why |
|---|---|---|
| Historical FX rates | [Frankfurter](https://www.frankfurter.app/) | Free, no key, clean daily rates since 1999 |
| Real-time FX quotes | [Twelve Data](https://twelvedata.com/) | Intraday forex data on free tier |
| Economic indicators | [FRED](https://fred.stlouisfed.org/docs/api/fred/) | Interest rate differentials, CPI, employment |
| Economic calendar | [World Bank](https://datahelpdesk.worldbank.org/) | Cross-country macro comparisons |
| Currency codes | [OpenFIGI](https://www.openfigi.com/) | Standardize instrument identifiers |

### Crypto Research Starter Stack

Analyze crypto markets and build a portfolio tracker:

| Need | API | Why |
|---|---|---|
| Market data | [CoinGecko](https://docs.coingecko.com/) | Prices, market cap, volume for 10,000+ coins |
| Order books & trades | [Binance Public API](https://binance-docs.github.io/apidocs/) | Deep real-time market data |
| Derivatives | [Deribit](https://docs.deribit.com/) | Options and futures market data for BTC/ETH |
| On-chain / fundamental | [Messari](https://messari.io/api) | Asset profiles and quantitative metrics |
| Social sentiment | [Reddit API](https://www.reddit.com/dev/api/) | Track r/CryptoCurrency, r/Bitcoin sentiment |

---

## Caveats & Compliance

Before building anything production-grade with free-tier data, keep these in mind:

- **Data quality varies.** Free-tier data may be delayed, adjusted differently, or have gaps. Always validate against a trusted source before making financial decisions.
- **Rate limits are real.** Exceeding free-tier limits will get you throttled or banned. Build in backoff and caching from day one.
- **Licensing matters.** Some APIs restrict commercial use on free tiers. Read the terms of service — "free" doesn't always mean "free to monetize."
- **Exchange data agreements.** Redistribution of real-time exchange data (NYSE, NASDAQ, CME, etc.) typically requires exchange agreements regardless of your data vendor's pricing.
- **Not financial advice.** This list is a developer resource. Nothing here constitutes investment advice, and API data should not be the sole basis for trading decisions.
- **Regulatory considerations.** If you're building for end users, be aware of regulations in your jurisdiction (MiFID II, Reg NMS, GDPR for PII in banking APIs, etc.).

---

## Roadmap / Ideas

Things that could make this list even better — PRs welcome:

- [ ] **SDK code samples** — Minimal working examples (Python, JavaScript, Go) for each API.
- [ ] **Comparison tables** — Side-by-side feature matrix for overlapping APIs (e.g., all equity data providers).
- [ ] **Uptime & latency tracking** — Community-sourced reliability data for each API.
- [ ] **Machine-readable list** — JSON/YAML version in `data/` for programmatic consumption.
- [ ] **Authentication guide** — Common patterns (API key, OAuth, WebSocket auth) across providers.
- [ ] **Rate-limit cheat sheet** — Quick-reference table of all free-tier limits.
- [ ] **Dead link checker** — GitHub Action to periodically validate all URLs.

---

## Contributing

Found an API we're missing? See something wrong? Contributions are welcome — but please read the guidelines first.

**[Read CONTRIBUTING.md](CONTRIBUTING.md)** before opening a PR. It contains:

- The **entry template** (required for all new API submissions).
- **Quality guidelines** — what gets merged and what gets closed.
- **Self-promotion policy** — disclose affiliations or get banned.
- **Anti-spam rules** — link dumps, SEO spam, and unverified AI-generated content are closed on sight.

The short version:

1. Check for duplicates (README + open issues/PRs).
2. One API per PR, using the entry template.
3. Fill out the PR checklist completely.
4. Maintainers reserve the right to close PRs without detailed justification.

We also have a [Code of Conduct](CODE_OF_CONDUCT.md). The TL;DR: be respectful, be constructive, don't spam.

---

## License

[MIT](LICENSE) — use this list however you like.

---

**If this list saved you time, [star the repo](../../stargazers)** — it helps other developers find it.

Found something wrong? [Open an issue](../../issues/new/choose). Know an API we're missing? [Submit a PR](CONTRIBUTING.md).
