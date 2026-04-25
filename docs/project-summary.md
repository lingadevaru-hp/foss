# Project Summary

I created the `FOSS` token on Solana as a live technical project connected to the idea of Free and Open Source Software. This repository documents that project properly: what I created, how it was configured, what is verifiable, and where the supporting material is stored.

## What I Built

I created a Solana SPL token with the following core properties:

- symbol: `FOSS`
- on-chain name: `Free Open Source Soft `
- mint address: `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin`
- decimals: `6`
- fixed supply: `1,000,000,000`
- metadata stored through IPFS
- liquidity pool created on Orca for `FOSS / SOL`

## What The Project Was Meant To Represent

The original token description presents `FOSS` as a community-created token connected to:

- supporting Free and Open Source Software
- rewarding developers and contributors
- raising awareness about Linux, privacy, and open technologies

I have kept that original idea in this repository, but I have presented it as project documentation rather than promotion.

## What I Verified

From the chain data and collected source files in this repository, I was able to confirm that:

- the token exists on Solana mainnet
- the token uses the legacy SPL Token Program
- the token decimals are `6`
- the supply is fixed at `1,000,000,000`
- the mint authority is revoked
- the freeze authority is revoked
- metadata resolves through IPFS
- an Orca Whirlpool pool exists for the token
- the main creation, pool, liquidity, and later transfer transactions are traceable

## Why This Repository Matters

I wanted the repository to be understandable even if someone does not know Solana.

At the top level, a reader should be able to quickly understand:

- what I built
- what makes it technically real
- where to verify it

If they want more detail, the deeper documentation and raw files are available in the rest of the repository.

## Key Outcome

This project is not just a written explanation. It is a documented on-chain implementation with supporting records, corrected details, and preserved source material.
