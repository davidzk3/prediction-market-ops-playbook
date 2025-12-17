\# Oracle Design for an Orderbook Based Prediction Market



This document explains a realistic oracle setup for an orderbook based prediction market on an EVM chain.



The core operations goal is simple:

\- markets must resolve correctly

\- resolution must be defensible and auditable

\- the exchange must remain tradeable while resolution is pending

\- disputes must be handled with clear timers and escalation paths



\## 1. What the oracle must answer



A prediction market ultimately needs an on chain answer for:

\- outcome value (YES, NO, or a multi outcome index)

\- an effective timestamp (when the outcome is considered final)

\- finality guarantees (how disputes are handled)



In an orderbook market, trading can continue until a known cutoff, but settlement must be blocked until the oracle finalizes.



\## 2. Recommended oracle pattern



A typical production pattern is a dual layer oracle approach:



Primary data source layer

\- Chainlink Data Feeds where available (price, rates, indices)

\- Chainlink Functions where a feed does not exist and you want a programmable off chain fetch

\- other canonical sources if needed (but you want deterministic and well scoped sources)



Finality and dispute layer

\- UMA Optimistic Oracle (OO) or similar optimistic mechanism

\- optimistic oracles provide a dispute window and an economic security model

\- the contract enforces time windows and finalization rules on chain



Why this combination works operationally

\- Chainlink gives low latency updates and broad coverage for numeric data

\- UMA OO provides a robust dispute and finality process for “what happened” questions

\- the system can standardize resolution handling across many market types



\## 3. Core contracts and components



Market contracts

\- MarketFactory creates markets with parameters

\- Market contracts define payout logic and resolution path



Exchange contract (orderbook)

\- holds collateral escrow logic (or integrates with a vault)

\- matches orders and records fills

\- locks trading at a cutoff timestamp

\- prevents settlement until market is resolved



Collateral vault

\- USDC (or chain native stable) custody rules

\- fee accounting (taker, maker, protocol)

\- withdrawal rules depend on market state



Oracle adapter

\- normalizes oracle responses into a single “resolved outcome”

\- validates freshness and allowed sources

\- enforces time windows (no early resolve, no resolve before cutoff)

\- emits events for monitoring



Indexer and monitoring

\- watches all market events

\- tracks oracle request state, disputes, finalization

\- triggers ops alerts when resolution deviates from expected



\## 4. Oracle request lifecycle (high level)



1\) Market created

\- factory records market metadata

\- adapter precomputes how resolution will be requested



2\) Trading active

\- orderbook matches orders

\- oracle layer only needs to be monitored for uptime and feed freshness



3\) Trading cutoff

\- market is locked for new orders (or matching stops)

\- positions are frozen for settlement



4\) Resolution request

\- adapter submits request to UMA OO OR reads Chainlink feed if the market is purely numeric and deterministic

\- request includes identifier and ancillary data (what to check, sources, rules)



5\) Dispute window

\- UMA dispute window open

\- if disputed, resolution goes to escalation process (UMA voting)



6\) Finalize

\- resolved outcome written on chain

\- settlement can execute



\## 5. Operational safeguards



Freshness checks

\- oracle adapter rejects stale values beyond a configured freshness threshold

\- monitoring triggers “oracle delay” runbook if freshness is breached



Source integrity

\- fixed allowed sources per market type

\- no dynamic “any URL” without strict allowlists



Time window enforcement

\- cannot resolve before cutoff timestamp

\- cannot settle until finalization timestamp plus safety buffer



Circuit breakers

\- ops can pause settlement if invalid resolution is detected

\- trades may already be locked but settlement should not proceed



Auditability

\- store oracle request parameters on chain or emit them in events

\- store an off chain evidence bundle in an incident ticket when disputed



\## 6. What ops monitors daily



Oracle health

\- freshness gap

\- request volume

\- dispute rate

\- time to finalize



Market risk

\- unresolved markets backlog

\- markets approaching cutoff without a resolution plan

\- markets with abnormal price moves near cutoff



Settlement safety

\- settlement attempts blocked

\- settlement retries

\- unexpected payout distributions



\## 7. Failure modes and expected responses



Oracle delay

\- trigger runbook oracle delay

\- pause settlement if required

\- communicate timeline to users



Invalid resolution

\- trigger runbook invalid resolution

\- freeze settlement and withdrawals

\- escalate to governance emergency process



High dispute frequency

\- review market templates and sources

\- tighten eligibility for certain market types

\- adjust dispute bond incentives if applicable



