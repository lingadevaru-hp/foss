
<div align="center">

<img src="./foss-logo.png" alt="FOSS Token Logo" width="140" style="border-radius: 50%;" />

<br/>

# $FOSS — Free Open Source Soft

### A Solana SPL token I built, deployed, listed on a DEX, and fully documented on-chain.

<br/>

[

![Solana](https://img.shields.io/badge/Solana-Mainnet-9945FF?style=for-the-badge&logo=solana&logoColor=white)

](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[

![Live Since](https://img.shields.io/badge/Live%20Since-July%2023%2C%202025-brightgreen?style=for-the-badge)

](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)
[

![Supply](https://img.shields.io/badge/Supply-1%2C000%2C000%2C000%20Fixed-blue?style=for-the-badge)

](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[

![Mint Authority](https://img.shields.io/badge/Mint%20Authority-Revoked-red?style=for-the-badge)

](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[

![DEX](https://img.shields.io/badge/DEX-Orca%20Whirlpool-00C2CB?style=for-the-badge)

](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)
[

![GeckoTerminal](https://img.shields.io/badge/GeckoTerminal-Tracked-orange?style=for-the-badge)

](https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)

</div>

---

## What This Repository Is

This is the complete project record for `$FOSS` — a Solana SPL token I created, listed on Orca's DEX, and documented from the ground up.

The repository contains no application code. It is a technical documentation project: every on-chain action is traceable, every claim has a source, and the raw data collected during research is preserved in full.

The token was built around an idea I care about — Free and Open Source Software runs most of the internet, the people maintaining it rarely have sustainable funding, and blockchain provides a transparent, permissionless way to represent and route that value. Whether a token is the right answer to that problem is a separate question. Building and documenting one was the point of this project.

---

## Token Specifications

| Property | Value |
|---|---|
| **Symbol** | `FOSS` |
| **On-chain Name** | `Free Open Source Soft ` |
| **Network** | Solana Mainnet |
| **Mint Address** | `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` |
| **Token Standard** | SPL Token — `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` |
| **Decimals** | `6` |
| **Total Supply (human-readable)** | `1,000,000,000` |
| **Total Supply (raw on-chain)** | `1,000,000,000,000,000` ÷ 10⁶ = 1B |
| **Mint Authority** | `null` — revoked, irreversible, enforced by Solana runtime |
| **Freeze Authority** | `null` — revoked |
| **Metadata Standard** | Metaplex Token Metadata v3 |
| **Metadata URI** | [IPFS](https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n) |
| **Token Logo** | [IPFS PNG ~2.5MB](https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf) |
| **DEX** | Orca Whirlpool — concentrated liquidity AMM |
| **Pool Address** | `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` |
| **Trading Pair** | FOSS / Wrapped SOL |
| **Creation Platform** | No-code launchpad — `HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr` |
| **Last On-chain Activity** | January 18, 2026 |

---

## What I Built — Step by Step

### July 23, 2025 — Token Created on Solana Mainnet

Everything happened in a **single atomic transaction** at slot `355,223,383`:

```
1. System Program         → allocated 82-byte mint account
2. InitializeMint2        → 6 decimals, initial mint authority set
3. Metaplex               → Create Metadata Accounts v3 (name, symbol, IPFS URI registered on-chain)
4. ATokenGPvbdGVxr1b2...  → Associated Token Account created for creator wallet
5. MintTo                 → 1,000,000,000 tokens minted to creator ATA
6. SetAuthority → None    → mint authority permanently revoked
7. Launchpad Buy          → initial 35,765.474485 FOSS purchased immediately
```

> Mint authority was revoked **in the same transaction as creation** — the supply was never mutable, not even for a single block.

**Fee payer / creator wallet:** `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b`  
**Transaction:** [`VQT5gJr...C9iGroN`](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)

---

### October 21, 2025 — Listed on Orca Whirlpool DEX

**Pool creation** at slot `374,850,194`:

- `InitializePoolWithAdaptiveFee` — Orca Whirlpool program initialized
- Dynamic tick arrays created for price range management
- Pool: `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2`

**Liquidity provision** 19 seconds later at slot `374,850,239`:

- Position NFT minted via Token-2022: `8RVfhVxFGUo5uJKcMZQUu6MD7FhLH8v8WFRaxsT3doxY`
- `IncreaseLiquidityV2` — deposited `2.900653 FOSS` + `0.0004 SOL`

Orca Whirlpool uses **concentrated liquidity** — not a standard constant-product AMM. Liquidity sits within defined price tick ranges. I read the raw pool account state (`sqrtPrice`, `tickCurrentIndex`, `liquidity`) directly from the chain rather than relying on the UI.

---

### January 18, 2026 — Token Airdrops

Distributed `$FOSS` to wallets using `TransferChecked` — the SPL instruction that enforces decimal precision at the protocol level on every transfer.

---

## All On-Chain Transactions

| # | Date (UTC) | Description | Signature | Link |
|---|---|---|---|---|
| 1 | 2025-07-23 07:43:36 | Token creation — mint, metadata, 1B supply, mint authority revoked, initial buy | `VQT5gJr...iGroN` | [Explorer](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN) |
| 2 | 2025-08-17 07:32:10 | Transfer — 2 FOSS to external wallet | `3BmzHV...K29g` | [Explorer](https://explorer.solana.com/tx/3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g) |
| 3 | 2025-10-21 14:13:04 | Orca Whirlpool pool creation | `5obapS...tWiB` | [Explorer](https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB) |
| 4 | 2025-10-21 14:13:23 | Liquidity provision — position NFT created | `2xR9TX...JEGm` | [Explorer](https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm) |
| 5 | 2026-01-18 12:59:51 | Airdrop — 1 FOSS | `4Xu9TW...REq` | [Explorer](https://explorer.solana.com/tx/4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq) |
| 6 | 2026-01-18 13:19:03 | Airdrop — 1 FOSS | `4CchR5...kj4T` | [Explorer](https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T) |

---

## Programs Involved

| Program | ID | Role in This Project |
|---|---|---|
| SPL Token Program | `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` | Core token operations — mint, transfer, authority |
| SPL Token-2022 | `TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb` | Used for Orca position NFT |
| Associated Token Account | `ATokenGPvbdGVxr1b2hvZbsiqW5xWH25efTNsLJA8knL` | Auto-creates token accounts for wallets |
| Metaplex Token Metadata | `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s` | On-chain name, symbol, IPFS URI |
| Orca Whirlpool | `whirLbMiicVdio4qvUfM5KAg6Ct8VwpYzGff3uctyCc` | Concentrated liquidity AMM — DEX listing |
| Launchpad (custom BPF) | `HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr` | Atomic token creation — not pump.fun |
| System Program | `11111111111111111111111111111111` | Account creation, SOL transfers |
| Compute Budget | `ComputeBudget111111111111111111111111111111` | Transaction compute unit management |

---

## Supply Distribution

| Recipient | Amount | % | Notes |
|---|---|---|---|
| Orca Whirlpool vault | ~999,964,234 FOSS | 99.9964% | Publicly tradeable via DEX |
| Creator ATA | ~35,759 FOSS | 0.0036% | `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` |
| Airdrops | < 100 FOSS | < 0.001% | Individual wallets |

---

## Verify It Yourself

| What | Link |
|---|---|
| Token — Solana Explorer | [View](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) |
| Token — Solscan | [View](https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) |
| Token — Solana FM | [View](https://solana.fm/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) |
| Creation TX | [View](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN) |
| Orca Pool | [View](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) |
| GeckoTerminal Analytics | [View](https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) |
| Metadata JSON — IPFS | [View](https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n) |
| Token Logo — IPFS | [View](https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf) |
| Creator Wallet | [View](https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b) |
| GeckoTerminal Token API | [View](https://api.geckoterminal.com/api/v2/networks/solana/tokens/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) |

**To confirm fixed supply:** Solana Explorer → token page → `Mint Authority: None`. This is a runtime-level state, not a setting.

**To verify via RPC directly:**
```bash
curl https://api.mainnet-beta.solana.com -X POST \
  -H "Content-Type: application/json" \
  -d '{
    "jsonrpc":"2.0","id":1,
    "method":"getAccountInfo",
    "params":["64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin",{"encoding":"jsonParsed"}]
  }'
```

---

## Repository Contents

```
foss/
├── README.md                     ← you are here
├── foss-logo.png                 ← token logo (same file as on IPFS)
├── overview.md                   ← token concept, supply, authorities, metadata
├── how-it-was-built.md           ← full creation walkthrough with instruction-level detail
├── on-chain-verification.md      ← every claim with its direct on-chain source
├── programs.md                   ← all Solana programs involved, with roles
├── transactions.md               ← all 6 transactions — dates, slots, descriptions, links
├── resources.md                  ← every public URL organized by category
├── data/
│   └── token-spec.json           ← structured token data (Jupiter token list format + extras)
└── raw/
    ├── mint_account_info.json    ← RPC getAccountInfo response for the mint
    ├── token_supply.json         ← RPC getTokenSupply response
    ├── mint_signatures.json      ← RPC getSignaturesForAddress response
    ├── foss_tx_1.json            ← creation transaction (parsed)
    ├── foss_tx_2.json            ← transfer tx
    ├── foss_tx_3.json            ← pool creation tx
    ├── foss_tx_4.json            ← liquidity provision tx
    ├── foss_tx_5.json            ← airdrop tx
    ├── foss_tx_6.json            ← airdrop tx
    ├── foss_metadata_accounts.json
    ├── foss_token_accounts.json
    ├── foss_pool_account.json
    ├── foss_pool_foss_balance.json
    ├── foss_pool_sol_balance.json
    ├── foss_pool_gecko.json
    ├── geckoterminal_token.json
    ├── orca_pool_api.json
    ├── orca_pool_search.json
    ├── foss_ipfs_metadata.json
    ├── foss_logo.png
    ├── coinbook_token.html       ← saved explorer HTML captures
    ├── solana_explorer_mint_page.html
    └── solscan_mint_page.html
```

---

## Known Limitations

This project is honest about what it is and what it isn't.

- **Low liquidity** — initial pool had ~0.0004 SOL + ~2.9 FOSS. High slippage on any meaningful trade.
- **Not on Jupiter** — Solana's primary swap aggregator. Token won't appear in most wallet swap UIs.
- **No on-chain utility** — no transfer hooks, no governance, no donation routing mechanism yet.
- **IPFS dependency** — metadata and logo rely on IPFS availability. Not pinned to Arweave.
- **Creator holds the LP position NFT** — liquidity can be withdrawn. That's a real centralisation point.
- **Legacy Token Program** — not Token-2022, so no modern extensions like transfer hooks.
- **6 total transactions** — low activity since creation.

---

## What I Learned

Working through this at the instruction level — not just through a UI — taught me how SPL tokens actually work, how Metaplex connects on-chain accounts to IPFS, what mint authority revocation means at the consensus level, and how Orca Whirlpool's tick-array model differs from a constant-product AMM. The documentation here is the output of that process.

---

<div align="center">

Built by [Lingadevaru H P](https://github.com/lingadevaru-hp) · [lingadevaru.in](https://lingadevaru.in)

</div>
