# FOSS Coin Master Dossier

Snapshot date: 2026-04-14

## Executive Summary

FOSS Coin is a Solana SPL token with mint address `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin`.[^mint_pages] The mint is initialized with `6` decimals, a fixed UI supply of `1,000,000,000`, `mintAuthority = null`, and `freezeAuthority = null`, which means no further tokens can be minted and no freeze authority currently exists.[^mint_pages][^creation_tx]

The token's on-chain/off-chain metadata resolves to the name `Free Open Source Soft` and symbol `FOSS`; the IPFS metadata JSON describes it as a community-created token for supporting free and open source software.[^metadata_account][^ipfs_metadata] The first observed mint transaction on Solana finalized at `2025-07-23 13:56:56 UTC` and both minted the full supply and revoked mint authority in the same transaction.[^creation_tx]

Based on the transaction structure and Coinbook's own token page, the token was most likely created through a Coinbook launch flow rather than a raw Solana CLI sequence. This is an inference, not a literal on-chain label: the creation transaction invokes a custom program (`HtKnLjomtPrjJwyuQe6HApuEcnb76AUp3oG3nTpnQSAr`) with `Create` and `Buy` instructions, and Coinbook publicly serves a token page for the same mint showing the same creator wallet and bonding-curve account.[^creation_tx][^coinbook_token][^coinbook_home]

Later, an Orca Whirlpool pool at `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` was created for `FOSS / SOL` on `2025-10-21`.[^orca_pool_page][^orca_pool_api][^pool_create_tx] Orca's API currently reports `tokenBalanceA = 400000` base units of SOL (`0.0004 SOL`), `tokenBalanceB = 2900653` base units of FOSS (`2.900653 FOSS`), `tvlUsdc = 0`, and `hasWarning = true`.[^orca_pool_api]

## Token Specification

| Field | Verified Value | Notes | Source |
| --- | --- | --- | --- |
| Token name | `Free Open Source Soft` | On-chain and IPFS metadata include trailing spaces; the human-readable core name is `Free Open Source Soft` rather than `Free Open Source Software`. | [^metadata_account][^ipfs_metadata] |
| Symbol | `FOSS` | Matches metadata, Coinbook, Orca, and GeckoTerminal. | [^metadata_account][^coinbook_token][^orca_pool_api][^gecko_token] |
| Mint address | `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` | Solana mainnet mint. | [^mint_pages] |
| Chain | Solana mainnet-beta | Mainnet token mint. | [^mint_pages] |
| Standard | SPL Token (legacy Token Program) | Mint owner is `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA`, not Token-2022. | [^mint_pages][^creation_tx] |
| Decimals | `6` | The local source file's `9` value was wrong. | [^mint_pages][^gecko_token] |
| Total supply | `1,000,000,000` | Raw amount `1000000000000000` with 6 decimals. | [^mint_pages][^gecko_token] |
| Mint authority | `null` | Revoked in the creation transaction. | [^mint_pages][^creation_tx] |
| Freeze authority | `null` | No freeze authority present. | [^mint_pages] |
| Metadata account | `48LMXvFKnmy5MLDPnBxD1mGwYLFcBbSToXQWv3PpHvu1` | Metaplex metadata PDA/account found via live `getProgramAccounts`. | [^metadata_account] |
| Metadata update authority | `9yifUgUbxr1pULtb4VRvfu35gP1Cm2GgS9fbr4WzQN8D` | Present in the metadata account and used as mint authority in the creation transaction. | [^metadata_account][^creation_tx] |
| Metadata URI | `https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n` | Stored in the Metaplex metadata account. | [^metadata_account][^ipfs_metadata] |
| Logo/image URI | `https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf` | PNG logo referenced by the IPFS metadata JSON. | [^ipfs_metadata] |
| DEX evidence | Orca Whirlpool `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` | `FOSS / SOL` pool. | [^orca_pool_page][^orca_pool_api][^gecko_pool] |

## Creator Proof

The strongest creator evidence points to `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b`.[^creation_tx][^coinbook_token]

1. The first signer and fee payer in the original mint transaction is `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b`.[^creation_tx]
2. The same transaction creates the creator's associated token account `3i4DkdbqinJ7ULjndmegwSnSn5wVu2FDWRhJdd1feqVk` and transfers `35,765.474485 FOSS` into it.[^creation_tx]
3. Coinbook's public token page embeds the same wallet as `owner` for this mint.[^coinbook_token]
4. The later Orca pool creation and liquidity-add transactions are also signed and funded by the same wallet.[^pool_create_tx][^pool_liquidity_tx]

## Creation Timeline

| Time (UTC) | Signature / Record | What Happened | Source |
| --- | --- | --- | --- |
| 2025-07-23 13:56:28.324 | Coinbook token `createdAt` | Coinbook page timestamp for token creation. Secondary indexer evidence, not the canonical chain timestamp. | [^coinbook_token] |
| 2025-07-23 13:56:56 | `VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN` | Mint account created, mint initialized to 6 decimals, Metaplex metadata created, full supply minted, mint authority revoked, creator ATA created, and `35,765.474485 FOSS` transferred to creator. | [^creation_tx] |
| 2025-08-17 07:32:10 | `3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g` | ATA `B2gZw2...` created for wallet `7pZqRi...`; `2 FOSS` transferred from creator-controlled account `3i4Dkd...`. | [^transfer_two_tx] |
| 2025-10-21 14:13:04 | `5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB` | Orca Whirlpool `3Ub4oj...` initialized for `FOSS / SOL`; pool vaults `8rWNAr...` (SOL) and `2zZRzE...` (FOSS) created. | [^pool_create_tx] |
| 2025-10-21 14:13:23 | `2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm` | Orca position NFT minted and liquidity added: `2.900653 FOSS` plus `0.0004 SOL` moved into the pool vaults. | [^pool_liquidity_tx] |
| 2025-10-21 14:15:37 | GeckoTerminal `pool_created_at` | GeckoTerminal's indexed pool timestamp. This is later than the on-chain pool-init block time, so the on-chain transaction is the authoritative creation proof. | [^gecko_pool] |
| 2026-01-18 12:59:51 | `4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq` | ATA `EZ2Qbn...` created for wallet `8psNvW...`; no FOSS transfer observed in that transaction. | [^ata_only_tx] |
| 2026-01-18 13:19:03 | `4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T` | ATA `DgwiF1...` created for wallet `DFQ8kw...`; creator wallet transferred `1 FOSS`. | [^transfer_one_tx] |

## Current Status

### Holders and Distribution

At the time of the live snapshot used for this dossier, the mint has `5` current token accounts and `5` unique owners in the preserved live RPC capture.[^solscan_holders][^evidence_raw]

| Rank | Owner | Token Account | Balance (FOSS) | Interpretation | Source |
| --- | --- | --- | --- | --- | --- |
| 1 | `3QHPzriYswpwpVuEWYJCWeb35UEmGoz3Z2wkg5RVJSvr` | `eR38Chm7PX2yLJebhoXbUzsrUbRxtNfQzoKmxzZWQqT` | `999,964,234.525515` | Coinbook token page labels this account as the token's `bondingCurve`, so this is likely platform reserve state rather than a normal retail wallet. | [^coinbook_token][^solscan_holders] |
| 2 | `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b` | `3i4DkdbqinJ7ULjndmegwSnSn5wVu2FDWRhJdd1feqVk` | `35,759.573832` | Creator-controlled wallet based on signing history. | [^creation_tx][^solscan_holders] |
| 3 | `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` | `2zZRzEDuXXdiccxfSiJsKoAExjEtjzSJeXMJXbSQPpEC` | `2.900653` | Orca FOSS vault inside the `FOSS / SOL` pool. | [^orca_pool_api][^solscan_holders] |
| 4 | `7pZqRiKbrr1VV6REzo8Bkfdb9u5F2TNZiW6KpdWS5P4L` | `B2gZw2wAuAMGrjCdiRaJ1TABg39zvQqHc81iqkGtAtxL` | `2` | Small transferred balance created on 2025-08-17. | [^transfer_two_tx][^solscan_holders] |
| 5 | `DFQ8kwb67RNZkMf4oVkpgLg91JUzuQCMqVWpikN6BQkR` | `DgwiF1jPBdWp13gHBwb3jaQKNBuad7m9QYK6qoGK8Gv7` | `1` | Small transferred balance created on 2026-01-18. | [^transfer_one_tx][^solscan_holders] |

### Liquidity and Trading

The only verified public liquidity pool found for the mint is Orca Whirlpool `3Ub4oj...`, pairing FOSS with SOL.[^orca_pool_page][^orca_pool_api][^gecko_pool] Orca's live API says the pool is a `splashpool`, marks `hasWarning = true`, reports `tokenBalanceA = 400000` (`0.0004 SOL`) and `tokenBalanceB = 2900653` (`2.900653 FOSS`), and returns `tvlUsdc = 0` with null recent volume fields.[^orca_pool_api] GeckoTerminal also returns `reserve_in_usd = null` and null price/volume fields for the pool and no top pools for the token, which is consistent with an effectively inactive or dust-level market.[^gecko_pool][^gecko_token]

## Why Mint Authority Revocation Matters

Short version: revoking mint authority is the on-chain proof that nobody can create more FOSS from this mint anymore.[^creation_tx][^mint_pages]

Technical detail: the SPL Token Program stores a mint-authority field in the mint account. In the creation transaction, that field is explicitly changed with `SetAuthority` so that `newAuthority = null` for `authorityType = mintTokens`.[^creation_tx] The current live mint account still reports `mintAuthority = null`, which independently confirms the change stuck.[^mint_pages]

Non-technical meaning: the supply is no longer a promise or a website claim. The mint account itself says "no one has mint permission now," which is the strongest practical trust signal for a fixed-supply SPL token.[^mint_pages][^creation_tx]

## Technical Reconstruction

### Most Likely Tooling

Most likely creation platform: Coinbook.fun launch flow (inference, high confidence).[^creation_tx][^coinbook_token][^coinbook_home]

Why this is the best fit:

1. The first transaction does not look like a simple raw CLI flow. A custom program (`HtKnLj...`) wraps mint creation, metadata creation, full minting, authority revocation, and an immediate `Buy` path into one user-facing flow.[^creation_tx]
2. Coinbook's public token page serves the same mint and embeds the same creator wallet, the same bonding-curve account (`3QHP...`), and a creation time aligned with the first chain event.[^coinbook_token]
3. Coinbook's homepage markets the product as a way to "launch a tradable coin without needing to seed liquidity," which fits the custom `Create` + `Buy` pattern seen on-chain.[^coinbook_home]

### Reconstructed Build Steps

| Step | What Happened Technically | Programs Involved | Plain-English Meaning | Source |
| --- | --- | --- | --- | --- |
| 1. Wallet connected | Creator wallet `HLwsSk...` signed and paid for the first transaction. | System Program for fees; custom launchpad program. | The creator used a normal Solana wallet to start the token-creation flow. | [^creation_tx] |
| 2. Mint created | Mint account `64AcKt...` created and initialized with `6` decimals. | System Program; SPL Token Program (`Tokenkeg...`). | The token itself came into existence on Solana. | [^creation_tx][^mint_pages] |
| 3. Metadata attached | Metaplex metadata account `48LM...` created with name, symbol, and IPFS URI. | Metaplex Token Metadata Program. | The token got a public name, ticker, description, and logo link. | [^creation_tx][^metadata_account][^ipfs_metadata] |
| 4. Full supply minted | `1,000,000,000` FOSS were minted as `1000000000000000` base units. | SPL Token Program `MintTo`. | All tokens were created at once. | [^creation_tx][^mint_pages] |
| 5. Mint authority revoked | `SetAuthority` changed `mintTokens` authority to `null`. | SPL Token Program `SetAuthority`. | Nobody can increase supply anymore. | [^creation_tx][^mint_pages] |
| 6. Creator received an initial allocation | ATA `3i4D...` created for `HLwsSk...`; `35,765.474485 FOSS` transferred into it during the custom `Buy` path. | Launchpad program; Associated Token Account Program; SPL Token Program. | The creator finished the launch flow holding a small visible token balance. | [^creation_tx] |
| 7. Small external transfers happened | Additional ATAs were created and small amounts (`2`, then `1`) were transferred out later. | ATA Program; SPL Token Program. | The token was later distributed in tiny amounts to two extra wallets. | [^transfer_two_tx][^transfer_one_tx] |
| 8. Orca pool created | Whirlpool `3Ub4...` plus vaults `8rWN...` and `2zZR...` were initialized. | Orca Whirlpools Program. | The token later got a DEX pool. | [^pool_create_tx][^orca_pool_api] |
| 9. Liquidity added | Orca position NFT minted; `2.900653 FOSS` and `0.0004 SOL` deposited into pool vaults. | Orca Whirlpools; Token-2022 for position NFT; SPL Token Program for actual FOSS/SOL transfers. | Trading infrastructure was added, but with extremely small liquidity. | [^pool_liquidity_tx][^orca_pool_api] |

### What This Means About the Stack

FOSS Coin itself is not a Token-2022 mint. The token mint uses the legacy SPL Token Program (`Tokenkeg...`).[^mint_pages] The only Token-2022 activity in the observed lifecycle is the Orca position NFT minted when liquidity was added; that NFT is separate from the FOSS token itself.[^pool_liquidity_tx]

## Cross-Verification of the Input Text File

Source file audited: `Free Open Source Soft.txt`

| Input Claim | Status | Corrected / Verified Reading | Source |
| --- | --- | --- | --- |
| `FOSS Coin is a community-created token built to support and promote Free and Open Source Software (FOSS).` | VERIFIED | Matches the IPFS metadata description and Coinbook token page. This is a project description, not a protocol-enforced function. | [^ipfs_metadata][^coinbook_token] |
| `It can be used to: Donate to FOSS projects / Reward developers and contributors / Raise awareness about digital privacy, Linux, and open technologies` | VERIFIED | Verified as the published description in metadata. Not verified as an on-chain permission set. | [^ipfs_metadata][^coinbook_token] |
| `This is not an official project by GNU, Linux.org, or the Free Software Foundation.` | UNVERIFIABLE | This is a narrative/legal statement, not something the chain can prove. | [^ipfs_metadata] |
| `$FOSS is an independent grassroots effort by passionate individuals...` | UNVERIFIABLE | Narrative claim; not provable from on-chain evidence alone. | [^ipfs_metadata] |
| `Your token is now live on Solana` | VERIFIED | The mint exists on Solana mainnet and has active token accounts. | [^mint_pages] |
| Mint address `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` | VERIFIED | Exact mint matches the live SPL mint account. | [^mint_pages] |
| JSON `symbol: "FOSS"` | VERIFIED | Correct. | [^metadata_account][^gecko_token] |
| JSON `name: "Free Open Source Software"` | INCORRECT | The observed metadata name is `Free Open Source Soft` (with trailing spaces in raw metadata), not `Free Open Source Software`. | [^metadata_account][^ipfs_metadata] |
| JSON `decimals: 9` | INCORRECT | Live mint account and indexers show `6` decimals. | [^mint_pages][^gecko_token] |
| JSON `logoURI: https://ipfs.io/ipfs/QmZj...` | VERIFIED | Correct; the IPFS metadata JSON points to that image. | [^ipfs_metadata] |
| JSON `tags: ["utility-token"]` | UNVERIFIABLE | No on-chain tag standard proves this; this looks like an off-chain classification only. | [^mint_pages][^ipfs_metadata] |
| Solscan tx `VQT5...` | VERIFIED | This is the original mint creation transaction and also the mint-authority revocation transaction. | [^creation_tx] |
| Metadata account `48LM...` | VERIFIED | Correct Metaplex metadata account. | [^metadata_account] |
| Orca pool `3Ub4...` | VERIFIED | Correct Orca Whirlpool address. | [^orca_pool_page][^orca_pool_api] |
| GeckoTerminal token endpoint | VERIFIED | Endpoint resolves and reports the token. | [^gecko_token] |
| GeckoTerminal pool endpoint | VERIFIED | Endpoint resolves and reports the FOSS/SOL pool. | [^gecko_pool] |
| IPFS metadata URI `QmNaa...` | VERIFIED | Correct metadata JSON URI. | [^ipfs_metadata] |
| IPFS logo URI `QmZj...` | VERIFIED | Correct logo URI. | [^ipfs_metadata] |

## Evidence Notes and Limitations

1. Solscan's public HTML response is protected by Cloudflare when fetched non-interactively, so the dossier uses live Solana RPC, Coinbook, Orca, GeckoTerminal, IPFS, and direct explorer URLs as the primary data sources. The raw Cloudflare challenge HTML is still preserved in `codex/raw/solscan_mint_page.html` for completeness.[^solscan_token]
2. GeckoTerminal and Orca indexer timestamps can differ slightly from block times. Where there was a conflict, the signed on-chain transaction block time was treated as authoritative.[^pool_create_tx][^gecko_pool]
3. The "likely created via Coinbook" conclusion is evidence-based inference, not a chain-labeled fact. It is strong because the Coinbook page embeds the same mint, creator wallet, and bonding-curve account that appear in the launch transaction and current distribution.[^creation_tx][^coinbook_token][^coinbook_home]

[^mint_pages]: Solana Explorer mint page: https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin ; Solscan token page: https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^creation_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN ; Solscan transaction: https://solscan.io/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN
[^metadata_account]: Solana Explorer metadata account: https://explorer.solana.com/address/48LMXvFKnmy5MLDPnBxD1mGwYLFcBbSToXQWv3PpHvu1 ; Solscan metadata account: https://solscan.io/account/48LMXvFKnmy5MLDPnBxD1mGwYLFcBbSToXQWv3PpHvu1
[^ipfs_metadata]: IPFS metadata JSON: https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n ; logo image: https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf
[^coinbook_token]: Coinbook token page: https://coinbook.fun/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^coinbook_home]: Coinbook homepage: https://coinbook.fun
[^transfer_two_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g
[^pool_create_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB
[^pool_liquidity_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm
[^ata_only_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/4Xu9TWvWCoxnye7ZTr1kswaMnyLUiVoWZnccu1dASuMMMtz6aJd6AAtpxiAPwULa3Kp6JUkxAMEGsjcNrnVtTREq
[^transfer_one_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T
[^orca_pool_page]: Orca pool page: https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2
[^orca_pool_api]: Orca pool API: https://api.orca.so/v2/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2
[^gecko_token]: GeckoTerminal token API: https://api.geckoterminal.com/api/v2/networks/solana/tokens/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^gecko_pool]: GeckoTerminal pool page/API: https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2 ; https://api.geckoterminal.com/api/v2/networks/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2
[^solscan_holders]: Solscan token page for manual holder verification: https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^evidence_raw]: Raw current token-account snapshot preserved locally: [foss_token_accounts.json](</home/libre/Documents/foss project/codex/raw/foss_token_accounts.json>)
[^solscan_token]: Solscan token page: https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
