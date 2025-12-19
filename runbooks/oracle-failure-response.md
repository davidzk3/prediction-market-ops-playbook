# Runbook: Oracle Failure Response



## Purpose



This runbook defines the operational response when an oracle **fails**, not merely delays.  

Oracle failure represents a breakdown in the mechanism used to resolve market outcomes and poses systemic risk to market integrity.



This runbook applies when:

- Oracle returns incorrect or contradictory data

- Oracle cannot be trusted to resolve an outcome

- Resolution assumptions are violated

- External data sources are compromised



---



## Definition of Oracle Failure



An oracle failure occurs when **resolution correctness cannot be guaranteed**, including:



- Conflicting oracle proposals

- Disputed resolution with unresolved escalation

- External data source proven incorrect or manipulated

- Oracle contract bug or misconfiguration

- Chain-level failure preventing oracle execution



Oracle failure is **not**:

- Normal resolution delay

- Slow proposer participation

- Expected optimistic dispute windows



---



## Detection & Signals



### Critical Indicators

- Multiple contradictory resolution proposals

- Repeated disputes without convergence

- Oracle feed deviates materially from authoritative sources

- Chain reorg impacts oracle transactions

- Oracle contract halted or reverted



### Monitoring Sources

- Oracle proposal history

- Dispute count per market

- Off-chain reference source verification

- Governance alerting channels



---



## Severity Classification



| Severity | Description |

|--------|------------|

| High | Single-market oracle failure |

| Critical | Multi-market oracle failure |

| Systemic | Oracle framework compromised |



---



## Immediate Actions (First 30 Minutes)



### Step 1: Freeze Market State

- Disable settlement execution

- Prevent claim withdrawals

- Pause new positions if market not archived



### Step 2: Preserve Evidence

- Snapshot oracle state

- Archive external reference data

- Record timestamps and proposal hashes



### Step 3: Notify Stakeholders

- Ops Lead

- Risk / Protocol Lead

- Governance or Admin Multisig

- Public status page (if applicable)



---



## Root Cause Assessment



Operators must determine:



- Is failure **data-related** or **mechanism-related**?

- Is failure isolated or systemic?

- Can resolution correctness be restored without governance action?



Common root causes:

- Ambiguous market specification

- Oracle incentive misalignment

- External data inconsistency

- Contract upgrade or configuration error



---



## Resolution Paths



### Path A: Governance-Driven Resolution

Used when:

- Oracle trust assumptions are broken

- Automated resolution is unsafe



Actions:

- Governance vote or multisig decision

- Publish resolution rationale

- Execute manual settlement transaction



### Path B: Market Invalidation

Used when:

- Outcome cannot be objectively determined

- Market wording is irreparably ambiguous



Actions:

- Invalidate market

- Refund collateral proportionally

- Close market permanently



### Path C: Oracle Replacement (Rare)

Used only when:

- Backup oracle system exists

- Governance-approved failover is predefined



---



## Communication Guidelines



All communication must:

- Avoid assigning blame prematurely

- Explain why automated resolution failed

- Provide clear next steps and timelines



Required disclosures:

- Impacted markets

- Resolution approach

- Expected settlement timing



---



## Settlement Execution



Once resolution path is approved:

- Execute settlement or refund logic

- Verify balances post-settlement

- Enable withdrawals

- Archive market



---



## Post-Incident Review



Required documentation:

- Failure root cause

- Detection latency

- Operator actions timeline

- User impact assessment

- Preventive changes



Potential follow-ups:

- Oracle incentive redesign

- Market creation checklist updates

- SLA tightening

- Governance process refinement



---



## Key Principles



- Capital preservation > speed

- Fairness over automation

- Governance legitimacy over convenience

- Trust recovery is an operational responsibility



Oracle failure is rare — mishandling it is catastrophic.



