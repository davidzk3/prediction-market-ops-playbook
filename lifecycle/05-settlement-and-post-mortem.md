\# Settlement \& Post-Mortem



This phase covers the finalization of markets after resolution and the structured review process that follows.  

Its goal is to ensure \*\*correct payouts\*\*, \*\*clear accountability\*\*, and \*\*continuous improvement\*\* of market operations.



Settlement is irreversible. Post-mortems are how operational quality compounds over time.



---



\## Settlement Preconditions



Before settlement is executed, operators must confirm:



\- Oracle resolution has finalized and is immutable

\- Any dispute windows have fully closed

\- No active market pauses remain

\- All intervention logs are complete

\- Indexers and balances are in sync



If any condition fails, settlement must be delayed.



---



\## Settlement Execution Flow



\### 1. Resolution Confirmation



Operators verify:

\- Winning outcome(s)

\- Oracle data source and timestamp

\- Matching between oracle result and market framing

\- Consistency across redundant data feeds (if applicable)



Resolution confirmation is recorded before execution.



---



\### 2. Trading Closure



Actions:

\- Disable order matching

\- Block new position creation

\- Allow position reductions only if applicable

\- Lock final prices



This ensures no state changes during payout calculation.



---



\### 3. Payout Calculation



For each account:

\- Determine net outcome token balances

\- Apply payout logic based on winning outcome

\- Account for fees, rebates, and incentives

\- Validate totals against locked collateral



Any discrepancy triggers a settlement halt.



---



\### 4. On-Chain Settlement



Execution steps:

\- Burn losing outcome tokens

\- Redeem winning outcome tokens for collateral

\- Distribute collateral to wallets

\- Emit settlement events



Settlement is atomic wherever possible.



---



\### 5. Post-Settlement Validation



Operators confirm:

\- No residual balances remain

\- All events emitted correctly

\- Wallet balances match expected payouts

\- No stuck or reverted transactions



Only after validation is the market marked as \*\*Settled\*\*.



---



\## Post-Mortem Objectives



Post-mortems are mandatory for:

\- High-volume markets

\- Markets with interventions

\- Markets with disputes

\- Any incident-triggered settlement



They are blameless and systems-focused.



---



\## Post-Mortem Review Areas



\### 1. Market Design Review



Evaluate:

\- Clarity of market question

\- Outcome framing accuracy

\- Resolution criteria precision

\- User confusion or misinterpretation



Feedback informs future market curation.



---



\### 2. Trading \& Liquidity Health



Analyze:

\- Orderbook depth over time

\- Spread stability

\- Liquidity concentration

\- Maker participation quality



Identify where incentives or parameters underperformed.



---



\### 3. Risk \& Intervention Analysis



Review:

\- Alerts triggered

\- Interventions applied

\- Timing and effectiveness

\- Any missed signals



Adjust thresholds and playbooks accordingly.



---



\### 4. Oracle Performance



Assess:

\- Oracle latency

\- Data consistency

\- Dispute frequency

\- Alignment with real-world outcomes



Oracle reliability is critical to platform credibility.



---



\### 5. User Impact



Measure:

\- User complaints or tickets

\- Dispute participation

\- Settlement delays

\- Trust-impacting events



High-impact issues require public communication.



---



\## Outputs \& Documentation



Each post-mortem produces:

\- A written summary

\- Timeline of key events

\- Root cause analysis (if applicable)

\- Action items with owners



Documents are stored and indexed for future reference.



---



\## Governance \& Feedback Loop



Significant findings may trigger:

\- Parameter updates

\- Market template changes

\- Oracle provider review

\- Governance proposals



Post-mortems directly influence system evolution.



---



\## Market Archival



After completion:

\- Market is marked Archived

\- Data remains queryable

\- Results are immutable

\- Operational logs are retained



Archival closes the lifecycle and feeds historical analytics.



