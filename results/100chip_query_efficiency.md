# 100-Chip Query Efficiency at \(N_p>Q\)

Covered-stratum accuracy (%). The pool ceiling is 100% on this stratum, so the
selection gap is \(\Gamma=100-\text{Accuracy}\).

## (a) MSTAR, score-only, \(N_p=24\)

| Method | \(Q=1\) | 3 | 5 | 10 |
|---|---:|---:|---:|---:|
| **CALD** | 87.4 | 93.7 | **97.3** | **98.6** |
| transfer | 89.2 | 89.2 | 89.2 | 89.2 |
| greedy | 89.2 | 91.9 | 93.2 | 98.6 |
| BALS-TS | 84.2 | 90.5 | 93.2 | 98.6 |
| stability | 89.2 | 91.9 | 90.5 | 91.9 |
| NES | 86.9 | 90.1 | 91.4 | 92.3 |
| SimBA | 89.2 | 90.1 | 90.1 | 91.0 |
| random search | 88.7 | 89.6 | 90.1 | 91.0 |
| oracle@24 | 100.0 | 100.0 | 100.0 | 100.0 |

## (b) MSTAR, label-only, \(N_p=24\)

| Method | \(Q=1\) | 3 | 5 | 10 |
|---|---:|---:|---:|---:|
| **CALD** | 87.4 | 93.7 | **97.7** | **99.1** |
| transfer | 89.2 | 89.2 | 89.2 | 89.2 |
| greedy | 89.2 | 91.9 | 93.2 | 98.6 |
| BALS-TS | 84.2 | 89.2 | 93.7 | 97.3 |
| stability | 89.2 | 91.9 | 90.5 | 91.9 |
| NES | 86.9 | 91.4 | 91.9 | 91.9 |
| SimBA | 89.2 | 90.1 | 90.1 | 90.5 |
| random search | 88.7 | 89.6 | 90.1 | 91.0 |
| oracle@24 | 100.0 | 100.0 | 100.0 | 100.0 |

## (c) SAMPLE, score-only, \(N_p=18\)

| Method | \(Q=1\) | 3 | 5 | 10 |
|---|---:|---:|---:|---:|
| **CALD** | 87.6 | 95.5 | **98.1** | **99.6** |
| transfer | 89.9 | 89.9 | 89.9 | 89.9 |
| greedy | 89.9 | 91.0 | 96.6 | 97.8 |
| BALS-TS | 88.4 | 95.9 | 96.6 | 97.8 |
| stability | 89.9 | 91.0 | 89.9 | 89.9 |
| NES | 89.9 | 95.1 | 95.1 | 97.4 |
| SimBA | 89.9 | 90.6 | 92.9 | 94.4 |
| random search | 88.0 | 94.8 | 95.5 | 96.6 |
| oracle@18 | 100.0 | 100.0 | 100.0 | 100.0 |

## (d) SAMPLE, label-only, \(N_p=18\)

| Method | \(Q=1\) | 3 | 5 | 10 |
|---|---:|---:|---:|---:|
| **CALD** | 87.6 | 95.5 | **98.1** | **99.6** |
| transfer | 89.9 | 89.9 | 89.9 | 89.9 |
| greedy | 89.9 | 91.0 | 96.6 | 97.8 |
| BALS-TS | 88.4 | 95.5 | 96.6 | 98.9 |
| stability | 89.9 | 91.0 | 89.9 | 91.0 |
| NES | 89.9 | 94.0 | 94.8 | 96.3 |
| SimBA | 89.9 | 90.3 | 92.1 | 92.1 |
| random search | 88.0 | 94.8 | 95.9 | 97.4 |
| oracle@18 | 100.0 | 100.0 | 100.0 | 100.0 |

## Notes

- CALD is the best or tied-best arm in all four panels at \(Q=5\) and
  \(Q=10\). At \(Q=5\) it is the sole best; at \(Q=10\) it is best or tied.
- At \(Q=1\)–3, source-prior and Bayesian arms can be competitive on some
  panels; their advantage disappears by \(Q=5\).
- At \(Q=10\), CALD is within 0.4–1.4 percentage points of the oracle.
- Transfer uses \(Q=0\); oracle@\(N_p\) uses \(N_p\) queries and is an analysis
  bound. NES, SimBA, and random search are matched-budget gradient-free
  controls and can leave the candidate pool.
- Failure categories over all 100 chips: MSTAR action-space/transfer/covered =
  19/7/74; SAMPLE = 0/11/89.
- Values are percentages; per-chip records are not included.
