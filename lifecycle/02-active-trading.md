\# Active Trading

\## Prediction Market Lifecycle — Phase 2



This document defines operational responsibilities during live trading

for an orderbook-based prediction market.



Once trading is live, Ops shifts from setup to continuous monitoring,

intervention, and incident response.



---



\## Objectives of Active Trading



During this phase, Ops must:

\- Maintain orderly markets

\- Ensure fair price discovery

\- Detect manipulation or abuse

\- Preserve oracle integrity

\- Minimize user-facing incidents



---



\## Live Market Monitoring



Ops monitors markets in real time across four dimensions.



\### 1. Liquidity Health



Key indicators:

\- Bid–ask spread

\- Orderbook depth at top levels

\- Liquidity concentration by account

\- Order cancellation rates



Warning signs:

\- Sudden spread widening

\- One-sided books

\- Single LP dominance



---



\### 2. Price Behavior



Key indicators:

\- Volatility spikes

\- Price gaps between ticks

\- Divergence from external reference prices

\- Rapid repricing near resolution



Abnormal behavior triggers alerts.



---



\### 3. Trading Activity



Key indicators:

\- Trade frequency

\- Average trade size

\- New vs returning traders

\- Whale activity patterns



Ops flags:

\- Wash trading

\- Self-crossing orders

\- Coordinated behavior



---



\### 4. System Performance



Key indicators:

\- Order matching latency

\- Failed order submissions

\- Indexer lag

\- RPC error rates



Any degradation escalates immediately.



---



\## Risk Controls During Trading



Ops enforces dynamic controls when risk rises.



\### Common Interventions



\- Reduce max order size

\- Reduce max position per account

\- Increase minimum tick size

\- Temporarily widen spreads

\- Throttle order submission rate



Controls are applied surgically per market.



---



\## Market Pausing Logic



Markets may be paused if:

\- Oracle feed becomes unreliable

\- Extreme volatility breaks price discovery

\- System instability occurs

\- Exploit or manipulation is suspected



Pauses are:

\- Logged

\- Time-bounded

\- Communicated clearly to users



---



\## Information Asymmetry Management



Near resolution, informational edges increase.



Ops may:

\- Reduce leverage (if applicable)

\- Increase trading fees

\- Shorten trading hours

\- Close trading early



Goal: prevent last-minute exploitation.



---



\## User Protection Measures



Ops actively monitors for:

\- New user exploitation

\- Front-running patterns

\- Coordinated whale behavior



Accounts may be:

\- Flagged

\- Rate-limited

\- Escalated for review



---



\## Incident Response Flow



When anomalies occur:



1\. Detection via monitoring or alerts

2\. Immediate containment action

3\. Root cause analysis

4\. Internal escalation if needed

5\. External communication if user-facing

6\. Post-incident documentation



Ops owns this end-to-end.



---



\## Communications During Active Trading



Ops coordinates with:

\- Product (UX messaging)

\- Engineering (technical fixes)

\- Support (user inquiries)

\- Legal (edge cases)



Clear communication prevents panic.



---



\## Transition to Trading Close



Before trading closes:

\- Liquidity is monitored closely

\- Orderbook volatility is expected

\- Final trading cut-off is enforced



No new orders are accepted after cut-off.



---



\## Summary



Active trading is where:

\- Most incidents occur

\- Reputation is made or lost

\- Ops judgment matters most



Strong monitoring and decisive intervention

keep markets credible and fair.



