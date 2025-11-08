# HyperEVM NFT Minting dApp

## Overview
A decentralized application for minting NFTs on the HyperEVM blockchain using Privy for wallet authentication.

## Project Structure
- `index.html` - Main application with embedded Privy authentication
- `server.py` - Simple Python HTTP server for serving the application

## Configuration
- **Contract Address**: `0x7d5C48A82E13168d84498548fe0a2282b9C1F16B`
- **Chain ID**: 998 (HyperEVM)
- **RPC**: `https://api.hyperliquid.xyz/evm`
- **Explorer**: `https://explorer.hyperliquid.xyz`
- **Privy App ID**: `cmhk5aqsf00r2k10d4m81x9ax`

## Features
- ✅ Privy authentication with email OTP
- ✅ Embedded wallet creation
- ✅ Supply tracking from contract
- ✅ Max mint per wallet detection from contract
- ✅ Price detection from contract
- ✅ Dynamic price display based on quantity
- ✅ Per-user mint limit enforcement
- ✅ Transaction tracking with explorer links

## Recent Changes (Nov 8, 2025)
- Implemented Privy JS SDK Core via ES modules
- Added contract-based price detection (`getPublicMintPrice`)
- Added max mint per wallet detection (`maxMintPerWallet`)
- Updated UI to show total cost and remaining mint allowance
- Added proper error handling for contract calls
- Implemented transaction value payment based on detected price

## User Flow
1. User clicks "Connect with Privy"
2. Enters email address
3. Receives OTP code via email
4. Enters OTP to authenticate
5. Privy creates embedded wallet on HyperEVM
6. User can mint NFTs with quantity selection
7. App shows price, remaining mint allowance, and total cost
8. Transaction is submitted with correct payment value
9. Success confirmation with explorer link

## Technical Notes
- Using `@privy-io/js-sdk-core` via `esm.sh` CDN
- Ethers.js v5.7.2 for blockchain interactions
- Quantity controls respect both global supply and per-user limits
- Free mints display "FREE" instead of "0 ETH"
- Price and max mint are fetched from contract on wallet connection

## Known Issues
- ES module loading may cause issues in some browsers
- Privy iframe requires proper CORS configuration
- Workflow restart issues due to port binding conflicts
