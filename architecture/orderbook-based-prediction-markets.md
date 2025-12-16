\# Orderbook-Based Prediction Markets

\## Architecture Rationale and Operational Implications



This document explains \*\*why an orderbook model is used for prediction markets\*\*, how it differs from AMM-based designs, and what this implies for \*\*operations, risk management, and governance\*\*.



This architecture aligns with:

\- Polymarket’s CTF exchange model

\- PancakeSwap’s existing orderbook experimentation

\- High-integrity, high-visibility markets



---



\## Why Orderbooks for Prediction Markets



Prediction markets differ fundamentally from spot AMMs:



\- Liquidity concentrates near probabilities (0–100%)

\- Information arrives discontinuously

\- Resolution events introduce binary risk

\- Market manipulation incentives are asymmetric



Orderbooks provide \*\*explicit control surfaces\*\* that AMMs lack.



---



\## Core Properties of an Orderbook Market



\### Explicit Price Discovery

\- Prices directly represent probabilities

\- Best bid / best ask is transparent

\- Depth reveals conviction, not curve math



This is critical for:

\- Market integrity

\- Media-facing probability signals

\- Operator oversight



---



\### Deterministic Matching

Orderbooks enforce:

\- Price-time priority

\- Deterministic fills

\- Clear maker vs taker roles



This simplifies:

\- Dispute investigation

\- Wash trading detection

\- Post-incident reconstruction



---



\### Discrete Liquidity Control

Operators can:

\- Set minimum tick sizes

\- Cap max order size

\- Enforce exposure limits

\- Adjust maker rebates



These controls are \*\*operational levers\*\*, not protocol guesses.



---



\## Comparison: Orderbook vs AMM



| Dimension | Orderbook | AMM |

|--------|---------|-----|

| Price discovery | Explicit | Implicit |

| Spread control | Direct | Indirect |

| Liquidity visibility | High | Low |

| Risk containment | Strong | Weak |

| Ops intervention | Precise | Coarse |

| Incident response | Auditable | Hard |



AMMs optimize for permissionless liquidity.

Prediction markets optimize for \*\*truth and safety\*\*.



---



\## Market Structure



Each market consists of:

\- A single question

\- One or more outcomes

\- A separate orderbook per outcome



Example:

\- Market: “Will ETH ETF be approved?”

\- Outcomes: YES / NO

\- Two independent orderbooks



Prices converge through arbitrage.



---



\## Operational Advantages



\### 1. Better Risk Monitoring

Ops can observe:

\- Spread widening

\- Orderbook thinning

\- One-sided pressure

\- Sudden depth withdrawal



These are \*\*early warning signals\*\*.



---



\### 2. Fine-Grained Interventions

During stress, operators can:

\- Reduce max position size

\- Pause new orders (not settlements)

\- Disable market creation

\- Increase fees temporarily



AMMs lack this granularity.



---



\### 3. Cleaner Resolution Path

Because positions are explicit:

\- Settlement math is simpler

\- Insolvency risk is lower

\- Dispute impact is bounded



This is critical during oracle delays or disputes.



---



\## Failure Modes and Mitigations



\### Low Liquidity

Risk:

\- Wide spreads

\- Manipulation at low volume



Mitigations:

\- Maker incentives

\- Market minimum liquidity requirements

\- Early warning alerts



---



\### Orderbook Manipulation

Risk:

\- Spoofing

\- Wash trading

\- Quote stuffing



Mitigations:

\- Rate limits

\- Trade surveillance

\- Post-trade analysis

\- Governance action



---



\### Oracle-Induced Shocks

Risk:

\- Sudden repricing near expiry

\- Information asymmetry



Mitigations:

\- Order throttling near resolution

\- Position caps

\- Temporary halts



---



\## Why PancakeSwap Would Choose This Model



From an ops perspective:

\- PancakeSwap already supports orderbook-like systems

\- Existing users understand limit orders

\- Governance expectations already exist

\- CAKE incentives map naturally to maker rebates



This model minimizes:

\- Black-box risk

\- Liquidity death spirals

\- Post-resolution disputes



---



\## Summary



Orderbook-based prediction markets:

\- Sacrifice some permissionlessness

\- Gain massive operational control

\- Improve safety during edge cases

\- Enable professional market oversight



For production-grade prediction markets, \*\*orderbooks are the correct default\*\*.



