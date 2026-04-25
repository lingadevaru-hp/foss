# FOSS Token Project Documentation

This repository documents my `FOSS` token project on Solana and the research collected around it. I have organized it as a technical GitHub repository rather than an interview script or a social post draft.

The repository is meant to work in two layers:

- a clear front layer for recruiters, HR, and non-technical readers
- a deeper technical layer for anyone who wants to inspect the chain data, records, and raw files

## What This Repository Covers

- what I created
- what is verifiable on-chain
- which sources support each major claim
- what corrections were needed during verification
- the raw collected files used during the research

## Quick Project Facts

| Item | Value |
|---|---|
| Token symbol | `FOSS` |
| On-chain name | `Free Open Source Soft ` |
| Network | `Solana Mainnet` |
| Mint address | `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` |
| Token standard | SPL Token |
| Decimals | `6` |
| Total supply | `1,000,000,000` |
| Mint authority | Revoked |
| Freeze authority | Revoked |
| Orca pool | `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` |

## Repository Structure

- [`docs/project-summary.md`](docs/project-summary.md)  
  High-level explanation of the project, written in first person and readable without blockchain background.
- [`docs/verification-and-evidence.md`](docs/verification-and-evidence.md)  
  Main verification record with confirmed facts, corrections, public references, and transaction-level proof.
- [`docs/technical-record.md`](docs/technical-record.md)  
  Deeper technical explanation of the token, metadata, authorities, liquidity setup, and what I learned.
- [`docs/reference-links.md`](docs/reference-links.md)  
  Consolidated index of all public URLs and local raw files.
- [`data/source/original-project-note.txt`](data/source/original-project-note.txt)  
  Original source note preserved inside the repo.
- [`data/raw/`](data/raw/)  
  Raw JSON, HTML, metadata, and image files collected during the research.

## Why I Reworked The Repository

The earlier version had useful material, but it was spread across duplicate files and some of it was written in interview format. That is not the right shape for a public technical repository.

This version keeps the content, removes duplication, and presents the work as a documented project record.

## Main Public References

- Token: <https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin>
- Creation transaction: <https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN>
- Orca pool: <https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2>
- Metadata JSON: <https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n>

## Notes

- I have kept the wording direct and technical where needed.
- I have removed the interview-style and duplicate documentation.
- I have kept the raw collected material available in the repository instead of hiding it.
