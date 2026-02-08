


USE ../DEC_HERO.PNG file in curr repo on git!



GO TO REPO: https://github.com/Decagon-Pay/Decagon-core/tree/main
Link to hosted website: https://decagon-core-web.vercel.app/



Bounties:

MAIN DEFI + PLASMA:
💎 Plasma Payments Bounty — Decagon
Decagon brings Stripe-like checkout to Plasma via HTTP 402.

What we built:

HTTP 402 protocol — Any HTTP resource returns 402 Payment Required with a payment challenge. Client pays on-chain on Plasma, submits proof, gets access. Standard HTTP, works with any client (browsers, CLIs, AI agents).
Drop-in SDK (@decagon/ui) — One <PaymentSheet /> React component handles wallet connection, tx signing, verification, and receipts. Developers add payments in minutes. SDK DOCS: https://decagon-core-web.vercel.app/sdk-docs
Two live demos — Pay-per-article news paywall + cross-border remittance, both settling instantly on Plasma testnet with sub-cent fees. news: https://decagon-core-web.vercel.app/news and cross-border remittance https://decagon-core-web.vercel.app/remittance
Agent-native payments — Scoped agent tokens with daily spend caps and path allowlists let AI agents pay for resources autonomously within policy bounds.
Why it matters for adoption:
Users never think about crypto — they click "Unlock", MetaMask signs, content appears in <2s. The 402 standard means every API, every paywall, every SaaS can accept Plasma stablecoins with zero custom integration. One protocol, infinite verticals.




RABOT - EFFECTFUL
🏗 Effectful Programming Core — Decagon
Runtime: TypeScript + Effect

Decagon's entire backend is built on Effect as the core architectural paradigm. Every side effect — persistence, on-chain RPC, time, ID generation, logging — is modeled as an Effect service (Context Tag), declared in typed capability interfaces, and injected at the application boundary.

How it works:

13 capability interfaces (packages/core/src/capabilities/) define all I/O boundaries — PaymentVerifier, ReceiptsStore, ChallengesStore, Clock, PlasmaRpc, PolicyStore, etc.
Pure workflows (packages/core/src/workflows/) compose these capabilities via Effect.gen — getArticle, verifyPaymentAndIssueSession, createTransfer, checkPaymentPolicy
Two provider layers — in-memory mocks for testing, SQLite + RPC for production — wired via Effect.provide() in Fastify route handlers
Zero scattered side effects — business logic never touches the database, network, or clock directly
📄 Full architecture: EFFECTS.md[https://github.com/Decagon-Pay/Decagon-core/blob/main/EFFECTS.md]