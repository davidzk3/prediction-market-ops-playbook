\# Prediction Market Operations Playbook (Orderbook-Based)



This repository documents a \*\*production-grade operations framework\*\* for running

\*\*orderbook-based prediction markets\*\*, adapted from real-world systems such as

Polymarket (CTF / NegRisk), UMA Optimistic Oracle workflows, and exchange-grade

market operations.



The focus is \*\*execution\*\*, not theory.



This playbook is designed for:

\- Operations Leads

\- Protocol Ops \& Risk teams

\- Prediction Market product teams

\- Orderbook-based on-chain exchanges (EVM)



---



\## What This Repository Covers



This is \*\*not a smart contract repo\*\*.



It covers the \*\*operational lifecycle\*\* of prediction markets:

\- Market creation and curation

\- Live market monitoring and intervention

\- Oracle resolution and disputes

\- Incident response and postmortems

\- Governance and parameter management



---



\## System Assumptions



This playbook assumes:



\- \*\*Orderbook-based prediction markets\*\*

\- Conditional Tokens (Yes / No / Multi-outcome)

\- External oracle resolution (UMA Optimistic Oracle style)

\- USDC-style collateral

\- Operator-managed market safety controls



AMM-style prediction markets are discussed only for comparison.



---



\## Repository Structure



\- architecture/ → System design and oracle architecture

\- lifecycle/ → End-to-end market lifecycle

\- runbooks/ → Step-by-step operational actions

\- monitoring/ → Metrics, dashboards, alerting

\- incidents/ → Incident response and postmortems

\- governance/ → Market curation and parameter control

