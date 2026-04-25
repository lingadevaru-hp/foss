<div align="center">

<img src="https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf" alt="FOSS Token Logo" width="120" style="border-radius: 50%;" />

# FOSS

**I deployed a real token on Solana mainnet — as a college student, to learn how blockchain actually works.**

[![Solana](https://img.shields.io/badge/Solana-Mainnet-9945FF?logo=solana&logoColor=white)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Live Since](https://img.shields.io/badge/Live%20Since-July%2023%2C%202025-brightgreen)](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)
[![Supply](https://img.shields.io/badge/Supply-1%2C000%2C000%2C000%20Fixed-blue)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Mint Authority](https://img.shields.io/badge/Mint%20Authority-Revoked-red)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![DEX](https://img.shields.io/badge/DEX-Orca%20Whirlpool-00C2CB)](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)

> ⚠️ This is a student learning project — not a product, not an investment, not a startup.

</div>

---

## What I Built

I created `FOSS` — a Solana token that stands for **Free and Open Source Software**.

The internet runs on open-source tools — Linux, Git, Python, OpenSSL — most of them maintained by volunteers with no real funding. I wanted to explore whether a token on a public blockchain could represent that idea.

More than the concept, this was a hands-on learning project. I wanted to go past reading about blockchain and actually deploy something real, trace every transaction, and understand what's happening at the protocol level.

Everything you see here is live on Solana mainnet. Every claim is publicly verifiable.

---

## What This Means, Even If You're Not Technical

- I created a digital token called `FOSS` on the Solana blockchain
- It's similar to creating a coin — except it lives permanently on a public ledger that anyone in the world can read
- The total supply is fixed at **1 billion** — I permanently disabled the ability to create more (this is called revoking mint authority — it's a one-way, irreversible action enforced by the blockchain itself, not just a promise)
- I then listed it on **Orca**, a decentralized exchange, so anyone can trade it
- Every single step — creation, listing, every transfer — is recorded as a transaction on the blockchain and publicly visible

---

## Token at a Glance

| | |
|---|---|
| **Symbol** | `FOSS` |
| **Full name** | Free Open Source Soft |
| **Network** | Solana Mainnet |
| **Total supply** | 1,000,000,000 (fixed forever) |
| **Mint authority** | Revoked — no one can ever mint more |
| **Freeze authority** | Revoked — no one can freeze your tokens |
| **DEX listing** | Orca Whirlpool (FOSS / SOL pair) |
| **Live since** | July 23, 2025 |

---

## What I Actually Did — Step by Step

**July 23, 2025 — Token created**

In a single Solana transaction, I:
1. Created the token mint account on-chain
2. Registered the name, symbol, logo, and description using Metaplex (stored on IPFS)
3. Minted exactly 1,000,000,000 tokens
4. Immediately revoked the mint authority — supply fixed from block one
5. Made an initial purchase through the launchpad

**October 21, 2025 — Listed on Orca**

I created an Orca Whirlpool liquidity pool for the `FOSS / SOL` trading pair and added initial liquidity — making the token publicly tradeable on a decentralized exchange.

**January 18, 2026 — Airdrops**

Sent small amounts of FOSS to a few wallets as the project's first distribution activity.

---

## What I Learned

- How Solana's **SPL Token Program** works at the instruction level — `InitializeMint2`, `MintTo`, `SetAuthority`, `TransferChecked`
- How **Metaplex** connects on-chain token accounts to off-chain metadata stored on IPFS
- Why **mint authority revocation** is a cryptographic guarantee, not a social promise — once it's done, the Solana runtime rejects any future minting at the consensus level
- How **concentrated liquidity AMMs** work — Orca Whirlpool uses tick arrays and price ranges, not a simple constant-product model
- How to read raw blockchain transactions, trace program invocations, and verify claims against live chain data
- What actually happens inside a no-code launchpad — the program IDs, the inner instructions, the atomic execution

---

## Verify It Yourself

You don't have to take my word for any of this. Everything is public.

| What to check | Link |
|---|---|
| Token on Solana Explorer | [View token](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) |
| Token on Solscan | [View on Solscan](https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) |
| Creation transaction | [View creation TX](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN) |
| Orca liquidity pool | [View pool](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) |
| Token metadata (IPFS) | [View metadata JSON](https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n) |
| Token logo (IPFS) | [View logo](https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf) |
| GeckoTerminal analytics | [View analytics](https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) |
| Creator wallet | [View wallet](https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b) |

**To verify the supply cap yourself:** Go to the Solana Explorer link above → look for `Mint Authority: None` — that confirms no one can ever create more tokens.

---

## Repository Contents

Everything in this repo is documentation of what I built and how I verified it.

| File | What's inside |
|---|---|
| `FOSS_COIN_MASTER.md` | Full technical spec — token config, creation timeline, supply distribution |
| `FOSS_COIN_EVIDENCE.md` | Every verifiable fact with its on-chain source |
| `FOSS_COIN_CROSS_VERIFICATION.md` | 18 claims checked against live chain data — including two corrections I found |
| `FOSS_COIN_ALL_URLS.md` | Every public link, organized by category |
| `FOSS_COIN_BLIND_SPOTS.md` | Technical gaps, risks, and limitations — honest assessment |
| `codex/` | Raw research files — JSON exports, HTML captures, API responses |

---

## The Honest Part

This token has very low liquidity. It's not listed on Jupiter (the main Solana swap aggregator). It has no utility beyond representing an idea. The metadata lives on IPFS and depends on continued availability.

I documented all of this openly in [`FOSS_COIN_BLIND_SPOTS.md`](./FOSS_COIN_BLIND_SPOTS.md).

The point was never to build a product. The point was to understand how this technology actually works — by doing it, not just reading about it.

---

<div align="center">

Built by [Lingadevaru H P](https://github.com/lingadevaru-hp) · MCA Final Year · Siddaganga Institute of Technology

</div>
