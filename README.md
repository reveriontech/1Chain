<p align="center">
  <img src="https://raw.githubusercontent.com/MystenLabs/sui/refs/heads/main/docs/site/static/img/logo.svg" alt="1Chain Logo" width="100" height="100">
</p>

# 🧬 1Chain — Internet-Scale Layer 1 Blockchain

[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](LICENSE)
[![Build Status](https://img.shields.io/github/actions/workflow/status/1chain-network/1chain/ci.yml)](https://github.com/1chain-network/1chain/actions)
[![Rust](https://img.shields.io/badge/language-Rust-orange.svg)](https://www.rust-lang.org/)
[![Move](https://img.shields.io/badge/Smart%20Contracts-Move-ff69b4.svg)](https://github.com/move-language/move)

---

## 🌍 Overview

**1Chain** is a **next-generation Layer 1 blockchain** forked from [Sui](https://sui.io), designed for **real-world scalability**, **low-latency finality**, and **programmable digital assets** through the [Move language](https://github.com/move-language/move).

Built with **Rust** and optimized for **parallel execution**, 1Chain enables developers to create composable on-chain assets, scalable dApps, and Layer-2 integrations with instant settlement.

> 1Chain = Sui performance + Custom parameters + On-chain governance + L2-ready RPC

---

## 🚀 Key Features

- **Customizable Chain Parameters**
  - Adjustable Chain ID, Epoch Duration, Gas Limits, and Genesis Allocations  
  - Fine-grained control over block time and validator economics
- **Parallel Execution Engine**
  - Narwhal + Bullshark-based DAG consensus (tuned for 1Chain)
- **Asset-Oriented Smart Contracts**
  - Built with Move, enabling ownership-based logic and composable resources
- **Governance-Driven Evolution**
  - Native DAO governance via on-chain staking, proposals, and upgrades
- **L2-Ready RPC Architecture**
  - Wallet adapter and REST endpoints for custom dApps, explorers, and SDKs

---

## ⚙️ Architecture Overview

```mermaid
flowchart LR
    U[User / Wallet] --> RPC
    RPC --> ValidatorAggregator
    ValidatorAggregator --> V1[Validator 1]
    ValidatorAggregator --> V2[Validator 2]
    V1 <--> Storage1[(Storage Node)]
    V2 <--> Storage2[(Storage Node)]
    V1 & V2 --> Consensus[Narwhal + Bullshark]
    Consensus --> Finality
    Finality --> Ledger[(1Chain Ledger)]
