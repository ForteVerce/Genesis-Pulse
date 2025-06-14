<p align="center">
  <img src="docs/images/Genesis Pulse (GEN).png" alt="Genesis Pulse Logo" width="120" />
  <h1 align="center">Genesis Pulse <sup>($GEN)</sup></h1>
  <p align="center"><em>Passive Solana arbitrage opportunity scanner</em></p>
  <p align="center">
    <a href="https://github.com/ForteVerce/Genesis-Pulse/actions">
      <img src="https://img.shields.io/github/actions/workflow/status/ForteVerce/Genesis-Pulse/ci.yml?branch=main" alt="CI Status"/>
    </a>
    <a href="https://github.com/ForteVerce/Genesis-Pulse/releases">
      <img src="https://img.shields.io/github/v/release/ForteVerce/Genesis-Pulse" alt="Latest Release"/>
    </a>
    <a href="https://github.com/ForteVerce/Genesis-Pulse/blob/main/LICENSE">
      <img src="https://img.shields.io/github/license/ForteVerce/Genesis-Pulse" alt="License"/>
    </a>
  </p>
</p>

---

## 🔎 Table of Contents
1. [Overview](#-overview)  
2. [Features](#-features)  
3. [How It Works](#-how-it-works)  
4. [Roadmap](#-roadmap)  
5. [Getting Started](#-getting-started)  
6. [Configuration](#-configuration)  
7. [Usage](#-usage)  
8. [Contributing](#-contributing)  
9. [License](#-license)  

---

## 🛰️ Overview
**Genesis Pulse** is a **passive** Solana arbitrage scanner that continuously monitors on-chain prices across top DEXes (Orca, Raydium, Jupiter, etc.) and raises real-time alerts when cross-market spreads exceed your configured threshold.  
_No automated trading—scan only, alert only._

---

## ✨ Features
- **Multi-DEX Coverage**: Orca, Raydium, Jupiter, Saber, Serum, and more.  
- **Configurable Thresholds**: Set profit, slippage & fee margins.  
- **Real-Time Alerts**: WebSocket, HTTP Webhook, Email, Slack, Discord.  
- **Lightweight Agent**: Docker & Helm ready, minimal CPU/RAM usage.  
- **Optional Dashboard**: React UI with live tables, heatmaps & charts.  
- **Data Logging**: CSV/JSON logs for backtesting & analytics.  
- **Plugin-Ready**: Easily add new DEX adapters or custom modules.

---

## 🚀 How It Works
1. **Initialization**  
   - Load DEX adapters & user config (pairs, thresholds, endpoints).  
2. **Polling Loop**  
   - High-frequency RPC/WebSocket calls fetch quotes & orderbooks.  
   - Normalize decimals & fee structures.  
3. **Spread Analysis**  
   - Compute bid-ask differences across DEXes.  
   - Filter by user thresholds & sanity checks.  
4. **Alert Dispatch**  
   - Bundle opportunities into payloads.  
   - Dispatch via configured channels with retries & rate limits.  
5. **UI & Logging**  
   - Stream to dashboard over WebSocket.  
   - Append to local or remote logs for history.

---

## 🗺️ Roadmap

| Version | Target Date | Highlights                                       |
| ------- | ----------- | ------------------------------------------------ |
| **v1.0**| Q3 2025     | Orca, Raydium, Jupiter support<br>Docker & Helm<br>Slack & Email alerts |
| **v1.1**| Q4 2025     | Saber & Serum adapters<br>REST Webhooks<br>Multi-user auth |
| **v2.0**| Q1 2026     | Backtest replay<br>PWA mobile dashboard<br>Plugin marketplace |
| **v2.1**| Q2 2026     | On-chain event listeners<br>Volume-weighted filters<br>ML anomaly detection |

---

## ⚙️ Getting Started

```bash
# Clone the repo
git clone https://github.com/ForteVerce/Genesis-Pulse.git
cd Genesis-Pulse

# Install dependencies
npm install   # or yarn

# Copy & edit config
cp config.sample.json config.json
# Set your RPC endpoints, DEX list, thresholds, alert channels

# Run the scanner
npm run start
