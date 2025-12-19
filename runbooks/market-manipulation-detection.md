# Market Manipulation Detection Runbook

## Orderbook-Based Prediction Markets



This runbook defines how the operations team detects,

investigates, and mitigates market manipulation in

orderbook-based prediction markets.



Manipulation undermines price discovery and trust.

Detection must be systematic, not subjective.



---



## What Is Market Manipulation?



Market manipulation refers to intentional behavior

designed to distort prices, liquidity, or perceived

probabilities without reflecting genuine information.



In prediction markets, manipulation often targets:

- Price signals

- Liquidity perception

- Resolution incentives



Not all aggressive trading is manipulation.



---



## Core Manipulation Categories



### 1. Wash Trading

Repeated self-trading to inflate volume or signal interest.



Indicators:

- Repeated matched orders between the same wallets

- High volume with low net position change

- Abnormally tight timing patterns



---



### 2. Spoofing

Placing large orders with intent to cancel before execution.



Indicators:

- Large visible orders repeatedly canceled

- Short-lived depth spikes

- Price movement without execution



---



### 3. Liquidity Signaling Attacks

Artificially creating the appearance of deep liquidity.



Indicators:

- Sudden liquidity appearance and withdrawal

- One-sided depth concentration

- Liquidity vanishing near resolution



---



### 4. Outcome Price Manipulation

Forcing prices toward a desired outcome near resolution.



Indicators:

- Large late-stage order flow

- Price divergence from external information

- Aggressive trading during oracle reporting windows



---



### 5. Oracle Incentive Exploitation

Trading behavior aligned with expected oracle weaknesses.



Indicators:

- Trading spikes around oracle update delays

- Positions aligned with disputed outcomes

- Correlation between oracle uncertainty and volume



---



## Detection Signals



Ops monitors the following signals continuously:



### Orderbook Signals

- Bid-ask spread anomalies

- Depth concentration ratios

- Cancel-to-fill ratios

- Order lifetime distributions



### Trading Behavior Signals

- Wallet-level churn rates

- Position open/close symmetry

- Repeated small-volume executions

- Time-based clustering



### Market-Level Signals

- Price deviation from consensus

- Volume spikes without news

- Liquidity cliffs near key events



---



## Alert Thresholds



Alerts are triggered when:



- Cancel-to-fill ratio exceeds threshold

- Single wallet controls dominant depth

- Volume spikes exceed baseline deviation

- Price diverges materially from reference signals



Thresholds are adaptive, not static.



---



## Investigation Workflow



When an alert triggers:



1\. Assign incident owner

2\. Identify affected markets

3\. Isolate suspicious wallets

4\. Review order and trade history

5\. Cross-check external information

6\. Assess intent vs normal behavior



Ops collaborates with engineering and compliance if needed.



---



## Immediate Mitigation Actions



Depending on severity:



- Increase margin requirements

- Reduce maximum order size

- Temporarily widen tick size

- Pause affected markets

- Flag wallets for enhanced monitoring



Mitigation must minimize collateral damage.



---



## Escalation Criteria



Escalate to Severity 1 incident if:



- Manipulation affects resolution

- User funds are materially impacted

- Oracle integrity is threatened

- Legal or regulatory risk emerges



Escalation follows the Incident Response Runbook.



---



## Documentation and Evidence



All investigations must log:



- Wallet addresses

- Time windows

- Order and trade samples

- Mitigation actions taken

- Final determination



Evidence must be reproducible.



---



## Post-Incident Review



After confirmed manipulation:



- Update detection thresholds

- Improve monitoring logic

- Adjust market design if needed

- Document lessons learned



Repeated patterns trigger structural changes.



---



## Key Metrics Tracked



Ops tracks:



- Manipulation alert frequency

- False positive rate

- Time to detection

- Time to mitigation

- Market integrity score



These metrics inform quarterly reviews.



---



## Summary



Healthy prediction markets require:



- Transparent orderbooks

- Disciplined monitoring

- Rapid intervention

- Fair enforcement



Market integrity is an operational responsibility, not just a technical one.



