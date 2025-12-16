\# Incident Response Runbook

\## Prediction Market Operations



This runbook defines how the operations team detects,

triages, mitigates, communicates, and resolves incidents

across the prediction market lifecycle.



Incidents are inevitable. Poor response is not.



---



\## What Is an Incident?



An incident is any unexpected event that threatens:



\- Market integrity

\- Fair pricing

\- Timely resolution

\- User funds

\- System availability

\- Trust in outcomes



Not all anomalies are incidents, but all incidents start as anomalies.



---



\## Incident Severity Levels



\### Severity 1 — Critical

Immediate threat to funds or market integrity.



Examples:

\- Incorrect resolution

\- Oracle failure during resolution

\- Funds at risk

\- Market exploit or manipulation



\### Severity 2 — High

Severe degradation but no immediate fund loss.



Examples:

\- Oracle delays

\- Liquidity collapse

\- Orderbook desynchronization

\- Failed settlement attempt



\### Severity 3 — Medium

User-facing issues with limited impact.



Examples:

\- UI inconsistencies

\- Delayed market updates

\- Partial data outages



\### Severity 4 — Low

Cosmetic or informational issues.



Examples:

\- Display bugs

\- Non-blocking notifications

\- Documentation mismatches



---



\## Detection Sources



Incidents may be detected via:



\- Monitoring dashboards

\- Automated alerts

\- User reports

\- Oracle provider notifications

\- Internal QA checks



First detection time must be logged.



---



\## Incident Intake Checklist



Upon detection:



\- Assign an incident owner

\- Record timestamp and affected markets

\- Classify severity

\- Freeze non-essential changes

\- Notify core stakeholders



Ops lead coordinates response.



---



\## Immediate Containment Actions



Depending on severity:



\- Pause new order placement

\- Halt market creation

\- Freeze settlement execution

\- Disable affected markets

\- Isolate oracle feeds



Containment prioritizes safety over uptime.



---



\## Root Cause Investigation



Ops coordinates investigation with:



\- Engineering

\- Oracle providers

\- Legal or compliance (if applicable)



Key questions:

\- What failed?

\- Why did it fail?

\- Was detection timely?

\- Could automation have prevented it?



All findings are documented.



---



\## Communication Protocol



\### Internal

\- Engineering

\- Product

\- Legal or compliance

\- Leadership



\### External

\- Status page updates

\- User notifications

\- Public post-mortem (if required)



Communication must be factual, calm, and time-stamped.



---



\## Resolution and Recovery



Once the issue is resolved:



\- Validate system integrity

\- Resume paused operations gradually

\- Monitor closely for recurrence

\- Confirm user balances and market states



Recovery must be verified, not assumed.



---



\## Post-Mortem Process



Every Severity 1 or 2 incident requires a post-mortem.



Post-mortem includes:

\- Timeline

\- Root cause

\- Impact assessment

\- What went well

\- What failed

\- Preventive actions



Blameless, but rigorous.



---



\## Preventive Actions



Outcomes may include:



\- New alerts

\- Updated thresholds

\- Playbook changes

\- Automation improvements

\- Market design adjustments



Prevention is part of resolution.



---



\## Metrics Tracked



Ops tracks:



\- Mean time to detect (MTTD)

\- Mean time to resolve (MTTR)

\- Incident frequency

\- Recurrence rate

\- User impact



These metrics feed quarterly ops reviews.



---



\## Summary



A strong incident response system:



\- Protects users

\- Preserves trust

\- Enables fast recovery

\- Scales with market complexity



Ops excellence is defined in crisis.



