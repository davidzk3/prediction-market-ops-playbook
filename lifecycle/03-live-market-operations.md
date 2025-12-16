\# Live Market Operations



This section describes how prediction markets are actively operated once trading is live.  

The focus is on real-time monitoring, operational controls, and intervention mechanisms required to maintain fair, liquid, and resolvable markets.



Live market operations sit at the intersection of trading activity, oracle readiness, and risk management.



---



\## Objectives



During live trading, the operations team is responsible for:



\- Maintaining continuous and orderly markets

\- Monitoring liquidity and price formation

\- Detecting manipulation or abnormal behavior

\- Ensuring oracle assumptions remain valid

\- Preparing markets for clean resolution



---



\## Core Operational Domains



\### 1. Trading Activity Monitoring



Operators continuously monitor:



\- Orderbook depth and spread

\- Trade frequency and volume

\- Price volatility relative to implied probability

\- Concentration of open interest



Key signals:

\- Sudden price jumps without external news

\- One-sided order flow dominance

\- Rapid cancellation or spoof-like behavior



These signals feed both automated alerts and human review.



---



\### 2. Liquidity Health



Liquidity is critical for meaningful price discovery.



Operational checks include:

\- Bid/ask spread thresholds

\- Minimum resting liquidity requirements

\- Maker participation consistency

\- Slippage on market orders



If liquidity degrades:

\- Maker incentives may be adjusted

\- Market exposure limits may be reduced

\- New position sizes may be capped



---



\### 3. Price Integrity \& Fairness



Operators ensure prices reflect collective information rather than manipulation.



Ongoing checks:

\- Cross-market price consistency (related outcomes)

\- Correlation with external reference markets (where applicable)

\- Detection of wash trading or self-matching



Suspicious behavior is escalated to runbooks covering:

\- Market manipulation

\- Position concentration abuse

\- Coordinated trading patterns



---



\### 4. Oracle Readiness \& Assumptions



Even before resolution, oracle assumptions must remain valid.



Operators track:

\- Oracle data sources availability

\- Expected resolution conditions clarity

\- Event framing consistency with real-world outcomes



If ambiguity or risk emerges:

\- Markets may be flagged for review

\- Trading warnings may be issued

\- Market parameters may be frozen



---



\### 5. Risk Controls \& Guardrails



Live risk controls include:



\- Maximum position size per user

\- Market-wide exposure caps

\- Volatility-based throttles

\- Temporary trading halts (soft pauses)



These controls are designed to:

\- Prevent cascading liquidations

\- Avoid oracle manipulation incentives

\- Limit systemic risk across markets



---



\### 6. Human-in-the-Loop Oversight



While many checks are automated, final decisions remain human-led.



Operators are responsible for:

\- Reviewing alerts and anomalies

\- Approving escalations

\- Coordinating with oracle and governance teams

\- Documenting decisions and rationale



All actions are logged for post-market review.



---



\## Escalation Triggers



Common escalation triggers include:



\- Extreme price divergence from expectations

\- Sustained low liquidity

\- Suspected oracle manipulation incentives

\- External events invalidating market assumptions



Escalations follow predefined runbooks and governance policies.



---



\## Outputs



At the end of the live trading phase, operators ensure:



\- Market state is stable

\- Oracle resolution conditions are clear

\- No unresolved incidents remain

\- All interventions are documented



This prepares the market for the resolution and dispute phase.



