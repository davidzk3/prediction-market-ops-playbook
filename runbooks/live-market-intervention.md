\# Runbook: Live Market Intervention



\## Purpose



This runbook defines \*\*when and how operations teams may intervene in live prediction markets\*\* to preserve market integrity, user trust, and outcome validity.



Interventions must be:

\- Minimal

\- Auditable

\- Justified

\- Reversible where possible



Improper intervention is more damaging than no intervention.



---



\## Guiding Principles



1\. Preserve fair price discovery

2\. Avoid influencing outcomes

3\. Minimize user disruption

4\. Prefer parameter adjustments over pauses

5\. Escalate irreversible actions



---



\## Legitimate Intervention Triggers



\### Market Integrity

\- Abnormal price movement

\- Suspected manipulation

\- One-sided liquidity collapse

\- Orderbook spoofing or wash behavior



\### Infrastructure

\- Oracle delays or inconsistency

\- Indexer lag or data desync

\- Network congestion affecting execution



\### External Events

\- Event ambiguity or wording ambiguity

\- Source reliability issues

\- Sudden real-world rule changes



---



\## Severity Assessment



| Level | Description |

|---|---|

| Observation | Monitor only |

| Soft Intervention | Parameter adjustment |

| Hard Intervention | Trading restrictions |

| Emergency | Market pause |



---



\## Approved Intervention Types



\### Soft Interventions (Preferred)



These \*\*do not stop trading\*\*:



\- Reduce max order size

\- Increase minimum order size

\- Adjust tick size

\- Increase margin or collateral requirements

\- Display user warnings



---



\### Hard Interventions



Used when soft measures fail:



\- Disable large orders

\- Restrict new positions

\- Limit order cancellation frequency

\- Temporarily hide market from discovery pages



Hard interventions require documentation.



---



\### Emergency Actions



Last resort actions:



\- Pause market

\- Freeze orderbook

\- Lock settlement state



Emergency actions require:

\- Incident ticket

\- Governance escalation

\- Post-mortem



---



\## Intervention Decision Flow



1\. Detect anomaly

2\. Validate signal (not noise)

3\. Assess severity

4\. Select lowest-impact intervention

5\. Apply intervention

6\. Monitor effects

7\. Roll back if stabilized



---



\## What Ops Must NOT Do



\- Trade on the market

\- Influence prices directly

\- Add discretionary liquidity

\- Override oracle outcomes

\- Modify resolution logic post-hoc



Violations compromise protocol neutrality.



---



\## Documentation Requirements



Every intervention must record:

\- Timestamp

\- Market ID

\- Trigger signal

\- Action taken

\- Expected impact

\- Rollback criteria



Documentation protects ops and protocol.



---



\## User Communication Guidelines



\- Be factual, not speculative

\- Avoid implying outcomes

\- Do not disclose internal thresholds

\- Acknowledge risk where applicable



---



\## Escalation Criteria



Escalate to governance if:

\- Intervention lasts > predefined window

\- Market outcome credibility is questioned

\- Intervention materially alters payoff dynamics



---



\## Post-Intervention Review



Required after any hard or emergency intervention:

\- Root cause analysis

\- Impact assessment

\- Metric review

\- Runbook update



---



\## Key Principle



Operations teams manage \*\*market conditions\*\*, not outcomes.



The moment ops influence outcomes, the market has failed.



