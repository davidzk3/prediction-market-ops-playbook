# Monitoring Dashboards



## Purpose



This document defines the **core operational dashboards** required to run an orderbook-based prediction market safely and at scale.



Dashboards are designed for:

- Real-time decision making

- Incident detection

- Post-incident analysis

- Governance reporting



Dashboards do not replace alerts — they **contextualize them**.



---



## Dashboard Design Principles



- One dashboard per operational question

- Metrics must be actionable

- Defaults should show “what is wrong”

- Historical views must be available



---



## 1. Market Health Dashboard (Primary Ops View)



**Audience:** Ops on-call  

**Cadence:** Real-time



### Key Metrics

- Active markets count

- Bid–ask spread (median, max)

- Market depth at top levels

- Liquidity imbalance

- Volume by market



### Purpose

Quickly answer:

> “Are markets trading normally right now?”



### Typical Actions

- Reduce max order sizes

- Pause individual markets

- Escalate abnormal behavior



---



## 2. Oracle Health Dashboard



**Audience:** Ops + Governance  

**Cadence:** Real-time + historical



### Key Metrics

- Oracle heartbeat freshness

- Source agreement / disagreement

- Resolution delays

- Dispute counts



### Purpose

Detect oracle degradation before it affects settlement.



### Typical Actions

- Pause affected markets

- Trigger oracle runbooks

- Escalate to governance



---



## 3. Trading Behavior & Integrity Dashboard



**Audience:** Ops, Risk  

**Cadence:** Near real-time



### Key Metrics

- Trade concentration

- Volume anomalies

- Self-trading indicators

- Correlated account behavior



### Purpose

Identify manipulation, wash trading, or coordinated behavior.



### Typical Actions

- Flag accounts

- Limit market access

- Initiate investigations



---



## 4. Resolution & Settlement Dashboard



\*\*Audience:\*\* Ops + Governance  

**Cadence:** Event-driven



### Key Metrics

- Markets awaiting resolution

- Time since event end

- Dispute status

- Settlement success/failure



### Purpose

Ensure markets resolve correctly and on time.



### Typical Actions

- Escalate delayed resolutions

- Pause settlement

- Trigger governance decisions



---



## 5. Incident & Escalation Dashboard



**Audience:** Ops leadership  

**Cadence:** Ongoing



### Key Metrics

- Active incidents

- Incident severity

- Time to resolution

- Escalation frequency



### Purpose

Track operational stability over time.



### Typical Actions

- Identify systemic weaknesses

- Adjust thresholds

- Improve runbooks



---



## 6. Governance Reporting Dashboard



**Audience:** Governance, Executives  

**Cadence:** Weekly / Monthly



### Key Metrics

- Market pauses

- Disputes and invalidations

- Parameter updates

- Incident summaries



### Purpose

Provide transparency and accountability.



---



## Data Sources



Dashboards typically pull from:

- Orderbook state

- Trade events

- Oracle feeds

- Resolution contracts

- Incident logs



Data freshness is more important than granularity for Ops views.



---



## Access Controls



| Role | Access |

|---|---|

| Ops | Full |

| Risk | Read |

| Governance | Read |

| Public | Limited / delayed |



Sensitive dashboards are not public.






If a chart does not inform an action, it does not belong on an Ops dashboard.



