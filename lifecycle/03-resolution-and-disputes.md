\# Resolution and Disputes

\## Prediction Market Lifecycle — Phase 3



This document defines how markets are resolved, disputed, and settled

in an orderbook-based prediction market using external oracles.



Resolution is the highest-risk phase of the market lifecycle.



---



\## Objectives of the Resolution Phase



Ops must ensure:

\- Correct outcome determination

\- Transparent resolution logic

\- Fair handling of disputes

\- Timely settlement of positions

\- Protection against manipulation



---



\## Resolution Preconditions



Before resolution begins, Ops verifies:



\- Trading is fully halted

\- No open orders remain

\- Final prices are frozen

\- Oracle source is available and responsive

\- Resolution timestamp has passed



Only then does resolution proceed.



---



\## Oracle-Based Resolution Model



The system relies on an external oracle framework

(e.g. UMA Optimistic Oracle, Chainlink feeds).



Resolution follows an optimistic pattern:



1\. Outcome is proposed

2\. Dispute window opens

3\. Outcome is finalized if undisputed



---



\## Outcome Proposal



\### Who Proposes



Outcomes may be proposed by:

\- Protocol operators

\- Permissioned proposers

\- Automated oracle adapters



The proposer submits:

\- Outcome value

\- Reference source

\- Timestamp

\- Supporting evidence



---



\## Dispute Window



Once proposed, a fixed dispute window opens.



Typical duration:

\- 24–72 hours depending on market sensitivity



During this window:

\- Trading remains closed

\- Funds are locked

\- Outcome can be challenged



---



\## Dispute Triggers



Disputes may occur if:

\- Outcome is factually incorrect

\- Oracle source is ambiguous

\- Event definition is unclear

\- Evidence contradicts proposal



Ops monitors disputes continuously.



---



\## Dispute Process



If disputed:



1\. Dispute bond is posted

2\. Oracle escalation is triggered

3\. Additional data sources are consulted

4\. Final ruling is produced



Disputes are expensive by design to prevent spam.



---



\## Escalation and Arbitration



Escalation paths may include:

\- UMA Data Verification Mechanism

\- Decentralized arbitration

\- Multi-oracle consensus checks



Ops does NOT decide outcomes directly.



Ops ensures process integrity.



---



\## Finalization



Once:

\- Dispute window expires without dispute, or

\- Arbitration resolves the dispute



The outcome is finalized and immutable.



At this point:

\- Outcome is locked

\- Settlement begins



---



\## Settlement Process



Settlement includes:



\- Winning positions credited

\- Losing positions closed

\- Fees distributed

\- Treasury updated



Settlement is atomic and auditable.



---



\## Edge Case Handling



Ops prepares for edge cases such as:



\- Event cancellation

\- Ambiguous outcomes

\- Delayed oracle data

\- Conflicting data sources



Fallback rules must be predefined

and published before market launch.



---



\## Post-Resolution Review



After settlement:



\- Market metrics are reviewed

\- Dispute costs analyzed

\- Oracle performance evaluated

\- Incident reports written if needed



Lessons feed back into future market design.



---



\## User Communication



Throughout resolution, Ops ensures:



\- Clear status updates

\- Transparent dispute explanations

\- Predictable timelines



Trust is maintained through clarity.



---



\## Summary



Resolution is where:

\- Credibility is tested

\- Legal risk concentrates

\- User trust is earned or lost



Strong resolution processes

are the foundation of prediction markets.



