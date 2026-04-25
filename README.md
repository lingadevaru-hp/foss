# FOSS: My Journey into Blockchain with a Real Token

<div align="center">

<img src="https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf" alt="FOSS Token Logo" width="120" style="border-radius: 50%;" />

# FOSS

**As a college student, I deployed a real token on the Solana mainnet to truly understand how blockchain works.**

[![Solana](https://img.shields.io/badge/Solana-Mainnet-9945FF?logo=solana&logoColor=white)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Live Since](https://img.shields.io/badge/Live%20Since-July%2023%2C%202025-brightgreen)](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)
[![Supply](https://img.shields.io/badge/Supply-1%2C000%2C000%2C000%20Fixed-blue)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Mint Authority](https://img.shields.io/badge/Mint%20Authority-Revoked-red)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![DEX](https://img.shields.io/badge/DEX-Orca%20Whirlpool-00C2CB)](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)

> ⚠️ This project was a personal learning endeavor — it is not a product, an investment, or a startup. It represents my hands-on exploration of blockchain technology.

</div>

---

## My Motivation: Beyond Theory to Practice

I created `FOSS` — a Solana token that stands for **Free and Open Source Software**. My journey began with a simple question: how does blockchain *really* work? I wanted to move beyond reading articles and whitepapers and actually deploy something tangible on a live network. The internet thrives on open-source tools like Linux, Git, and Python, often maintained by dedicated volunteers. I was curious to explore if a token on a public blockchain could embody and support this ethos.

This project was a deep dive into the practicalities of blockchain development. I aimed to deploy a real asset, meticulously trace every transaction, and gain a firsthand understanding of the Solana protocol at a fundamental level. Every component you see here is live on the Solana mainnet, and every claim I make is publicly verifiable.

---

## What I Built: FOSS Token Explained

In essence, I deployed a digital token named `FOSS` on the Solana blockchain. Think of it like creating a digital coin, but one that lives permanently on a public, immutable ledger accessible to anyone globally. Here’s a breakdown of its core characteristics:

*   **Fixed Supply:** The total supply of FOSS is permanently capped at **1 billion** tokens. I achieved this by immediately revoking the mint authority after creation. This is a critical, irreversible action enforced by the blockchain itself, not merely a promise.
*   **Decentralized Exchange Listing:** I subsequently listed FOSS on **Orca**, a decentralized exchange, making it publicly tradable.
*   **Transparent Record:** Every single action — from the token's creation and listing to every subsequent transfer — is recorded as a transaction on the blockchain and is publicly visible.

### Token at a Glance

| Field | Value |
|---|---|
| **Symbol** | `FOSS` |
| **Full name** | Free Open Source Soft |
| **Network** | Solana Mainnet |
| **Mint address** | `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` [1] |
| **Total supply** | 1,000,000,000 (fixed forever) |
| **Mint authority** | Revoked — no one can ever mint more |
| **Freeze authority** | Revoked — no one can freeze your tokens |
| **DEX listing** | Orca Whirlpool (FOSS / SOL pair) [2] |
| **Live since** | July 23, 2025 |

---

## My Journey: Step-by-Step Actions

### July 23, 2025 — Token Creation [3]

In a single, atomic Solana transaction, I:

1.  Created the token mint account on-chain.
2.  Registered the token's name, symbol, logo, and description using Metaplex, with metadata stored on IPFS.
3.  Minted exactly 1,000,000,000 tokens.
4.  Immediately revoked the mint authority, ensuring the supply was fixed from the very first block.
5.  Made an initial purchase through the launchpad I used.

### October 21, 2025 — Listed on Orca [4]

I created an Orca Whirlpool liquidity pool for the `FOSS / SOL` trading pair and added initial liquidity. This crucial step made the token publicly tradable on a decentralized exchange.

### January 18, 2026 — Airdrops [5] [6]

I conducted small airdrops, sending minor amounts of FOSS to a few external wallets. This served as the project's initial distribution activity and allowed me to observe token transfers on-chain.

---

## What I Learned: Key Takeaways

This hands-on experience provided invaluable insights into various aspects of blockchain and Solana development:

*   **Solana's SPL Token Program:** I gained a deep understanding of how core token operations like `InitializeMint2`, `MintTo`, `SetAuthority`, and `TransferChecked` work at the instruction level.
*   **Metaplex Integration:** I learned how Metaplex bridges on-chain token accounts with off-chain metadata stored on IPFS, enabling rich token representation.
*   **Cryptographic Guarantees:** I witnessed firsthand why mint authority revocation is a cryptographic guarantee, not just a social promise. Once revoked, the Solana runtime fundamentally rejects any future minting attempts at the consensus level.
*   **Concentrated Liquidity AMMs:** I explored the mechanics of Orca Whirlpool, understanding how concentrated liquidity Automated Market Makers (AMMs) utilize tick arrays and price ranges, a more advanced model than simple constant-product AMMs.
*   **On-Chain Verification:** I developed skills in reading raw blockchain transactions, tracing program invocations, and cross-verifying claims against live chain data.
*   **No-Code Launchpads:** I analyzed the internal workings of a no-code launchpad, observing the program IDs, inner instructions, and atomic execution that facilitate token deployment.

---

## Verify It Yourself: Transparency and Evidence

I believe in the principle of 
transparency and verifiable truth. You don't have to take my word for any of this; everything is publicly accessible on the Solana blockchain. Here are the key links to verify my claims:

| What to check | Link |
|---|---|
| Token on Solana Explorer | [View token](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) [1] |
| Token on Solscan | [View on Solscan](https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) [7] |
| Creation transaction | [View creation TX](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN) [3] |
| Orca liquidity pool | [View pool](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) [2] |
| Token metadata (IPFS) | [View metadata JSON](https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n) [8] |
| Token logo (IPFS) | [View logo](https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf) [9] |
| GeckoTerminal analytics | [View analytics](https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) [10] |
| Creator wallet | [View wallet](https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b) [11] |

**To verify the supply cap yourself:** Navigate to the Solana Explorer link for the token [1] and look for `Mint Authority: None`. This confirms that no one, including myself, can ever create more tokens.

---

## Repository Contents: My Documentation

This repository serves as a comprehensive documentation of what I built and how I verified it. It contains all the raw data, analysis, and cross-verification I performed during this learning journey.

| File | What you'll find inside |
|---|---|
| `how-it-was-built.md` | A detailed account of the technical steps and decisions I made during the token creation and deployment process. |
| `on-chain-verification.md` | My process of verifying claims against live chain data, including any corrections or discrepancies I found. |
| `overview.md` | A high-level summary of the FOSS token, its purpose, and key specifications. |
| `programs.md` | A list and explanation of the various Solana programs and program IDs involved in the FOSS token ecosystem. |
| `resources.md` | A comprehensive index of all public links, organized by category, used throughout this project. |
| `transactions.md` | A chronological record of all significant transactions related to the FOSS token, with links to Solana Explorer. |
| `data/` | Contains structured data, such as `token-spec.json`, which outlines the token's technical specifications. |
| `raw/` | My raw research files, including JSON exports, HTML captures, and API responses used for verification. |

---

## The Honest Part: Limitations and Learning

It's important to be transparent about the nature of this project. The FOSS token currently has very low liquidity and is not listed on major Solana swap aggregators like Jupiter. Beyond representing an idea, it has no inherent utility. Furthermore, its metadata relies on the continued availability of IPFS gateways.

I documented all these limitations and potential blind spots openly throughout my research. The core purpose of this project was never to build a product or a financial instrument. Instead, it was an intensive, hands-on learning experience to understand the intricate workings of blockchain technology by actively participating in its deployment and verification.

---

<div align="center">

Built by [Lingadevaru H P](https://github.com/lingadevaru-hp) · MCA Final Year · Siddaganga Institute of Technology

</div>

## References

[1] Solana Explorer. (n.d.). *Token Address: 64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin*. Retrieved from [https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[2] Orca. (n.d.). *Whirlpool: FOSS / SOL*. Retrieved from [https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)
[3] Solana Explorer. (n.d.). *Transaction: VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN*. Retrieved from [https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfPBTSZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)
[4] Solana Explorer. (n.d.). *Transaction: 2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm*. Retrieved from [https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm](https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm)
[5] Solana Explorer. (n.d.). *Transaction: 4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq*. Retrieved from [https://explorer.solana.com/tx/4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq](https://explorer.solana.com/tx/4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq)
[6] Solana Explorer. (n.d.). *Transaction: 4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693ShJng4Be5Xkj4T*. Retrieved from [https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693ShJng4Be5Xkj4T](https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693ShJng4Be5Xkj4T)
[7] Solscan. (n.d.). *Token: 64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin*. Retrieved from [https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin](https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[8] IPFS. (n.d.). *Metadata JSON: QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n*. Retrieved from [https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n](https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n)
[9] IPFS. (n.d.). *Token Logo: QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf*. Retrieved from [https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf](https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf)
[10] GeckoTerminal. (n.d.). *Solana Pool: 3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2*. Retrieved from [https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2](https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)
[11] Solana Explorer. (n.d.). *Wallet Address: HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b*. Retrieved from [https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b](https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b)
