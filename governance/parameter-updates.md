# Governance: Parameter Updates Framework



## Purpose



This document defines how \*\*protocol and market parameters\*\* are updated safely without disrupting active markets or undermining trust.



Parameter updates must balance:

- Responsiveness to new risks

- Predictability for users

- Operational stability



---



## Parameter Categories



### 1. Market Parameters

Affect individual markets.



Examples:

- Max position size

- Minimum liquidity thresholds

- Spread limits

- Market duration



### 2. Oracle Parameters

Affect resolution mechanics.



Examples:

- Oracle sources

- Heartbeat intervals

- Dispute windows

- Quorum thresholds



### 3. System Parameters

Affect the entire platform.



Examples:

- Fee rates

- Incentive emissions

- Pause thresholds

- Risk limits



---



## Update Authority



| Parameter Type | Ops | Governance |

|---|---|---|

| Market-level | Propose | Approve |

| Oracle-level | Propose | Approve |

| System-level | Propose | Approve |



Ops **cannot unilaterally update** parameters that affect settlement or user funds.



---



## Update Triggers



Parameter updates may be triggered by:

- Incident post-mortems

- Market behavior analysis

- Oracle performance degradation

- Ecosystem growth or scaling

- Regulatory or reputational risk



---



## Update Process



### Step 1: Proposal Creation

Includes:

- Parameter description

- Current vs proposed values

- Rationale

- Risk assessment

- Impact analysis



### Step 2: Impact Review

Ops evaluates:

- Effects on active markets

- Backward compatibility

- Edge-case interactions



### Step 3: Governance Approval

- Vote or approval threshold applied

- Emergency path available if critical



### Step 4: Deployment

- Changes applied during low-activity windows

- Versioned and logged on-chain



---



## Emergency Updates



Emergency updates are permitted when:

- User funds are at immediate risk

- Oracle integrity is compromised

- Exploits are detected



Constraints:

- Temporary only

- Mandatory post-hoc governance review

- Full disclosure required



---



## Change Isolation Rules



To minimize disruption:

- No parameter changes during active settlement

- No retroactive changes to resolved markets

- No silent parameter drift



---



## Communication Requirements



Before deployment:

- Public notice

- Clear explanation

- Effective date



After deployment:

- Confirmation notice

- Updated documentation



---



## Audit and Transparency



All updates must be:

- Logged on-chain

- Time-stamped

- Attributable to governance action



Historical parameters remain queryable.



---



## Anti-Abuse Safeguards



- Rate limits on updates

- Minimum review windows

- Multi-signature approval

- Rollback capability



Parameter control must never be opaque or discretionary.






