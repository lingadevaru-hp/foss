# Overview

I created `FOSS` as an SPL token on Solana mainnet with a fixed supply and a public on-chain record. The token is live, the mint authority is revoked, and liquidity was later added on Orca DEX through an Orca Whirlpool pool.

The idea behind this project was to use blockchain as a real technical medium to represent support for Free and Open Source Software. I built it as a learning project, but I also wanted the project itself to reflect open verifiability, public records, and transparent technical evidence.


## Quick Verification Links

- Mint: <https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin>
- Creation transaction: <https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN>
- Orca pool: <https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2>
- Full resource index: [resources.md](resources.md)

## Token Specification

| Field | Value |
|---|---|
| Name | `Free Open Source Soft ` |
| Symbol | `FOSS` |
| Mint address | `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` |
| Decimals | `6` |
| Total supply | `1,000,000,000` |
| Mint authority | `null` / revoked |
| Freeze authority | `null` / revoked |
| Token program | `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` |
| Metadata program | `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s` |
| DEX | Orca Whirlpool |
| Pool address | `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` |

## IPFS Metadata JSON

The metadata JSON below is the verified project metadata used for the token:

```json
{
  "name": "Free Open Source Soft ",
  "symbol": "FOSS",
  "description": "FOSS Coin is a community-created token built to support and promote Free and Open Source Software (FOSS).\n\nIt can be used to:\n- Donate to FOSS projects\n- Reward developers and contributors\n- Raise awareness about digital privacy, Linux, and open technologies\n\nThis is not an official project by GNU, Linux.org, or the Free Software Foundation. $FOSS is an independent grassroots effort by passionate individuals who believe in the freedom to build, share, and innovate without restrictions.\n\nBy holding or using FOSS Coin, you become part of a decentralized movement to fund the tools that power the internet — freely and ethically.",
  "image": "https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf"
}
```

## Logo

- IPFS hash: `QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf`
- Format: PNG
- Size: about 2.5 MB
- Status: HTTP 200 confirmed

## Supply Distribution

| Holder / destination | Approx. amount | Percentage |
|---|---|---|
| Creator ATA | ~35,759 FOSS | ~0.0036% |
| Orca Whirlpool vault | ~999,964,234 FOSS | ~99.9964% |
| Airdrops and small transfers | <100 FOSS | <0.001% |

The recorded distribution shows that almost the entire supply ended up in the Orca Whirlpool vault, with a much smaller amount remaining in the creator wallet and very small amounts transferred out later.
