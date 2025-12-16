\# Runbook: Dispute Handling



\## Purpose



This runbook defines how disputes are handled when a proposed or finalized market resolution is challenged.



Disputes are a \*\*core integrity mechanism\*\* in prediction markets and must be managed neutrally, transparently, and according to predefined rules — never ad hoc.



---



\## What Is a Dispute



A dispute occurs when a participant or designated actor challenges a resolution proposal on the grounds that:



\- The proposed outcome is factually incorrect

\- The oracle data source is wrong or incomplete

\- The market question is ambiguous or misinterpreted

\- Resolution timing violated protocol rules



This runbook applies from \*\*dispute initiation through final resolution\*\*.



---



\## Dispute Entry Points



\### On-Chain

\- Optimistic oracle dispute submission

\- Bond posted by disputer

\- Dispute window opened automatically



\### Off-Chain

\- User support escalation

\- Governance delegate escalation

\- Ops-initiated dispute escalation (if allowed)



---



\## Immediate Ops Actions (T+0 to 15 min)



\### Step 1: Confirm Dispute Validity

\- Verify market ID and resolution proposal

\- Confirm dispute window is open

\- Validate dispute transaction and bond



\### Step 2: Freeze Settlement

\- Prevent settlement finalization

\- Disable claims execution

\- Lock market state



\### Step 3: Log \& Notify

\- Log dispute details

\- Notify Ops Lead and Risk team

\- Notify Governance if applicable



---



\## Evidence Collection



Ops must gather:

\- Market question and specification

\- Resolution criteria

\- Oracle data sources referenced

\- External authoritative data

\- Timeline of resolution events



All evidence must be \*\*timestamped and archived\*\*.



---



\## Dispute Resolution Flow



\### Phase 1: Oracle Arbitration

If using an optimistic oracle:

\- Oracle protocol adjudicates dispute

\- Economic incentives enforce honest reporting

\- Final outcome determined on-chain



Ops role:

\- Monitor oracle progress

\- Ensure no premature settlement

\- Communicate timelines clearly



\### Phase 2: Governance Arbitration (If Required)

Triggered when:

\- Oracle escalates to governance

\- Market ambiguity cannot be resolved algorithmically



Governance actions:

\- Vote on correct outcome

\- Vote to invalidate market

\- Approve remediation plan



Ops role:

\- Provide neutral briefing

\- Execute approved outcome

\- Coordinate communications



---



\## Possible Outcomes



| Outcome | Action |

|------|------|

| Dispute Rejected | Proceed with original resolution |

| Resolution Corrected | Apply new outcome and settle |

| Market Invalidated | Refund collateral |

| Compensation Required | Execute approved payouts |



---



\## Settlement Execution



After dispute resolution:

\- Apply final outcome

\- Execute settlement or refunds

\- Re-enable withdrawals

\- Archive market



Settlement must occur \*\*only after final oracle or governance confirmation\*\*.



---



\## Communication Guidelines



Required disclosures:

\- Dispute reason

\- Process followed

\- Final outcome

\- Timeline impact



Avoid:

\- Speculation during dispute

\- Partial information

\- Delayed announcements



Transparency preserves trust even when outcomes are unpopular.



---



\## Abuse \& Spam Prevention



Monitor for:

\- Frivolous disputes

\- Coordinated griefing

\- Bond exploitation attempts



Mitigations:

\- Minimum dispute bonds

\- Rate limits per address

\- Escalation thresholds



---



\## Post-Dispute Review



After closure:

\- Root cause analysis

\- Market design review

\- Oracle configuration review

\- Update market creation checklist if needed



Recurring disputes signal \*\*systemic design flaws\*\*, not user behavior problems.



---



\## Core Principles



\- Disputes are expected, not failures

\- Neutrality is mandatory

\- Process integrity matters more than speed

\- Economic incentives must align with truth



A platform that handles disputes well earns long-term credibility.



