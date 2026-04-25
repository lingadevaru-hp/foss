<div align="center">

<img src="./foss-logo.png" alt="FOSS Token Logo" width="130" style="border-radius: 50%;" />

# $FOSS — Free Open Source Soft

**A real Solana token I built, listed, and fully documented — from concept to on-chain.**

[![Solana](https://img.shields.io/badge/Solana-Mainnet-9945FF?logo=solana&logoColor=white)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Live Since](https://img.shields.io/badge/Live%20Since-July%2023%2C%202025-brightgreen)](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)
[![Supply](https://img.shields.io/badge/Supply-1%2C000%2C000%2C000%20Fixed-blue)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Mint Authority](https://img.shields.io/badge/Mint%20Authority-Revoked-red)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![DEX](https://img.shields.io/badge/DEX-Orca%20Whirlpool-00C2CB)](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)

</div>

---

## What This Is

I created `$FOSS` — a token deployed on Solana mainnet. This repository is my full, public documentation of everything I built: how the token was created, what programs it touches on-chain, every key transaction, and where to verify all of it yourself.

I built this documentation for a specific reason — I wanted a permanent record of what I did and how I did it, so that anyone can come here, read through it, and verify every single claim without needing to ask me. No trust required. Everything points to live, public on-chain data.

---

## Why I Built This

My motivation comes directly from the **Free and Open Source Software** movement.

**Richard Stallman** founded the **Free Software Foundation (FSF)** in 1985 and authored the GNU General Public License — establishing the principle that software should be free not just in price, but in freedom: free to run, study, modify, and redistribute. The GNU Project, combined with the Linux kernel, gave the world a completely free operating system. Everything that followed — Git, Python, OpenSSL, GCC — built on that foundation.

The internet today runs almost entirely on FOSS. And most of the people who maintain that infrastructure are volunteers with no sustainable funding model.

I've worked with these tools throughout my time as a developer. The question I kept returning to was: *what if there was an on-chain, decentralized way to represent and support the value that FOSS creates?*

That question became `$FOSS`.

The token's metadata — stored permanently on IPFS — captures this directly:

> *"FOSS Coin is a community-created token built to support and promote Free and Open Source Software. It can be used to donate to FOSS projects, reward developers and contributors, and raise awareness about digital privacy, Linux, and open technologies."*

This project is not affiliated with the FSF, GNU, or Linux.org. It is an independent effort, built entirely by me.

---

## Token Overview

| Property | Value |
|---|---|
| **Symbol** | `FOSS` |
| **Full Name** | Free Open Source Soft |
| **Network** | Solana Mainnet |
| **Total Supply** | 1,000,000,000 — fixed permanently |
| **Mint Authority** | Revoked — new tokens cannot be minted by anyone |
| **Freeze Authority** | Revoked — tokens cannot be frozen |
| **DEX** | Orca Whirlpool — `FOSS / SOL` pair |
| **Metadata** | Stored on IPFS via Metaplex standard |
| **Live Since** | July 23, 2025 |

---

## What I Did — Timeline

### July 23, 2025 — Token Created on Solana Mainnet

In a single atomic transaction, I:

1. Created the **token mint account** on-chain using the SPL Token Program (`InitializeMint2`)
2. Uploaded the token metadata JSON to IPFS and registered it on-chain via **Metaplex**
3. Minted exactly **1,000,000,000 tokens** (`MintTo`)
4. Immediately revoked the **mint authority** (`SetAuthority` → `None`) — supply is sealed at the consensus level, not by promise
5. Made an initial purchase through the launchpad

**Creation TX:** [`VQT5gJr...C9iGroN`](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)

---

### October 21, 2025 — Listed on Orca Whirlpool

I created a **concentrated liquidity pool** for the `FOSS / SOL` pair on Orca Whirlpool and deposited initial liquidity — making the token publicly tradeable on a decentralized exchange.

Orca Whirlpool is a **tick-array based concentrated liquidity AMM** — not a simple constant-product pool. Liquidity sits within defined price ranges using tick indices. I read the on-chain pool state (`sqrtPrice`, `tickCurrentIndex`, `liquidity`) directly to understand what I had deployed.

**Pool:** [`3Ub4ojh...bZnE2`](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)

---

### January 18, 2026 — Airdrops

I distributed `$FOSS` tokens to a set of wallets using the SPL `TransferChecked` instruction, which enforces decimal precision at the protocol level on every transfer.

---

## Technical Depth

**SPL Token Program**
I worked through `InitializeMint2`, how associated token accounts are derived, how `MintTo` operates against the mint's decimal configuration, and how `TransferChecked` enforces precision. I understand the difference between these instructions — not just that they exist.

**Metaplex Token Metadata**
The on-chain account holds a URI — not the metadata itself. That URI points to a JSON file on IPFS (`QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n`) following the Metaplex standard, with `name`, `symbol`, `description`, and `image` fields. The image is a separate IPFS file (`QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf`). This is the chain between what appears in a wallet UI and what actually lives on-chain.

**Mint Authority Revocation**
Revoking mint authority is not a setting or a policy — it is an irreversible state change enforced by the Solana runtime at consensus. After `SetAuthority` is called with `None`, no future `MintTo` instruction will be accepted for this mint. It cannot be undone. This is a cryptographic guarantee, not a social promise.

**Concentrated Liquidity (Orca Whirlpool)**
Whirlpool uses tick-array based price ranges. Liquidity providers define the price bounds of their position, and the AMM only uses capital within the active tick. I read the pool account structure on-chain rather than relying on the UI to understand where my position was.

**Reading Raw Transactions**
I learned to trace inner instructions and cross-program invocations (CPIs) inside a transaction — identifying the actual program IDs being invoked, compute unit usage, and the instruction sequence — rather than trusting what a launchpad UI surface describes.

---

## Verify Everything Yourself

| What | Link |
|---|---|
| Token — Solana Explorer | [View token](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) |
| Token — Solscan | [View on Solscan](https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) |
| Creation Transaction | [View TX](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN) |
| Orca Liquidity Pool | [View pool](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) |
| GeckoTerminal Analytics | [View analytics](https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) |
| Token Metadata (IPFS) | [View metadata JSON](https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n) |
| Token Logo (IPFS) | [View logo](https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf) |
| Creator Wallet | [View wallet](https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b) |

**To verify the fixed supply:** Go to the Solana Explorer token link → check `Mint Authority: None`. That is a runtime-level guarantee — not editable.

---

## Repository Contents

This repo contains no application code. It is entirely documentation — an audit trail of what I built and verified.

| File / Folder | What's inside |
|---|---|
| [`overview.md`](./overview.md) | Full token overview — concept, supply, authorities, and what this project is |
| [`how-it-was-built.md`](./how-it-was-built.md) | Step-by-step account of how the token was created, listed, and distributed |
| [`on-chain-verification.md`](./on-chain-verification.md) | Every verifiable claim with its direct on-chain or IPFS source |
| [`programs.md`](./programs.md) | Solana programs involved — SPL Token Program, Metaplex, Orca Whirlpool — with instruction-level detail |
| [`transactions.md`](./transactions.md) | Key transactions: creation, listing, airdrops — with links and what each one did |
| [`resources.md`](./resources.md) | All public links to this project, organized by category |
| [`data/`](./data/) | Structured data files used during research and verification |
| [`raw/`](./raw/) | Raw captures — API responses, JSON exports, HTML snapshots used as evidence |

---

## Honest Assessment

This token has low liquidity. It is not listed on Jupiter (Solana's primary aggregator), so most users won't find it through the standard discovery route. It has no on-chain utility beyond representing the FOSS idea. The metadata depends on IPFS availability.

I am not hiding any of this. The goal was never to ship a product. The goal was to understand how this technology actually works — at the level where you can read a transaction and trace every instruction — and to document that understanding completely and publicly.

---

## The Idea

Richard Stallman's argument in 1983 was simple and radical: software freedom is a matter of user rights, not just developer preference. That argument produced the GPL, the GNU Project, and eventually the foundation that the Linux kernel was built on. The tools that run most of the modern internet came from that movement.

Most of that infrastructure has no real funding model. The people maintaining it are often doing it for free.

I don't know if a token is the answer to that problem. But I thought the question was worth asking in a real way — not as a whitepaper or a concept, but as something actually deployed, traceable, and documented on a public ledger.

This is that attempt.

---

<div align="center">

Built by [Lingadevaru H P](https://github.com/lingadevaru-hp)

</div>
