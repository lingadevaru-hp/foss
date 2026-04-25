# FOSS Coin — Evidence & Verification Links

> All links point to public, verifiable on-chain data sources. Anyone can independently verify every claim.

---

## 1. Token Mint Account

| Source | Link |
|---|---|
| **Solana Explorer (Token)** | https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin |
| **Solscan (Token)** | https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin |
| **Solana FM** | https://solana.fm/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin |

**What to verify:** Token name, symbol, decimals (6), total supply (1,000,000,000,000,000 raw), mint authority (`null`), freeze authority (`null`), owner program (`TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA`).

---

## 2. Creation Transaction

| Field | Value |
|---|---|
| **Signature** | `VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN` |
| **Slot** | 355,223,383 |
| **Timestamp** | July 23, 2025, 07:43:36 UTC |

| Source | Link |
|---|---|
| **Solana Explorer** | https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN |
| **Solscan** | https://solscan.io/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN |

**What to verify:** Fee payer (`HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b`), `InitializeMint2` (6 decimals), Metaplex `Create Metadata Accounts v3`, `MintTo` (1B tokens), `SetAuthority` (mint authority revoked), launchpad `Buy` instruction.

---

## 3. Mint Authority Revocation

Mint authority was revoked **in the creation transaction itself** (same tx as #2 above).

| Evidence | Link |
|---|---|
| **Creation TX → Inner Instruction: SetAuthority** | https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN |
| **Live Mint Account (confirm null)** | https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin |

**What to verify:** In the creation transaction logs, look for `Program log: Instruction: SetAuthority` — this sets mintAuthority to `null`. The current mint account confirms `mintAuthority: null`.

---

## 4. Freeze Authority Revocation

Freeze authority was also set to `null` during creation (confirmed via live on-chain query — `freezeAuthority: null`).

| Evidence | Link |
|---|---|
| **Live Mint Account** | https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin |

---

## 5. Orca Whirlpool (DEX Liquidity Pool)

| Field | Value |
|---|---|
| **Pool Address** | `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` |
| **Trading Pair** | FOSS / SOL (Wrapped SOL) |
| **Pool Type** | Whirlpool (concentrated liquidity AMM) |
| **Program** | `whirLbMiicVdio4qvUfM5KAg6Ct8VwpYzGff3uctyCc` |

| Source | Link |
|---|---|
| **Orca** | https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2 |
| **GeckoTerminal** | https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2 |
| **Solana Explorer (Pool)** | https://explorer.solana.com/address/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2 |
| **Pool Creation TX** | https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB |

**What to verify:** Pool contains FOSS + Wrapped SOL token vaults, initialized with `InitializePoolWithAdaptiveFee`, dynamic tick arrays created.

---

## 6. Metaplex Metadata

| Field | Value |
|---|---|
| **Metadata Program** | `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s` (Metaplex Token Metadata v3) |
| **Metadata URI (IPFS)** | https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n |
| **Image URI (IPFS)** | https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf |

**Metadata JSON (verified):**
```json
{
  "name": "Free Open Source Soft ",
  "symbol": "FOSS",
  "description": "FOSS Coin is a community-created token built to support and promote Free and Open Source Software (FOSS)...\n[full description in MASTER doc]",
  "image": "https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf"
}
```

**Image verification:**
- HTTP Status: 200 ✅
- Content-Type: `image/png` ✅
- File size: 2,508,148 bytes (~2.5 MB)

---

## 7. Creator / Fee Payer Wallet

| Field | Value |
|---|---|
| **Wallet Address** | `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` |

| Source | Link |
|---|---|
| **Solana Explorer** | https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b |
| **Solscan** | https://solscan.io/account/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b |

**What to verify:** This wallet is the fee payer (signer) on every FOSS-related transaction: creation, pool setup, liquidity provision, and all transfers.

---

## 8. Launchpad Program

| Field | Value |
|---|---|
| **Program ID** | `HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr` |
| **Type** | BPF Upgradeable Loader Program |
| **Program Data** | `Fsih13MhLm6cFNYGjBY6Vu1cTuBM3STwTVonz7igrhbr` |

| Source | Link |
|---|---|
| **Solana Explorer** | https://explorer.solana.com/address/HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr |
| **Solana FM** | https://solana.fm/address/HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr |

**Note:** This is NOT pump.fun (pump.fun program ID: `6EF8rrecthR5Dkzon8Nwu78hRvfCKubJ14M5uBEwF6P`). This is a separate no-code token launchpad that handles token creation, metadata, minting, mint revocation, and initial buy in a single atomic transaction.

---

## 9. All On-Chain Transactions (Chronological)

| # | Date (UTC) | Signature | Description | Explorer Link |
|---|---|---|---|---|
| 1 | 2025-07-23 07:43:36 | `VQT5g...iGroN` | **Token creation** — mint, metadata, mint 1B tokens, revoke mint authority, initial buy | [Explorer](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN) |
| 2 | 2025-08-17 07:32:10 | `3BmzH...K29g` | Token transfer — 2 FOSS to external wallet via `DeJBGdMFa1uynnnKiwrVioatTuHmNLpyFKnmB5kaFdzQ` | [Explorer](https://explorer.solana.com/tx/3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g) |
| 3 | 2025-10-21 14:13:04 | `5obap...tWiB` | **Orca Whirlpool creation** — `InitializePoolWithAdaptiveFee`, tick arrays | [Explorer](https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB) |
| 4 | 2025-10-21 14:13:23 | `2xR9T...JEGm` | **Liquidity provision** — position NFT created, liquidity added to pool | [Explorer](https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm) |
| 5 | 2026-01-18 12:59:51 | `4Xu9T...pxiAP` | Token transfer — 1 FOSS airdrop | [Explorer](https://explorer.solana.com/tx/4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq) |
| 6 | 2026-01-18 13:19:03 | `4CchR...kj4T` | Token transfer — 1 FOSS airdrop | [Explorer](https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T) |

---

## 10. API Endpoints (for programmatic verification)

| API | Endpoint |
|---|---|
| **Solana RPC (getAccountInfo)** | `POST https://api.mainnet-beta.solana.com` — query mint account |
| **Solana RPC (getSignaturesForAddress)** | `POST https://api.mainnet-beta.solana.com` — transaction history |
| **Solana RPC (getTokenLargestAccounts)** | `POST https://api.mainnet-beta.solana.com` — top holders |
| **GeckoTerminal Token API** | https://api.geckoterminal.com/api/v2/networks/solana/tokens/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin |
| **GeckoTerminal Pool API** | https://api.geckoterminal.com/api/v2/networks/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2 |
| **Orca Whirlpool Docs** | https://docs.orca.so/developers/whirlpools/interacting-with-the-protocol |
| **IPFS Metadata JSON** | https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n |
| **IPFS Token Logo** | https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf |

---

## 11. Key Program IDs Referenced

| Program | Program ID | Purpose |
|---|---|---|
| SPL Token Program | `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` | Core token operations (mint, transfer, authority) |
| SPL Token-2022 | `TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb` | Token extensions (used for position NFT) |
| Associated Token Account | `ATokenGPvbdGVxr1b2hvZbsiqW5xWH25efTNsLJA8knL` | Auto-creates token accounts for wallets |
| Metaplex Token Metadata | `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s` | On-chain name, symbol, URI, image |
| Orca Whirlpool | `whirLbMiicVdio4qvUfM5KAg6Ct8VwpYzGff3uctyCc` | Concentrated liquidity AMM |
| System Program | `11111111111111111111111111111111` | Account creation, SOL transfers |
| Compute Budget | `ComputeBudget111111111111111111111111111111` | Transaction compute unit limits |
| Launchpad (custom) | `HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr` | No-code token creation program |
| Transfer Service | `DeJBGdMFa1uynnnKiwrVioatTuHmNLpyFKnmB5kaFdzQ` | Token distribution/airdrop service |
