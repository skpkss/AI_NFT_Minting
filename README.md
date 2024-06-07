# AI_NFT_Minting

This repository contains a smart contract and associated scripts for minting and managing NFTs on the Ethereum blockchain. The contract mints a limited series of "GIGANTIC BLACK HOLE" NFTs using the ERC721A standard. The images for these NFTs were generated using OpenAI's DALL-E 2.

## Project Overview

AI_NFT_Minting is designed to deploy an NFT collection on the Ethereum blockchain, map the collection to Polygon, and transfer assets via the Polygon Bridge. This project includes the generation of NFT images using DALL-E 2 and follows a comprehensive workflow to ensure efficient deployment and transfer.

## Project Walkthrough

https://www.loom.com/share/a9532e3f9c384200885302df2aa58d6d?sid=8c5324f1-4709-4508-bd31-2ba173cee428

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
- **Pinata.cloud** for storing items on IPFS

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

## Full Project Workflow

1. **Generate a 5-item collection using DALL-E 2**:
    - Use DALL-E 2 to generate unique images for the NFTs.
2. **Store items on IPFS using Pinata.cloud**:
    - Upload the generated images to IPFS using Pinata.cloud for decentralized storage.
3. **Deploy an ERC721A contract to the Goerli Ethereum Testnet**:
    - Deploy the smart contract using Hardhat and verify the deployment on Goerli.
4. **Map your NFT collection using the Polygon network token mapper** (optional):
    - Use the token mapper to map the NFT collection to the Polygon network for better visualization.
5. **Write a Hardhat script to batch mint all NFTs**:
    - Use the ERC721A standard to efficiently batch mint all 5 NFTs.
6. **Write a Hardhat script to batch transfer all NFTs from Ethereum to Polygon Mumbai using the FxPortal Bridge**:
    - Approve the NFTs for transfer.
    - Deposit the NFTs to the Polygon Bridge.
    - Test the balance of the NFTs on the Mumbai network to ensure successful transfer.

## License

This project is licensed under the MIT License.
