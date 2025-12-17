\# Lifecycle Stage 02 Trading and Liquidity



This stage covers what ops must run day to day while markets are live on an orderbook based prediction market.



The goal is to keep markets tradeable, fair, and liquid while minimizing operational risk.



\## 1. What “healthy trading” looks like



A healthy market has:

\- stable matching engine performance

\- consistent order acceptance and fill rates

\- reasonable spreads relative to volatility

\- enough depth to absorb typical order sizes

\- no abnormal patterns that indicate manipulation



Ops should treat “liquidity” as an operational SLO, not a marketing metric.



\## 2. Liquidity sources in an orderbook prediction market



Orderbook liquidity typically comes from:

\- professional market makers (primary)

\- semi automated traders and power users (secondary)

\- incentive driven makers (tertiary)



Unlike AMMs, orderbook liquidity can disappear instantly. This means monitoring needs to be real time, and interventions must be preapproved.



\## 3. Maker and taker fee structure



Ops responsibilities:

\- define maker rebate tiers and taker fees per market class

\- prevent “wash rebates” (makers earning rebates by trading with themselves)

\- track effective fees paid versus expected fees



Common controls:

\- fee tier eligibility requires minimum uptime, minimum unique counterparty fills, and behavior checks

\- cap rebates per time window for new accounts until risk score improves



\## 4. CAKE token integrations (incentives)



If CAKE is used for incentives, ops needs clear rules:

\- who qualifies (makers, referrers, high volume traders)

\- when rewards accrue (per epoch)

\- how rewards can be revoked (fraud, wash trading, sybil)



Operational risk:

\- incentives can create attack surfaces (wash volume, fake depth)

\- incentives can distort markets near cutoff windows



Ops policies:

\- rewards should be based on executed volume with anti wash constraints

\- rewards should be weighted by time at top of book and by unique counterparties

\- rewards should be reduced in the final window before cutoff unless explicitly intended



\## 5. Core liquidity metrics to monitor



Market depth

\- depth at 10 bps, 25 bps, 50 bps from mid

\- depth concentration (how much is one maker)



Spread health

\- median spread

\- worst spread in last 15 minutes

\- spread spikes correlated with oracle or chain events



Fill quality

\- fill rate (orders that execute)

\- cancellation rate

\- partial fill ratio



Adverse selection proxies

\- maker PnL proxy (if available)

\- toxicity metrics (short term price impact after fills)



\## 6. Thresholds and alerts (examples)



These need tuning per chain and asset class.



Liquidity alert

\- depth at 25 bps drops below a minimum for more than N minutes

\- spread exceeds a maximum for more than N minutes



Manipulation alert

\- sudden one sided depth appearing then disappearing repeatedly

\- repeated small trades at increasing prices without external catalyst

\- abnormal cancel to fill ratio



System alert

\- order acceptance latency increases above SLO

\- match rate drops

\- error rate increases



\## 7. Standard interventions



Interventions must be predefined and logged.



Soft interventions

\- notify makers

\- adjust incentives for next epoch

\- adjust fee tier eligibility



Hard interventions

\- reduce max order size

\- increase minimum tick size for unstable markets

\- temporarily disable new orders for a single market

\- pause the market if integrity is at risk



Intervention rules

\- always preserve audit trail

\- always announce user visible changes

\- always time box emergency measures



\## 8. End of stage handoff



As markets approach cutoff:

\- review liquidity conditions near cutoff

\- ensure oracle request plan is prepared

\- ensure dispute handling on call schedule is set

\- ensure settlement and finalization playbooks are ready



