# Verification And Evidence

This document is the main verification record for the repository. It combines the most important facts, the corrections made during review, and the public references needed to verify the project independently.

## 1. Token Identity

| Field | Verified Value | Source |
|---|---|---|
| On-chain name | `Free Open Source Soft ` | IPFS metadata / on-chain metadata |
| Symbol | `FOSS` | IPFS metadata / on-chain metadata |
| Mint address | `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` | Token explorers / raw account info |
| Network | `Solana Mainnet` | Public explorer records |
| Token standard | SPL Token | Mint owner program |
| Program ID | `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` | Raw mint account info |
| Decimals | `6` | Raw mint account info |
| Total supply | `1,000,000,000` | Raw mint account info / supply response |

## 2. Authority Status

| Field | Verified Value | Why It Matters |
|---|---|---|
| Mint authority | `null` / revoked | No one can mint additional supply |
| Freeze authority | `null` / revoked | No one can freeze token accounts |

These two points are central to the project record because they show that the token supply is fixed and that token holders are not exposed to freeze control through the mint.

## 3. Metadata

| Field | Value |
|---|---|
| Metadata URI | `https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n` |
| Image URI | `https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf` |
| Metadata program | `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s` |

The saved raw files for this metadata are included in [`data/raw/`](../data/raw/).

## 4. Main Transactions

| # | Purpose | Signature | Date |
|---|---|---|---|
| 1 | Token creation | `VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN` | 2025-07-23 |
| 2 | Transfer | `3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g` | 2025-08-17 |
| 3 | Orca pool creation | `5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB` | 2025-10-21 |
| 4 | Liquidity provision | `2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm` | 2025-10-21 |
| 5 | Transfer | `4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq` | 2026-01-18 |
| 6 | Transfer | `4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T` | 2026-01-18 |

## 5. Creator / Fee Payer Trail

| Field | Value |
|---|---|
| Wallet | `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` |
| Public explorer | <https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b> |

The collected writeups consistently identify this wallet as the fee payer used across the main project transactions.

## 6. Orca Liquidity Pool

| Field | Value |
|---|---|
| Pool address | `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` |
| Pair | `FOSS / SOL` |
| Pool type | Orca Whirlpool |
| Pool page | <https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2> |

## 7. Corrections Kept Explicit

During the rewrite, I kept the corrected facts visible instead of silently replacing them:

| Topic | Correct Value | Note |
|---|---|---|
| Decimals | `6` | Earlier draft comparisons discussed a mismatch in one input snippet |
| Creator wallet reference | `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` | Treated in the research set as the creator / fee payer wallet |
| On-chain name | `Free Open Source Soft ` | Exact string kept as recorded |

## 8. Public Verification Links

### Token and mint

- <https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin>
- <https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin>
- <https://solana.fm/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin>

### Main transactions

- <https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN>
- <https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB>
- <https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm>
- <https://explorer.solana.com/tx/3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g>
- <https://explorer.solana.com/tx/4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq>
- <https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T>

### Pool and metadata

- <https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2>
- <https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2>
- <https://api.geckoterminal.com/api/v2/networks/solana/tokens/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin>
- <https://api.geckoterminal.com/api/v2/networks/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2>
- <https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n>
- <https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf>
