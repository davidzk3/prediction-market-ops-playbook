\# Incident Postmortem: Oracle Delay Leading to Incorrect Market State



\## Incident Summary



On \*\*2025-XX-XX\*\*, a prediction market experienced an extended oracle delay during the resolution phase, resulting in the market remaining in an unresolved state beyond the expected settlement window. While no incorrect settlement occurred, the delay caused user confusion, temporary liquidity withdrawal, and elevated dispute risk.



This document outlines what happened, how it was handled, and what changes were implemented to prevent recurrence.



---



\## Market Details



\- \*\*Market ID:\*\* PM-2025-042

\- \*\*Question:\*\* “Will \[Event X] occur by \[Date]?”

\- \*\*Market Type:\*\* Orderbook-based, binary outcome

\- \*\*Oracle Provider:\*\* UMA Optimistic Oracle

\- \*\*Chain:\*\* EVM-compatible chain

\- \*\*Market Status at Incident:\*\* Resolution Pending



---



\## Impact Assessment



\### User Impact

\- Settlement delayed by ~18 hours

\- Temporary uncertainty around outcome finality

\- Reduced confidence in resolution timing



\### Market Impact

\- Liquidity dropped ~22% during delay window

\- Bid–ask spreads widened significantly

\- Increased cancellation of open orders



\### Protocol Impact

\- No funds lost

\- No incorrect settlement executed

\- Elevated support and moderation workload



---



\## Timeline of Events (UTC)



| Time | Event |

|-----|------|

| T0 | Market entered resolution phase |

| T0 + 2h | Oracle proposal expected but not received |

| T0 + 4h | Oracle delay alert triggered |

| T0 + 6h | Ops team escalated to oracle monitoring |

| T0 + 7h | Market flagged as “Resolution Delayed” |

| T0 + 10h | Communication posted to users |

| T0 + 14h | Oracle proposal submitted |

| T0 + 16h | Dispute window opened |

| T0 + 18h | Market resolved and settled |



---



\## Root Cause Analysis



\### Primary Cause

\- Oracle proposer failed to submit resolution within the expected SLA window.



\### Contributing Factors

\- No automated proposer redundancy for this market

\- Oracle delay thresholds not surfaced clearly to end users

\- Manual escalation required to initiate fallback monitoring



\### What Did NOT Happen

\- No malicious oracle behavior

\- No manipulation attempt detected

\- No incorrect data fed to the system



---



\## Detection \& Response



\### Detection

\- Oracle freshness monitoring triggered an alert after SLA breach

\- Liquidity metrics indicated abnormal withdrawal behavior



\### Immediate Actions Taken

\- Market status updated to “Resolution Delayed”

\- New market creation paused for similar event categories

\- Ops team notified governance and oracle partners



\### User Communication

\- In-app banner explaining delay

\- Public update via official communication channel

\- Assurance that settlement correctness was prioritized over speed



---



\## Resolution



\- Oracle proposer submitted outcome

\- Standard dispute window opened

\- No disputes raised

\- Market settled successfully

\- Funds distributed according to outcome



---



\## Lessons Learned



\### What Worked Well

\- Alerting caught the issue early

\- Manual intervention prevented premature settlement

\- Clear escalation ownership avoided conflicting actions



\### What Didn’t Work

\- Oracle proposer redundancy was insufficient

\- Users lacked clear expectations around resolution timing

\- Too much reliance on manual escalation paths



---



\## Action Items \& Preventive Measures



\### Immediate Fixes

\- Introduced secondary oracle proposer monitoring

\- Added explicit “Resolution ETA” status to UI

\- Updated runbook for oracle delays



\### Medium-Term Improvements

\- Automated fallback proposer escalation

\- Clearer user-facing resolution state machine

\- Improved liquidity protection during resolution delays



\### Long-Term Enhancements

\- Multi-oracle redundancy for high-impact markets

\- Predictive oracle delay alerts

\- Governance-defined oracle SLA enforcement



---



\## Related Runbooks



\- `runbooks/oracle-delay.md`

\- `runbooks/oracle-failure-response.md`

\- `runbooks/invalid-resolution.md`

\- `governance/escalation-policy.md`



---



\## Final Notes



This incident did not result in financial loss, but it reinforced the importance of:

\- Conservative resolution handling

\- Transparent user communication

\- Strong oracle monitoring and escalation paths



Postmortems are shared internally to continuously improve market integrity and operational resilience.



