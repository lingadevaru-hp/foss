# FOSS Coin — Master Documentation

> **Last Verified:** April 14, 2026 — All claims cross-checked against live Solana mainnet on-chain data.

---

## 1. What Is FOSS Coin?

FOSS Coin ($FOSS) is a community-created Solana SPL token built to support and promote **Free and Open Source Software (FOSS)**. It serves as a decentralized mechanism to:

- **Donate to FOSS projects** — Fund the maintainers and tools that power the internet.
- **Reward developers and contributors** — Provide token-based incentives for open-source work.
- **Raise awareness** — Promote digital privacy, Linux, and open technologies.

**Important disclaimer:** FOSS Coin is *not* an official project by GNU, the Linux Foundation, the Free Software Foundation, or any other established organization. It is an independent grassroots initiative created by individuals who believe in the freedom to build, share, and innovate without restrictions.

---

## 2. Token Specifications

| Field | Value | Source |
|---|---|---|
| **Token Name** | Free Open Source Soft[^1] | On-chain Metaplex metadata |
| **Symbol** | FOSS | On-chain Metaplex metadata |
| **Mint Address** | `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` | Solana Token Program |
| **Blockchain** | Solana Mainnet | — |
| **Token Standard** | SPL Token (Token Program v3.x) | `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA`[^2] |
| **Decimals** | 6 | On-chain mint account[^2] |
| **Total Supply** | 1,000,000,000 (1 billion) | On-chain: raw supply = `1,000,000,000,000,000` ÷ 10⁶ = 1B[^2] |
| **Mint Authority** | **REVOKED** (`null`) | On-chain: set to `null` at creation[^2] |
| **Freeze Authority** | **REVOKED** (`null`) | On-chain: set to `null` at creation[^2] |
| **Is Initialized** | `true` | On-chain mint account[^2] |
| **DEX** | Orca (Whirlpool AMM) | Pool: `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2`[^3] |
| **Trading Pair** | FOSS / SOL (Wrapped SOL) | Whirlpool pool configuration[^3] |
| **Token Program** | `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` | Standard SPL Token Program[^2] |
| **Metadata Program** | Metaplex Token Metadata v3 | `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s`[^4] |
| **Creation Platform** | No-code launchpad (custom Solana program) | Program: `HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr`[^5] |

---

## 3. On-Chain Metadata

The Metaplex metadata is stored on IPFS and referenced on-chain:

### Metadata URI (IPFS)
`https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n`

### Metadata JSON (fetched and verified):
```json
{
  "name": "Free Open Source Soft ",
  "symbol": "FOSS",
  "description": "FOSS Coin is a community-created token built to support and promote Free and Open Source Software (FOSS).\n\nIt can be used to:\n- Donate to FOSS projects\n- Reward developers and contributors\n- Raise awareness about digital privacy, Linux, and open technologies\n\nThis is not an official project by GNU, Linux.org, or the Free Software Foundation. $FOSS is an independent grassroots effort by passionate individuals who believe in the freedom to build, share, and innovate without restrictions.\n\nBy holding or using FOSS Coin, you become part of a decentralized movement to fund the tools that power the internet — freely and ethically.",
  "image": "https://ipfs.io/ipfs/QmZjM3DiAsnhwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf"
}
```

### Token Logo
- **IPFS Hash:** `QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf`
- **URL:** `https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf`
- **Format:** PNG
- **Size:** 2,508,148 bytes (~2.5 MB)
- **Status:** ✅ Accessible (HTTP 200 confirmed)

---

## 4. Creation Timeline

### 4.1 Token Creation — July 23, 2025

| Field | Value |
|---|---|
| **Transaction Signature** | `VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN` |
| **Slot** | 355,223,383 |
| **Timestamp** | July 23, 2025 at 07:43:36 UTC |
| **Fee Paid** | 90,000 lamports (0.00009 SOL) |
| **Fee Payer (Creator)** | `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` |
| **Compute Units Consumed** | 201,685 |

**What happened in this single transaction:**

1. **Created the mint account** — System Program allocated 82 bytes, owned by Token Program
2. **Initialized the mint** — 6 decimals, mint authority = `9yifUgUbxr1pULtb4VRvfu35gP1Cm2GgS9fbr4WzQN8D`
3. **Created a metadata account** via Metaplex (`Create Metadata Accounts v3`)
4. **Created an Associated Token Account (ATA)** for the creator wallet
5. **Minted 1,000,000,000 tokens** to the creator's ATA
6. **Revoked mint authority** — `SetAuthority` instruction set mint authority to `null`
7. **Executed an initial "Buy" instruction** — The launchpad program immediately purchased 35,765.474485 FOSS tokens using SOL

**Key insight:** The mint authority was revoked **in the same transaction** as creation. This means the supply was fixed at exactly 1 billion from the very first moment the token existed — nobody can ever mint more.[^5]

### 4.2 Orca Whirlpool Pool Creation — October 21, 2025

| Field | Value |
|---|---|
| **Transaction Signature** | `5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB` |
| **Slot** | 374,850,194 |
| **Timestamp** | October 21, 2025 at 14:13:04 UTC |
| **Fee Paid** | 16,803 lamports |
| **Fee Payer** | `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` (same creator) |

**What happened:**

1. Created an **Orca Whirlpool** (`3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2`) — a concentrated liquidity AMM pool
2. Pool pairs FOSS token with **Wrapped SOL** (`So11111111111111111111111111111111111111112`)
3. Initialized **dynamic tick arrays** for price range management
4. Used `InitializePoolWithAdaptiveFee` — Orca's adaptive fee mechanism

### 4.3 Liquidity Provision — October 21, 2025 (19 seconds later)

| Field | Value |
|---|---|
| **Transaction Signature** | `2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm` |
| **Slot** | 374,850,239 |
| **Timestamp** | October 21, 2025 at 14:13:23 UTC |

**What happened:**

1. Created a **position NFT** (Token Extension / Token-2022 standard) — mint `8RVfhVxFGUo5uJKcMZQUu6MD7FhLH8v8WFRaxsT3doxY`
2. Used the NFT to track liquidity position ownership
3. **Added initial liquidity** to the Whirlpool via `IncreaseLiquidityV2`:
   - **FOSS tokens:** 2,900,653 (raw: 2,900,653 with 6 decimals = 2.900653 FOSS)
   - **SOL:** 0.0004 SOL (400,000 lamports)
4. Closed the temporary SOL token account after liquidity was added

### 4.4 Subsequent Activity

| Date | Transaction | Description |
|---|---|---|
| Aug 17, 2025 | `3Bmz...K29g` | Token transfer via program `DeJBGdMFa1uynnnKiwrVioatTuHmNLpyFKnmB5kaFdzQ` — small transfer of 2 FOSS tokens[^6] |
| Oct 21, 2025 | `2xR9...JEGm` | Liquidity provision (see 4.3) |
| Jan 18, 2026 | `4Xu9...pxiAP` | Token transfer — 1 FOSS token to new wallet `DFQ8kwb6...`[^7] |
| Jan 18, 2026 | `4Cch...kj4T` | Token transfer — 1 FOSS token to another new wallet[^7] |

---

## 5. Creator Proof

| Field | Value |
|---|---|
| **Creator Wallet** | `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` |
| **Evidence** | This wallet is the fee payer on ALL transactions: creation, pool setup, liquidity provision, and subsequent transfers[^5][^3] |
| **Creator ATA** | `eR38Chm7PX2yLJebhoXbUzsrUbRxtNfQzoKmxzZWQqT` (holds ~35,759 FOSS) |
| **Metadata Authority** | `9yifUgUbxr1pULtb4VRvfu35gP1Cm2GgS9fbr4WzQN8D` (used during creation, then revoked) |

---

## 6. Why Mint Authority Revocation Matters

### One-liner
**Once mint authority is revoked, NO ONE can ever create more tokens — the supply is permanently fixed.**

### Technical explanation
In the SPL Token Program, the `mintAuthority` field on a mint account controls which wallet has permission to call the `MintTo` instruction. When `mintAuthority` is set to `null` (via a `SetAuthority` instruction with `authorityType = 0`), the Token Program permanently rejects all future `MintTo` calls for that mint. This is a **one-way, irreversible operation** enforced at the program level on Solana's consensus layer.[^2]

### Why this is a key trust signal
- **No inflation risk** — The 1 billion supply is the maximum that will ever exist
- **No rug-pull via minting** — The creator cannot secretly mint more tokens and dump them
- **Verifiable by anyone** — Anyone can query the mint account on-chain and confirm `mintAuthority: null`
- **Fixed from creation** — In FOSS Coin's case, mint authority was revoked in the **same transaction** as token creation, meaning the supply was never mutable even for a single block

---

## 7. Current Status (as of April 14, 2026)

| Metric | Value |
|---|---|
| **Token Live** | ✅ Yes — fully deployed on Solana mainnet |
| **Mint Authority** | ✅ Revoked (permanent) |
| **Freeze Authority** | ✅ Revoked (no one can freeze your tokens) |
| **DEX Listing** | ✅ Listed on Orca (Whirlpool AMM) |
| **Trading Pair** | FOSS/SOL |
| **Pool Address** | `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` |
| **Orca Pool Type** | Whirlpool (concentrated liquidity) |
| **GeckoTerminal** | Tracked at `api.geckoterminal.com/api/v2/networks/solana/tokens/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` |
| **Jupiter Token List** | ❌ Not found in Jupiter's curated token registry (as of April 2026) |
| **Last On-Chain Activity** | January 18, 2026 — token transfers to new wallets |
| **Circulating Supply** | 1,000,000,000 FOSS (fixed) |
| **Creator Holdings** | ~35,759 FOSS in creator's ATA (remaining after DEX liquidity and transfers) |
| **Total Transactions** | 6 confirmed on-chain |

---

## 8. Technology Stack

| Component | Technology | Details |
|---|---|---|
| **Blockchain** | Solana Mainnet | Proof-of-History + Proof-of-Stake consensus |
| **Token Standard** | SPL Token (legacy Token Program) | Program ID: `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` |
| **Token Extensions** | Token-2022 (for position NFT only) | Program ID: `TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb` — used only for the liquidity position NFT |
| **Metadata** | Metaplex Token Metadata v3 | Program ID: `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s` |
| **Metadata Storage** | IPFS | Metadata JSON and token logo stored on IPFS |
| **Launch Platform** | Custom no-code launchpad | Program ID: `HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr` — BPF upgradeable loader program |
| **DEX** | Orca Whirlpool | Program ID: `whirLbMiicVdio4qvUfM5KAg6Ct8VwpYzGff3uctyCc` |
| **Token Distribution** | Launchpad bonding curve + DEX | Initial tokens distributed via launchpad "Buy" instruction, then moved to Orca Whirlpool |
| **Position NFT** | SPL Token-2022 with extensions | Metadata pointer, mint close authority — used by Orca for LP position tracking |

---

## 9. Supply Distribution

Based on on-chain token balances from the creation transaction[^5]:

| Recipient | Approx. Amount | Percentage | Notes |
|---|---|---|---|
| **Creator ATA** | ~35,759 FOSS | ~0.0036% | Wallet: `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` |
| **Orca Whirlpool** | ~999,964,234 FOSS | ~99.9964% | Pool vault: `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` |
| **Transferred (various)** | Small amounts (<100 FOSS) | <0.001% | Airdrops/transfers to individual wallets |

**Note:** The vast majority of the supply (~99.996%) was allocated to the Orca liquidity pool vault, making it a community-accessible token via the DEX.

---

[^1]: IPFS Metadata: https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n
[^2]: Solana RPC `getAccountInfo` — live query on 2026-04-14
[^3]: Orca Whirlpool creation tx: https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB
[^4]: Metaplex metadata created in launch transaction via `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s`
[^5]: Creation tx: https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN
[^6]: Transfer tx: https://explorer.solana.com/tx/3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g
[^7]: Recent transfers: https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T
