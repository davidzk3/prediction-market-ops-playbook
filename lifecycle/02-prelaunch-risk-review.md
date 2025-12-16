\# Pre-Launch Risk Review



\## Purpose



The Pre-Launch Risk Review is a mandatory operational checkpoint conducted \*\*before any prediction market is opened for trading\*\*.  

Its goal is to ensure that markets are \*\*safe to launch\*\*, \*\*resolvable\*\*, \*\*legally defensible\*\*, and \*\*operationally supportable\*\*.



No market proceeds to launch unless all required checks pass or explicit governance approval is granted.



---



\## When This Review Occurs



\- After market proposal approval

\- Before orderbook activation

\- Before liquidity incentives are enabled

\- Before public announcement or UI exposure



---



\## Risk Review Checklist



\### 1. Market Definition Risk



\*\*Objective:\*\* Ensure the question is precise, unambiguous, and objectively resolvable.



Checks:

\- Outcome wording is binary or clearly enumerable

\- Resolution criteria are unambiguous

\- No subjective interpretation required

\- Time bounds are explicit

\- Event source is publicly verifiable



Fail Conditions:

\- Ambiguous phrasing

\- Multiple interpretations of outcomes

\- Undefined resolution source



---



\### 2. Oracle \& Resolution Risk



\*\*Objective:\*\* Ensure the market can be reliably resolved.



Checks:

\- Oracle provider assigned (e.g. UMA Optimistic Oracle)

\- Clear resolution data source defined

\- Proposer incentives confirmed

\- Disputer incentives confirmed

\- Dispute window parameters verified

\- Fallback oracle path documented



Fail Conditions:

\- No credible data source

\- Oracle SLA undefined

\- No dispute escalation path



---



\### 3. Market Structure Risk (Orderbook)



\*\*Objective:\*\* Validate the orderbook design will not create systemic risk.



Checks:

\- Tick size appropriate for expected volatility

\- Minimum order size defined

\- Max position size limits set

\- Market depth expectations reviewed

\- Spread tolerance thresholds configured



Fail Conditions:

\- Excessively tight ticks on volatile events

\- No position caps

\- No spread safeguards



---



\### 4. Liquidity \& Incentive Risk



\*\*Objective:\*\* Prevent unhealthy liquidity dynamics at launch.



Checks:

\- Initial liquidity source identified

\- Incentives aligned with CAKE emissions policy

\- No single LP dominance expected

\- Incentive duration defined

\- Liquidity withdrawal safeguards enabled



Fail Conditions:

\- One-sided liquidity incentives

\- Over-concentration risk

\- Incentives encouraging wash trading



---



\### 5. Market Manipulation Risk



\*\*Objective:\*\* Reduce exploitability and bad actor incentives.



Checks:

\- Wash trading detection enabled

\- Self-trading limits configured

\- Large order monitoring active

\- Pre-resolution trading controls defined

\- Known manipulation vectors reviewed



Fail Conditions:

\- No surveillance in place

\- No intervention authority defined



---



\### 6. Legal \& Compliance Risk



\*\*Objective:\*\* Ensure regulatory and reputational safety.



Checks:

\- Market category reviewed

\- Restricted jurisdictions identified

\- Political or sensitive events escalated

\- Compliance sign-off recorded

\- Disclosure language prepared



Fail Conditions:

\- Unreviewed regulated event

\- Jurisdictional ambiguity

\- Missing disclosures



---



\### 7. Operational Readiness



\*\*Objective:\*\* Confirm the ops team can support the market post-launch.



Checks:

\- On-call ownership assigned

\- Runbooks linked

\- Incident response paths defined

\- Monitoring dashboards active

\- Escalation contacts confirmed



Fail Conditions:

\- No operational owner

\- No monitoring coverage

\- No escalation policy



---



\## Approval Process



A market is approved when:

\- All checklist items pass \*\*OR\*\*

\- Explicit governance override is documented



Approval requires sign-off from:

\- Operations

\- Product

\- Risk / Compliance (where applicable)



---



\## Output Artifacts



Upon approval, the following are generated:

\- Market Risk Review record

\- Linked runbooks

\- Monitoring configuration

\- Oracle resolution parameters

\- Market launch ticket



---



\## Related Documents



\- `lifecycle/01-market-creation.md`

\- `lifecycle/03-resolution-and-disputes.md`

\- `runbooks/market-creation-checklist.md`

\- `runbooks/market-manipulation-detection.md`

\- `governance/escalation-policy.md`



---



\## Key Principle



\*\*No market should fail at resolution because of something that could have been caught before launch.\*\*



The Pre-Launch Risk Review exists to enforce that standard.



