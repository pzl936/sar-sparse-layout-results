# Sparse Scattering-Center Layout Design — Summary Results

This is a results-only repository for a study of black-box sparse
scattering-center layout design for SAR target emulation. It contains aggregated
tables and summary figures. It does **not** contain code, raw data, per-chip
records, model weights, or document sources.

## Method in brief

The study evaluates **Ceiling-Aware Layout Design (CALD)**:

1. A diverse pool of \(N_p\) physically valid attributed-scattering-center
   layouts is constructed offline with a white-box source ensemble.
2. The black-box target receives at most \(Q\) score-only or label-only queries.
3. CALD samples \(Q\) candidates uniformly without replacement and returns the
   best observed layout; under label-only feedback it stops at the first
   correct label.
4. The pool ceiling and the selection gap are reported separately, and a
   target-specific self-pool is used only as a diagnostic to partition chips
   into action-space-limited, transfer-limited, and covered cases.

For a pool containing \(s\) target-successful candidates, the probability that
uniform best-of-\(Q\) queries at least one successful candidate is

\[
P_{\mathrm{ceil}}(Q;N_p,s)
=1-\frac{\binom{N_p-s}{Q}}{\binom{N_p}{Q}},
\qquad Q\le N_p-s,
\]

with \(P_{\mathrm{ceil}}=1\) for \(Q>N_p-s\) and \(0\) for \(s=0\). The expected
selection gap is \(1-P_{\mathrm{ceil}}\), and the expected number of queries to
the first success is \((N_p+1)/(s+1)\) for \(s>0\). At \(Q=N_p\), CALD attains
the pool ceiling when \(s>0\).

The label-only attainment probability is exact. For score-only feedback, the
same bound is used as a sufficient condition: the selected layout is the
highest-scoring queried candidate, and the measured score-only retention is
reported in the tables.

## Key aggregated findings

- On the 50-chip sweeps, CALD with \(Q=N_p=10\) attains the pool ceiling
  exactly: 62.0/72.0% on MSTAR and 88.0/90.0% on SAMPLE for \(K=10/20\).
- On the 100-chip sweeps with \(N_p>Q\), CALD is the best or tied-best arm in all
  four dataset/interface panels at \(Q=5\) and \(Q=10\): 97.3–99.6%
  covered-stratum accuracy, within 0.4–2.7 percentage points of the oracle.
- At \(Q=1\)–3, source-prior and Bayesian arms can be competitive on some
  panels; their advantage disappears by \(Q=5\).
- The dominant MSTAR failure is action-space-limited; residual SAMPLE failures
  are predominantly transfer-limited.
- A robust multi-surrogate pool with realization-error regularization does not
  raise the five-chip pilot ceiling.

## Repository map

| Path | Content |
|---|---|
| [`results/50chip_ceiling.md`](results/50chip_ceiling.md) | 50-chip pool statistics and full-pool ceiling |
| [`results/100chip_query_efficiency.md`](results/100chip_query_efficiency.md) | 100-chip \(N_p>Q\) query efficiency, score-only and label-only |
| [`results/failure_modes.md`](results/failure_modes.md) | Three-way failure-mode counts and per-class MSTAR results |
| [`results/pilot.md`](results/pilot.md) | Five-chip intervention pilot |
| [`figures/`](figures) | Summary figures generated from the aggregated values |

## Scope and limitations

- The tables are aggregated summaries; per-chip records and raw outputs are not
  included.
- "Optimality" in the summary is scoped to the tested \(Q=5\) and \(Q=10\)
  budget and to the ceiling-optimal case \(Q=N_p\). It is not a claim of
  unconditional optimality at every \(Q\).
- The score-only guarantee relies on a score-consistency condition; the
  label-only guarantee is exact.
- No code or data are released in this repository. The figures are summary
  plots of the tabulated values, not raw experimental outputs.
