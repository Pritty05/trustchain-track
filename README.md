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

## ✨ Features
- Multi-wallet support (Freighter, xBull, Albedo)
- 3 error types handled
- Smart contract integration
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
- Contract ID: CDZZQYUKOSTHDOUCU273NHRVYJ67A37JC5SL3JAOJ77FUT4KGQXSJBUI
- Network: Stellar Testnet
- Type: WASM Contract
- Called from frontend via Soroban RPC
- Contract Link: https://stellar.expert/explorer/testnet/contract/CDZZQYUKOSTHDOUCU273NHRVYJ67A37JC5SL3JAOJ77FUT4KGQXSJBUI
- 🔗 [View Deployed Contract on Stellar Expert](https://stellar.expert/explorer/testnet/contract/CDZZQYUKOSTHDOUCU273NHRVYJ67A37JC5SL3JAOJ77FUT4KGQXSJBUI)

## 🚀 Setup Instructions

1. Clone the repository:
   git clone https://github.com/Pritty05/trustchain-track.git

2. Install dependencies:
   cd trustchain-track
   npm install

3. Run the app:
   npm run dev

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
- Transaction Hash: `55da28143fc47e09bc1709a2130c449d61e58ba25256a9c5440bd198779163d8`
- Transaction Link: https://stellar.expert/explorer/testnet/tx/55da28143fc47e09bc1709a2130c449d61e58ba25256a9c5440bd198779163d8
- [View on Stellar Explorer](https://stellar.expert/explorer/testnet/tx/55da28143fc47e09bc1709a2130c449d61e58ba25256a9c5440bd198779163d8)

---
Made with ❤️ for the Stellar Community 🚀