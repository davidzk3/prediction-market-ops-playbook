\# Runbook: Oracle Delay Handling



\## Purpose



This runbook defines the operational response when a market’s resolution is delayed due to oracle latency, missing data, or stalled proposer activity.  

Oracle delays are common in real-world event markets and must be handled transparently to preserve trader trust and market integrity.



This runbook applies to:

\- UMA Optimistic Oracle–based resolutions

\- Hybrid oracle systems (UMA + Chainlink data feeds)

\- Manual escalation scenarios



---



\## What Is an Oracle Delay



An oracle delay occurs when:

\- No valid resolution proposal is submitted after market close

\- The optimistic oracle proposal window exceeds expected timing

\- External data sources (APIs, Chainlink feeds) are unavailable or inconsistent

\- A dispute is ongoing and blocks finalization



---



\## Detection \& Monitoring Signals



\### Primary Signals

\- Market state = `CLOSED` but not `RESOLVED`

\- Time since market close > expected oracle SLA

\- No proposer transaction observed within resolution window

\- Chainlink feed heartbeat missing or stale

\- UMA oracle request pending beyond threshold



\### Dashboards / Metrics

\- Time-to-resolution (per market)

\- Oracle request age

\- Proposer activity rate

\- Dispute frequency per oracle request



---



\## Severity Classification



| Severity | Description |

|--------|------------|

| Low | Short delay within expected oracle window |

| Medium | Delay exceeds SLA but oracle system responsive |

| High | Oracle stalled or external data unavailable |

| Critical | Systemic oracle outage or governance-level risk |



---



\## Immediate Operator Actions



\### Step 1: Verify Oracle State

\- Confirm oracle request exists on-chain

\- Check proposer and disputer activity

\- Validate reference data source availability



\### Step 2: Identify Root Cause

\- Data feed outage

\- Low proposer incentives

\- Ambiguous market wording

\- External event uncertainty

\- Network congestion



\### Step 3: Communicate Status

\- Update market status banner (e.g. “Resolution Pending”)

\- Publish expected resolution timing range

\- Avoid speculative resolution statements



---



\## Intervention Playbooks



\### Case A: Low Proposer Participation

\- Increase proposer incentives (if supported)

\- Notify trusted proposers / oracle operators

\- Monitor for new proposals



\### Case B: External Data Unavailable

\- Wait until authoritative source updates

\- Document acceptable fallback sources

\- Escalate if delay exceeds predefined window



\### Case C: Prolonged Oracle Stall

\- Escalate to governance or ops lead

\- Freeze secondary market actions if required

\- Prepare contingency resolution process



---



\## Escalation Path



1\. Ops On-Call

2\. Protocol Risk Lead

3\. Governance / Admin Multisig

4\. Public incident disclosure (if threshold exceeded)



Escalation is mandatory if:

\- Delay > maximum defined resolution window

\- Multiple markets affected simultaneously

\- Oracle trust assumptions are compromised



---



\## Resolution Completion



Once oracle response is received:

\- Validate resolution correctness

\- Execute settlement transactions

\- Unfreeze withdrawals and claims

\- Update market status to `RESOLVED`



---



\## Post-Incident Actions



\- Log delay duration and root cause

\- Review incentive adequacy for proposers

\- Assess clarity of market wording

\- Update oracle SLA thresholds if needed



---



\## Key Principles



\- Accuracy over speed

\- Transparency over silence

\- Consistency across markets

\- Minimal discretionary intervention



Oracle delays are operational risks, not failures — how they are handled defines platform credibility.



