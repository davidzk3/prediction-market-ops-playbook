# Orderbook vs AMM for Prediction Markets

## Architecture Tradeoffs and Operational Implications



This document explains why orderbook-based market design is preferred over AMM-based design for scalable, credible prediction markets.



The analysis is grounded in:

- Real-world prediction market operations

- Polymarket’s architecture choices

- Liquidity, manipulation, and resolution risks



---



## Core Difference



Prediction markets differ from spot markets because:

- They converge to a binary or discrete outcome

- Liquidity collapses near resolution

- Incentives to manipulate peak late



Architecture choices must reflect this.



---



## AMM-Based Prediction Markets



### How AMMs Work in Predictions



AMMs:

- Use pooled liquidity

- Price outcomes via invariant curves

- Allow trades against the pool



Examples:

- LMSR-style AMMs

- Constant-product outcome pools



---



### Strengths of AMMs



- Simple UX

- No need for active makers

- Always-on liquidity (early phase)



These are useful for:

- Low-stakes markets

- Early experimentation

- Small, casual participation



---



### Structural Weaknesses of AMMs



#### 1. Late-Stage Manipulation Risk

Near resolution:

- Liquidity thins

- Prices become extremely sensitive

- Capital-efficient manipulation becomes possible



---



#### 2. Poor Capital Efficiency

AMMs require:

- Large idle liquidity

- Subsidies to maintain depth

- Continuous incentives



This scales poorly.



---



#### 3. Loss of Informational Signal

AMM prices:

- Reflect curve mechanics

- Not true market depth

- Mask disagreement



This weakens the predictive signal.



---



## Orderbook-Based Prediction Markets



### How Orderbooks Work



Orderbooks:

- Match bids and asks directly

- Reflect true supply and demand

- Allow price discovery via depth



Used by:

- Polymarket

- Financial exchanges

- Institutional trading venues



---



### Strengths of Orderbooks



#### 1. Superior Price Discovery

- Depth shows conviction

- Spread reflects uncertainty

- Orders reveal intent



This is critical for prediction accuracy.



---



#### 2. Reduced Manipulation Surface

- Manipulation requires crossing real liquidity

- Attacks are visible

- Slippage is explicit



This deters late-stage gaming.



---



#### 3. Better Risk Controls

Operators can:

- Impose max order size

- Widen tick sizes

- Halt specific markets

- Monitor order flow anomalies



These controls are precise.



---



## Operational Control Comparison



| Dimension | AMM | Orderbook |

|--------|-----|-----------|

| Liquidity Control | Indirect | Direct |

| Manipulation Detection | Weak | Strong |

| Late-Stage Stability | Poor | Strong |

| Risk Intervention | Crude | Granular |

| Institutional Readiness | Low | High |



---



## Oracle Interaction Differences



AMM:

- Pools remain exposed during disputes

- LPs bear resolution uncertainty



Orderbook:

- Trading halts cleanly

- Positions are fixed pre-resolution

- No pool exposure during disputes



This is a major operational advantage.



---



## Cost and Incentives



AMM:

- Continuous liquidity subsidies

- High long-term token emissions



Orderbook:

- Targeted maker incentives

- Fee rebates

- Performance-based rewards



This aligns better with sustainable token economics.



---



## Why Polymarket Uses Orderbooks



Polymarket chose orderbooks because:

- They scale to large volumes

- They reduce oracle manipulation

- They support real money markets

- They resemble traditional financial infrastructure



This choice is intentional, not cosmetic.



---



## Implications for PancakeSwap



Given:

- Existing trading infrastructure

- Sophisticated users

- CAKE-based incentives

- Risk-sensitive brand



Orderbook-based prediction markets are the correct choice.



AMMs may exist as:

- Bootstrapping layers

- Educational products

- Low-stakes experiments



But **core prediction markets must be orderbook-based**.



---



## Summary



Orderbooks:

- Produce better predictions

- Are harder to attack

- Offer superior ops control

- Align with institutional-grade systems



For serious prediction markets, AMMs are a stepping stone — not the destination.



