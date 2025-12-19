# Runbook: Emergency Market Pause



## Purpose



This runbook defines **when and how to execute an emergency market pause** to protect users, preserve market integrity, and prevent cascading failures.



An emergency pause is a **protective action**, not a resolution.



---



## When This Runbook Is Used



Trigger this runbook only when **immediate risk** is present.



### Valid Triggers

- Oracle failure or inconsistent data

- Suspected market manipulation

- Smart contract vulnerability

- Extreme liquidity collapse

- Settlement or resolution malfunction

- External event invalidating market assumptions



If the issue can wait for governance review, \*\*do not use this runbook\*\*.



---



## Pause Scope Decision



Before acting, determine scope:



| Scope | Use When |

|---|---|

| Market-level | Single market affected |

| Category-level | Multiple related markets |

| System-level | Platform-wide integrity risk |



Default to the **smallest effective scope**.



---



## Immediate Actions (First 5 Minutes)



### 1. Halt Trading

- Disable order placement

- Cancel open orders if required

- Prevent new positions



### 2. Freeze Settlement

- Block resolution execution

- Preserve current state

- Prevent partial settlement



### 3. Preserve Funds

- Ensure user balances remain unchanged

- Disable withdrawals if system-wide



---



## Verification Checklist



Confirm:

- Pause is active

- No new trades are executing

- No settlement calls are processing

- State is consistent across services



If any item fails, escalate immediately.



---



## Evidence Capture



Record the following **before investigation proceeds**:

- Timestamp of pause

- Triggering alert or observation

- Affected markets

- Oracle state

- Relevant metrics and logs



Evidence quality determines governance speed later.



---



## Internal Notification



Notify:

- Ops leadership

- Risk / integrity team

- Governance liaison



Do **not** notify users yet.



---



## Initial Assessment (Within 30 Minutes)



Determine:

- Root cause hypothesis

- Severity classification

- Estimated time to resolution

- Whether governance escalation is required



Document findings.



---



## Governance Escalation Criteria



Escalate immediately if:

- User funds may be affected

- Resolution outcome is uncertain

- Pause expected to exceed 24 hours

- Market invalidation is possible



Use the **Escalation Policy**.



---



## External Communication



Once governance is informed:



Required user update:

- Markets paused

- Reason (high-level)

- Next update timeline



Avoid speculation.



---



## Resume or Transition Decision



Markets may only resume when:

- Root cause is resolved

- Oracle integrity is restored

- Governance approves (if required)



Possible outcomes:

- Resume trading

- Modify market parameters

- Invalidate market

- Sunset market permanently



---



## Post-Incident Review



Mandatory after resolution:

- Full incident report

- Timeline reconstruction

- Control failures identified

- Runbook updates



Repeated emergency pauses indicate systemic issues.



---



## Key Principle



An emergency pause protects **trust**, not just capital.



Fast, calm, and transparent pauses preserve credibility — delayed action destroys it.



