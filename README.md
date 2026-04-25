# FOSS: My Hands-On Exploration of Blockchain and Free Software Principles

<div align="center">

<img src="https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf" alt="FOSS Token Logo" width="120" style="border-radius: 50%;" />

# FOSS

**This project documents my journey to understand blockchain technology by deploying a real token on the Solana mainnet, driven by the principles of Free and Open Source Software.**

[![Solana](https://img.shields.io/badge/Solana-Mainnet-9945FF?logo=solana&logoColor=white)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Live Since](https://img.shields.io/badge/Live%20Since-July%2023%2C%202025-brightgreen)](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)
[![Supply](https://img.shields.io/badge/Supply-1%2C000%2C000%2C000%20Fixed-blue)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Mint Authority](https://img.shields.io/badge/Mint%20Authority-Revoked-red)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![DEX](https://img.shields.io/badge/DEX-Orca%20Whirlpool-00C2CB)](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)

> ⚠️ This project is a personal technical exploration and documentation effort. It is not intended as a product, an investment, or a startup. My focus was on practical learning and verifiable execution.

</div>

---

## My Inspiration: Free Software Principles in a Decentralized World

My journey into creating `FOSS` — a Solana token representing **Free and Open Source Software** — was deeply inspired by the foundational principles of the Free Software movement. Visionaries like Richard Stallman and organizations such as the Free Software Foundation have profoundly influenced my understanding of freedom in computing. Their unwavering commitment to transparency, community collaboration, and the fundamental rights to study, modify, and distribute software has always motivated me. I believe their contributions to the community and their advocacy for open principles are paramount.

This project emerged from my desire to explore how these enduring ideals could manifest within the rapidly evolving, decentralized landscape of blockchain technology. It became my hands-on endeavor to move beyond theoretical understanding, to actively build, deploy, and meticulously document every step. My primary goal was to gain a profound, practical understanding of how blockchain truly operates at the protocol level, and to create a comprehensive, auditable record of this experience for both my personal reference and for external verification.

---

## What I Built: The FOSS Token and Its Technical Foundation

I deployed a digital token, `FOSS`, on the Solana mainnet. This was more than just creating a digital asset; it was about establishing a permanent, publicly auditable record of my work on a decentralized ledger. Here are the key technical aspects of what I achieved:

*   **Fixed and Immutable Supply:** A core tenet of my design was to ensure the token's scarcity and integrity. I minted exactly **1 billion** FOSS tokens and, crucially, immediately revoked both the mint and freeze authorities. This action is cryptographically enforced by the Solana protocol, meaning no one, including myself, can ever create more tokens or freeze existing ones. This provides a strong, verifiable guarantee of the token's fixed supply.
*   **Decentralized Exchange Integration:** To demonstrate practical utility and accessibility, I integrated FOSS with **Orca**, a leading decentralized exchange on Solana. I established an Orca Whirlpool, a concentrated liquidity pool, for the FOSS/SOL trading pair, making the token available for public trading.
*   **Transparent On-Chain Record:** Every action I took, from the initial token creation to its listing and subsequent transfers, is immutably recorded as a transaction on the Solana blockchain. This entire history is publicly visible and verifiable, embodying the transparency inherent in decentralized systems.

### FOSS Token Specifications

| Field | Value |
|---|---|
| **Symbol** | `FOSS` |
| **Full name** | Free Open Source Soft |
| **Network** | Solana Mainnet |
| **Mint address** | `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` [1] |
| **Decimals** | 6 |
| **Total supply** | 1,000,000,000 (fixed forever) |
| **Mint authority** | Revoked (`null`) |
| **Freeze authority** | Revoked (`null`) |
| **Token program** | `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` |
| **Metadata program** | `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s` |
| **DEX** | Orca Whirlpool [2] |
| **Pool address** | `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` [2] |
| **Live since** | July 23, 2025 |

---

## My Technical Journey: A Step-by-Step Documentation

This section outlines the chronological and technical steps I undertook, providing verifiable transaction links for each significant event.

### July 23, 2025 — Token Creation and Authority Revocation [3]

In a single, atomic Solana transaction, I executed the foundational steps for the FOSS token:

1.  **Mint Account Creation:** I initialized the token mint account on-chain, defining its properties.
2.  **Metadata Registration:** Using Metaplex, I registered the token's name, symbol, logo, and description. This metadata is stored off-chain on IPFS, with its URI linked to the on-chain token.
3.  **Token Minting:** I minted the entire supply of 1,000,000,000 FOSS tokens.
4.  **Authority Revocation:** Immediately after minting, I revoked both the mint and freeze authorities. This critical step permanently capped the supply and prevented any future manipulation of token accounts.
5.  **Initial Purchase:** I performed an initial purchase through the custom launchpad program I utilized, marking the token's genesis on the network.

### October 21, 2025 — Orca Whirlpool Listing and Liquidity Provision [4]

To enable decentralized trading, I created and initialized an Orca Whirlpool liquidity pool for the `FOSS / SOL` trading pair. This involved:

1.  **Pool Creation:** Establishing the Whirlpool account and configuring its parameters, including adaptive fees.
2.  **Liquidity Provision:** Adding initial liquidity to the pool, comprising FOSS tokens and Wrapped SOL, to facilitate trading.

### January 18, 2026 — Initial Token Distribution (Airdrops) [5] [6]

I conducted small-scale airdrops of FOSS tokens to several external wallets. This activity served to test the token transfer mechanisms and observe on-chain distribution dynamics.

---

## My Learning Outcomes: Technical Insights Gained

This project was an immersive learning experience that provided me with practical expertise in several key areas of blockchain development:

*   **Solana SPL Token Program Mastery:** I gained a deep, instruction-level understanding of the Solana Program Library (SPL) Token Program, including critical instructions like `InitializeMint2`, `MintTo`, `SetAuthority`, and `TransferChecked`.
*   **Metaplex Metadata Integration:** I learned the intricacies of connecting on-chain token accounts with off-chain metadata via Metaplex and IPFS, essential for rich token representation.
*   **Understanding Cryptographic Guarantees:** I developed a clear appreciation for how on-chain actions, such as mint authority revocation, provide cryptographic guarantees enforced at the consensus level, far beyond mere social promises.
*   **Concentrated Liquidity AMM Mechanics:** I explored the advanced concepts behind Orca Whirlpool's concentrated liquidity Automated Market Makers (AMMs), understanding their use of tick arrays and price ranges, which differ significantly from simpler constant-product models.
*   **On-Chain Data Analysis:** I honed my skills in reading raw blockchain transactions, tracing program invocations, and performing rigorous cross-verification of claims against live chain data.
*   **Launchpad Program Analysis:** I analyzed the internal operations of a no-code launchpad program, dissecting its program IDs, inner instructions, and atomic execution flows.

---

## Verify My Work: Transparency and Auditability

In the spirit of Free and Open Source Software, I firmly believe in the principle of "Don't Trust, Verify." Every claim I make about this project is backed by publicly accessible data on the Solana blockchain. This section provides direct links for you to audit and verify my work independently. This verifiable record also serves as a robust demonstration of my practical skills and technical understanding for potential recruiters.

| What to Verify | Link |
|---|---|
| **FOSS Token on Solana Explorer** | [View Token](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) [1] |
| **FOSS Token on Solscan** | [View on Solscan](https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin) [7] |
| **Token Creation Transaction** | [View Creation TX](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN) [3] |
| **Orca Liquidity Pool** | [View Pool](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) [2] |
| **Token Metadata (IPFS)** | [View Metadata JSON](https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n) [8] |
| **Token Logo (IPFS)** | [View Logo](https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf) [9] |
| **GeckoTerminal Analytics** | [View Analytics](https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2) [10] |
| **My Creator Wallet** | [View Wallet](https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b) [11] |

**To verify the fixed supply:** Navigate to the Solana Explorer link for the FOSS token [1]. Observe the `Mint Authority: None` field, which cryptographically confirms that no additional tokens can ever be minted.

---

## Repository Structure: My Documentation Artifacts

This repository is designed as a comprehensive record of my project. It contains all the supporting documentation, raw data, and analysis that underpin my work, serving as a reference for both myself and anyone interested in auditing my process. This structured documentation is also intended to provide clear insights into my development process and technical rigor for potential employers.

| File/Directory | Purpose and Content |
|---|---|
| `how-it-was-built.md` | A detailed narrative of the technical decisions, challenges, and solutions encountered during the token's development and deployment. |
| `on-chain-verification.md` | My systematic approach to verifying all project claims against live blockchain data, including any discrepancies or corrections identified during the process. |
| `overview.md` | A concise summary of the FOSS token's purpose, technical specifications, and overall project scope. |
| `programs.md` | An exhaustive list and explanation of all Solana programs and their respective Program IDs that were integral to the FOSS token ecosystem. |
| `resources.md` | A curated index of all external public links, categorized for easy reference, that were utilized or generated throughout this project. |
| `transactions.md` | A chronological log of every significant transaction related to the FOSS token, complete with direct links to Solana Explorer for independent verification. |
| `data/` | A directory containing structured data files, such as `token-spec.json`, which provides a programmatic overview of the token's technical attributes. |
| `raw/` | My collection of raw research data, including JSON exports, HTML captures of web pages, and API responses, used for in-depth analysis and verification. |

---

## My Reflection: Limitations and Future Considerations

It is crucial to present an honest assessment of this project. The FOSS token, as a learning artifact, currently possesses very low liquidity and is not integrated with major Solana swap aggregators like Jupiter. Its utility, beyond embodying an idea and serving as a learning tool, is limited. Furthermore, the token's metadata relies on the continued availability and persistence of IPFS gateways.

These limitations were openly acknowledged and documented throughout my research. The fundamental objective of this endeavor was never to create a financial product or a commercial venture. Instead, it was an intensive, practical exercise to demystify blockchain technology by engaging directly with its deployment, operation, and rigorous verification. This repository stands as a testament to that learning process, a personal record of my exploration into the decentralized world, and a transparent portfolio piece for my technical capabilities.

---

<div align="center">

Built by Lingadevaru H P

</div>

## References

[1] Solana Explorer. (n.d.). *Token Address: 64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin*. Retrieved from [https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[2] Orca. (n.d.). *Whirlpool: FOSS / SOL*. Retrieved from [https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)
[3] Solana Explorer. (n.d.). *Transaction: VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN*. Retrieved from [https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)
[4] Solana Explorer. (n.d.). *Transaction: 2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm*. Retrieved from [https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm](https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm)
[5] Solana Explorer. (n.d.). *Transaction: 4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq*. Retrieved from [https://explorer.solana.com/tx/4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq](https://explorer.solana.com/tx/4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq)
[6] Solana Explorer. (n.d.). *Transaction: 4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693ShJng4Be5Xkj4T*. Retrieved from [https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693ShJng4Be5Xkj4T](https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693ShJng4Be5Xkj4T)
[7] Solscan. (n.d.). *Token: 64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin*. Retrieved from [https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin](https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[8] IPFS. (n.d.). *Metadata JSON: QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n*. Retrieved from [https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n](https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n)
[9] IPFS. (n.d.). *Token Logo: QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf*. Retrieved from [https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf](https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf)
[10] GeckoTerminal. (n.d.). *Solana Pool: 3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2*. Retrieved from [https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2](https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)
[11] Solana Explorer. (n.d.). *Wallet Address: HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b*. Retrieved from [https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b](https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b)
