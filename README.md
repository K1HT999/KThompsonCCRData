# Can USDA Crop-Condition Shocks Predict Short-Term Corn Futures Returns?

This research investigates whether sudden deterioration in USDA corn crop-condition data has historically preceded short-term upside in front-month corn futures.

Crop Condition Reports (CCRs) are official USDA reports released weekly from planting to harvest season. For corn, this generally lies between late April and November.
Reports contain the percentage of each crop condition: very poor, poor, fair, good, and excellent.

The core finding is a September-specific event pattern: when a production-weighted crop-condition surprise deteriorated sharply, ZC corn futures tended to rise over the next five trading sessions.

This is not production-ready alpha. It is a research signal with a plausible economic mechanism, clean implementation checks, and meaningful limitations.

## Headline Result

Strategy:

```text
Signal: ΔSurprise <= -0.10
Calendar filter: September only
Entry: next Tuesday 08:00 CT day-session open proxy after USDA Crop Progress release
Exit: 5 trading-session opens later
Market: adjusted front-month CBOT corn futures
Sample: 2013-2025 signal years, based on 2012-2025 available testing window
```

Performance:

| Metric | Value |
|---|---:|
| Trades | 23 |
| Wins / Losses | 19 / 4 |
| Mean 5d return | 1.42% |
| Median 5d return | 1.12% |
| Hit rate | 82.6% |
| t-stat | 2.78 |
| Profit factor | 5.03 |
| Exact binomial p-value | 0.0026 |
| Compounded return across trades | 37.3% |

Source table: [sep_ΔSurprise_strategy_summary.csv](assets/tables/sep_ΔSurprise_strategy_summary.csv)

| Benchmark | Trades | Mean | Hit rate | t-stat | Profit factor |
|---|---:|---:|---:|---:|---:|
| ΔSurprise strategy | 23 | 1.42% | 82.6% | 2.78 | 5.03 |
| All September session-open days, rolling 5d | 285 | 0.25% | 51.9% | 1.70 | 1.29 |
| September monthly buy-and-hold | 14 | -0.52% | 71.4% | -0.40 | 0.74 |
| Monthly rolling Jun-Oct long | 70 | -0.86% | 44.3% | -0.90 | 0.75 |

Source table: [benchmark_summary.csv](assets/tables/benchmark_summary.csv)

This investigation showed the viability of Crop Condition Reports in Corn futures trading intelligence. There are further applications to other crops and expanded datasets to continue testing. I will continue researching this specific channel in further iterations. This strategy will begin to be tracked live as of August 1st, 2026. 

**Author**: K. Thompson
**Research Platform**: ThomPlatz Research
**Contact**: thomplatzresearch@gmail.com
