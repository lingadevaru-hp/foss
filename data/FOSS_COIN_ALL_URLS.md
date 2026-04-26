# FOSS Coin — All URLs & Evidence Links

## Token & Mint

**https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin**
Solana Explorer page for the FOSS token mint account.
Shows decimals (6), supply (1B raw), mint authority (null), freeze authority (null).

**https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin**
Solscan token page — same data in a different explorer format.
Shows holder count, transfer history, and top holders.

## Creation Transaction

**https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN**
The original token creation transaction (July 23, 2025).
Token was created, 1B minted, mint authority revoked, and initial buy executed — all in one tx.

**https://solscan.io/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN**
Same creation transaction on Solscan with parsed inner instructions.

## Creator Wallet

**https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b**
The creator's wallet that paid fees for all FOSS transactions.
Signed the creation tx, pool creation, liquidity provision, and all transfers.

**https://solscan.io/account/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b**
Same creator wallet on Solscan with full transaction history.

## Orca DEX Pool

**https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2**
The Orca Whirlpool page for the FOSS/SOL trading pair.
Concentrated liquidity AMM pool where anyone can swap FOSS ↔ SOL.

**https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2**
GeckoTerminal chart and analytics for the FOSS/SOL Orca pool.
Shows price history, liquidity depth, and volume data.

**https://explorer.solana.com/address/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2**
Solana Explorer view of the Orca Whirlpool program account.
Shows the pool's on-chain data including token vaults and tick arrays.

## Pool Creation Transaction

**https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB**
Transaction that created the Orca Whirlpool (Oct 21, 2025).
Initialized pool with adaptive fee, created SOL + FOSS vaults, and set up tick arrays.

## Liquidity Provision Transaction

**https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm**
Transaction that added initial liquidity to the Orca pool (19 seconds after pool creation).
Created a position NFT and deposited FOSS + SOL into the Whirlpool.

## GeckoTerminal APIs

**https://api.geckoterminal.com/api/v2/networks/solana/tokens/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin**
GeckoTerminal REST API endpoint for FOSS token price and market data.
Returns JSON with current price, market cap, and trading pairs.

**https://api.geckoterminal.com/api/v2/networks/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2**
GeckoTerminal REST API endpoint for the Orca pool data.
Returns JSON with reserves, volume, and pool statistics.

## Metadata (IPFS)

**https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n**
The Metaplex metadata JSON file stored on IPFS.
Contains token name ("Free Open Source Soft "), symbol (FOSS), description, and image link.

**https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf**
The FOSS token logo image (PNG, ~2.5 MB) stored on IPFS.
This is what wallets and explorers display as the token's icon.

## Orca Developer Docs

**https://docs.orca.so/developers/whirlpools/interacting-with-the-protocol**
Official Orca documentation for developers interacting with Whirlpools.
Explains how to create pools, add liquidity, swap, and manage positions programmatically.

## Launchpad Program

**https://explorer.solana.com/address/HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr**
The no-code launchpad BPF program that created the FOSS token.
Handles token creation, metadata, minting, authority revocation, and initial buy in one atomic tx.

## Recent Transfer Transactions

**https://explorer.solana.com/tx/3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g**
Token transfer on Aug 17, 2025 — moved 2 FOSS to an external wallet.

**https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T**
Token transfer on Jan 18, 2026 — airdropped 1 FOSS to a new wallet.

## Solana RPC (for programmatic verification)

**https://api.mainnet-beta.solana.com**
Solana's public JSON-RPC endpoint.
Use `getAccountInfo` with the mint address to verify token specs live from the chain.
