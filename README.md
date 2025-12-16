# Prediction Market Operations Playbook
## Orderbook-Based Prediction Markets (PancakeSwap-style)

This repository is an **operations-first playbook** for running an **orderbook-based prediction market** at production scale.

It is designed for:
- Web3-native prediction markets
- Orderbook-based trading systems (not AMMs)
- Oracle-driven market resolution (UMA Optimistic Oracle, Chainlink)
- High-stakes, real-money markets with governance, disputes, and risk controls

The focus is **real operational execution**, not theory.

---

## Why This Exists

Prediction markets are not just smart contracts.
They are **live financial systems** that require:

- Market creation controls
- Liquidity and spread monitoring
- Oracle resolution governance
- Dispute handling
- Emergency intervention
- Post-mortem analysis

This playbook documents **how operators actually run these systems** day-to-day.

---

## System Assumptions

This playbook assumes:

- **Orderbook-based exchange**
  - Limit & market orders
  - Makers and takers
  - Explicit spreads and depth
- **Custodied or semi-custodied collateral** (e.g. USDC)
- **Conditional tokens** (Yes/No or multi-outcome)
- **Oracle-based resolution**
  - UMA Optimistic Oracle for final truth
  - Chainlink for reference data
- **Governance and Ops authority**
  - Ability to pause markets
  - Restrict position sizes
  - Escalate disputes

---

## Repository Structure



architecture/
system-overview.md
orderbook-based-prediction-markets.md
orderbook-vs-amm.md
oracle-design.md
oracle-resolution-flow.md

lifecycle/
01-market-creation.md
02-prelaunch-risk-review.md
02-trading-and-liquidity.md
03-live-market-operations.md
03-risk-and-interventions.md
04-resolution-oracles.md
04-resolution-and-disputes.md
05-settlement-disputes.md
05-settlement-and-post-mortem.md
06-post-market-review.md

monitoring/
core-metrics.md
alerts-and-thresholds.md
dashboards.md

runbooks/
market-creation-checklist.md
live-market-intervention.md
low-liquidity.md
market-manipulation.md
oracle-delay.md
oracle-failure-response.md
invalid-resolution.md
dispute-handling.md
emergency-market-pause.md

governance/
market-curation.md
parameter-updates.md
pausing-and-escalation.md
escalation-policy.md

## How To Use This Playbook

1. **Architecture**  
   Understand system design and oracle flows

2. **Lifecycle**  
   Follow the market from creation → trading → resolution → settlement

3. **Monitoring**  
   Track the metrics that actually matter in live markets

4. **Runbooks**  
   Execute predefined responses when things go wrong

5. **Governance**  
   Make decisions transparently and defensibly

---

## Intended Audience

- Protocol Operations Leads
- Prediction Market Operators
- Risk Managers
- Governance Committees
- Protocol Engineers working with Ops

---

## Key Design Principle

> **Markets fail operationally before they fail technically.**

This playbook exists to prevent that.

