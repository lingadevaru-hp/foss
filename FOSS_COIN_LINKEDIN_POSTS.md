# LinkedIn Post — FOSS Coin Student Project

> Pick one. All are written as a **student showcasing a college project** — not a product launch.

---

## Option 1 — Detailed (Recommended)

**I'm a college student. Here's a blockchain project I built and shipped on a live network.**

For a personal project, I created and deployed a token on Solana mainnet — from scratch, end to end.

**Project: FOSS Coin ($FOSS) — SPL Token on Solana**

What I technically did:
▸ Created a token mint on Solana mainnet (SPL Token Program)
▸ Set up on-chain metadata via Metaplex — name, symbol, logo stored on IPFS
▸ Revoked mint authority at creation — supply is permanently fixed at 1 billion (enforced by Solana's consensus, not a promise)
▸ Deployed a liquidity pool on Orca using their Whirlpool AMM (concentrated liquidity model)
▸ Verified every single transaction on Solana Explorer — all public, anyone can audit

**What I learned doing this:**

→ How Solana's Token Program works at the instruction level (`InitializeMint2`, `MintTo`, `SetAuthority`, `TransferChecked`)
→ What mint authority revocation means at the protocol level — it's irreversible, enforced by the program, not by trust
→ How Metaplex connects on-chain accounts to off-chain metadata (IPFS)
→ How AMM liquidity pools work — Orca's Whirlpool uses concentrated liquidity with tick arrays and position NFTs
→ How to read raw blockchain transactions, trace program invocations, and verify claims against live chain data
→ The difference between using a no-code launchpad vs understanding what it actually does under the hood

**Technologies / Skills demonstrated:**
Solana blockchain · SPL Token Program · Metaplex · IPFS · Orca Whirlpool (AMM) · On-chain data analysis · Transaction verification · Decentralized finance concepts

**This is not a product, startup, or investment.**
It's a student project — built to learn how blockchains work at the protocol level, not just read about them.

Every claim is verifiable on-chain. Recruiters, teachers, or anyone curious — you don't have to take my word for it. You can check it yourself:

🔗 Token: https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
🔗 Creation TX: https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN
🔗 Orca Pool: https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2

Full project documentation: https://github.com/yourusername/foss-coin (add your repo link)

#StudentProject #Solana #Blockchain #CollegeProject #Web3 #OpenSource #LearningByDoing

---

## Option 2 — Short & Clean

**Student project: I deployed a token on Solana mainnet and documented everything.**

As a college student learning blockchain technology, I wanted to go beyond theory and actually build something live.

So I created FOSS Coin — an SPL token on Solana.

**What the project covers:**

✅ Token creation on Solana (mint account, 6 decimals, 1B supply)
✅ Metaplex metadata (name, symbol, image on IPFS)
✅ Mint authority revoked at creation — supply permanently fixed
✅ Orca Whirlpool liquidity pool deployment (concentrated liquidity AMM)
✅ Full transaction-level verification on Solana Explorer

**Skills I gained:**
Solana SPL Token Program · Metaplex metadata · IPFS · AMM/DEX mechanics · On-chain data analysis · Blockchain transaction forensics

This isn't a startup. It's a learning project — built to understand how tokens actually work at the protocol level.

Everything is public and verifiable:
🔗 https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin

#StudentProject #Solana #Blockchain #CollegeProject #LearningByDoing

---

## Option 3 — "What I Built" Format

**As a college student, I wanted to understand blockchain beyond textbooks. So I built this:**

**Project Name:** FOSS Coin ($FOSS)
**Blockchain:** Solana Mainnet (live)
**Type:** SPL Token + DEX Liquidity Pool
**Status:** Deployed, verified, documented

**What it does:**
An experimental token created to learn how Solana's token infrastructure works at the protocol level.

**What I technically implemented:**

| Step | What happened | Program used |
|---|---|---|
| Token mint | Created the token account with 6 decimals, 1B supply | SPL Token Program |
| Metadata | Registered name, symbol, image on-chain | Metaplex Token Metadata |
| Storage | Uploaded logo and description to IPFS | IPFS (decentralized storage) |
| Mint revocation | Set mint authority to null — irreversible | SPL Token Program (SetAuthority) |
| DEX listing | Created Orca Whirlpool pool (FOSS/SOL pair) | Orca Whirlpool Program |
| Liquidity | Added initial liquidity with position NFT | Orca + Token-2022 extensions |

**What I learned:**
- How Solana's Token Program manages tokens at the instruction level
- Why mint authority revocation is a cryptographic guarantee, not a social promise
- How concentrated liquidity AMMs differ from constant-product AMMs
- How to read, trace, and verify raw blockchain transactions
- The difference between a no-code tool and understanding what it does under the hood

**Technologies:** Solana · SPL Token · Metaplex · IPFS · Orca Whirlpool · AMM · On-chain Analysis

**This is a student project.** Not a product, not an investment, not a startup.
Built for learning. Everything is publicly verifiable on-chain.

🔗 Token: https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
🔗 Creation TX: https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN

#StudentProject #Solana #Blockchain #CollegeProject #Web3 #OpenSource #LearningByDoing

---

## Before You Post

1. **Add a screenshot** — Open your token on Solana Explorer and take a screenshot showing:
   - Token name: Free Open Source Soft
   - Supply: 1,000,000,000
   - Mint Authority: ❌ None (this is the trust signal)
   - This visual alone proves you deployed something real

2. **Add a GitHub repo** (optional but recommended):
   - Put all 4 documentation files + this post in a repo
   - Recruiters who click through will see thorough documentation
   - `github.com/yourusername/foss-coin-project`

3. **Pin to your profile** — After posting, click "..." → "Pin to top" so it's the first thing on your profile.

4. **Add to Featured section** — Go to your profile → "Add profile section" → "Featured" → Add the post.

5. **Tag your college** (optional) — Helps teachers and classmates see it. They may share it further.

6. **Best time** — Tuesday–Thursday, 8–10 AM or 12–2 PM.

7. **Replace `yourusername`** in any GitHub links with your actual GitHub username before posting.
