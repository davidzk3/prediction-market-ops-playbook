\# Runbook: Low Liquidity Management



\## Purpose



This runbook defines how to \*\*detect, assess, and mitigate low liquidity conditions\*\* in orderbook-based prediction markets.



Low liquidity degrades:

\- Price discovery

\- Fair execution

\- Resolution confidence

\- User trust



Liquidity issues must be addressed early to prevent manipulation or invalid outcomes.



---



\## Liquidity Definition (Operational)



A market is considered \*\*low liquidity\*\* when one or more of the following occurs:

\- Bid–ask spread exceeds acceptable thresholds

\- Orderbook depth cannot support normal trade sizes

\- Slippage exceeds expected bounds

\- Market becomes easily price-manipulable



---



\## Detection Signals



\### Primary Metrics

\- Bid–ask spread %

\- Depth at best N price levels

\- Slippage on standard order size

\- Orderbook imbalance ratio

\- Active maker count



\### Secondary Indicators

\- Sudden order cancellations

\- Whale-dominated orderbook

\- One-sided liquidity

\- Declining trade frequency



---



\## Severity Classification



| Level | Description |

|---|---|

| Mild | Spread widening, thin depth |

| Moderate | Trades moving price materially |

| Severe | Market easily manipulable |

| Critical | No meaningful price discovery |



---



\## Immediate Actions



\### Mild

\- Increase monitoring frequency

\- Flag market for ops review

\- Notify growth / liquidity team



\### Moderate

\- Reduce max trade size

\- Increase tick size or minimum order size

\- Display liquidity warning to users



\### Severe

\- Temporarily disable large orders

\- Restrict market visibility

\- Escalate to risk team



\### Critical

\- Pause trading

\- Escalate to emergency pause runbook

\- Prepare market invalidation assessment



---



\## Liquidity Support Options



Depending on protocol design:



\### Incentive-Based

\- Temporary fee rebates

\- Maker rewards

\- CAKE-based liquidity incentives (if applicable)



\### Structural

\- Adjust order size limits

\- Modify price increment rules

\- Merge overlapping markets (if valid)



---



\## Anti-Manipulation Safeguards



Low liquidity increases attack surface.



Apply:

\- Position size caps

\- Time-weighted price checks

\- Abnormal order pattern detection

\- Enhanced monitoring of large traders



---



\## User Communication



If user experience is affected:

\- Display liquidity warnings

\- Explain higher slippage risks

\- Avoid implying guaranteed outcomes



Transparency reduces disputes later.



---



\## Resolution Decision



Markets may:

\- Recover organically

\- Require incentive intervention

\- Be paused

\- Be invalidated if outcome integrity is compromised



Document rationale for all decisions.



---



\## Escalation Criteria



Escalate to governance if:

\- Liquidity remains critical for extended period

\- Market outcome credibility is compromised

\- Incentives materially alter expected payoff structure



---



\## Post-Event Review



Required review:

\- Root cause of liquidity loss

\- Effectiveness of interventions

\- Incentive efficiency

\- Runbook updates



Repeated liquidity failures signal market design issues.



---



\## Key Principle



Liquidity is not optional infrastructure.



Without sufficient liquidity, prediction markets stop being information markets and become manipulation vectors.



