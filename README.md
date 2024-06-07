# AI_NFT_Minting

This repository provides a smart contract and scripts for minting and managing Non-Fungible Tokens (NFTs) on the Ethereum blockchain, specifically representing "GIGANTIC BLACK HOLE" NFTs.

## Contract Information

- **Contract Name:** BLACKHOLE
- **Contract Type:** ERC721A (Extends ERC721 standard)
- **Solidity Version:** 0.8.9
- **License:** MIT

## Overview

The `BLACKHOLE.sol` contract allows the owner to mint a limited number (5) of unique GIGANTIC BLACK HOLE NFTs. These tokens are based on the ERC721A standard, offering additional functionalities over the standard ERC721.

## Features

1. **Minting:** The owner can mint up to 5 GIGANTIC BLACK HOLE NFTs.
2. **Base URL:** The contract includes a base URL for the NFT metadata.
3. **Prompt Description:** Provides a description for the NFTs, specifically "GIGANTIC BLACK HOLE."

## Contract Functions

### mint(uint256 quantity)

- **Description:** Mints the specified number of NFTs.
- **Modifier:** onlyOwner
- **Parameters:** `quantity` - The number of NFTs to mint.
- **Requirements:** Total supply must not exceed 5.

### _baseURI() internal view override returns (string memory)

- **Description:** Returns the base URL for the NFTs.

### promptDescription() external view returns (string memory)

- **Description:** Returns the prompt description "GIGANTIC BLACK HOLE."

## Deployment

Ensure dependencies such as `erc721a/contracts/ERC721A.sol` are in place and deploy the contract using Solidity 0.8.9.

### Deploy to Goerli Testnet

```bash
npx hardhat run scripts/deploy.js --network goerli
```

- Update `contractAddress.js` and `batchMint.js` with the generated contract address.

### Batch Mint NFTs

```bash
npx hardhat run scripts/batchMint.js --network goerli
```

### Approve and Deposit NFTs to Polygon Mumbai

Use the FxPortal Bridge:

```bash
npx hardhat run scripts/approveDeposit.js --network goerli
```

## Repository Structure

- **artifacts/**: Compiled contract artifacts.
- **cache/**: Cached data.
- **contracts/**: Solidity contract files.
- **images/**: NFT images.
- **metadata/**: Metadata for NFTs.
- **scripts/**: Deployment and minting scripts.
- **.env**: Environment variables.
- **hardhat.config.js**: Hardhat configuration.
- **package.json**: Project dependencies.

## License

This project is licensed under the MIT License.
