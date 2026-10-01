<p align="center">
  <img src="https://raw.githubusercontent.com/parsec-wallet/.github/main/profile/img/parsec-mark.png" width="96" height="96" alt="The Parsec mark: a gold delta inside an orbital ring">
</p>

<h1 align="center">PARSEC</h1>

<p align="center">
  <b>A sovereign wallet for a multi-chain, agent-paying internet.</b><br>
  Your keys stay on your machine. Your wallet pays for what it uses. Every claim here links to the code that makes it true.
</p>

<p align="center">
  <a href="https://github.com/parsec-wallet/PARSEC"><img alt="PARSEC on GitHub" src="https://img.shields.io/badge/PARSEC-the%20wallet-f2c14b?style=flat-square&labelColor=0b0f16"></a>
  <a href="https://github.com/parsec-wallet/x402"><img alt="x402 module" src="https://img.shields.io/badge/x402-pay%20per%20request-4fa8e8?style=flat-square&labelColor=0b0f16"></a>
  <a href="https://github.com/parsec-wallet/PARSEC/blob/dev/LICENSE"><img alt="Licence: GPL-3.0 / Apache-2.0 / MIT by component" src="https://img.shields.io/badge/licence-GPL--3.0%20%C2%B7%20Apache--2.0%20%C2%B7%20MIT-555?style=flat-square&labelColor=0b0f16"></a>
</p>

<p align="center">
  <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-66%25-3178c6?style=flat-square&logo=typescript&logoColor=white&labelColor=0b0f16">
  <img alt="Rust" src="https://img.shields.io/badge/Rust-15%25-dea584?style=flat-square&logo=rust&logoColor=white&labelColor=0b0f16">
  <img alt="SCSS" src="https://img.shields.io/badge/SCSS-14%25-c6538c?style=flat-square&logo=sass&logoColor=white&labelColor=0b0f16">
  <img alt="Lua" src="https://img.shields.io/badge/Lua%20(AO)-2%25-2c2d72?style=flat-square&logo=lua&logoColor=white&labelColor=0b0f16">
  <img alt="Tauri 2" src="https://img.shields.io/badge/Tauri-2-24c8db?style=flat-square&logo=tauri&logoColor=white&labelColor=0b0f16">
  <img alt="Algorand first" src="https://img.shields.io/badge/Algorand-first-ffffff?style=flat-square&logo=algorand&logoColor=white&labelColor=0b0f16">
</p>

---

<p align="center">
  <img src="https://raw.githubusercontent.com/parsec-wallet/.github/main/profile/img/landing.png" width="860" alt="The Parsec landing: a live market pyramid ranked by the selected period, floating price glyphs, and the overlay toggles">
</p>

## Parsec, in a paragraph

Parsec is a desktop wallet that treats your keys as yours alone. It is **Algorand first**, with
Solana, Arweave, EVM / Base and Bitcoin beside it, and it is built so the part that can spend your
money is small and inspectable: **Rust signs and validates; the interface only asks**. It opens on a
live market, creates a wallet in three plain steps, registers `.algo` names, publishes to the
permaweb, and pays for paid APIs over **x402** — the HTTP status code that finally means something:
*402 Payment Required*.

## What you can do with it today

| | |
|---|---|
| **Create a wallet you understand** | Your address first. Then the private key and the recovery phrase, each hidden until you reveal it and each one copyable. Then verify and save into the encrypted vault. Algorand's own 25-word phrase; 24-word BIP-39 for Solana and Arweave (the Arweave key also downloads as its JWK). |
| **Hold many chains under one identity** | Algorand is required and comes first; Solana, Arweave, EVM / Base and Bitcoin (desktop) are added beside it. Every address is shown in its chain's own format, on one line. |
| **Register a `.algo` name** | Search, see the price, pay, own it. The review screen separates what registration *requires* — the NFD registry price and network fee, in ALGO — from the **BANKON fee** Parsec charges, in USDC over x402. Two currencies, two parties, never added together. |
| **Pay per request with x402** | Probe any URL, see what it costs on which network, choose the rail, approve. The receipt keeps the settled transaction id. |
| **Read the market at a glance** | The landing ranks the top coins into a pyramid by the period you choose (1h, 4h, 24h, 7d, 30d) — gainers right, losses left, largest moves nearest the apex — with stablecoin pegs and supply flow beside it. |
| **Publish permanently** | Upload to Arweave through Turbo, manage ArNS names, and bridge or stake on ar.io from the Permaweb section. |
| **Connect dApps without a browser extension** | Parsec Connect: a local WebSocket bridge (`127.0.0.1:9876`); every signature is approved on screen. |

<p align="center">
  <img src="https://raw.githubusercontent.com/parsec-wallet/.github/main/profile/img/create-wallet.png" width="720" alt="Creating an Algorand wallet in Parsec: the address first, then the private key and recovery phrase, each hidden until revealed">
</p>

## Wallets for agents, and for agency

Parsec makes wallets for agents as readily as for people, and keeps a person in the loop where it matters.

| | |
|---|---|
| **One vault, many wallets** | Any number of accounts across five chains, each with its own keys, encrypted together. Watch-only accounts let an agent read what it cannot spend. |
| **A family from one seed** | Algorand HD (ARC-52) derives an account per agent or per task from a single seed — one backup, many addresses. |
| **Spending with limits** | Payments under a cap you set go through unattended; anything larger waits for you. Zero means always ask. |
| **Headless when it should be** | The x402 payer runs outside a browser with any signer, so a script or a service can pay its own way. |
| **Agency with consent** | Through Parsec Connect an agent asks for a signature or a name action, and you approve or refuse it on screen. The key never leaves Parsec. |
| **Earn as well as spend** | The same rail sells: an agent's own service can answer 402 and settle into its own address. |

## How it is built

Shiny on the outside; on the inside, an engineered movement you can open and read.

- **Rust decides, TypeScript suggests.** Signing for every chain pack and address validation run in
  Rust, and keys rest encrypted in the Rust vault. A signing command returns a signature, never a key.
- **No UI framework.** Vanilla TypeScript and one small DOM kit; no React, no wallet-connection SDKs,
  no chart libraries. The same build ships as the desktop app and as a permaweb site.
- **An encrypted vault you can read the specification of.** Argon2id key derivation and AES-256-GCM,
  with an optional LUKS cold volume ("the Tomb"). [Vault specification](https://github.com/parsec-wallet/PARSEC/blob/dev/docs/security/bankon-vault-spec.md) ·
  [threat model](https://github.com/parsec-wallet/PARSEC/blob/dev/docs/security/threat-model.md)
- **Modular by contract.** A new chain or tool is one module registration and one document.
  [The module contract](https://github.com/parsec-wallet/PARSEC/blob/dev/docs/modules.md)
- **Designed for what comes after elliptic curves.** Algorand is first because its accounts can move to
  Falcon-1024 keys while keeping the same address. [QUANTUM.md](https://github.com/parsec-wallet/PARSEC/blob/dev/QUANTUM.md)

## x402: paying for the web, one request at a time

**What it is.** A server answers a request with `402 Payment Required` and a `PAYMENT-REQUIRED`
header describing exactly what it will accept: the price, the asset, the address to pay, the network.
The client builds and signs a payment, sends the same request again carrying it, and a *facilitator*
verifies and settles it on chain. No account, no API key, no subscription — **the payment is the
authentication**. That is what makes it a rail for agents: one with a key can buy something it has
never seen, from a seller it will never meet again.

**How Parsec does it.**

- **Three rails, one client.** Algorand (USDC, ASA `31566704` on mainnet), EVM (EIP-3009
  transfer-with-authorization, with the EIP-712 digest built in Rust) and Solana (a partially signed
  transaction). A new chain is one `registerRail()`.
- **Gasless on Algorand.** The payment is an atomic group: the payer's USDC transfer, plus a
  fee-payer transaction the facilitator signs. The payer needs USDC, not ALGO for fees.
- **Built not to pay twice.** Every wait is bounded; a payment sent to a server that then goes silent
  reports *indeterminate*, not *failed* — reporting failed is how a payer pays twice. The amount is
  validated before it becomes a number, and every receipt keeps the settled transaction id.
- **Portable.** The module talks to its host through three small ports — signing, storage, network —
  so any Algorand wallet can embed it: an `algosdk.TransactionSigner` is the signer, unchanged.
  Discovery reads the facilitator's Bazaar catalogue.

**Use it in your own wallet or agent** ([github.com/parsec-wallet/x402](https://github.com/parsec-wallet/x402)):

```ts
import { createX402Client, algorandSigner } from './x402';

const x402 = createX402Client({
  signers: { avm: algorandSigner(address, transactionSigner) },   // use-wallet, AlgoKit, Pera, Defly
  approve: async (p) => confirm(`Pay ${p.quote.amountDisplay} ${p.quote.assetSymbol}?`),
});

const res = await x402.fetch('https://api.example.com/weather');   // pays the 402, retries, returns the 200
```

Find out what something costs without a key: `await createX402Client().quote(url)`.

**Sell with it.** The same repository carries the seller half: a FastAPI dependency that answers
`402` with the terms, verifies and settles through the facilitator, advertises each endpoint in the
Bazaar catalogue, and prices every route from one hot-reloaded file:

```python
@app.post("/names/algo", dependencies=[Depends(x402_required("/names/algo"))])
async def register_algo_name(order: NameOrder): ...
```

**In Parsec.** The x402 desk probes and pays any resource (GET or POST with a JSON body) with an explicit
*Pay on* rail picker; `.algo Names` pays its BANKON fee this way.
[Protocol and design](https://github.com/parsec-wallet/PARSEC/blob/dev/docs/x402-integration.md) ·
[every export and error](https://github.com/parsec-wallet/PARSEC/blob/dev/docs/x402-api.md) ·
[usage recipes](https://github.com/parsec-wallet/x402/blob/main/usage.md)

## Where it stands

Parsec is **alpha**, and says so. What is open is listed, not hidden:

- The first mainnet x402 settlement through Parsec is the next step; until then everything is verified
  against stubs, test shapes and live read endpoints, which is not the same as having settled.
- The second-generation vault format (wrapped keys, per-entry derivation, Rust-enforced auto-lock) is
  written and specified but not yet compiled in; today's auto-lock is a five-minute interface timer.
- Parsec's destination is the [cypherpunk4096](https://github.com/parsec-wallet/PARSEC/blob/dev/docs/cypherpunk4096.md)
  standard, which is binary: all of it or none. Two commitments are not met yet — zero runtime
  dependencies, and no floating point in any value path.

## The repositories

| | |
|---|---|
| [**PARSEC**](https://github.com/parsec-wallet/PARSEC) | The wallet: Tauri 2 desktop app and permaweb build. Start with [the docs index](https://github.com/parsec-wallet/PARSEC/blob/dev/docs/README.md). |
| [**x402**](https://github.com/parsec-wallet/x402) | x402 on Algorand, standalone: the payer module (any wallet) and the seller middleware. Apache-2.0. |
| [**ARCtestnetUI**](https://github.com/parsec-wallet/ARCtestnetUI) | A chain-agnostic EVM wallet module with a one-click Arc testnet USDC faucet. |

<details>
<summary><b>The reference library</b> — wallets and protocol stacks kept here to learn from</summary>

<br>

The rest of this organization is a working library: forks of wallets, chain clients and protocol
tooling (Bitcoin, Litecoin, Safe, Pera, MetaMask, Avalanche, D'CENT, the xchain-accounts and lightspeed
experiments and more), kept so that Parsec's design can be argued from real code rather than from
memory. Nothing in the library is Parsec, and Parsec vendors none of it. A structured guide to the
whole library, written for AI systems, is in [`corpus.prompt.md`](https://github.com/parsec-wallet/.github/blob/main/corpus.prompt.md).

</details>

## For machines

Language models and agents: start at [`llms.txt`](https://github.com/parsec-wallet/.github/blob/main/llms.txt) — what Parsec is, where every
document lives, and how to pay its endpoints.

## Get in touch

[sales@pythai.net](mailto:sales@pythai.net) · [bankon.pythai.net](https://bankon.pythai.net) ·
security reports: see [SECURITY.md](https://github.com/parsec-wallet/PARSEC/blob/dev/SECURITY.md)

<sub>Parsec is built by BANKON. Licensed by component: GPL-3.0-or-later for everything that holds or uses
a key, Apache-2.0 for the rest, MIT for the server-side AO processes — per path in
<a href="https://github.com/parsec-wallet/PARSEC/blob/dev/REUSE.toml">REUSE.toml</a>.</sub>
