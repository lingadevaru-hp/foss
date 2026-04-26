<div align="center">

<img src="./foss-logo.png" alt="FOSS Token Logo" width="140" style="border-radius: 50%;" />

<br/>

# $FOSS — Free Open Source Soft

**A Solana SPL token I built, deployed on mainnet, listed on a DEX, and documented end-to-end.**

<br/>

[![Solana](https://img.shields.io/badge/Solana-Mainnet-9945FF?style=for-the-badge&logo=solana&logoColor=white)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Live Since](https://img.shields.io/badge/Live%20Since-July%202025-brightgreen?style=for-the-badge)](https://explorer.solana.com/tx/VQT5gJrktGkJNuSChKwnfQNeni4ULDLfgHV4bfspBTsZj44v6Wxqc6nGCZze7Mg66atQEmzuVf5MgyUBC9iGroN)
[![Supply](https://img.shields.io/badge/Supply-1B%20Fixed-blue?style=for-the-badge)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![Mint Authority](https://img.shields.io/badge/Mint%20Authority-Revoked-red?style=for-the-badge)](https://explorer.solana.com/address/64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin)
[![DEX](https://img.shields.io/badge/DEX-Orca%20Whirlpool-00C2CB?style=for-the-badge)](https://www.orca.so/pools/3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2)

<br/>

<img src="https://i.pinimg.com/originals/ee/e0/c1/eee0c1dc806da44930fc6eb26b94a737.gif" width="600" alt="coding gif" />

</div>

---

<div class="tenor-gif-embed" data-postid="14794084" data-share-method="host" data-aspect-ratio="1.50235" data-width="100%"><a href="https://tenor.com/view/computer-nerds-geeky-coding-hack-gif-14794084">Computer Nerds GIF</a>from <a href="https://tenor.com/search/computer-gifs">Computer GIFs</a></div> <script type="text/javascript" async src="https://tenor.com/embed.js"></script> 

## Why I Built This

In 1983, [Richard Stallman](https://stallman.org/) declared that software should be free — not free as in price, but free as in freedom. Free to run, study, modify, and share. That declaration became the GNU Project, the GPL license, and the philosophical foundation that the Linux kernel was eventually built on.

The internet today runs almost entirely on the output of that movement. Linux, Git, OpenSSL, Python, GCC — tools maintained largely by volunteers or small underfunded teams with no real financial model behind them.

I've used these tools every day as a developer. At some point the question became unavoidable: *blockchain is supposed to be this open, permissionless, transparent system — is there a way to use it to represent and route real value back to the people building FOSS?*

That question became `$FOSS`.

The token's description, stored permanently on IPFS:

> *"FOSS Coin is a community-created token built to support and promote Free and Open Source Software. It can be used to donate to FOSS projects, reward developers and contributors, and raise awareness about digital privacy, Linux, and open technologies."*

Not affiliated with the FSF, GNU, or Linux.org. Built independently by me — to ask that question on a live network, not just in theory.

---

## Token

| Property | Value |
|---|---|
| **Symbol** | `FOSS` |
| **On-chain Name** | `Free Open Source Soft ` |
| **Network** | Solana Mainnet |
| **Mint Address** | `64AcKtFgExrtJWPJVr6U4iQrJ1VpiUvDHvRtdMHAcoin` |
| **Token Standard** | SPL Token — `TokenkegQfeZyiNwAJbNbGKPFXCWuBvf9Ss623VQ5DA` |
| **Decimals** | `6` |
| **Total Supply** | `1,000,000,000` (raw on-chain: `1,000,000,000,000,000` ÷ 10⁶) |
| **Mint Authority** | `null` — revoked at creation, enforced by Solana runtime |
| **Freeze Authority** | `null` — revoked |
| **Metadata** | Metaplex Token Metadata v3 → [IPFS JSON](https://ipfs.io/ipfs/QmNaaTSFFy4ZBp95vhA8F8MCoYHu9tmzWgcW16YyQcni9n) |
| **Token Logo** | [IPFS PNG ~2.5MB](https://ipfs.io/ipfs/QmZjM3DiAsnwzVPBD2zNzDN518fJqTCmmw41u2bfRZFJMf) |
| **DEX** | Orca Whirlpool — `3Ub4ojhVSiMZtmrS8bHSEiMo9oqzauTyYtd3HjFbZnE2` |
| **Trading Pair** | FOSS / Wrapped SOL |
| **Live Since** | July 23, 2025 |

---

## What I Did — End to End

### July 23, 2025 — Token Deployed on Solana Mainnet

One atomic transaction. Seven steps in a single block at slot `355,223,383`:

```
