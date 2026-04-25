# How It Was Built

I built this project through a no-code Solana launchpad flow, but I documented it at the instruction and transaction level so the technical steps are still clear.

## Step 1 — Token creation

Date: July 23, 2025  
Slot: `355,223,383`  
Time: `07:43:36 UTC`

I created the token in one atomic transaction. This is what happened inside that single transaction:

1. System Program allocated the mint account with 82 bytes.
2. `InitializeMint2` set the token to 6 decimals and assigned the initial mint authority.
3. Metaplex `Create Metadata Accounts v3` registered the name, symbol, and IPFS metadata URI on-chain.
4. An Associated Token Account was created for my creator wallet.
5. `MintTo` minted `1,000,000,000` tokens to the creator ATA.
6. `SetAuthority` set the mint authority to `null`, which is permanent and irreversible.
7. The launchpad `Buy` instruction immediately purchased `35,765.474485` FOSS.

Fee payer: `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b`  
Fee: `90,000` lamports

The important technical point here is that token creation, metadata registration, minting, authority revocation, and the initial launchpad buy all happened in one block with no exposed intermediate state.

## Step 2 — Orca Whirlpool pool creation

Date: October 21, 2025  
Slot: `374,850,194`  
Time: `14:13:04 UTC`

I later created an Orca Whirlpool pool for the token.

- `InitializePoolWithAdaptiveFee`
- Pool: `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2`
- Pair: `FOSS / Wrapped SOL`
- Tick arrays initialized

This step moved the project from just being a token on-chain to also being a token with a real liquidity pool on a Solana DEX.

## Step 3 — Liquidity provision

Date: October 21, 2025  
Time: `14:13:23 UTC`  
Delay from pool creation: `19 seconds`

I added liquidity to the pool immediately after it was created.

- Position NFT minted: `8RVfhVxFGUo5uJKcMZQUu6MD7FhLH8v8WFRaxsT3doxY` using Token-2022
- `IncreaseLiquidityV2`: `2.900653` FOSS + `0.0004` SOL added

This created the initial Orca liquidity position and tied the pool to a position NFT rather than a simple LP token account.

## What I Learned

This project taught me how Solana token infrastructure works beyond the surface level.

- I learned the SPL Token Program instruction set in practical terms: `InitializeMint2`, `MintTo`, `SetAuthority`, and `TransferChecked`.
- I learned that Metaplex metadata connects on-chain token accounts to off-chain IPFS data, which is how explorers and wallets show names, symbols, descriptions, and images.
- I learned that mint authority revocation is enforced by Solana consensus. It is not reversible and it is not just a promise from the creator.
- I learned that Orca Whirlpool uses concentrated liquidity, tick arrays, and position NFTs instead of a simple constant-product AMM design.
- I learned why atomic transactions matter. All seven creation steps happened in one block, so the token was never left in a partially configured state.
- I learned the difference between using a no-code launchpad and actually understanding what the BPF program executed under the hood.
