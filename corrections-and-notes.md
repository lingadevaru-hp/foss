# Corrections And Notes

I kept the corrections explicit because the point of this repository is to show the project clearly, not to hide mismatches from the original notes.

## Correction 1 — Decimals

The original notes included `decimals = 9`. On-chain reality is `6`.

Raw supply math:

`1,000,000,000,000,000 ÷ 10^6 = 1,000,000,000 FOSS`

That math is important because the token only makes sense as a 1 billion supply token when the decimals are treated correctly.

## Correction 2 — Creator wallet

The original notes listed `48LMXvFKnmy5MLDPnBxD1mGwYLFcBbSToXQWv3PpHvu1` as the creator wallet. That address is a launchpad program-derived account, not the fee payer.

The actual fee payer used throughout the project documentation is:

`HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b`

## Correction 3 — Token name

The on-chain name is `Free Open Source Soft `.

It includes a trailing space and it is truncated. It is not `Free Open Source Software`.

## Known Limitations

I also kept the project limitations visible instead of pretending the token is stronger than it is.

- Very low initial liquidity, about `0.0004 SOL + ~2.9 FOSS`, creates high slippage risk.
- The token was not listed on Jupiter token registry as of April 2026.
- About `99.996%` of the supply sits in the Orca pool vault, so the distribution is highly concentrated.
- The metadata depends on IPFS availability and is not pinned to Arweave in the documented setup.
- I still hold the Orca position NFT, which means the pool liquidity can be withdrawn.
- The token has no utility beyond symbolic representation in its current state.
- There are only 6 on-chain transactions in the project history, with the last recorded activity on January 18, 2026.
- The token uses the legacy Token Program instead of Token-2022, so it does not have transfer hooks or other newer extensions.

## What I Would Do Differently

If I built this again, I would raise the technical quality and the usefulness of the token from day one.

- I would use Token-2022 for the main token instead of the legacy Token Program.
- I would build utility around it, especially a platform where FOSS projects could register and receive donations.
- I would add meaningful liquidity from day one so the token is not only live, but also practically tradable.
- I would design a clearer supply distribution with a community treasury and developer grant allocation.
- I would get the token listed on Jupiter.
- I would document everything during the build process instead of reconstructing the record afterward.
