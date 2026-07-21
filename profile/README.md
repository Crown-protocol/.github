<h1 align="center">CROWN</h1>

<p align="center">
  Creator donations with no middleman between the donor's wallet and the recipient.<br>
  The money moves on-chain. We don't hold it and we can't stop it.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Solana-devnet-7C3AED?style=flat-square" alt="Solana devnet">
  <img src="https://img.shields.io/badge/Internet_Computer-canisters-7C3AED?style=flat-square" alt="Internet Computer">
  <img src="https://img.shields.io/badge/Rust-core-7C3AED?style=flat-square" alt="Rust">
</p>

---

## How it works

```
donor ──▶ splitter (Solana)  ──▶ recipient
              │                  no fee, no balance
              ▼
        crown-index (ICP)
        open reputation ledger
              │
              ▼
        Crown App — profile, goals, OBS overlay
```

Three things worth understanding up front:

1. **The splitter is immutable.** It has no owner, no fee and no balance — funds pass straight through.
2. **The reputation ledger is open.** Who donated how much is public and independently verifiable.
3. **The frontend decides nothing.** It sits outside the trusted perimeter: no money, no keys. If the site goes down, payments keep working.

## Repositories

### Core

| | |
|---|---|
| **[Crown-Core](https://github.com/Crown-protocol/Crown-Core)** | The Solana splitter plus `crown-index`, the canister folding settlements into a reputation ledger |
| **[Crown-Factory](https://github.com/Crown-protocol/Crown-Factory)** | `two-outcome` escrow factories and `crown-derive` — attributing a settlement to its donor via PDA |

### Application

| | |
|---|---|
| **[Crown-App](https://github.com/Crown-protocol/Crown-App)** | Site, creator cabinet, campaigns, mini-games, OBS overlays. Next.js 14 |

### Crown Games

ICP resolvers built on the forms exposed by `Crown-Factory`. None of them holds funds or sends transactions — they read the chain and sign an outcome.

| | |
|---|---|
| **[Conditional-Tasks](https://github.com/Crown-protocol/Conditional-Tasks)** | Conditional tasks: ledger-weighted voting, threshold verdicts |
| **[Conditional-Funding](https://github.com/Crown-protocol/Conditional-Funding)** | Funding: crowdfunding, one verdict per escrow collection |
| **[Auction](https://github.com/Crown-protocol/Auction)** | Auction: lot registry, bids read from the chain, winner by price |
| **[Subscription](https://github.com/Crown-protocol/Subscription)** | Subscription: prepaid streams, `cancel` by the donor's signature |

## Stack

**Solana** — settlement and escrow, Rust
**Internet Computer** — resolvers and the reputation ledger, Rust canisters
**Next.js 14** — frontend in TypeScript

## Status

Devnet. Under active development — interfaces may change.
