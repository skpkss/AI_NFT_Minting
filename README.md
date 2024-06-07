# AI_NFT_Minting

This repository contains a smart contract and associated scripts for minting and managing NFTs on the Ethereum blockchain. The contract mints a limited series of "GIGANTIC BLACK HOLE" NFTs using the ERC721A standard.

## Overview

AI_NFT_Minting is a project designed to create and manage Non-Fungible Tokens (NFTs) on the Ethereum blockchain. This particular project focuses on minting a limited series of "GIGANTIC BLACK HOLE" NFTs. The images for these NFTs were generated using OpenAI's DALL-E 2.

## Features

- **Minting:** Limited to 5 NFTs
- **Base URI:** URL for metadata
- **Prompt Description:** "GIGANTIC BLACK HOLE"

## Prerequisites

- **Node.js**
- **Hardhat**
- **Goerli Testnet** for deployment
- **Polygon Mumbai** for bridging
- **MetaMask** for wallet integration

## Setup

1. **Clone the repository:**
    ```bash
    git clone https://github.com/skpkss/AI_NFT_Minting.git
    cd AI_NFT_Minting
    ```

2. **Install dependencies:**
    ```bash
    npm install
    ```

3. **Set up environment variables:**
    - Create a `.env` file in the root directory.
    - Add the following variables:
      ```plaintext
      ALCHEMY_API_KEY = "your-alchemy-api-key"
      PRIVATE_KEY = "your-private-key"
      ```

## Contract Deployment

### Compile Contracts

```bash
npx hardhat compile
```

### Deploy to Goerli Testnet

```bash
npx hardhat run scripts/deploy.js --network goerli
```

### Update Configurations

- **Update `contractAddress.js` and `batchMint.js` with the deployed contract address.**

## Minting NFTs

### Batch Mint

```bash
npx hardhat run scripts/batchMint.js --network goerli
```

### Approve and Deposit NFTs

Use the FxPortal bridge for depositing NFTs to Polygon Mumbai:

```bash
npx hardhat run scripts/approveDeposit.js --network goerli
```

## Directory Structure

- **artifacts/**: Compiled contracts
- **cache/**: Cache data
- **contracts/**: Solidity contracts
- **images/**: NFT images
- **metadata/**: NFT metadata
- **scripts/**: Deployment and minting scripts
- **.env**: Environment variables
- **hardhat.config.js**: Hardhat configuration
- **package.json**: Project dependencies

## Contract Information

- **Contract Name:** BLACKHOLE
- **Contract Type:** ERC721A (Extends ERC721 standard)
- **Solidity Version:** 0.8.9
- **License:** MIT

### Contract Functions

#### mint(uint256 quantity)

- **Description:** Mints the specified number of NFTs.
- **Modifier:** onlyOwner
- **Parameters:** `quantity` - The number of NFTs to mint.
- **Requirements:** Total supply must not exceed 5.

#### _baseURI() internal view override returns (string memory)

- **Description:** Returns the base URL for the NFTs.

#### promptDescription() external view returns (string memory)

- **Description:** Returns the prompt description "GIGANTIC BLACK HOLE."

## Note on Images

The images used for the "GIGANTIC BLACK HOLE" NFTs were generated using OpenAI's DALL-E 2, an advanced AI model for generating images from text prompts.

## License

This project is licensed under the MIT License.
