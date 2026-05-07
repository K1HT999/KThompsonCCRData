# September Effect Deep Dive

## Core Result
- Strategy: `ΔSurprise <= -0.10`, September only, Tuesday 08:00 CT open proxy, 5 trading-session hold
- Trades: `23`
- Mean: `1.42%`
- Median: `1.12%`
- Hit rate: `82.61%` (`19` wins / `4` losses)
- t-stat: `2.78`
- Profit factor: `5.03`
- Exact binomial p-value: `0.0026`

## Baseline Comparison
| Sample | n | Mean | Median | Hit | t-stat | Profit factor |
|---|---:|---:|---:|---:|---:|---:|
| Sep ΔSurprise<=-0.10 signal weeks | 23 | 1.42% | 1.12% | 82.61% | 2.78 | 5.03 |
| All September crop-report weeks | 61 | 0.33% | 0.39% | 59.02% | 1.01 | 1.40 |
| September non-signal crop-report weeks | 38 | -0.33% | -0.09% | 44.74% | -0.86 | 0.70 |
| All Jun-Oct crop-report weeks | 301 | -0.00% | -0.31% | 45.18% | -0.01 | 1.00 |
| Jun-Oct ΔSurprise<=-0.10 signal weeks | 86 | 0.58% | 0.36% | 56.98% | 1.44 | 1.54 |
| All September session-open days rolling 5d | 285 | 0.25% | 0.19% | 51.93% | 1.70 | 1.29 |
| September monthly buy-and-hold | 14 | -0.52% | 1.08% | 71.43% | -0.40 | 0.74 |
| Monthly rolling Jun-Oct long | 70 | -0.86% | -1.13% | 44.29% | -0.90 | 0.75 |

## Randomization Test
Randomly selected `23` September crop-report weeks from the `61` available September weekly observations, repeated `50,000` times.

| Test | p-value |
|---|---:|
| Simulated mean >= observed mean | 0.0037 |
| Simulated hit rate >= observed hit rate | 0.0028 |
| Simulated profit factor >= observed profit factor | 0.0078 |

The average simulated mean was `0.33%`. The 95th percentile simulated mean was `1.01%`; the 99th percentile was `1.27%`.

## Month And Threshold Check
At the selected `ΔSurprise <= -0.10` threshold, September is the standout month.

| Month | Trades | Mean 5d | Hit | t-stat | Profit factor |
|---|---:|---:|---:|---:|---:|
| Jun | 19 | 0.70% | 47.37% | 0.51 | 1.35 |
| Jul | 18 | 1.13% | 50.00% | 1.32 | 2.30 |
| Aug | 14 | -1.03% | 42.86% | -1.53 | 0.28 |
| Sep | 23 | 1.42% | 82.61% | 2.78 | 5.03 |
| Oct | 12 | -0.14% | 50.00% | -0.23 | 0.85 |

## Timing Inside September
| Bucket | Trades | Mean | Hit | t-stat | Dates |
|---|---:|---:|---:|---:|---|
| Sep 1-10 | 12 | 1.20% | 83.33% | 1.52 | 2013-09-01, 2013-09-08, 2014-09-07, 2015-09-06, 2016-09-04, 2018-09-02, 2019-09-08, 2020-09-06, 2021-09-05, 2023-09-03, 2024-09-01, 2025-09-07 |
| Sep 11-20 | 4 | 0.75% | 75.00% | 0.97 | 2015-09-20, 2017-09-17, 2022-09-18, 2023-09-17 |
| Sep 21-30 | 7 | 2.16% | 85.71% | 2.37 | 2016-09-25, 2019-09-22, 2019-09-29, 2020-09-27, 2022-09-25, 2025-09-21, 2025-09-28 |

## Year Stability
| Year | Trades | Mean | Hit | t-stat | Dates |
|---|---:|---:|---:|---:|---|
| 2013 | 2 | -2.16% | 50.00% | -0.74 | 2013-09-01, 2013-09-08 |
| 2014 | 1 | 0.14% | 100.00% | NA | 2014-09-07 |
| 2015 | 2 | 4.04% | 100.00% | 1.89 | 2015-09-06, 2015-09-20 |
| 2016 | 2 | 3.97% | 100.00% | 4.46 | 2016-09-04, 2016-09-25 |
| 2017 | 1 | 0.07% | 100.00% | NA | 2017-09-17 |
| 2018 | 1 | 0.75% | 100.00% | NA | 2018-09-02 |
| 2019 | 3 | 2.39% | 100.00% | 2.06 | 2019-09-08, 2019-09-22, 2019-09-29 |
| 2020 | 2 | 4.09% | 100.00% | 4.07 | 2020-09-06, 2020-09-27 |
| 2021 | 1 | -1.15% | 0.00% | NA | 2021-09-05 |
| 2022 | 2 | 0.08% | 50.00% | 0.07 | 2022-09-18, 2022-09-25 |
| 2023 | 2 | 1.40% | 100.00% | 1.93 | 2023-09-03, 2023-09-17 |
| 2024 | 1 | 1.12% | 100.00% | NA | 2024-09-01 |
| 2025 | 3 | 0.54% | 66.67% | 0.73 | 2025-09-07, 2025-09-21, 2025-09-28 |

## Top-Winner Dependence
| Dropped top winners | Trades | Mean | Hit | t-stat | Profit factor |
|---:|---:|---:|---:|---:|---:|
| 0 | 23 | 1.42% | 82.61% | 2.78 | 5.03 |
| 1 | 22 | 1.20% | 81.82% | 2.49 | 4.26 |
| 2 | 21 | 1.01% | 80.95% | 2.18 | 3.63 |
| 3 | 20 | 0.82% | 80.00% | 1.84 | 3.03 |
| 5 | 18 | 0.52% | 77.78% | 1.19 | 2.16 |

## Interpretation
The September effect is not simply generic September long exposure: September buy-and-hold is weak, and random September weekly selections rarely match the observed signal mean, hit rate, or profit factor. The pattern is strongest when crop-condition surprise deteriorates abruptly, which fits the economic story of late-season yield-risk repricing.

The main caveat is still selection bias: September became the focus after exploration. This should be treated as a promising research effect that needs live paper trading, cross-crop tests, and a formal walk-forward design before it is treated as production alpha.
