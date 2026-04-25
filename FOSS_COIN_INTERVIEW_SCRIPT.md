# FOSS Coin — Interview Script

> A structured Q&A guide for the creator to use in interviews, portfolio reviews, or public presentations. Every answer is backed by on-chain evidence.

---

## Q1: "What is FOSS Coin?"

**Short answer:**
FOSS Coin is a Solana-based cryptocurrency token created to support and promote Free and Open Source Software. The ticker is $FOSS, and it's a fully decentralized, community-driven token with a fixed supply of 1 billion tokens.

**Detailed answer:**
FOSS Coin ($FOSS) is an SPL token on the Solana blockchain. SPL stands for Solana Program Library — it's the standard token format on Solana, similar to ERC-20 on Ethereum. The token has a fixed supply of 1 billion, and its mint authority has been permanently revoked, meaning nobody can ever create more. It's listed on Orca, which is Solana's leading decentralized exchange, so anyone can buy or sell it. The whole idea behind it is to create a token that represents the values of the open-source movement — transparency, freedom, and community funding.

**On-chain proof:** Mint address `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` — anyone can look this up on Solana Explorer.

---

## Q2: "Why did you create it?"

**Short answer:**
I wanted to explore how blockchain technology can be used to fund and reward open-source software development — the tools that power the internet but are often underfunded.

**Detailed answer:**
Most of the internet runs on free, open-source software — Linux, OpenSSL, Git, Python, and thousands of other projects maintained by volunteers or small teams. These projects rarely have sustainable funding models. I created FOSS Coin as an experiment: what if we could use a token to create a decentralized funding mechanism for FOSS projects? People could hold, transfer, or donate FOSS tokens to support the developers they admire. It's also a learning project — building and deploying a real token on Solana taught me more about blockchain, smart contracts, and decentralized finance than any tutorial could.

---

## Q3: "How did you technically create it? Walk me through the steps."

**Short answer:**
I used a no-code Solana token launchpad that handled everything in a single transaction — creating the token, setting up metadata on IPFS, minting 1 billion tokens, revoking the mint authority, and even executing an initial buy order.

**Step-by-step (plain language):**

1. **Set up a Solana wallet** — I used a wallet that could interact with Solana's mainnet. The wallet address is `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b`.

2. **Used a token launchpad** — Instead of writing code from scratch, I used a no-code launch platform (program ID: `HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr`). This platform bundles all the steps into one click.

3. **Configured token details** — I set the name ("Free Open Source Soft"), symbol (FOSS), decimals (6), and total supply (1 billion). I also uploaded a logo and description to IPFS — a decentralized file storage system.

4. **Token was created in one transaction** — On July 23, 2025, a single transaction on Solana did all of this:
   - Created the token mint account on Solana
   - Registered the metadata (name, symbol, image) via Metaplex
   - Minted all 1 billion tokens
   - **Immediately revoked the mint authority** — making the supply permanently fixed
   - Executed an initial purchase to distribute some tokens

5. **Added liquidity on Orca** — On October 21, 2025, I created a liquidity pool on Orca (a decentralized exchange). This pairs FOSS tokens with SOL so that anyone can trade the token. The pool uses Orca's "Whirlpool" technology, which is a concentrated liquidity model — meaning the liquidity is more efficient.

6. **All verified on-chain** — Every single step is recorded as a transaction on the Solana blockchain, and anyone can verify it using the transaction signatures I can provide.

---

## Q4: "What does 'revoking mint authority' mean, and why is it important?"

**Short answer:**
It means nobody can ever create more tokens. The supply is permanently capped at 1 billion. This is the single most important trust signal for any token.

**Detailed answer:**
When you create an SPL token on Solana, the token starts with a "mint authority" — essentially an admin key that can create new tokens at will. Think of it like a central bank that can print unlimited money. If the mint authority is active, the creator could mint billions more tokens and dilute everyone's holdings.

Revoking mint authority means setting that admin key to `null`. On Solana, this is a one-way operation — once it's done, it **cannot be undone**. The SPL Token Program at the consensus level will reject any attempt to mint more tokens. For FOSS Coin, I revoked the mint authority in the **same transaction** that created the token. So from the very first block, the supply was fixed at exactly 1 billion.

**Anyone can verify this** by looking up the token on Solana Explorer and checking that `mintAuthority` is `null`. The Solana RPC also confirms this: `mintAuthority: null`, `freezeAuthority: null`.

---

## Q5: "Is it live? Can I verify it right now?"

**Short answer:**
Yes, it's fully live on Solana mainnet. Here's how you can verify it yourself in 30 seconds.

**How to verify:**

1. **Go to Solana Explorer:** https://explorer.solana.com
2. **Search the mint address:** `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin`
3. **You'll see:**
   - Token name: Free Open Source Soft
   - Symbol: FOSS
   - Supply: 1,000,000,000,000,000 (raw) ÷ 10⁶ decimals = 1 billion
   - Mint Authority: **None** (revoked)
   - Freeze Authority: **None** (revoked)

4. **Check the creation transaction:** Click on the first transaction — you'll see it was created on July 23, 2025, and the mint authority was revoked in that same transaction.

5. **Check the DEX listing:** Go to Orca at https://www.orca.so and search for FOSS — you'll find the trading pool with SOL.

6. **Check the metadata:** The IPFS metadata is at https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n — it contains the full description and links to the logo.

---

## Q6: "What did you learn from this project?"

**Answer:**
This project taught me several things across different domains:

**Blockchain / Technical:**
- How Solana's SPL Token Program works at the instruction level — `InitializeMint2`, `MintTo`, `SetAuthority`, and how these map to actual program invocations.
- What Metaplex metadata is and how it connects on-chain token accounts to off-chain data (IPFS).
- How concentrated liquidity AMMs work — specifically Orca's Whirlpool model, which uses tick arrays and price ranges instead of the simpler constant-product model.
- The importance of atomic transactions — FOSS Coin's entire creation (mint, metadata, authority revocation, initial buy) happened in a single transaction, eliminating any risk of intermediate states.

**Trust / Governance:**
- How mint authority revocation is the foundational trust mechanism for any token. Without it, the token is essentially "unverifiable."
- How transparency on a blockchain means every action is publicly auditable — including mistakes, which makes accountability automatic.

**Practical:**
- The difference between using a no-code launchpad versus writing custom Solana programs — the launchpad abstracts complexity but you still need to understand what's happening under the hood.
- How to use Solana Explorer, Solscan, and RPC APIs to verify on-chain data.

---

## Q7: "What would you do differently?"

**Answer:**
Looking back with what I know now, there are several things I'd approach differently:

1. **Use Token Extensions (Token-2022) for the main token** — FOSS Coin uses the legacy SPL Token Program. Token-2022 adds features like transfer hooks, interest-bearing tokens, and confidential transfers. If I recreated it today, I'd use the modern standard.

2. **Get listed on Jupiter's curated token list** — FOSS Coin isn't currently on Jupiter's token registry, which means it doesn't show up in the most widely used Solana swap interface. Getting listed requires meeting certain criteria around liquidity and holder count.

3. **Add more initial liquidity** — The initial liquidity was quite small (about 0.0004 SOL and ~2.9 FOSS tokens). More liquidity would reduce slippage and make the token more usable for trading.

4. **Community distribution** — Rather than holding the majority of tokens in the creator wallet and a DEX pool, I'd design a more structured distribution plan — perhaps allocating portions to a community treasury, developer grants, or FOSS project donations.

5. **Build utility** — Right now, FOSS Coin is primarily a symbolic token. The next step would be building actual utility: a platform where FOSS projects can register, receive donations in FOSS tokens, and convert them to stablecoins or SOL.

6. **Documentation from day one** — This documentation process (creating the MASTER, EVIDENCE, and interview files) was done after the fact. In a future project, I'd document everything during the creation process for better traceability.

---

## Bonus: Quick Reference Card

| Question | Key Answer |
|---|---|
| Token name? | Free Open Source Soft (FOSS) |
| Chain? | Solana mainnet |
| Supply? | 1 billion, fixed, mint authority revoked |
| Created when? | July 23, 2025 |
| DEX? | Orca Whirlpool (FOSS/SOL pair) |
| Can I verify it? | Yes — search `64AcKtFg...MHAcoin` on Solana Explorer |
| Is it a security? | No — it's a community/experimental token with no investment promise |
| Who controls it? | Nobody — mint authority is revoked, supply is fixed |
