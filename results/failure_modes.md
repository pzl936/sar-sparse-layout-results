# Three-Way Failure Modes and Per-Class Results

## (a) Ceiling and failure-mode counts

| Dataset / pair | \(n\) | \(K\) | \(N_p\) | \(C_{\mathrm{src}}\) (%) | Action-space | Transfer | Covered | \(\Gamma_5\) | \(\Gamma_{10}\) |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| MSTAR R50→A-ConvNet | 50 | 10 | 10 | 62.0 | 18 | 1 | 31 | — | 0.0 |
| MSTAR R50→A-ConvNet | 50 | 20 | 10 | 72.0 | 11 | 3 | 36 | — | 0.0 |
| SAMPLE R18→EffB0 | 50 | 10 | 10 | 88.0 | 1 | 5 | 44 | — | 0.0 |
| SAMPLE R18→EffB0 | 50 | 20 | 10 | 90.0 | 0 | 5 | 45 | — | 0.0 |
| MSTAR R50→A-ConvNet | 100 | 20 | 24 | 74.0 | 19 | 7 | 74 | 2.7 | 1.4 |
| SAMPLE R18→EffB0 | 100 | 20 | 18 | 89.0 | 0 | 11 | 89 | 1.9 | 0.4 |

## (b) MSTAR per-class results at \(K=20\), \(n=5\) chips per class

| Class | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| CALD accuracy (%) | 100 | 100 | 80 | 0 | 40 | 100 | 80 | 40 | 100 | 80 |
| Action-space | 0 | 0 | 1 | 4 | 2 | 0 | 1 | 3 | 0 | 0 |
| Transfer | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 1 |
| Covered | 5 | 5 | 4 | 0 | 2 | 5 | 4 | 2 | 5 | 4 |

## Definitions and notes

- \(C_{\mathrm{self}}\) is the target-specific self-pool ceiling;
  \(C_{\mathrm{src}}\) is the source-pool ceiling.
- **Action-space-limited:** \(C_{\mathrm{self}}=0\) and \(C_{\mathrm{src}}=0\).
- **Transfer-limited:** \(C_{\mathrm{self}}=1\) and \(C_{\mathrm{src}}=0\).
- **Covered:** \(C_{\mathrm{src}}=1\).
- \(\Gamma_Q\) is the selection gap at \(Q\), in percentage points.
- The 50-chip rows use \(Q=N_p=10\), so \(\Gamma_{10}=0\); the 100-chip rows
  use \(N_p=24/18\) and report the covered-stratum gap.
- The per-class breakdown uses five chips per class; the counts are descriptive
  and per-chip records are not included.
