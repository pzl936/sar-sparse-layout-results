# 50-Chip Pool Ceiling and Query Allocation

Full-pool ceiling on 50 chips (five per class). CALD uses \(Q=N_p=10\);
transfer uses \(Q=0\); NES uses \(Q=512\).

| Dataset | \(K\) | Arm | \(Q\) | Source succ. (%) | Candidate succ. (%) | \(C_{\mathrm{nom}}\) (%) | Accuracy (%) [95% CI] | Confidence | \(\Gamma\) (pp) |
|---|---:|---|---:|---:|---:|---:|---:|---:|---:|
| MSTAR | 10 | CALD | 10 | 95.2 | 56.2 | 62.0 | 62.0 [48.2, 74.1] | 0.61 | 0.0 |
| MSTAR | 10 | transfer | 0 | 95.2 | 56.2 | 62.0 | 54.0 [40.4, 67.0] | 0.54 | 8.0 |
| MSTAR | 20 | CALD | 10 | 100.0 | 65.0 | 72.0 | 72.0 [58.3, 82.5] | 0.70 | 0.0 |
| MSTAR | 20 | transfer | 0 | 100.0 | 65.0 | 72.0 | 66.0 [52.2, 77.6] | 0.63 | 6.0 |
| MSTAR | 20 | NES-surrogate | 512 | 100.0 | 65.0 | 72.0 | 45.0 [25.8, 65.8] | 0.45 | 27.0 |
| MSTAR | 20 | NES-random | 512 | 100.0 | 65.0 | 72.0 | 45.0 [25.8, 65.8] | 0.40 | 27.0 |
| SAMPLE | 10 | CALD | 10 | 82.6 | 73.2 | 88.0 | 88.0 [76.2, 94.4] | 0.70 | 0.0 |
| SAMPLE | 10 | transfer | 0 | 82.6 | 73.2 | 88.0 | 86.0 [73.8, 93.0] | 0.69 | 2.0 |
| SAMPLE | 20 | CALD | 10 | 99.6 | 76.6 | 90.0 | 90.0 [78.6, 95.7] | 0.76 | 0.0 |
| SAMPLE | 20 | transfer | 0 | 99.6 | 76.6 | 90.0 | 94.0 [83.8, 97.9] | 0.78 | −4.0 |
| SAMPLE | 20 | NES-surrogate | 512 | 99.6 | 76.6 | 90.0 | 75.0 [53.1, 88.8] | 0.64 | 15.0 |
| SAMPLE | 20 | NES-random | 512 | 99.6 | 76.6 | 90.0 | 85.0 [64.0, 94.8] | 0.70 | 5.0 |

Notes:

- Source success is measured on the surrogate; candidate success and
  \(C_{\mathrm{nom}}\) are measured on the hidden target.
- Negative \(\Gamma\) on the SAMPLE \(K=20\) transfer row means the transfer
  layout lies outside the ten-candidate pool; the pool ceiling is specific to
  this pool and is not a universal bound.
- CIs are Wilson 95% intervals; \(n=50\) for CALD/transfer and \(n=20\) for NES.
- CALD at \(Q=N_p\) attains the pool ceiling by construction whenever at least
  one candidate succeeds.
