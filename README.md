# 📈 Trading Gym — Institutional-Grade Financial Simulator & AI Coach

**Trading Gym** is an interactive, browser-based financial market simulator designed to teach technical analysis, disciplined execution, and risk management in a zero-risk paper trading environment. Featuring high-frequency live candlestick charting, bracket order execution (Stop-Loss / Take-Profit), historical market stress replays, and an AI trading mentor ("Athena"), Trading Gym bridges the gap between financial theory and live market psychology.

---

## 🎯 Vision & Purpose

Most beginner traders fail not because of flawed indicators, but due to poor capital sizing, lack of invalidation criteria, and emotional panic during liquidity drawdowns. 

Trading Gym simulates realistic tick dynamics, order book filling, and volatility shocks—giving users a safe, hands-on playground to:
- Test breakout, trend-following, and mean-reversion setups.
- Internalize strict $1\text{–}2\%$ risk management rules before committing real capital.
- Experience high-volatility events (flash crashes, parabolic rallies) without financial loss.
- Receive instant feedback on trade setups from an AI risk auditor.

---

## 🚀 Key Features

### 1. 📊 Real-Time Interactive Canvas Charting
- **Candlestick & Line Modes**: High-performance HTML5 Canvas rendering of price action, dynamic wicks, bodies, and volume histograms.
- **Technical Overlays**:
  - **Moving Average ($MA_{20}$)**: 20-period dynamic trend baseline.
  - **Interactive Crosshair HUD**: Inspect precise Open, High, Low, Close, and Volume values for any bar on hover.
  - **Visual Trade Entry Markers**: Active position entries are drawn directly onto the chart with real-time level tags.

### 2. ⚡ Execution Ticket & Risk Manager
- **Long (Buy) & Short (Sell) Execution**: Full support for two-way directional trading.
- **Order Types**: Instant Market Orders and target Limit Orders.
- **Bracket Risk Protection**:
  - Pre-configure exact **Stop-Loss** and **Take-Profit** price thresholds.
  - Built-in tick engine continuously monitors prices and automatically triggers bracket exits.
- **Fractional Sizing Helpers**: One-click position allocation buttons ($25\%$, $50\%$, $100\%$ of available liquidity) and live dollar value/portfolio risk exposure readouts.

### 3. 🌐 Multi-Asset Market Watch & Live Ticker
- **Diverse Asset Classes**:
  - **Tech Equities**: NVIDIA (`NVDA`), Apple (`AAPL`), Tesla (`TSLA`).
  - **Cryptocurrencies**: Bitcoin (`BTC/USD`), Ethereum (`ETH/USD`).
  - **Commodities**: Gold Spot (`GOLD`).
- **Category Filtering**: Instant switching between All, Tech Stocks, and Crypto.
- **Streaming Ticker Ribbon**: Top marquee ticker simulating streaming interbank feeds.
- **Market Sentiment / Fear & Greed Gauge**: Visual representation of current market momentum.

### 4. 🌪️ Market Engine & Stress Replay Scenarios
- **Speed Control**: Toggle between Paused (`0x`), Normal (`1x`), Accelerated (`3x`), and Hyper (`5x`) time speeds to backtest setups rapidly.
- **Scenario Stress Testing**:
  - **Normal Market Flow**: Natural drift and brownian random walk volatility.
  - **Scenario 1: 2023 AI Momentum Surge**: Bullish drift simulating parabolic breakout rallies.
  - **Scenario 2: 2020 Flash Liquidity Dump**: Sudden sharp gap-downs to test stop-loss execution and panic resilience.
  - **Scenario 3: Range-Bound Consolidation**: Low-trend chop designed for support/resistance practice.

### 5. 💼 Portfolio Ledger & Performance Metrics
- **Real-Time Header HUD**: Tracks Total Equity, Available Cash, Unrealized P&L ($ and %), and aggregate Win Rate.
- **Dual Position Ledger**:
  - **Open Positions Tab**: Live mark-to-market valuations and instant manual close options.
  - **Trade Log Tab**: Historical record of filled orders, exit prices, realized P&L, timestamps, and exit reasons (Take-Profit, Stop-Loss, Manual Close).
- **One-Click Reset**: Restore paper balance back to $\$100,000.00$ at any time.

### 6. 🧠 AI Trading Mentor: "Athena" (Powered by Google Gemini)
- Embedded strategy auditor evaluating chart patterns, overextended momentum, and risk-to-reward ratios.
- **Preset Audit Prompts**:
  - 📈 *Breakout Check*: Validates volume confirmation and invalidation levels.
  - 🛡️ *Risk Sizing*: Computes strict dollar-risk limits based on your current account balance.
- **Resilient Hybrid Engine**: Connects to the Gemini API (`gemini-3-flash`) with an automatic offline heuristic fallback for uninterrupted learning.

---

## 🛠️ Technology Stack

| Layer | Technology | Role |
| :--- | :--- | :--- |
| **Markup & Structure** | HTML5 Semantic Elements | Terminal workspace layout |
| **Styling & Theme** | Tailwind CSS CDN (Obsidian Palette) | Dark institutional aesthetic (`#07090e`) |
| **Typography & Icons** | JetBrains Mono, Inter, FontAwesome 6.5 | Terminal-grade data clarity and symbols |
| **Charting Engine** | Native HTML5 Canvas 2D API | Zero-dependency candlestick & volume rendering |
| **Simulation Runtime** | Vanilla ES6+ Event Loop | Asset drift models, tick updates, order bracket checking |
| **Artificial Intelligence**| Google Gemini API (`gemini-3-flash`) | Contextual technical analysis and trading mentorship |
| **Architecture** | Single-File Standalone Architecture | Entire platform packaged in one self-contained `.html` file |

---

## 📦 Quick Start & Installation

Because Trading Gym is completely self-contained within a single file, no package manager, compiler, or build step is needed.

### Method 1: Direct File Launch
1. Download or clone this repository:
   ```bash
   git clone https://github.com/your-username/trading-gym.git
   cd trading-gym
   ```
2. Double-click `trading_gym_platform.html` (or open it with any modern web browser like Chrome, Edge, Brave, or Safari).

### Method 2: Local HTTP Server (Recommended)
Running through a local web server provides the smoothest rendering performance:

```bash
# Python 3
python -m http.server 8000

# Node.js npx
npx serve .
```
Navigate to `http://localhost:8000/trading_gym_platform.html` in your browser.

---

## 🔑 Configuring the AI Mentor (Gemini API)

The simulator includes built-in heuristic responses out of the box. To activate live, deep-reasoning insights from Athena:

1. Open `trading_gym_platform.html` in your text editor.
2. Locate the `apiKey` variable in the `submitAiQuery()` function:
   ```javascript
   const apiKey = "YOUR_GEMINI_API_KEY_HERE";
   ```
3. Get a free API key from [Google AI Studio](https://aistudio.google.com/) and paste it between the quotes.
4. Save the file and reload your browser.

> **Note:** If no API key is supplied, Athena seamlessly activates her offline institutional guidance rulebook.

---

## 📋 Recommended Educational Drill: The 2:1 R:R Rule

To get the most out of Trading Gym:
1. Select **NVDA** or **BTC/USD**.
2. Identify a support level on the chart.
3. Place a **BUY** order with:
   - **Stop-Loss** set $\$1.50$ below your entry price.
   - **Take-Profit** set $\$3.00$ above your entry price (a $2:1$ reward-to-risk ratio).
4. Increase simulation speed to **3x** and observe how the market plays out without intervening emotionally.
5. Review your outcome in the **Trade Log** tab.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE). Feel free to modify, expand, or incorporate it into financial literacy workshops, university trading clubs, or algorithmic research sandboxes.
