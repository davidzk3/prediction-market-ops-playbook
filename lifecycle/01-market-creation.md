\# Market Creation

\## Prediction Market Lifecycle — Phase 1



This document defines the operational process for creating a new orderbook-based prediction market.



Market creation is the highest-risk phase of the lifecycle.

Mistakes here propagate into liquidity issues, disputes, and reputational damage.



---



\## Objectives of Market Creation



A correctly created market must:

\- Be objectively resolvable

\- Minimize ambiguity

\- Attract informed participation

\- Avoid oracle and manipulation risk

\- Be operationally supportable



---



\## Market Intake Pipeline



\### 1. Market Proposal Submission



Markets can originate from:

\- Internal curation (Ops / Product)

\- Scheduled thematic calendars

\- Community proposals (optional)



Each proposal must include:

\- Clear question text

\- Outcome definitions

\- Expected resolution source

\- Target resolution date



---



\### 2. Market Type Classification



Markets are classified before approval.



Common types:

\- Binary (Yes / No)

\- Multi-outcome (single winner)

\- Mutually exclusive binary set (NegRisk-style)



Classification determines:

\- Orderbook structure

\- Settlement logic

\- Risk controls



---



\### 3. Resolution Feasibility Check



Ops must validate that:

\- A trusted data source exists

\- The outcome is not subjective

\- Resolution timing is predictable

\- No retroactive interpretation is required



Markets failing this step are rejected.



---



\## Question Design Standards



\### Clarity Requirements



All market questions must:

\- Use unambiguous language

\- Define exact resolution conditions

\- Avoid probabilistic phrasing

\- Specify the authoritative data source



Example:

> “Will ETH close above $3,000 on Binance at 00:00 UTC on 31 Dec 2025?”



---



\### Outcome Definitions



Each outcome must:

\- Be mutually exclusive

\- Be collectively exhaustive

\- Have deterministic settlement



For multi-outcome markets:

\- One and only one outcome must resolve true



---



\## Risk Review (Pre-Launch)



Before approval, Ops performs a structured risk review.



\### Key Risk Dimensions



\- Market manipulability

\- Information asymmetry

\- Liquidity concentration risk

\- Oracle failure risk

\- Legal or jurisdictional risk



High-risk markets require:

\- Reduced limits

\- Higher fees

\- Manual approval gates



---



\## Oracle Strategy Selection



Each market must define:

\- Primary oracle (e.g. Chainlink feed, UMA OO)

\- Fallback oracle

\- Dispute escalation path



Oracle choice is locked before launch.



---



\## Market Parameters Configuration



Ops configures:

\- Minimum tick size

\- Max order size

\- Max position per account

\- Trading cut-off time

\- Settlement delay buffer



These parameters are adjustable only by Ops.



---



\## Market Approval Checklist



A market may launch only if:

\- Question clarity is approved

\- Oracle source is validated

\- Risk review is passed

\- Parameters are set

\- Monitoring hooks are active



Approval is logged and auditable.



---



\## Launch Readiness Signal



Once approved:

\- Market is deployed on-chain

\- Orderbook is initialized

\- Trading is opened

\- Monitoring dashboards go live



The market enters \*\*Active Trading\*\*.



---



\## Operational Ownership



During creation:

\- Ops owns approval and risk

\- Product owns UX presentation

\- Engineering owns deployment

\- Legal advises on edge cases



Final launch authority rests with Ops.



---



\## Summary



Market creation determines:

\- Trustworthiness

\- Liquidity quality

\- Dispute frequency

\- Long-term credibility



Strong upfront discipline prevents downstream failures.



