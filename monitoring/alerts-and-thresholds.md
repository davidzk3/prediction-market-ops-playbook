\# Monitoring: Alerts and Thresholds



\## Purpose



This document defines the \*\*alerting framework\*\* used to detect, classify, and respond to operational risks in an orderbook-based prediction market.



Alerts exist to:

\- Surface risks early

\- Enable fast, proportionate responses

\- Prevent escalation into market failure



Alerts should be \*\*actionable\*\*, not noisy.



---



\## Alert Design Principles



\- Every alert must map to a clear action

\- Severity must reflect real user impact

\- False positives are operational debt

\- Silent failures are unacceptable



---



\## Alert Severity Levels



\### Informational

\- No immediate action required

\- Used for visibility and trend tracking



\### Warning

\- Potential degradation

\- Ops review required



\### Critical

\- Immediate risk to market integrity or funds

\- Requires intervention or escalation



---



\## Core Alert Categories



\### 1. Oracle Health Alerts



| Metric | Threshold | Severity |

|---|---|---|

| Oracle heartbeat delay | >2x expected interval | Warning |

| Oracle unavailable | No update for defined window | Critical |

| Conflicting oracle data | Source mismatch | Critical |



\*\*Actions\*\*

\- Pause affected markets

\- Escalate to oracle runbook

\- Notify governance if unresolved



---



\### 2. Market Integrity Alerts



| Metric | Threshold | Severity |

|---|---|---|

| Spread widening | > predefined bps | Warning |

| Liquidity drop | Below minimum depth | Warning |

| Extreme imbalance | > threshold ratio | Critical |



\*\*Actions\*\*

\- Reduce max order size

\- Pause market if sustained

\- Investigate manipulation



---



\### 3. Trading Behavior Alerts



| Metric | Threshold | Severity |

|---|---|---|

| Wash trading signals | Pattern detected | Warning |

| Abnormal volume spikes | Deviation from baseline | Warning |

| Coordinated trading | Repeated correlated activity | Critical |



\*\*Actions\*\*

\- Flag accounts

\- Limit market access

\- Escalate to investigation runbook



---



\### 4. Resolution \& Settlement Alerts



| Metric | Threshold | Severity |

|---|---|---|

| Resolution delay | Past expected resolution time | Warning |

| Dispute spike | Above normal rate | Warning |

| Failed settlement | Any occurrence | Critical |



\*\*Actions\*\*

\- Pause settlement

\- Escalate to governance

\- Publish status update



---



\### 5. System Health Alerts



| Metric | Threshold | Severity |

|---|---|---|

| Transaction failure rate | Above baseline | Warning |

| Chain congestion | Sustained block delays | Warning |

| Contract error | Any unhandled error | Critical |



\*\*Actions\*\*

\- Rate-limit actions

\- Pause non-critical functions

\- Trigger incident response



---



\## Alert Routing



| Severity | Recipient |

|---|---|

| Informational | Ops dashboards |

| Warning | Ops on-call |

| Critical | Ops + Governance |



Critical alerts must page a human.



---



\## Alert Fatigue Controls



\- Alert deduplication

\- Cooldown periods

\- Threshold tuning via post-incident review



Repeated alerts without action indicate design failure.



---



\## Post-Alert Requirements



For Warning and Critical alerts:

\- Incident log entry

\- Root cause analysis if recurring

\- Threshold reassessment



---



\## Key Principle



Alerts are not signals of failure — \*\*ignored alerts are\*\*.



A healthy system is one where alerts are trusted, rare, and decisive.



