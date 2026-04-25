# Technical Record

This document keeps the deeper technical context for the repository. It is meant for readers who want more than the top-level summary.

## 1. Token Configuration

The token is documented as a Solana SPL token using the legacy Token Program rather than Token-2022. The main recorded configuration is:

- mint address: `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin`
- decimals: `6`
- total supply: `1,000,000,000`
- mint authority: revoked
- freeze authority: revoked

From a trust and verification point of view, the authority status matters most because it means the token supply is presented as fixed and non-freezable.

## 2. Metadata Layer

The token metadata uses the Metaplex metadata flow with a URI pointing to IPFS.

Relevant items:

- metadata program: `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s`
- metadata JSON: `QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n`
- logo image: `QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf`

This gives the token its readable name, symbol, description, and image in public explorers and wallet interfaces.

## 3. Creation Flow

The collected research describes the creation flow as a launchpad-based Solana transaction that handled several actions together:

- token mint creation
- token initialization
- metadata creation
- token minting
- authority revocation
- initial buy / launchpad activity

The main creation transaction recorded for this process is:

- `VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN`

## 4. Liquidity Setup

The project record also includes a later Orca Whirlpool setup:

- pool creation transaction: `5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB`
- liquidity transaction: `2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm`
- pool address: `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2`

This is important because it shows that the project documentation is not limited to token creation alone. It also covers the later market/liquidity setup.

## 5. Program References

| Program | Program ID | Role |
|---|---|---|
| SPL Token Program | `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` | Fungible token operations |
| SPL Token-2022 | `TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb` | Mentioned in relation to position NFT usage |
| Associated Token Account Program | `ATokenGPvbdGVxr1b2hvZbsiqW5xWH25efTNsLJA8knL` | Token account creation |
| Metaplex Metadata | `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s` | Metadata layer |
| Orca Whirlpool | `whirLbMiicVdio4qvUfM5KAg6Ct8VwpYzGff3uctyCc` | Liquidity pool |
| Launchpad program | `HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr` | Recorded launchpad flow |

## 6. Notes On Accuracy

This repository intentionally keeps the technical wording tighter than the earlier drafts.

The main cleanup decisions were:

- remove duplicate documents
- remove interview-style presentation
- keep the exact recorded on-chain values
- keep corrected details visible
- separate summary content from deep technical content

## 7. Limitations

The repository documents what was researched and collected. It does not claim more than that.

Important limits:

- low liquidity does not equal strong market depth
- token existence does not prove community adoption
- IPFS metadata availability depends on access to the stored content
- the launchpad behavior is documented through recorded outputs, not by reverse engineering the full program source
