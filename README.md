# TrustChain Track 🔗

A multi-wallet Stellar dApp with smart contract integration built for Level 2.

## 🌐 Live Demo
👉 https://trustchain-track.vercel.app

## 📌 Project Description
TrustChain Track is an upgraded Stellar blockchain dApp that supports multiple wallets, handles 3 error types, integrates a smart contract, and provides real-time transaction tracking with a live activity feed.

## 🛠️ Tech Stack
- React + Vite
- Stellar SDK
- Freighter Wallet API
- Stellar Testnet (Horizon)
- Soroban RPC (Smart Contract)
- Rust + Soroban SDK (Smart Contract)

## ✨ Features
- Multi-wallet support (Freighter, xBull, Albedo)
- 3 error types handled
- Custom smart contract deployed and called from frontend
- Real-time XLM balance
- Send XLM transactions
- Transaction status (⏳ Pending → ✅ Success → ❌ Failed)
- Transaction hash + Stellar Explorer link
- Live Activity Feed
- Disconnect wallet

## ⚠️ Error Handling

### Error Type 1: Account not found on testnet
When wallet address doesn't exist on Stellar testnet.
![Error Type 1](level-2-screenshots/error-handling.jpg.jpg)

### Error Type 2: Wallet extension not installed
When user clicks xBull or Albedo which are not installed.
![Error Type 2](level-2-screenshots/error-rejected.jpg.jpg)

### Error Type 3: User rejected wallet connection
When user cancels the wallet connection request.
![Error Type 3](level-2-screenshots/wallet-options.jpg.jpg)

## 📜 Smart Contract

### About the Contract
This is a **custom, self-made Soroban smart contract** written from scratch in **Rust**. It was built specifically for TrustChain Track and deployed directly to Stellar Testnet using the Stellar CLI.

The contract has 3 functions:
- `send_payment` — records and validates XLM payment amount
- `validate` — validates payment amount is positive and within limits
- `version` — returns the contract version

### Contract Details
- **Contract ID:** CA7S27CDLIGZMZT3FMBROSGCJRP4BNPWDXUN5MKTKOVX3RGAGLSVT4EA
- **Network:** Stellar Testnet
- **Type:** WASM Contract (Soroban)
- **Language:** Rust
- **Contract Folder:** `contract/src/lib.rs`

### Contract Links
- 🔗 Direct URL: https://stellar.expert/explorer/testnet/contract/CA7S27CDLIGZMZT3FMBROSGCJRP4BNPWDXUN5MKTKOVX3RGAGLSVT4EA
- 🔗 [View Deployed Contract on Stellar Expert](https://stellar.expert/explorer/testnet/contract/CA7S27CDLIGZMZT3FMBROSGCJRP4BNPWDXUN5MKTKOVX3RGAGLSVT4EA)

### How the Contract Was Written
The contract is located in `contract/src/lib.rs`. It was written using the Soroban SDK:

```rust
#![no_std]
use soroban_sdk::{contract, contractimpl, Env, Symbol, symbol_short, Address, log};

#[contract]
pub struct TrustChainContract;

#[contractimpl]
impl TrustChainContract {
    pub fn send_payment(env: Env, from: Address, amount: u64) -> u64 {
        from.require_auth();
        log!(&env, "Payment sent: {}", amount);
        amount
    }
    pub fn version(_env: Env) -> Symbol {
        symbol_short!("TC_v1")
    }
    pub fn validate(_env: Env, amount: u64) -> bool {
        amount > 0 && amount <= 1_000_000
    }
}
```

### How the Contract Was Built
```bash
# Step 1: Install Rust and Stellar CLI
cargo install --locked stellar-cli

# Step 2: Add WASM target
rustup target add wasm32v1-none

# Step 3: Initialize contract project
stellar contract init trustchain-contract

# Step 4: Build the contract
stellar contract build
```

### How the Contract Was Deployed
```bash
# Step 1: Generate deployer key
stellar keys generate pritty --network testnet

# Step 2: Fund the account on testnet
stellar keys fund pritty --network testnet

# Step 3: Deploy the contract
stellar contract deploy \
  --wasm target/wasm32v1-none/release/hello_world.wasm \
  --source pritty \
  --network testnet
```

## 🚀 Setup Instructions

1. Clone the repository:
```bash
git clone https://github.com/Pritty05/trustchain-track.git
```

2. Install dependencies:
```bash
cd trustchain-track
npm install
```

3. Run the app:
```bash
npm run dev
```

4. Open browser at http://localhost:5173

## 📋 Requirements
- Freighter Wallet browser extension installed
- Freighter set to Testnet network

## 📸 Screenshots

### 1. Wallet Options
![Wallet Options](level-2-screenshots/wallet-options.jpg.jpg)

### 2. Wallet Connected
![Wallet Connected](level-2-screenshots/wallet-connected.jpg.jpg)

### 3. Smart Contract Called
![Smart Contract Called](level-2-screenshots/contract-called.jpg.jpg)

### 4. Transaction Success
![Transaction Success](level-2-screenshots/transaction-success.jpg.jpg)

## 🔗 Testnet Transaction Proof
- **Transaction Hash:** `3313802f198a4351e6060ee8c4b460d1fab18a87022833768f08d41e9a265f51`
- 🔗 Direct URL: https://stellar.expert/explorer/testnet/tx/3313802f198a4351e6060ee8c4b460d1fab18a87022833768f08d41e9a265f51
- 🔗 [View Transaction on Stellar Explorer](https://stellar.expert/explorer/testnet/tx/3313802f198a4351e6060ee8c4b460d1fab18a87022833768f08d41e9a265f51)

---
Made with ❤️ for the Stellar Community 🚀