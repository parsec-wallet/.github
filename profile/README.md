# PARSEC Wallet GitHub Organization — README.prompt

> **Purpose**
>
> This document is a polished, machine-ready ingestion prompt and quick-reference catalog for the GitHub organization at `parsec-wallet`.
> It is designed to help an AI system rapidly understand the repository landscape, identify architectural themes, and extract reusable patterns for a sovereign, universal wallet platform.

---

## 1. Executive Framing

The `parsec-wallet` organization reads like a **wallet systems laboratory**: a deliberately broad collection of repositories spanning wallet frontends, chain infrastructure, signing stacks, hardware wallet integrations, distributed-web tooling, token-onboarding utilities, standards references, and experimental protocol work.

Taken together, this org can be read as a **research corpus for sovereign wallet design**:

- **Wallet UX surfaces** across Bitcoin, EVM, Cosmos, Avalanche, Arweave, IOTA, and Safe-style multisig
- **Protocol adapters and infrastructure** for Bitcoin, EVM, RPC registries, gas, signing, and cross-chain abstractions
- **Hardware and provider bridges** for D'CENT and EIP-1193-compatible discovery
- **Distributed web and privacy systems** built around Hypercore, Hyperdrive, Earthstar, and Agregore
- **Reference standards and research material** such as EIPs, Ethereum educational resources, zkSNARK examples, and ETC ecosystem references
- **Prototype and sovereign experiments** that touch proxy wallets, cross-chain routers, QR-based signature minting, oracle-aware consumer contracts, and more

This makes the org valuable not only as a code source, but as an **AI-ingestible design map** for constructing Parsec as a modular, chain-aware, security-first wallet platform.

---

## 2. claude.prompt

Copy the following prompt into Claude exactly as-is, then attach or paste repository material as needed.

```md
You are ingesting the entire `parsec-wallet` GitHub organization as a design and implementation corpus for a sovereign universal wallet platform named **Parsec**.

Your goals:

1. Build a mental model of the organization as a wallet R&D ecosystem rather than a random repo list.
2. Classify each repository by function:
   - wallet frontend
   - chain client / protocol stack
   - provider / signer / hardware integration
   - token / NFT / onboarding utility
   - distributed web / storage / privacy
   - standards / research / examples
   - Parsec-native or sovereign experiment
3. For each repository:
   - summarize what it contributes
   - identify what is reusable for Parsec
   - identify risks or mismatches for a no-external-dependency TSX/CSS + Tauri + Tomb architecture
   - note likely upstream ecosystem alignment (Bitcoin, EVM, Cosmos, Avalanche, Arweave, IOTA, etc.)
4. Produce:
   - a dependency-free architectural recommendation for Parsec
   - a prioritized ingestion order
   - a “borrow / reimplement / ignore” decision for every repository
   - a cross-reference map showing which repos inform:
     - wallet import and account handling
     - address and key recognition
     - chain adapters
     - transaction signing
     - multisig / smart accounts
     - RPC and network registry handling
     - DEX and token onboarding UX
     - distributed storage / sovereign sync
     - browser / extension / dApp provider support
5. Prefer extracting ideas, interfaces, flows, and security lessons over copying code blindly.
6. Treat licensing, architecture style, runtime weight, and security posture as first-class considerations.

Output style:
- elegant technical markdown
- crisp sections
- no fluff
- decisive recommendations
- explicit reuse strategy for Parsec
```

---

## 3. Recommended Ingestion Order

### Tier 1 — Wallet Architecture and Core UX
Start here to understand mainstream wallet surface area and account-management expectations.

1. `parsec-pod`
2. `wallet`
3. `safe-wallet-web`
4. `web-core-safe-webui`
5. `metamask-extension`
6. `keplr-wallet`
7. `avalanche-wallet`
8. `ArweaveWebWallet`
9. `wallet.rs`
10. `emeris-extension`

### Tier 2 — Chain Infrastructure and Protocol Mechanics
These repos inform signing, networking, gas, chain metadata, multi-chain abstraction, and smart account flows.

1. `bitcoin`
2. `litecoin`
3. `bitcore`
4. `bitcore-p2p`
5. `chainlist`
6. `ankr.js`
7. `signatory`
8. `gsn`
9. `xchainjs-lib-1`
10. `contracts`
11. `DELTAVstargaterouter.sol`
12. `EIPs`
13. `sputnikvm`
14. `sputnikvm-in-browser`

### Tier 3 — Provider / Hardware / Browser Interop
These help with signer discovery, hardware connectors, and wallet-provider patterns.

1. `detect-provider`
2. `dai-plugin-dcent-web`
3. `dcent-provider`
4. `eth-dcent-keyring`
5. `web3-react-dcent-connector`
6. `forwarder`

### Tier 4 — Token / NFT / Onboarding UX
Useful for wallet growth loops, user prompts, vault access, and token discovery.

1. `Add-Token`
2. `watch-token`
3. `vault-decryptor`
4. `bitauth`
5. `bitpay-checkout-for-woocommerce`
6. `proxy-contract-wallet-example`
7. `signature-minting-to-qr-code`
8. `MintLIT`
9. `eth-gas-price-suggestor`

### Tier 5 — Distributed Web / Sovereign Data / Privacy
These are strategic repos if Parsec expands into sovereign sync, offline-first state, or distributed content distribution.

1. `hypercore`
2. `hyperdrive-next`
3. `earthstar`
4. `earthstar-fetch`
5. `agregore-browser`
6. `slingshot`

### Tier 6 — Research, Study, and Experimental Context
These sharpen the conceptual layer around Ethereum, ETC, zk systems, and general wallet thinking.

1. `ethereumbook`
2. `Awesome-ETC`
3. `zksnarks_example`
4. `lightspeed`

---

## 4. Quick Reference Catalog

Below is the full quick-reference inventory for **every repository** visible in the `parsec-wallet` organization repository listing.

---

## 4A. Wallet Frontends, Wallet Products, and User-Facing Interfaces

### `parsec-pod`
- **URL:** https://github.com/parsec-wallet/parsec-pod
- **Quick summary:** Smart wallet in Node.js; likely the most directly Parsec-aligned product artifact in the org.
- **Why it matters:** Strong candidate for understanding prior Parsec naming, wallet data models, and orchestration patterns.

### `wallet`
- **URL:** https://github.com/parsec-wallet/wallet
- **Quick summary:** BitPay Wallet / Copay-style multi-currency wallet platform for desktop and mobile.
- **Why it matters:** Useful reference for mature wallet flows, account management, transaction UX, and cross-platform product structure.

### `safe-wallet-web`
- **URL:** https://github.com/parsec-wallet/safe-wallet-web
- **Quick summary:** Default Safe web interface for smart-account and multisig wallet interaction.
- **Why it matters:** Important reference for contract wallets, multisig flows, policy surfaces, and high-assurance signing UX.

### `web-core-safe-webui`
- **URL:** https://github.com/parsec-wallet/web-core-safe-webui
- **Quick summary:** New Safe web interface, closely related to Safe multisig / account-abstraction UX.
- **Why it matters:** Useful companion to `safe-wallet-web` when studying smart-account interface patterns.

### `metamask-extension`
- **URL:** https://github.com/parsec-wallet/metamask-extension
- **Quick summary:** MetaMask browser extension codebase for Ethereum-enabled site interaction.
- **Why it matters:** Critical reference for provider injection, extension wallet UX, vault patterns, and dApp permission handling.

### `keplr-wallet`
- **URL:** https://github.com/parsec-wallet/keplr-wallet
- **Quick summary:** Powerful wallet for the Cosmos ecosystem and the Interchain.
- **Why it matters:** Strong reference for chain-aware account UX, Bech32 flows, staking-centric design, and Cosmos provider patterns.

### `avalanche-wallet`
- **URL:** https://github.com/parsec-wallet/avalanche-wallet
- **Quick summary:** Avalanche web wallet.
- **Why it matters:** Useful for subnet-aware wallet ideas, chain-specific UX, and non-Ethereum account handling.

### `ArweaveWebWallet`
- **URL:** https://github.com/parsec-wallet/ArweaveWebWallet
- **Quick summary:** Source for the arweave.app wallet interface.
- **Why it matters:** Good reference for wallet flows on a storage-centric network and for alternative key/address models.

### `wallet.rs`
- **URL:** https://github.com/parsec-wallet/wallet.rs
- **Quick summary:** Rust wallet toolkit for applications involving IOTA value transfer.
- **Why it matters:** Highly relevant to Rust-side wallet logic, especially if Parsec centralizes signing and account handling in Tauri/Rust.

### `emeris-extension`
- **URL:** https://github.com/parsec-wallet/emeris-extension
- **Quick summary:** Browser extension for digital signature controls in the Emeris ecosystem.
- **Why it matters:** Useful for extension-based signature mediation and user-consent patterns.

---

## 4B. Chain Infrastructure, Protocol Tooling, and Multi-Chain Foundations

### `bitcoin`
- **URL:** https://github.com/parsec-wallet/bitcoin
- **Quick summary:** Bitcoin Core integration / staging tree.
- **Why it matters:** Foundational for UTXO rules, node interaction, transaction policy, and canonical Bitcoin wallet behavior.

### `litecoin`
- **URL:** https://github.com/parsec-wallet/litecoin
- **Quick summary:** Litecoin source tree.
- **Why it matters:** Useful as a second UTXO-family reference and for multi-chain wallet support beyond Bitcoin itself.

### `bitcore`
- **URL:** https://github.com/parsec-wallet/bitcore
- **Quick summary:** Full stack for Bitcoin and blockchain-based applications.
- **Why it matters:** Good reference for Bitcoin service layers, wallet plumbing, transaction building, and supporting services.

### `bitcore-p2p`
- **URL:** https://github.com/parsec-wallet/bitcore-p2p
- **Quick summary:** Interface to the Bitcoin P2P network for Bitcore.
- **Why it matters:** Useful for direct network interaction patterns and node-level wallet intelligence.

### `chainlist`
- **URL:** https://github.com/parsec-wallet/chainlist
- **Quick summary:** Registry of blockchains and testnets by RPC, with add-to-wallet support.
- **Why it matters:** Excellent reference for Parsec network registry design and user-facing network onboarding.

### `ankr.js`
- **URL:** https://github.com/parsec-wallet/ankr.js
- **Quick summary:** JavaScript library for interacting with Ankr APIs.
- **Why it matters:** Useful for RPC aggregation, remote data access patterns, and service-backed chain integration.

### `gsn`
- **URL:** https://github.com/parsec-wallet/gsn
- **Quick summary:** Ethereum Gas Station Network v2 implementation.
- **Why it matters:** Valuable for gas abstraction, meta-transactions, relayers, and fee sponsorship models.

### `signatory`
- **URL:** https://github.com/parsec-wallet/signatory
- **Quick summary:** Transaction and message signer for the Ethereum stack.
- **Why it matters:** Strong reference for signer interfaces, message signing, and transaction authorization boundaries.

### `xchainjs-lib-1`
- **URL:** https://github.com/parsec-wallet/xchainjs-lib-1
- **Quick summary:** Lightweight TypeScript library for cross-chain wallets via a common interface.
- **Why it matters:** Particularly relevant as an architecture reference for Parsec’s chain-pack / adapter strategy.

### `contracts`
- **URL:** https://github.com/parsec-wallet/contracts
- **Quick summary:** Consumer contract wallet for oracle-based price interaction.
- **Why it matters:** Suggests smart-wallet patterns connected to external price data and on-chain logic.

### `DELTAVstargaterouter.sol`
- **URL:** https://github.com/parsec-wallet/DELTAVstargaterouter.sol
- **Quick summary:** Omnibridge / symbiosis / rosen-bridge / all-chain routing experiment.
- **Why it matters:** Useful as a conceptual artifact for multi-chain routing and bridge-aware wallet ambitions.

### `EIPs`
- **URL:** https://github.com/parsec-wallet/EIPs
- **Quick summary:** Ethereum Improvement Proposal repository.
- **Why it matters:** Essential standards corpus for provider rules, account abstraction, signing, RPC, token standards, and wallet compatibility.

### `sputnikvm`
- **URL:** https://github.com/parsec-wallet/sputnikvm
- **Quick summary:** Blockchain virtual machine in Rust.
- **Why it matters:** Relevant for low-level EVM execution understanding and Rust-based chain tooling.

### `sputnikvm-in-browser`
- **URL:** https://github.com/parsec-wallet/sputnikvm-in-browser
- **Quick summary:** Browser-targeted WASM build of SputnikVM.
- **Why it matters:** Useful when exploring lightweight in-browser or portable execution patterns.

### `slingshot`
- **URL:** https://github.com/parsec-wallet/slingshot
- **Quick summary:** Blockchain architecture focused on scalability, privacy, and safety.
- **Why it matters:** More strategic than immediate, but interesting for sovereign network and protocol-design thinking.

---

## 4C. Provider Detection, Hardware Wallet Bridges, and Signing Interop

### `dai-plugin-dcent-web`
- **URL:** https://github.com/parsec-wallet/dai-plugin-dcent-web
- **Quick summary:** Browser plugin for using D'CENT with `dai.js`.
- **Why it matters:** Useful for hardware-wallet connectivity patterns and browser-signing bridges.

### `dcent-provider`
- **URL:** https://github.com/parsec-wallet/dcent-provider
- **Quick summary:** Ethereum web3 provider for D'CENT Biometric Wallet.
- **Why it matters:** Important reference for provider wrapping and hardware signer integration.

### `eth-dcent-keyring`
- **URL:** https://github.com/parsec-wallet/eth-dcent-keyring
- **Quick summary:** JS wrapper around D'CENT connector libraries for MetaMask-style keyring control.
- **Why it matters:** Excellent for understanding how hardware wallets can plug into extension wallet keyring systems.

### `web3-react-dcent-connector`
- **URL:** https://github.com/parsec-wallet/web3-react-dcent-connector
- **Quick summary:** D'CENT connector for `web3-react`.
- **Why it matters:** Useful as a thin interoperability reference for connector-style wallet composition.

### `detect-provider`
- **URL:** https://github.com/parsec-wallet/detect-provider
- **Quick summary:** Tiny utility for detecting MetaMask or any EIP-1193-compliant provider.
- **Why it matters:** Very relevant to dApp-connection UX and provider discovery logic.

### `forwarder`
- **URL:** https://github.com/parsec-wallet/forwarder
- **Quick summary:** Redirect page for installing MetaMask and returning users to the requesting app.
- **Why it matters:** Small but instructive for wallet onboarding, install flow continuity, and dApp fallback UX.

---

## 4D. Token UX, NFT Utilities, Auth, Vault Access, and Transaction Experience

### `Add-Token`
- **URL:** https://github.com/parsec-wallet/Add-Token
- **Quick summary:** Simple web3 dApp for suggesting a token to compatible wallets like MetaMask.
- **Why it matters:** Good reference for user-friendly token onboarding and wallet-initiated asset discovery.

### `watch-token`
- **URL:** https://github.com/parsec-wallet/watch-token
- **Quick summary:** DApp for suggesting and adding a token to compatible wallets.
- **Why it matters:** Similar to `Add-Token`; useful for pattern comparison and simplified token-watch flows.

### `vault-decryptor`
- **URL:** https://github.com/parsec-wallet/vault-decryptor
- **Quick summary:** Web app for decrypting MetaMask vault data.
- **Why it matters:** Extremely relevant for understanding wallet vault serialization, recovery tooling, and security boundaries.

### `bitauth`
- **URL:** https://github.com/parsec-wallet/bitauth
- **Quick summary:** Authentication with web services using Bitcoin-style cryptographic strategy.
- **Why it matters:** Useful for Parsec-native authentication flows grounded in wallet signatures rather than passwords.

### `bitpay-checkout-for-woocommerce`
- **URL:** https://github.com/parsec-wallet/bitpay-checkout-for-woocommerce
- **Quick summary:** WooCommerce integration for BitPay checkout.
- **Why it matters:** Helpful for merchant-facing payment experience and commerce-oriented wallet interoperability.

### `proxy-contract-wallet-example`
- **URL:** https://github.com/parsec-wallet/proxy-contract-wallet-example
- **Quick summary:** Example smart-contract setup mapping an end-user wallet to an ownable proxy wallet.
- **Why it matters:** Important for delegated control, smart-wallet abstraction, and end-user proxy patterns.

### `signature-minting-to-qr-code`
- **URL:** https://github.com/parsec-wallet/signature-minting-to-qr-code
- **Quick summary:** Signature-minting workflow tied to QR code output.
- **Why it matters:** Interesting experimental reference for offline signing, attestations, or transferable proof UX.

### `MintLIT`
- **URL:** https://github.com/parsec-wallet/MintLIT
- **Quick summary:** Encrypt data behind an NFT using Lit-oriented concepts.
- **Why it matters:** Useful for token-gated encryption, access control, and crypto-native content permissions.

### `eth-gas-price-suggestor`
- **URL:** https://github.com/parsec-wallet/eth-gas-price-suggestor
- **Quick summary:** Module for recommending default gas prices from recent successful transactions.
- **Why it matters:** Directly relevant for wallet fee estimation and safe default gas selection.

---

## 4E. Distributed Web, Sovereign Data, Offline-First Systems, and Alternative Network Surfaces

### `hyperdrive-next`
- **URL:** https://github.com/parsec-wallet/hyperdrive-next
- **Quick summary:** Secure, real-time distributed file system.
- **Why it matters:** Strategic reference for sovereign sync, distributed storage, and user-controlled data distribution.

### `hypercore`
- **URL:** https://github.com/parsec-wallet/hypercore
- **Quick summary:** Secure, distributed append-only log.
- **Why it matters:** Useful if Parsec later needs replicated event logs, wallet journaling, or offline-synchronizable state.

### `earthstar`
- **URL:** https://github.com/parsec-wallet/earthstar
- **Quick summary:** Tool for private, undiscoverable, offline-first networks.
- **Why it matters:** Very relevant to local-first / sovereign-first wallet data strategies.

### `earthstar-fetch`
- **URL:** https://github.com/parsec-wallet/earthstar-fetch
- **Quick summary:** Earthstar fetch utility.
- **Why it matters:** Small companion artifact that may inform content retrieval or transport within Earthstar-style systems.

### `agregore-browser`
- **URL:** https://github.com/parsec-wallet/agregore-browser
- **Quick summary:** Minimal desktop browser for the distributed web.
- **Why it matters:** Helpful for thinking about a wallet-plus-browser future, especially around distributed protocols and native dApp discovery.

---

## 4F. Research, Standards, Books, and Experimental Context

### `ethereumbook`
- **URL:** https://github.com/parsec-wallet/ethereumbook
- **Quick summary:** *Mastering Ethereum* source repository by Andreas M. Antonopoulos and Gavin Wood.
- **Why it matters:** Foundational reading corpus for Ethereum wallet, key, transaction, and smart-contract architecture.

### `Awesome-ETC`
- **URL:** https://github.com/parsec-wallet/Awesome-ETC
- **Quick summary:** Awesome-list resource collection for Ethereum Classic.
- **Why it matters:** Helpful ecosystem map for ETC-oriented support or for comparative Ethereum-family design research.

### `zksnarks_example`
- **URL:** https://github.com/parsec-wallet/zksnarks_example
- **Quick summary:** zkSNARK tutorial repository.
- **Why it matters:** Research-oriented reference if Parsec later incorporates privacy proofs, verifiable attestations, or succinct-auth patterns.

### `lightspeed`
- **URL:** https://github.com/parsec-wallet/lightspeed
- **Quick summary:** Light.js / THRUST-flavored experiment emphasizing speed-of-light execution.
- **Why it matters:** Experimental and likely speculative, but potentially useful as a naming / concept artifact for performance-first wallet thinking.

---

## 5. Practical Reuse Guidance for Parsec

### Borrow directly at the idea/interface level
- `chainlist`
- `detect-provider`
- `xchainjs-lib-1`
- `safe-wallet-web`
- `web-core-safe-webui`
- `wallet.rs`
- `vault-decryptor`
- `bitcore`
- `bitcore-p2p`
- `EIPs`

### Reimplement in-house for Parsec’s architecture
Because Parsec is targeting **Tauri + Rust backend + zero-dependency TSX/CSS frontend + Tomb-backed local vault**, the right move is usually to **reimplement the good ideas**, not pull large runtime-heavy codebases directly.

Especially true for:
- `metamask-extension`
- `wallet`
- `keplr-wallet`
- `avalanche-wallet`
- `ArweaveWebWallet`
- `gsn`
- `ankr.js`
- `Add-Token`
- `watch-token`

### Read strategically, not for direct inclusion
- `ethereumbook`
- `Awesome-ETC`
- `zksnarks_example`
- `slingshot`
- `lightspeed`

---

## 6. What Claude Should Notice

Claude should recognize that this organization is not just “a bunch of crypto repos.” It is a **composite wallet intelligence set** covering:

- classical UTXO systems
- account-based smart-contract ecosystems
- multisig and smart accounts
- extension/provider patterns
- hardware wallet bridges
- distributed-web and offline-first infrastructure
- wallet UX growth loops
- standards and deep protocol references

That combination makes it unusually useful for designing **Parsec as a universal sovereign wallet**.

---

## 7. Closing Directive

If this corpus is used to inform Parsec:

- prefer **small, explicit interfaces**
- keep **signing in Rust**
- keep **UI dependency-free**
- keep **chain support adapter-driven**
- treat **vault design, import safety, and provider boundaries** as security-critical
- extract **ideas and architecture**, not accidental complexity

The right outcome is not to imitate any single upstream wallet.

The right outcome is to synthesize a **cleaner, safer, more sovereign Parsec**.
