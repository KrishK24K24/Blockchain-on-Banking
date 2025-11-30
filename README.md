# Blockchain on Banking — demo

A small end-to-end demo that shows a simple Solidity smart contract for recording transactions, a minimal Node.js server, and a frontend to interact with the contract.

What’s in this repo
- `Transactions.sol` — Solidity contract that records simple transactions (sender, receiver, amount, timestamp). It is intended for learning purposes (not production-ready).
- `index.html`, `style.css`, images — Frontend UI that demonstrates contract interaction (viewing/creating transactions).
- `server.js` — Small server used to serve the frontend and (optionally) provide an API endpoint for demo data.
- `package-lock.json` and static assets.

What the code does — high-level summary
1. Smart contract (Transactions.sol)
   - Defines a transaction record structure and stores an array (or mapping) of transactions.
   - Exposes functions to add a transaction and to fetch stored transactions.
   - Designed to demonstrate basic concepts: state variables, events, and public view/getter functions.

2. Frontend (index.html + style.css)
   - Simple UI to show existing transactions and to submit a new one.
   - Connects to an Ethereum provider (e.g., MetaMask) or to a local test node via web3/ethers if you wire it up in the page.
   - Renders returned transaction data in a table.

3. Server (server.js)
   - Minimal static server to serve the web files.
   - Can be extended to act as a bridge/API between the frontend and an off-chain service.

Steps performed in the code / how to use
- Deploy the contract:
  - Quick option: Use Remix (remix.ethereum.org). Paste `Transactions.sol`, compile, and deploy on a local Ganache instance or a testnet.
  - Alternatively, use Hardhat/Truffle for deployment if you prefer a scriptable workflow.

- Connect the frontend:
  - Update the contract address and ABI in the frontend (index.html or a separate JS file) after deployment.
  - Serve the frontend via the provided server or open `index.html` in a browser that supports your chosen provider.

- Run the demo locally:
  1. (Optional) Start a local Ethereum node: Ganache or Hardhat node.
  2. Deploy `Transactions.sol` (Remix or Hardhat/Truffle).
  3. Install Node dependencies (if you plan to use the server):
     npm install
  4. Start the server:
     node server.js
  5. Open the app in the browser (http://localhost:3000 by default if server.js uses that port) and connect MetaMask to your local node/testnet network.

Dependencies
- Node.js (for server)
- An Ethereum provider: MetaMask, Ganache, or Hardhat node
- Remix, Hardhat, or Truffle to compile/deploy the Solidity contract

Notes & security
- This repo is an educational demo. The Solidity code is simplistic and not audited. Do not use this as-is for production or real funds.
- If you want, I can add a small Hardhat configuration and deployment script to automate building and deploying locally.
