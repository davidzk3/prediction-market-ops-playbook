# Runbook: Invalid Resolution Handling



## Purpose



This runbook defines the operational response when a market is resolved \*\*incorrectly\*\*, whether due to oracle error, ambiguous market specification, or execution failure.



Invalid resolutions directly undermine platform credibility and must be handled with speed, transparency, and procedural rigor.



---



## What Is an Invalid Resolution



An invalid resolution occurs when the **final outcome does not reflect objective reality or agreed resolution rules**, including:



- Outcome contradicts authoritative data

- Oracle resolves wrong option

- Market wording allows multiple interpretations

- Resolution applied before dispute window closes

- Manual execution error during settlement



This runbook applies **after a resolution has been posted**, not before.



---



## Detection Triggers



### Internal Signals

- Ops review flags inconsistency

- Monitoring detects mismatch vs reference sources

- Settlement validation checks fail



### External Signals

- User disputes or appeals

- Community escalation

- Governance delegate alerts



---



## Immediate Actions (T+0 to 30 min)



### Step 1: Halt Settlement Finality

- Freeze withdrawals for affected market

- Prevent further claim executions

- Lock market state



### Step 2: Preserve Resolution State

- Snapshot resolution transaction

- Record oracle proposal and dispute history

- Archive off-chain reference data



### Step 3: Escalate Internally

Notify:

- Ops Lead

- Risk / Protocol Lead

- Governance or Admin Multisig



---



## Classification of Invalid Resolution



| Type | Description |

|----|------------|

| Data Error | Oracle source incorrect |

| Ambiguity | Market question unclear |

| Process Error | Dispute window bypassed |

| Execution Error | Settlement logic failure |



Classification determines remediation path.



---



## Resolution Paths



### Path A: Resolution Reversal (Preferred)

Used when:

- Correct outcome is objectively verifiable

- Governance or oracle framework allows override



Actions:

- Governance-approved reversal

- Re-execute settlement with correct outcome

- Reconcile balances



### Path B: Market Invalidation

Used when:

- Correct outcome cannot be determined

- Market question fundamentally flawed



Actions:

- Invalidate market

- Refund collateral to participants

- Close market permanently



### Path C: Partial Compensation (Rare)

Used when:

- Some users irreversibly settled

- Full rollback not possible



Actions:

- Compensation framework approval

- Treasury or insurance payout

- Public disclosure



---



## Communication Protocol



Public communication must include:

- Clear admission of error

- Impacted market IDs

- Chosen resolution path

- Timeline for settlement or refunds



Avoid:

- Assigning blame prematurely

- Vague explanations

- Silent resolution changes



---



## Settlement & Recovery



Once remediation is approved:

- Execute corrected settlement or refund

- Verify balances and claims

- Re-enable withdrawals

- Archive market



Post-settlement verification is mandatory.



---



## Post-Incident Review



Required analysis:

- Root cause

- Detection latency

- User impact

- Process breakdown

- Preventive controls



Potential improvements:

- Market creation checklist tightening

- Oracle dispute window enforcement

- Resolution confirmation delays

- Additional ops approval gates



---



## Key Principles



- Correctness overrides automation

- Trust recovery is more important than speed

- Invalid resolutions are governance-level events

- Every incident must strengthen future safeguards



Invalid resolutions are survivable. Mishandled responses are not.



