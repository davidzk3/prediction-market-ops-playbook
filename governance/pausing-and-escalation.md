# Governance: Pausing and Escalation Framework



## Purpose



This document defines **when, why, and how** market operations are paused and escalated to governance.



Pausing is a **last-resort safety mechanism**, not a routine control.  

Escalation ensures decisions affecting market integrity are made transparently and with accountability.



---



## Guiding Principles



- Pauses protect users, not protocols

- Escalation paths must be deterministic

- Governance intervention should be rare but decisive

- Ops teams **initiate**, governance **authorizes**



---



## When a Pause Is Permitted



A market or system-level pause may be triggered only under the following conditions:



### Oracle Failures

- Oracle unavailable or unresponsive

- Conflicting oracle data

- Missed heartbeat thresholds



### Resolution Integrity Risks

- Ambiguous market wording discovered post-launch

- Dispute escalation beyond oracle scope

- Invalid or unverifiable outcome sources



### Market Integrity Threats

- Suspected manipulation or wash trading

- Liquidity collapse or extreme imbalance

- Abnormal pricing detached from reality



### Systemic Risk

- Smart contract vulnerability

- Chain congestion affecting settlement

- External infrastructure outage



---



## Pause Scope Levels



| Scope | Description |

|---|---|

| Market-Level | Single market paused |

| Category-Level | All related markets paused |

| System-Level | Entire prediction platform paused |



---



## Authority Matrix



| Action | Ops | Governance |

|---|---|---|

| Temporary Market Pause | Yes | No |

| Extended Pause (>24h) | No | Yes |

| Market Invalidation | No | Yes |

| Emergency Settlement Override | No | Yes |

| Protocol Parameter Change | No | Yes |



Ops may **initiate** pauses but **cannot finalize irreversible actions**.



---



## Pause Execution Flow



### Step 1: Trigger Detection

- Automated alerts or manual review

- Evidence logged immediately



### Step 2: Temporary Pause (Ops)

- Halt trading and settlement

- Lock state transitions

- Preserve user balances



### Step 3: Internal Review

- Root cause assessment

- Risk classification

- Recommended actions prepared



### Step 4: Governance Escalation

- Submit escalation report

- Include evidence, timelines, and options

- Define required decision deadline



---



## Governance Escalation Inputs



Governance receives:

- Market details

- Incident summary

- Oracle data

- Risk assessment

- Proposed outcomes



Governance must decide:

- Resume market

- Modify resolution logic

- Invalidate market

- Extend pause



---



## Decision Outcomes



| Outcome | Result |

|---|---|

| Resume | Trading and settlement restored |

| Modify | Market parameters updated |

| Invalidate | Users refunded |

| Sunset | Market archived permanently |



All outcomes must be **on-chain auditable**.



---



## Communication Requirements



Mandatory disclosures:

- Reason for pause

- Scope and duration

- Decision authority

- Next update timeline



Silence or ambiguity erodes trust faster than bad outcomes.



---



## Abuse Prevention



Safeguards against misuse:

- Rate limits on pause actions

- Audit trail of pause triggers

- Governance review of Ops actions

- Transparency reports



Pausing power must never be discretionary or opaque.



---



## Post-Incident Review



After resolution:

- Full incident report published

- Control gaps identified

- Market templates updated

- Oracle configurations reviewed



Recurring pauses indicate **design failure**, not user error.



---



## Core Takeaway



Pausing is not about control — it is about \*\*credibility\*\*.



A platform that pauses decisively, escalates transparently, and resolves fairly earns long-term trust.



