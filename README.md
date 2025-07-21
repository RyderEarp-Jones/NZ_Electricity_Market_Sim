# NZ Electricity Pricing Interval Simulation

## Goal
Show, with a tiny synthetic model, how changing New Zealand’s wholesale electricity price‑setting from the current **30‑minute** interval to a much finer **30‑second** interval could unlock new pricing signals and efficiency gains.

## Quant Method Used
A minimal **mean‑reversion** (Ornstein–Uhlenbeck) process produces:

* **30‑minute anchor prices** – the existing dispatch horizon.
* **30‑second micro‑prices** – prices that wobble around each half‑hour anchor.

A toy **mean‑reversion arbitrage strategy** then:
1. Goes **long** when the micro‑price dips more than a set amount below its anchor.
2. Goes **short** when it rises the same amount above.
3. Exits on a small profit target, stop‑loss, or time cap.

## Why the Time Change Matters
| Interval | Market Effect | Potential Benefit |
|----------|---------------|-------------------|
| 30 min (today) | Coarse signals, slower correction | Wider spreads, higher risk premia |
| 30 sec (proposed) | Finer signals, quicker correction | Tighter spreads → lower wholesale cost |

**Savings pathway:** tighter spreads push down average clearing prices; retailers pass savings to consumers.  Even a modest **NZ$1/MWh** reduction on ~40 TWh/year ≈ **NZ$40 million per year** in sector‑wide savings.

## Quick Start
```bash
pip install numpy pandas matplotlib
python market_sim.py
