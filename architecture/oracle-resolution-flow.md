\# Oracle Resolution Flow

\## Resolution, Disputes, and Operational Control



This document describes how prediction markets are resolved using external oracles, how disputes are handled, and how operators monitor and intervene during the resolution phase.



The design aligns with:

\- UMA Optimistic Oracle (as used by Polymarket)

\- Orderbook-based prediction markets

\- Production-grade operational requirements



---



\## Why Oracle Resolution Is the Highest-Risk Phase



Market resolution is where:

\- Capital is redistributed

\- Incentives to attack peak

\- Legal, reputational, and trust risks concentrate



Most catastrophic failures in prediction markets occur \*\*after trading has ended\*\*, not during it.



---



\## High-Level Resolution Flow



1\. Market reaches expiry condition

2\. Trading halts automatically

3\. Oracle request is submitted

4\. Oracle proposer submits outcome

5\. Dispute window opens

6\. Outcome is finalized

7\. Settlement executes

8\. Post-mortem checks run



Each step has \*\*explicit ops hooks\*\*.



---



\## Step 1: Market Expiry



Trigger conditions:

\- Timestamp reached

\- External event concluded

\- Governance-forced resolution



Actions:

\- Disable new order placement

\- Allow order cancellations

\- Snapshot open positions



This prevents last-second manipulation.



---



\## Step 2: Oracle Request Creation



The protocol submits:

\- Market ID

\- Question text

\- Expected answer format

\- Resolution timestamp

\- Bond requirement



This request is immutable once submitted.



Ops monitors:

\- Request correctness

\- Timestamp alignment

\- Question ambiguity



---



\## Step 3: Oracle Proposal (Optimistic Phase)



A proposer submits:

\- Outcome value (YES / NO / multi-outcome index)

\- Stake/bond



Assumption:

> The proposal is correct unless challenged.



This minimizes oracle latency.



---



\## Step 4: Dispute Window



During the dispute window:

\- Any actor may challenge the proposal

\- A higher bond is required

\- Dispute escalates to oracle governance



Ops monitors:

\- Dispute frequency

\- Repeated challenger behavior

\- Market exposure during dispute



High dispute rates are \*\*trust signals\*\*.



---



\## Step 5: Dispute Resolution (If Triggered)



If disputed:

\- Oracle governance resolves the outcome

\- Final decision is binding

\- Disputing bonds are redistributed



Operational risks:

\- Extended resolution delays

\- Media-sensitive outcomes

\- Liquidity freezes



Mitigations:

\- Pre-defined max dispute duration

\- Emergency comms playbooks

\- Partial settlement blocking



---



\## Step 6: Finalization



Once resolved:

\- Oracle marks outcome as final

\- No further disputes allowed

\- Settlement becomes executable



This is the \*\*point of no return\*\*.



---



\## Step 7: Market Settlement



Settlement actions:

\- Winning outcome tokens redeem at par

\- Losing outcomes redeem to zero

\- Fees are applied

\- Maker incentives finalized



Settlement is deterministic and auditable.



---



\## Step 8: Post-Resolution Ops Checks



After settlement:

\- Verify collateral conservation

\- Validate fee accounting

\- Check abnormal profit patterns

\- Flag suspicious resolution behavior



These checks feed:

\- Governance review

\- Future parameter tuning

\- Market curator reputation



---



\## Monitoring Metrics



Key oracle-related metrics:

\- Time to proposal

\- Dispute rate per market

\- Average resolution duration

\- Bond size vs market size

\- Oracle latency near expiry



These metrics should be dashboarded.



---



\## Common Failure Modes



\### Oracle Delay

Mitigation:

\- UI warnings

\- Trading halt extensions

\- Clear comms to users



---



\### Bad Question Design

Mitigation:

\- Pre-launch question review

\- Strict phrasing templates

\- Governance veto power



---



\### Coordinated Disputes

Mitigation:

\- Escalation thresholds

\- Governance intervention

\- Temporary market category freeze



---



\## Operator Intervention Rights



Operators may:

\- Pause settlement (not resolution)

\- Block new markets in category

\- Flag oracle anomalies

\- Trigger emergency governance



Operators may NOT:

\- Override oracle outcomes

\- Manually select winners

\- Alter resolved data



This separation preserves trust.



---



\## Summary



Oracle resolution is:

\- The most sensitive phase

\- The most reputationally risky

\- The most ops-intensive



Strong prediction markets treat resolution as an \*\*operations product\*\*, not a background process.



