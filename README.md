# nft-mining-arbitrum

Foundry project for minting Blockchain Accelerator Certificate (BAC) NFTs on Arbitrum One. Includes the certificate contract interface and a script to mint BAC certificates.

## Contracts

### IBlockchainAcceleratorCertificate

Interface for the Blockchain Accelerator certificate contract:

- **`mintBAC()`** — Mints a BAC (Blockchain Accelerator Certificate) for the caller.

Location: `src/IBlockchainAcceleratorCertificate.sol`

## Requirements

- [Foundry](https://book.getfoundry.sh/getting-started/installation)
- `PRIVATE_KEY` environment variable with the private key of the account that will run the script

## Usage

### Build

```bash
forge build
```

### Mint certificate (mint BAC)

The `MintCertificate` script calls `mintBAC()` on the deployed contract. It is configured by default for the contract on Arbitrum One (chain id 42161).

```bash
forge script script/MintCertificate.s.sol:MintCertificate \
  --rpc-url <RPC_URL> \
  --private-key $PRIVATE_KEY \
  --broadcast
```

Example with environment variables:

```bash
forge script script/MintCertificate.s.sol:MintCertificate \
  --rpc-url $RPC_URL \
  --private-key $PRIVATE_KEY \
  --broadcast
```

> **Note:** The contract address is defined in `script/MintCertificate.s.sol`. If the contract is deployed on a different network or address, update the `contractaddress` variable in the script.

### Test

```bash
forge test
```

### Format

```bash
forge fmt
```

### Gas snapshots

```bash
forge snapshot
```

## Project structure

```
src/
  IBlockchainAcceleratorCertificate.sol   # Certificate contract interface
script/
  MintCertificate.s.sol                   # Script to mint BAC certificates
broadcast/                                # Execution history (e.g. Arbitrum 42161)
```

## Foundry documentation

https://book.getfoundry.sh/
