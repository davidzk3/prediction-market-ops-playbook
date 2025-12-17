# System Overview

## Orderbook-Based Prediction Market Architecture



This document describes the **high-level system architecture** of an orderbook-based prediction market, with emphasis on **operational control, oracle resolution, and risk management**.



The architecture is designed for production environments similar to:

- Polymarket (CTF + Optimistic Oracle)

- PancakeSwap-style Web3-native products

- High-liquidity retail markets with governance oversight



---



## Core System Components



### 1. Users and Traders

Participants interact with the system by:

- Depositing collateral (e.g. USDC)

- Placing limit and market orders

- Holding outcome tokens (YES / NO or multi-outcome)

- Settling positions post-resolution



Users do **not** interact directly with oracles.



---



### 2. Frontend & Wallet Layer

Responsibilities:

- Market discovery

- Order placement (EIP-712 signed orders or on-chain txs)

- Position visualization

- Settlement claims



Operational note:

Frontend must be capable of **disabling actions** (new orders, new markets) during incidents.



---



### 3. Orderbook Exchange Engine

This is the core trading system.



Responsibilities:

- Maintain orderbook per outcome

- Match limit and market orders

- Enforce tick size, min order size, max exposure

- Charge fees and rebates



Key properties:

- Explicit spreads

- Visible depth

- Deterministic matching rules



This design allows **better price discovery** and **tighter risk controls** than AMMs.



---



### 4. Conditional Token System

Each market mints conditional tokens representing outcomes.



Examples:

- YES / NO tokens

- Candidate A / Candidate B / Candidate C



Properties:

- Tokens are non-redeemable until oracle resolution

- Tokens represent claims on collateral post-settlement

- Supply expands/contracts based on trading



Operational risk:

Incorrect minting or redemption logic leads to insolvency.



---



### 5. Oracle Infrastructure



Prediction markets require **objective truth resolution**.



This system assumes:

- **UMA Optimistic Oracle** for final resolution

- Optional **Chainlink feeds** for reference data



Oracle flow:

1\. Market reaches end time

2\. Resolution is proposed

3\. Dispute window opens

4\. Final outcome is confirmed or escalated



Ops must monitor oracle status continuously.



---



### 6. Governance & Ops Authority



Certain actions must be **explicitly centralized** for safety:

- Pause markets

- Restrict new positions

- Cap exposure

- Trigger dispute escalation



Governance actions must be:

- Logged

- Justified

- Reversible where possible



---



### 7. Monitoring & Indexing Layer



Operators rely on real-time data from:

- Orders and fills

- Open interest

- Oracle state

- Dispute frequency

- Liquidity health



Monitoring feeds into:

- Alerts

- Runbooks

- Governance decisions



---



## High-Level System Flow



1\. Market is created with parameters

2\. Users deposit collateral

3\. Orders are placed and matched

4\. Outcome tokens are traded

5\. Market closes at expiry

6\. Oracle resolution begins

7\. Disputes are handled if needed

8\. Final settlement occurs

9\. Post-mortem review is conducted



---



## Operational Design Principles



- **Orderbooks over AMMs** for control and transparency

- **Optimistic oracles** with dispute-based security

- **Human-in-the-loop governance** for edge cases

- **Runbooks before automation**

- **Fail-safe defaults** over liveness



---



## What This Architecture Optimizes For



- Market integrity

- Fair price discovery

- Dispute resilience

- Operator observability

- User trust



This system intentionally trades some decentralization for **operational safety**.



