# FOSS Coin Interview Script

## 1. What is FOSS Coin?

Suggested answer:

FOSS Coin is a fixed-supply SPL token I launched on Solana to represent a community effort around free and open source software. The token's published metadata describes it as a community-created asset for supporting FOSS projects, rewarding contributors, and promoting open technologies.[^ipfs_metadata][^coinbook_token]

If someone wants the technical summary: it is the mint `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin`, it uses the legacy SPL Token Program, it has `6` decimals, and its total supply is permanently fixed at `1,000,000,000` because the mint authority was revoked on-chain.[^mint_pages][^creation_tx]

## 2. Why did you create it?

Suggested answer:

I created it as a Web3 experiment around the values of free and open source software. The public metadata I published says the goal was to support FOSS projects, reward contributors, and raise awareness around privacy, Linux, and open technology.[^ipfs_metadata][^coinbook_token]

If you want to stay strictly factual in an interview, say this: "That purpose statement is what I published in the token metadata and it is publicly verifiable on IPFS and on the token's public pages."[^ipfs_metadata][^coinbook_token]

## 3. How did you technically create it?

Suggested answer:

The evidence suggests I used a launchpad-style flow, most likely Coinbook, rather than only typing raw Solana CLI commands. The reason I say that is the first transaction invokes a custom program that bundles mint creation, metadata creation, minting, mint-authority revocation, and an initial buy into one flow, and Coinbook's public token page embeds the same mint, creator wallet, and bonding-curve account that appear on-chain.[^creation_tx][^coinbook_token][^coinbook_home]

Plain-language step-by-step:

1. I connected a Solana wallet, and the creator wallet that signed the launch is `HLwsSkx8v7z25N6aZo6rjAywJ1YfjjwhpCA7fCD1Db2b`.[^creation_tx]
2. The mint account was created and initialized with `6` decimals.[^creation_tx][^mint_pages]
3. A Metaplex metadata account was created and pointed to an IPFS JSON file containing the name, symbol, description, and logo.[^creation_tx][^metadata_account][^ipfs_metadata]
4. The full supply was minted in one shot.[^creation_tx][^mint_pages]
5. The mint authority was revoked in the same transaction, so no more supply can ever be created.[^creation_tx][^mint_pages]
6. Later, I created an Orca Whirlpool pool and added a small amount of FOSS and SOL as liquidity.[^pool_create_tx][^pool_liquidity_tx][^orca_pool_api]

## 4. What does revoking mint authority mean?

Suggested answer:

It means the token contract no longer has an account with permission to mint more tokens. On Solana, that is not a social promise; it is a field inside the mint account. In the creation transaction, that field was set to `null`, and the live mint account still shows `mintAuthority = null` today.[^creation_tx][^mint_pages]

The simple version is: the supply is fixed by the chain, not just by me saying it is fixed.[^creation_tx][^mint_pages]

## 5. Is it live? Can I verify it?

Suggested answer:

Yes. Anyone can verify the mint on Solana Explorer or Solscan, inspect the metadata account, open the creation transaction, and look at the Orca pool and IPFS metadata directly.[^mint_pages][^metadata_account][^creation_tx][^orca_pool_page][^ipfs_metadata]

If you want to hand them a short proof list, use:

1. Mint: `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin`.[^mint_pages]
2. Creation and revocation tx: `VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN`.[^creation_tx]
3. Metadata account: `48LMXvFKnmy5MLDPnBxD1mGwYLFcBbSToXQWv3PpHvu1`.[^metadata_account]
4. Orca pool: `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2`.[^orca_pool_page][^orca_pool_api]

## 6. What did you learn from this project?

Suggested answer:

I learned the difference between the token mint itself, token accounts that hold balances, metadata accounts that store identity, and DEX infrastructure like Orca Whirlpool vaults and position NFTs.[^mint_pages][^metadata_account][^orca_pool_api]

I also learned that "fixed supply" needs proof. It is not enough to say the supply is fixed. You need to show the `SetAuthority` instruction and the current mint account state.[^creation_tx][^mint_pages]

Another strong talking point is that I learned how much public blockchain evidence you can reconstruct after the fact: creator wallet, exact timestamps, mint parameters, metadata URI, holder distribution, and DEX pool state are all traceable if you know how to read the chain.[^creation_tx][^mint_pages][^metadata_account][^orca_pool_api]

## 7. What would you do differently?

Suggested answer:

I would make the branding and metadata cleaner from day one. The on-chain/off-chain name ended up as `Free Open Source Soft`, while some local notes say `Free Open Source Software`, and that inconsistency is visible during audits.[^metadata_account][^ipfs_metadata]

I would also publish a more explicit project site and documentation earlier. The metadata currently has no website, Telegram, or Twitter fields in the Coinbook token record, which makes the project harder to verify socially even though the on-chain proof is fine.[^coinbook_token]

Finally, I would think harder about liquidity strategy. The verified Orca pool exists, but its live balances are extremely small, so it functions more as proof-of-deployment than as a deep market.[^orca_pool_api][^gecko_pool]

## 8. Was this made with Solana CLI or a no-code tool?

Suggested answer:

The strongest evidence points to a launchpad flow, probably Coinbook. I say "probably" because the chain does not literally print the website name in the first instruction, but the pattern is clear: custom launchpad program calls, a bundled `Create` + `Buy` flow, a matching Coinbook token page, and a Coinbook-labeled bonding curve account that still holds almost the full supply.[^creation_tx][^coinbook_token][^coinbook_home]

If pressed, say this exactly:

"I would describe it as a launchpad-assisted SPL token deployment, later extended with a separate Orca pool. I would not present it as a bare Solana CLI mint unless I had the original local command history."[^creation_tx][^coinbook_token][^pool_create_tx][^pool_liquidity_tx]

[^mint_pages]: Solana Explorer mint page: https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin ; Solscan token page: https://solscan.io/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^creation_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN ; Solscan transaction: https://solscan.io/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN
[^metadata_account]: Explorer metadata account: https://explorer.solana.com/address/48LMXvFKnmy5MLDPnBxD1mGwYLFcBbSToXQWv3PpHvu1
[^ipfs_metadata]: IPFS metadata JSON: https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n ; logo image: https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf
[^coinbook_token]: Coinbook token page: https://coinbook.fun/token/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin
[^coinbook_home]: Coinbook homepage: https://coinbook.fun
[^pool_create_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/5obapSAxEfqkkQCJaYxCkLZb8dub5vthyk2eBqN56akHmAtVVC12nBbsYQXmbPZgQWexUArRnJrsk3dt86hXtWiB
[^pool_liquidity_tx]: Solana Explorer transaction: https://explorer.solana.com/tx/2xR9TXLpkjZPTd5BjCS58Xzwqw7X2wCLDZW2ZsWFnbH7sEkvxToxHKTDNA6r9Dto9rQLS7b5XXe5GhkJQDFmJEGm
[^orca_pool_page]: Orca pool page: https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2
[^orca_pool_api]: Orca pool API: https://api.orca.so/v2/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2
[^gecko_pool]: GeckoTerminal pool page/API: https://www.geckoterminal.com/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2 ; https://api.geckoterminal.com/api/v2/networks/solana/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2
