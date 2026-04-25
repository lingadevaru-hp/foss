# FOSS Coin Blind Spots

## 1. What the SPL Token Program Actually Is

Short version: the SPL Token Program is Solana's standard on-chain program for fungible-token mints and token accounts.[^solana_create_mint][^solana_mint_tokens]

Technical detail: the FOSS mint is owned by `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA`, which is the legacy SPL Token Program, not Token-2022.[^mint_pages] That means the token uses the standard mint/account/authority model most Solana tokens use: a mint account defines supply rules and decimals, while separate token accounts hold balances for wallets and pools.[^solana_create_mint][^solana_create_token_account]

Project-specific implication: FOSS Coin is structurally conventional. The unusual part is not the mint format; it is the launch flow around it.[^creation_tx][^coinbook_token]

## 2. What Metaplex Is, and Whether FOSS Coin Uses It

Short version: Metaplex Token Metadata is the common Solana standard for attaching a name, symbol, URI, and other metadata to a token mint.[^metaplex_docs]

Technical detail: FOSS Coin does use Metaplex. Its metadata account is `48LMXvFKnmy5MLDPnBxD1mGwYLFcBbSToXQWv3PpHvu1`, and the creation transaction includes a Metaplex metadata creation instruction. That metadata stores the URI `https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n`, which resolves to the token description and logo URL.[^creation_tx][^metadata_account][^ipfs_metadata]

Project-specific implication: when someone asks "where does the token name/logo come from?", the answer is "Metaplex metadata on-chain, pointing to IPFS off-chain content."[^metadata_account][^ipfs_metadata]

## 3. What "Decimals" Means, and What FOSS Coin Uses

Short version: decimals determine how many base units equal one human-readable token.[^solana_create_mint]

Technical detail: FOSS Coin has `6` decimals, so `1 FOSS = 1,000,000` base units. That is why the raw supply is `1000000000000000` while the UI supply is `1,000,000,000`.[^mint_pages]

Project-specific implication: one of the local notes said `9` decimals, but the chain says `6`. In interviews, always use `6`.[^mint_pages][^gecko_token]

## 4. What Associated Token Accounts (ATAs) Are

Short version: an ATA is the standard token account a wallet uses for a given mint.[^solana_create_token_account]

Technical detail: the ATA program deterministically derives a wallet's standard token account for a given mint, then creates it if it does not exist. In the FOSS lifecycle, examples include:

- `3i4Dkdb...` for creator wallet `HLwsSk...`.[^creation_tx]
- `B2gZw2w...` for wallet `7pZqRi...`.[^transfer_two_tx]
- `DgwiF1j...` for wallet `DFQ8kw...`.[^transfer_one_tx]

Project-specific implication: if someone says "wallet X owns Y FOSS," the actual balance lives in a token account, not directly in the wallet address.[^solana_create_token_account]

## 5. How Orca Pools Work Technically

Short version: Orca Whirlpools use concentrated liquidity, vault accounts, and position NFTs to manage liquidity ranges.[^orca_docs]

Technical detail: FOSS Coin later got an Orca Whirlpool at `3Ub4oj...`. The pool stores one token vault for SOL (`8rWNAr...`) and one for FOSS (`2zZRzE...`). Liquidity was added through a separate transaction that minted a Token-2022 position NFT and then transferred `0.0004 SOL` and `2.900653 FOSS` into the vaults.[^pool_create_tx][^pool_liquidity_tx][^orca_pool_api]

Project-specific implication: the FOSS mint itself is not Token-2022, but the Orca position NFT is. That distinction matters in audits.[^pool_liquidity_tx]

## 6. What Revoked Mint Authority Means at the Program Level

Short version: it means the mint's `mintAuthority` field is `null`, so no account can call `MintTo` successfully anymore.[^solana_mint_tokens][^creation_tx]

Technical detail: the creation transaction includes `SetAuthority` with `authorityType = mintTokens` and `newAuthority = null`. The current mint account independently confirms `mintAuthority = null`.[^creation_tx][^mint_pages]

Project-specific implication: the fixed supply is real. Anyone can verify it without trusting a website or the creator.[^mint_pages][^creation_tx]

## 7. Token vs Coin: Correct Terminology

Short version: technically, FOSS is a token on Solana, not a native coin.[^mint_pages]

Technical detail: Solana's native coin is SOL. FOSS is an SPL token created by a program on top of Solana. Calling it "FOSS Coin" is fine for branding, but in technical documentation it is more precise to say "Solana SPL token" or "fungible token mint."[^mint_pages][^solana_create_mint]

Project-specific implication: on resumes and in interviews, say "I created and launched a Solana SPL token called FOSS Coin." That is both market-friendly and technically correct.[^mint_pages]

## 8. How FOSS Coin Compares Structurally to Other Solana Meme / Utility Tokens

Short version: it looks much more like a launchpad-issued community token than a custom protocol token.[^creation_tx][^coinbook_token]

Technical detail:

1. It uses the standard legacy SPL Token Program rather than Token-2022 extensions.[^mint_pages]
2. It has a Metaplex metadata account and IPFS-hosted metadata, which is normal for consumer-facing Solana tokens.[^metadata_account][^ipfs_metadata]
3. A single custom launchpad program handled creation and an initial buy flow, which resembles launchpad/bonding-curve products more than a hand-written bespoke protocol.[^creation_tx][^coinbook_token]
4. It later got a separate Orca Whirlpool, which is common when projects want a visible DEX listing.[^pool_create_tx][^pool_liquidity_tx]

Project-specific implication: if someone asks whether this is "like a meme coin," the honest answer is "structurally yes, in the sense that it is a standard launchpad-style SPL token with metadata and later DEX liquidity; the differentiator is the FOSS theme and documentation depth."[^coinbook_token][^ipfs_metadata]

## 9. Risks and Limitations of How This Token Was Created

### Naming inconsistency

The local notes say `Free Open Source Software`, but the live metadata resolves to `Free Open Source Soft` with trailing spaces. That mismatch is visible to auditors.[^metadata_account][^ipfs_metadata]

### Holder concentration

Nearly the full supply sits in `3QHP...`, which Coinbook labels as the token's `bondingCurve`. That may be platform reserve state rather than a normal wallet, but the concentration is still visually extreme and should be explained proactively.[^coinbook_token]

### Very low visible liquidity

The Orca pool exists, but the live balances are only `0.0004 SOL` and `2.900653 FOSS`, and Orca reports `tvlUsdc = 0` and `hasWarning = true`.[^orca_pool_api]

### Weak social metadata

Coinbook's embedded token record shows empty `website`, `telegram`, and `twitter` fields, so technical verification is strong but social verification is thin.[^coinbook_token]

### Revocation proof is bundled, not standalone

The good news is that mint-authority revocation happened immediately. The downside is that it happened inside the same creation transaction, so casual reviewers may miss it unless you point them to the exact `SetAuthority` instruction.[^creation_tx]

### Solscan anti-bot friction

Solscan is useful for manual viewing in a browser, but its raw HTML fetch path is protected by Cloudflare in CLI evidence gathering. That does not affect the chain truth, but it does affect automated reproducibility.[^solscan_token]

## 10. What You Should Be Ready to Explain

If you present this project publicly, be ready to explain all five of these without hesitation:

1. Why `6` decimals matters and why `9` was wrong in the early notes.[^mint_pages]
2. Why `mintAuthority = null` is the real fixed-supply proof.[^creation_tx][^mint_pages]
3. Why the top holder is a bonding-curve account and not necessarily the creator personally.[^coinbook_token]
4. Why the token was likely launched through Coinbook rather than a raw CLI-only workflow.[^creation_tx][^coinbook_token][^coinbook_home]
5. Why the Orca pool is real but currently very small.[^orca_pool_api][^gecko_pool]

[^mint_pages]: Solana Explorer mint page: https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin ; Solscan token page: https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^creation_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN
[^metadata_account]: Explorer metadata account: https://explorer.solana.com/address/48LMXvFKnmy5MLDPnBxD1mGwYLFcBbSToXQWv3PpHvu1
[^ipfs_metadata]: IPFS metadata JSON: https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n ; logo image: https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf
[^coinbook_token]: Coinbook token page: https://coinbook.fun/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^coinbook_home]: Coinbook homepage: https://coinbook.fun
[^transfer_two_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/3BmzHVUWbFinDcRK9gKK4kFovLattTP8k411Yke2amD3vhiLhzGr99RxpQFfSHCKNiu1JjEJK2KMVjxkJup5K29g
[^transfer_one_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/4CchR52nCrirsLaViyM2vfvqraPYfkWhnb54gkfAQ78AisQqKUM4geiZg82oHwVqNFWTjxF693Shjng4Be5Xkj4T
[^pool_create_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB
[^pool_liquidity_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm
[^orca_pool_api]: Orca pool API: https://api.orca.so/v2/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2
[^gecko_pool]: GeckoTerminal pool page/API: https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2 ; https://api.geckoterminal.com/api/v2/networks/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2
[^gecko_token]: GeckoTerminal token API: https://api.geckoterminal.com/api/v2/networks/solana/tokens/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^solscan_token]: Solscan token page: https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^solana_create_mint]: Official Solana docs, create mint: https://solana.com/docs/tokens/basics/create-mint
[^solana_create_token_account]: Official Solana docs, create token account: https://solana.com/docs/tokens/basics/create-token-account
[^solana_mint_tokens]: Official Solana docs, mint tokens: https://solana.com/docs/tokens/basics/mint-tokens
[^metaplex_docs]: Official Metaplex token metadata docs: https://developers.metaplex.com/token-metadata
[^orca_docs]: Official Orca Whirlpools docs: https://docs.orca.so/developers/examples/cpi
