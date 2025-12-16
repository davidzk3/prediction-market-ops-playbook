\# Core Monitoring Metrics — Prediction Markets (Orderbook)



This document defines the live operational metrics required to run an orderbook-based prediction market safely.



\## Market Health

\- Best bid / ask spread

\- Orderbook depth at 1%, 2%, 5%

\- Cancel-to-fill ratio

\- Time-weighted spread



\## Liquidity Health

\- Maker concentration (top 5 LPs %)

\- Inventory imbalance per outcome

\- Liquidity decay near expiry

\- Sudden LP withdrawal detection



\## Trading Activity

\- Trade velocity per market

\- Average trade size

\- Wash-trade heuristics

\- Repeated self-cross detection



\## Oracle \& Resolution

\- Oracle update latency

\- Time since market expiry

\- Dispute frequency

\- Resolution confidence window



\## Risk Triggers

\- Spread widens beyond threshold

\- Oracle delayed beyond SLA

\- Abnormal volume spikes

\- One-sided outcome accumulation



Each metric maps directly to an automated or manual intervention defined in the Ops Runbooks.



