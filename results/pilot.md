# Five-Chip Intervention Pilot

Pilot with a 100-step multi-surrogate + realization-error pool,
\(N_p=16\), \(K=20\).

| Chip | \(y\) | Category | Nominal rate (%) | \(C_{\mathrm{nom}}\) | \(C_{\mathrm{rob}}\) (%) | Transfer nom./rob. | Self-pool \(K=20/40\)/phase | CALD |
|---|---:|---|---:|---:|---:|---|---|---:|
| `mstar_0000` | 0 | covered | 75 | 1 | 100 | 1 / 1.00 | s / — / — | 100 |
| `mstar_0100` | 1 | covered | 88 | 1 | 100 | 1 / 1.00 | s / — / — | 100 |
| `mstar_0200` | 2 | action-space | 0 | 0 | 0 | 0 / 0.00 | f / f / f | 0 |
| `mstar_0300` | 3 | transfer | 0 | 0 | 0 | 0 / 0.00 | s / — / — | 0 |
| `mstar_0400` | 4 | action-space | 0 | 0 | 0 | 0 / 0.00 | f / — / — | 0 |

Notes:

- Nominal rate is the fraction of candidates that preserve the class on the
  hidden target at nominal parameters.
- \(C_{\mathrm{rob}}\) is the best per-candidate success fraction over ten
  held-out jitters (\(\sigma_p=0.75\) ASC px, \(\rho=0.08\)).
- CALD reaches the per-chip ceiling at \(Q=1\)–16. The comparison arms
  (score/label, NES, SimBA, random search, BALS-TS, stability) reach the same
  ceiling and do not exceed it.
- s/f = success/failure; — = not tested. The pilot is exploratory; no paired
  claim is made.
