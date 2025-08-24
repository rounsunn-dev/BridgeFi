
# 🌉 BridgeFi

**BridgeFi** is a **cross-chain bridge** connecting **Ethereum ↔ Solana** with built-in **DeFi primitives** such as **liquid staking** and **yield farming**.  

The goal is to create a **trust-minimized, scalable, and developer-friendly protocol** that enables seamless asset transfers and value accrual across heterogeneous blockchains.  

---

## ✨ Features (Planned)

- **Cross-Chain Transfers**  
  Secure ERC-20 ↔ SPL token transfers between Ethereum and Solana.  

- **Liquid Staking Integration**  
  Deposit tokens into liquid staking protocols (e.g., stETH, mSOL) and bridge them.  

- **Yield Farming Opportunities**  
  Route liquidity into yield strategies while assets are bridged.  

- **Unified API Layer**  
  FastAPI backend to abstract chain complexity for frontends and integrators.  

- **Relayer/Orchestrator**  
  Event listener + proof submitter to handle cross-chain message flow.  

- **Minimal Frontend (MVP)**  
  Vite + React dashboard for bridge status and transactions.  

---

## 🏗️ System Architecture (High-Level)

```

\[ User ]
↓
Frontend (Vite React) ──► FastAPI Backend ──► Relayer Service
│                                          │
└───────────────► Ethereum Contracts ◄─────┘
(Solidity Vaults, LSTs)

└───────────────► Solana Program ◄─────────┘
(Anchor PDA, Mint/Burn)

```

- **Ethereum Contracts (Solidity):** Bridge vaults, staking integration.  
- **Solana Program (Anchor):** Mint/Burn counterpart, PDA authority.  
- **Relayer/Orchestrator (Node/TypeScript):** Submits proofs across chains.  
- **Backend API (FastAPI):** Quotes, status checks, tx submission.  
- **Frontend (React + Vite):** Minimal dashboard (expanded later).  

---

## 🚀 Development Roadmap

### ✅ Phase 0 — Environment & Repo Setup
- [x] GitHub repo initialization with docs and structure  
- [x] Project skeleton: contracts, relayer, API, frontend  
- [x] CI/CD placeholder  

### 🧩 Phase 1 — Core Bridge Contracts
- [ ] **Ethereum (Solidity):** Lock/Mint bridge vault contracts  
- [ ] **Solana (Anchor):** Mint/Burn bridge program with PDA authority  
- [ ] Define cross-chain message format (nonce, src/dest, payload, replay protection)  

### 🔄 Phase 2 — Relayer + API MVP
- [ ] Relayer service (listen → proof → submit)  
- [ ] FastAPI endpoints: `/health`, `/quote`, `/status/{tx}`, `/submit`  
- [ ] Local E2E test flow (ETH Sepolia ↔ Solana Devnet)  

### 🌐 Phase 3 — Testnet Demo
- [ ] Deploy contracts to **Sepolia (ETH testnet)** and **Solana Devnet**  
- [ ] Run relayer with monitoring/logging  
- [ ] Minimal frontend for transaction tracking  

### 💧 Phase 4 — Liquid Staking Integration
- [ ] Integrate **stETH** (Ethereum) + **mSOL** (Solana)  
- [ ] Enable bridging of LSTs  
- [ ] Add yield routing strategies  

### 🔐 Phase 5 — Security & Scaling
- [ ] Reorg handling, rate limiting, circuit breakers  
- [ ] Metrics, logging, alerting system  
- [ ] Cost analysis of infra + on-chain operations  

---

## 📂 Repository Structure

```

BridgeFi/
│── contracts/
│   ├── ethereum/      # Solidity vaults + verifiers
│   └── solana/        # Anchor programs
│
│── services/
│   └── relayer/       # Relayer/orchestrator (Node/TS)
│
│── backend/
│   └── api/           # FastAPI service
│
│── frontend/
│   └── app/           # React (Vite) frontend (MVP paused)
│
│── docs/              # Architecture, costs, roadmap
│── .github/workflows/ # CI/CD pipelines
│── README.md
│── LICENSE

```

---

## 💰 Cost Model (Draft)

| Component        | Dev/Testnet Cost | Mainnet Est. |
|------------------|-----------------|--------------|
| **Ethereum Gas** | ~0.1–0.3 gwei   | $ per tx (varies) |
| **Solana Fees**  | negligible      | negligible |
| **RPC Providers**| Free/Low Tier   | $49–$299/mo |
| **Relayer Infra**| Local Docker    | ~$50–200/mo |
| **Monitoring**   | Basic logs      | $30–100/mo |

---

## 🛠️ Tech Stack

- **Smart Contracts:** Solidity (Ethereum), Rust/Anchor (Solana)  
- **Backend API:** FastAPI (Python)  
- **Relayer:** Node.js + TypeScript  
- **Frontend:** React + Vite  
- **Testing:** Hardhat/Foundry + Anchor test suite  
- **Infra:** Docker, GitHub Actions, RPC providers (Alchemy, QuickNode, Helius)  

---

## 📅 Status

Currently in **Phase 0–1**:  
- Repo skeleton ✅  
- Writing **bridge contracts** and defining **message format** 🧩  

---

## 📜 License

MIT License © 2025 BridgeFi
