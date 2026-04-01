# 🐋 Whale Alert Oracle

**Decentralized Whale Movement Tracker — Built on GenLayer**

[![GenLayer](https://img.shields.io/badge/Built%20on-GenLayer-orange)](https://www.genlayer.com/)
[![Python](https://img.shields.io/badge/Language-Python-blue)](https://docs.genlayer.com/)
[![Testnet](https://img.shields.io/badge/Network-Testnet%20Bradbury-green)](https://studio.genlayer.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## Overview

Whale Alert Oracle is an **Intelligent Contract** that monitors large crypto whale transactions and analyzes their market impact using AI-powered consensus — fully on-chain and trustless.

Whale movements are among the strongest leading indicators in crypto markets. When whales accumulate, price tends to follow. When they distribute, corrections often follow. This contract brings whale intelligence **on-chain** with decentralized AI verification.

### Why GenLayer?

This project is **impossible on any other blockchain**:

- 🌐 **Native web access** — scraping whale transaction data without centralized APIs
- 🧠 **Natural language processing** — interpreting complex whale behavior patterns
- 🤝 **Non-deterministic consensus** — multiple AI models agreeing on whale intent classification

---

## How It Works

```
┌─────────────────────────────────────────────────────────┐
│                    Whale Alert Oracle                      │
├─────────────────────────────────────────────────────────┤
│                                                           │
│  📡 DATA LAYER (gl.nondet.web.render)                     │
│  └── Blockchain explorer / whale tracking sites           │
│                                                           │
│  🧠 AI ANALYSIS LAYER (gl.nondet.exec_prompt)             │
│  ├── Whale activity classification                        │
│  ├── Accumulation vs distribution detection               │
│  └── Market impact assessment                             │
│                                                           │
│  ⚖️ CONSENSUS LAYER → Optimistic Democracy                │
│  💾 STATE LAYER → On-chain whale intelligence              │
│                                                           │
└─────────────────────────────────────────────────────────┘
```

---

## Contract Interface

### Write Functions

| Function | Description |
|----------|-------------|
| `scan_whales()` | Scans for large whale transactions, classifies activity level and direction |

### State Variables

| Variable | Type | Description |
|----------|------|-------------|
| `whale_activity` | str | DORMANT / NORMAL / ELEVATED / EXTREME |
| `largest_tx` | str | Description of biggest whale transaction |
| `market_impact` | str | AI analysis of whale implications |
| `has_scanned` | bool | Whether scan has completed |

### Output Format

```json
{
  "whale_activity": "ELEVATED",
  "largest_tx": "10,000 BTC moved from Binance to cold storage",
  "direction": "ACCUMULATING",
  "summary": "Large exchange outflows suggest institutional accumulation phase."
}
```

---

## Quick Start

1. Open [GenLayer Studio](https://studio.genlayer.com/contracts)
2. Paste `03_whale_alert_oracle.py`
3. Constructor: `scan_url` = `https://www.coingecko.com/en/coins/bitcoin`
4. Deploy → Execute `scan_whales`

---

## Use Cases

### 📊 Smart Money Following
Track what whales are doing and align positions with institutional flow.

### 🚨 Early Warning System
Detect large exchange inflows (potential sell pressure) before price reacts.

### 🤖 Trading Agent Input
Autonomous trading agents use whale data as a signal input for position management.

---

## Roadmap

| Phase | Status | Description |
|-------|--------|-------------|
| **MVP Contract** | ✅ Complete | Whale scanning with activity classification |
| **Multi-Chain Tracking** | 📋 Planned | Track whales across BTC, ETH, SOL |
| **Real-Time Alerts** | 📋 Planned | Push alerts for extreme whale activity |
| **Historical Patterns** | 📋 Planned | Track whale behavior over time |

---

## Built With

- **[GenLayer](https://www.genlayer.com/)** — AI-native blockchain with Intelligent Contracts
- **[GenVM SDK](https://docs.genlayer.com/)** — Python SDK for Intelligent Contract development
- **[Optimistic Democracy](https://docs.genlayer.com/)** — Multi-validator AI consensus

---

## License

MIT License

---

<p align="center">
  <b>Built with 🧠 on GenLayer — The Intelligence Layer of the Internet</b>
</p>
