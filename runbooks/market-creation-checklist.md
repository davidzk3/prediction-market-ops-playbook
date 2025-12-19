# Runbook: Market Creation Checklist



## Purpose



This checklist ensures every prediction market is created with:

- Clear resolution criteria

- Reliable data sources

- Proper incentive alignment

- Minimal ambiguity



Most prediction market failures originate at market creation.



---



## Phase 1: Market Definition



### Question Design

- [ ] Question is **binary or clearly multi-outcome**

- [ ] Question is **objectively resolvable**

- [ ] Question avoids subjective language

- [ ] No overlapping or contradictory outcomes

- [ ] Timeframe is explicit (date + timezone)



### Outcome Set

- [ ] Outcomes are mutually exclusive

- [ ] Outcomes are collectively exhaustive

- [ ] No “other” or undefined outcomes

- [ ] Outcome labels are unambiguous



---



## Phase 2: Resolution Criteria



### Resolution Source

- [ ] Primary resolution source defined

- [ ] Backup source defined

- [ ] Sources are public and verifiable

- [ ] Source historically reliable



### Resolution Rules

- [ ] Exact resolution condition documented

- [ ] Edge cases documented

- [ ] Tie or null scenarios defined

- [ ] Resolution timestamp defined



---



## Phase 3: Oracle Configuration



### Oracle Selection

- [ ] Oracle mechanism selected (Optimistic / Push-based)

- [ ] Proposer and disputer roles defined

- [ ] Dispute window configured

- [ ] Bond amounts calibrated



### Oracle Risk Review

- [ ] Oracle latency acceptable

- [ ] Oracle manipulation vectors assessed

- [ ] Fallback logic defined

- [ ] Oracle failure runbook linked



---



## Phase 4: Market Mechanics



### Orderbook Parameters

- [ ] Tick size defined

- [ ] Minimum order size defined

- [ ] Maximum order size defined

- [ ] Cancel frequency limits configured

- [ ] Trading fee configured



### Trading Safeguards

- [ ] Price bounds set (if applicable)

- [ ] Max position per wallet set

- [ ] Market pause logic enabled



---



## Phase 5: Incentives & Fees



### Liquidity Incentives

- [ ] Maker incentives configured

- [ ] Early liquidity strategy defined

- [ ] Incentive duration defined

- [ ] Abuse vectors assessed



### Token Integration (if applicable)

- [ ] Incentive token source defined

- [ ] Emission limits set

- [ ] Governance approval (if required)



---



## Phase 6: Risk Review



### Manipulation Risk

- [ ] Low-liquidity manipulation assessed

- [ ] Whale dominance risk assessed

- [ ] Wash trading risk assessed



### Event Risk

- [ ] Event cancellation risk assessed

- [ ] Event ambiguity risk assessed

- [ ] External dependency risk assessed



---



## Phase 7: Compliance & Governance



- [ ] Jurisdictional review completed

- [ ] Restricted topics avoided

- [ ] Governance approval recorded

- [ ] Market category assigned



---



## Phase 8: Pre-Launch Validation



### Dry Run

- [ ] Test orders placed

- [ ] Order matching verified

- [ ] Oracle test executed

- [ ] Dispute flow simulated



### Monitoring Setup

- [ ] Alerts configured

- [ ] Dashboard linked

- [ ] Ops owner assigned



---



## Phase 9: Launch Authorization



- [ ] All checklist items complete

- [ ] Ops sign-off recorded

- [ ] Governance sign-off (if required)

- [ ] Market enabled for trading



---



## Key Principle



A market that cannot be clearly resolved  

**should never be created.**



Ops discipline at creation prevents disputes, loss of trust, and protocol damage.



