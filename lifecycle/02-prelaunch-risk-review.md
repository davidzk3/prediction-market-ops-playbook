# Pre Launch Risk Review (Orderbook Based Prediction Markets)

Purpose
This checklist is run before any market goes live. It is designed to prevent preventable incidents by validating market specs, settlement logic, oracle and resolution configuration, and operational readiness.

Owner
Ops Lead (primary)
Engineering On Call (consulted)
Risk or Compliance (consulted if applicable)

When to run
Before initial deployment of a new market template
Before each high impact market (major politics, major sports finals, large cap crypto events)
Before enabling incentives for a market
After any parameter change that affects resolution, fees, or collateral

Inputs
Market spec draft (question, outcomes, end time, resolution source)
Oracle configuration (UMA OO or Chainlink feed, dispute window, bonds)
Exchange configuration (order rules, fees, tick size, min size, maker incentives)
Collateral configuration (USDC or approved collateral list)
Monitoring and alert configuration
Market creator identity and permissions (internal or curated partner)

Non negotiable gate
If any item in the Gate Checks section fails, the market does not go live.

---

## 1) Market Spec Integrity

Checklist
- Question is unambiguous and answers are mutually exclusive
- Outcome set is complete and does not allow double winners
- End time and resolution time are clearly defined
- Resolution source is specified and publicly verifiable
- Market category and tags are correct for discovery and monitoring
- Market does not violate internal prohibited categories list

Failure modes to watch
- Ambiguous wording leads to disputes and reputational damage
- Outcomes allow loopholes or partial matches
- End time mismatch with data source publication schedule

Placeholders
[CHART PLACEHOLDER: Examples of good vs bad market questions]

---

## 2) Oracle and Resolution Configuration (UMA or Chainlink)

Decision
- If the market is a simple numeric or price based settlement and a robust feed exists, prefer Chainlink
- If the market is event based, narrative, or requires human verification, use UMA Optimistic Oracle

UMA Optimistic Oracle checks
- Identifier and ancillary data are correct
- Proposer bond is set to deter spam
- Dispute bond and dispute window are appropriate for expected market size
- Expected proposer and disputer roles are understood (who is likely to propose, who monitors)
- Escalation path is documented (what happens if disputed)

Chainlink feed checks
- Feed exists and is maintained
- Update frequency supports the resolution time needed
- Feed deviation threshold and staleness risk are acceptable
- Fallback behavior is defined if feed is stale or paused

Gate checks
- Oracle choice is justified and documented
- Dispute window is not shorter than the time needed for credible monitoring
- A clear finalization condition exists (when the market becomes final)

Placeholders
[DIAGRAM PLACEHOLDER: UMA propose dispute settle timeline]
[DIAGRAM PLACEHOLDER: Chainlink feed staleness and fallback logic]

---

## 3) Exchange and Market Microstructure (Orderbook)

Core checks
- Tick size is appropriate (not too fine to create spam, not too coarse to harm price discovery)
- Min order size and min notional prevent dust spam
- Order types enabled are intentional (limit only vs limit and market)
- Fee schedule is confirmed (maker taker, rebates, tiering)
- Cancel behavior and nonce handling are correct to avoid stuck orders

Liquidity and incentive checks
- Incentives do not overwhelm organic price discovery
- Maker incentives have caps and monitoring triggers
- Wash trading deterrence rules are ready (see runbook)

Gate checks
- Parameter set passes a basic stress test scenario
- There is a documented plan for low liquidity response in the first hours

Placeholders
[CHART PLACEHOLDER: Expected spread and depth targets for day 0]
[CHART PLACEHOLDER: Incentive budget vs expected maker volume]

---

## 4) Collateral, Custody, and Settlement

Collateral checks
- Collateral asset is approved and liquid
- Deposit and withdrawal flows are tested on the exact chain environment
- Fees and rounding are consistent across contracts and UI

Conditional token or position token checks
- Minting and redemption rules are correct
- Outcome token accounting matches the market outcomes
- Settlement path is tested with both winning and losing outcomes

Gate checks
- End to end simulation completed (create market, trade, resolve, settle, withdraw)

Placeholders
[DIAGRAM PLACEHOLDER: Collateral -> position token -> settlement -> redemption flow]

---

## 5) Monitoring and Ops Readiness

Must have dashboards or queries
- Orders, cancels, fills, unique traders
- Top accounts by volume, concentration metrics
- Spread and depth by outcome
- Oracle status (pending proposals, disputes, time to finality)
- Dispute frequency and abnormal spikes
- Error rates and failed transactions

Alerting
- Oracle delay or stale feed alerts
- Sudden spread blowout alerts
- Abnormal cancel spam alerts
- Concentration and whale exposure alerts
- Incentive budget burn rate alerts

On call readiness
- Named on call for the launch window
- Clear escalation path to engineering and risk
- Incident template ready and linked
- Runbooks linked for top scenarios

Gate checks
- Alerts are configured and tested
- On call and escalation are confirmed for the first 24 to 72 hours

Placeholders
[CHART PLACEHOLDER: Launch day ops dashboard layout]
[CHART PLACEHOLDER: Alert thresholds table]

---

## 6) Go Live Decision

Final review questions
- Can a reasonable third party independently verify the resolution source
- Is the oracle configuration robust for the market size and controversy risk
- Are incentives sized to bootstrap without distorting the market
- Do we have a clear plan for disputes, oracle delays, and manipulation attempts
- Do we know what metrics will trigger interventions

Sign off
Ops Lead
Engineering On Call
Risk or Compliance (if required)

Record
Link to market spec
Link to oracle config
Link to dashboards
Link to launch window notes
