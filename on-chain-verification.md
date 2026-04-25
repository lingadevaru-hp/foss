# On-Chain Verification

This document is the verification layer of the repository. I organized it so that anyone can start with simple explorer links and then go deeper into RPC calls, program IDs, and the cross-verification record.

## Section 1 — Token mint account

| Source | Link |
|---|---|
| Solana Explorer | <https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin> |
| Solscan | <https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin> |
| Solana FM | <https://solana.fm/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin> |

What to check:

- `decimals = 6`
- `supply = 1000000000000000` raw
- `mintAuthority = null`
- `freezeAuthority = null`
- `owner = TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA`

## Section 2 — All 6 transactions in chronological order

| # | Date | Signature | Description | Link |
|---|---|---|---|---|
| 1 | 2025-07-23 07:43:36 UTC | `VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN` | Token creation — mint, metadata, 1B supply, mint authority revoked, initial buy | <https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN> |
| 2 | 2025-08-17 07:32:10 UTC | `3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g` | Transfer — 2 FOSS to external wallet | <https://explorer.solana.com/tx/3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g> |
| 3 | 2025-10-21 14:13:04 UTC | `5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB` | Orca Whirlpool pool creation | <https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB> |
| 4 | 2025-10-21 14:13:23 UTC | `2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm` | Liquidity provision, position NFT created | <https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm> |
| 5 | 2026-01-18 12:59:51 UTC | `4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq` | Airdrop — 1 FOSS | <https://explorer.solana.com/tx/4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq> |
| 6 | 2026-01-18 13:19:03 UTC | `4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T` | Airdrop — 1 FOSS | <https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T> |

## Section 3 — Creator wallet

Address: `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b`

- Solana Explorer: <https://explorer.solana.com/address/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b>
- Solscan: <https://solscan.io/account/HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b>

This wallet is the fee payer on all 6 transactions according to the collected project documentation.

## Section 4 — Orca pool

- Pool: `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2`
- Orca: <https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2>
- GeckoTerminal: <https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2>
- Solana Explorer: <https://explorer.solana.com/address/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2>
- Pool type: Whirlpool (concentrated liquidity)
- Program: `whirLbMiicVdio4qvUfM5KAg6Ct8VwpYzGff3uctyCc`

## Section 5 — Metadata

- IPFS metadata JSON: <https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n>
- Logo: <https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf>
- Metaplex program: `metaqbxxUerdq28cj1RbAWkYQm3ybzjb6a8bt518x1s`

## Section 6 — Launchpad program

Program ID: `HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr`

This is not pump.fun. The pump.fun program ID is `6EF8rrecthR5Dkzon8Nwu78hRvfCKubJ14M5uBEwF6P`. The launchpad used here is a separate BPF upgradeable loader program that handled token creation, metadata, minting, mint revocation, and the initial buy in a single atomic transaction.

## Section 7 — RPC verification commands

Endpoint: `https://api.mainnet-beta.solana.com`

### getAccountInfo

```bash
curl https://api.mainnet-beta.solana.com \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"getAccountInfo","params":["64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin",{"encoding":"jsonParsed"}]}'
```

### getSignaturesForAddress

```bash
curl https://api.mainnet-beta.solana.com \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"getSignaturesForAddress","params":["64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin",{"limit":10}]}'
```

### getTokenLargestAccounts

```bash
curl https://api.mainnet-beta.solana.com \
  -H "Content-Type: application/json" \
  -d '{"jsonrpc":"2.0","id":1,"method":"getTokenLargestAccounts","params":["64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin"]}'
```

## Section 8 — Cross-verification results

| # | Claim from input file | Status | Corrected value / on-chain reality | Source |
|---|---|---|---|---|
| 1 | Token Name: "FOSS Coin" | ⚠️ PARTIAL | On-chain name is `Free Open Source Soft `, while the descriptive text says FOSS Coin | IPFS Metadata |
| 2 | Symbol: FOSS | ✅ VERIFIED | On-chain symbol is `FOSS` | IPFS Metadata |
| 3 | Blockchain: Solana | ✅ VERIFIED | Token is on Solana mainnet and owned by the SPL Token Program | Solana RPC |
| 4 | Mint Address: `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` | ✅ VERIFIED | Confirmed through Solana RPC account lookups | Solana RPC |
| 5 | Token Standard: SPL Token | ✅ VERIFIED | Uses the legacy SPL Token Program, not Token-2022 | Solana RPC |
| 6 | Total Supply: 1,000,000,000 (fixed) | ✅ VERIFIED | Raw supply `1000000000000000` with 6 decimals equals `1,000,000,000` | Solana RPC |
| 7 | Mint Authority: Revoked | ✅ VERIFIED | `mintAuthority: null` | Solana RPC |
| 8 | DEX: Orca | ✅ VERIFIED | Orca Whirlpool pool exists at `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` | Orca |
| 9 | Decimals: 9 | ❌ INCORRECT | On-chain decimals are `6`, not `9` | Solana RPC vs input file |
| 10 | Logo URI is the IPFS image link | ✅ VERIFIED | IPFS image is reachable, PNG, about 2.5 MB | IPFS |
| 11 | Metadata URI is the IPFS JSON link | ✅ VERIFIED | Metadata resolves and contains valid token JSON | IPFS |
| 12 | Creation TX is `VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN` | ✅ VERIFIED | This is the creation transaction for the mint | Solana Explorer |
| 13 | Creator wallet is `48LMXvFKnmy5MLDPnBxD1mGwYLFcBbSToXQWv3PpHvu1` | ❌ INCORRECT | The actual fee payer / creator wallet used in the documentation is `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` | Creation TX |
| 14 | Orca Pool: `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` | ✅ VERIFIED | Pool exists on Orca Whirlpool for FOSS / SOL | Orca |
| 15 | GeckoTerminal tracking | ✅ VERIFIED | Token and pool are both present in GeckoTerminal | GeckoTerminal API |
| 16 | Tags: `utility-token` | ⚠️ UNVERIFIABLE | This appears in the input JSON but is not an on-chain field | Input file only |
| 17 | chainId: 101 | ✅ VERIFIED | `101` is the standard Solana mainnet chain ID in token list conventions | Token list standard |
| 18 | Description about FOSS Coin purpose | ✅ VERIFIED | The input description matches the IPFS metadata description | IPFS Metadata |
