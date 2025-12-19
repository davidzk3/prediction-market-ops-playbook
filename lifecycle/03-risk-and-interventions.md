# Risk Management & Interventions



This document defines how operational risk is identified, assessed, and actively mitigated during live prediction market trading.



Unlike passive monitoring, this phase focuses on \*\*decision-making under uncertainty\*\* and \*\*timely intervention\*\* to protect market integrity, liquidity, and resolvability.



---



## Risk Categories



Live prediction markets face several overlapping risk domains.



### 1. Market Microstructure Risk



Risks arising from orderbook dynamics:



- Thin or one-sided liquidity

- Excessive bid-ask spreads

- Orderbook manipulation (spoofing, layering)

- Price gaps driven by single actors



These risks directly impact price discovery and user trust.



---



### 2. Concentration & Exposure Risk



Key indicators:

- High open interest concentration in a single account

- Large directional bets close to resolution

- Correlated exposure across related markets



High concentration increases:

- Manipulation incentives

- Oracle attack surface

- Dispute likelihood



---



### 3. Oracle-Linked Risk



Prediction markets rely on **future oracle truth**, not real-time pricing.



Risks include:

- Ambiguous resolution criteria

- Oracle data delays or outages

- Incentivized oracle manipulation

- Event framing mismatches with real-world outcomes



Oracle risk escalates sharply as markets approach resolution.



---



### 4. Behavioral & Manipulation Risk



Observed behaviors:

- Wash trading to influence price perception

- Coordinated trading across multiple wallets

- Artificial volatility creation

- Price anchoring before public news releases



Detection relies on pattern recognition rather than single metrics.



---



### 5. Systemic & Operational Risk



Includes:

- Infrastructure degradation

- Indexer lag or data inconsistency

- Alerting failures

- Operator overload during high-activity events



These risks affect the platform’s ability to respond in time.



---



## Intervention Principles



All interventions follow these principles:



- **Proportional**: Match severity to risk level

- **Reversible where possible**

- **Transparent post-action**

- **Documented for auditability**



Interventions are never arbitrary or retroactive.



---



## Intervention Toolkit



### 1. Soft Interventions



Used when risk is emerging but not critical.



Examples:

- Reduce maximum position size

- Increase margin or collateral requirements

- Throttle order placement frequency

- Issue market warnings to users



Goal: slow escalation without halting markets.



---



### 2. Liquidity Controls



Applied when orderbook health degrades.



Actions include:

- Temporarily increasing maker incentives

- Disabling certain order types

- Restricting market orders

- Narrowing eligible trading pairs



Liquidity actions aim to restore orderly trading.



---



### 3. Trading Restrictions



Used when manipulation or systemic risk is likely.



Examples:

- Freeze new positions

- Restrict position increases (allow reductions only)

- Cap exposure per account

- Temporarily pause matching engine



These controls are logged and time-bound.



---



### 4. Market Pause



A market pause is a **last-resort intervention**.



Triggers:

- Severe manipulation evidence

- Oracle integrity compromise

- External event invalidating market assumptions

- System instability preventing fair execution



During a pause:

- Trading is halted

- Positions remain intact

- Resolution conditions are reviewed



---



## Escalation Flow



1\. Automated alert triggers

2\. Operator review and classification

3\. Cross-functional consultation (risk, oracle, governance)

4\. Intervention decision

5\. Execution and logging

6\. Post-action monitoring



No single operator acts unilaterally on high-severity events.



---



## Documentation & Accountability



For every intervention, operators record:



- Timestamp

- Market ID

- Risk category

- Action taken

- Expected impact

- Follow-up requirements



These records feed:

- Post-market reviews

- Governance reporting

- Future parameter tuning



---



## Transition to Resolution Phase



Before allowing markets to proceed to resolution:



- All active interventions must be resolved or justified

- Oracle readiness must be confirmed

- No unresolved manipulation investigations remain



This ensures clean settlement and minimizes disputes.



