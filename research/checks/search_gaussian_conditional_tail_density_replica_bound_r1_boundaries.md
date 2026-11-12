---
type: search_round
title: 'Deterministic Gaussian replica-bound boundary search, round 1'
target_asset: gaussian_conditional_tail_density_replica_bound
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: d962a0c4c2ebebb96a5dc8b28cb1e9b4f8c265c0b7f73aedb2d43016b25043f7
performed_by: unknown
created_at: '2026-11-07T00:49:45.642Z'
extension_version: 0.0.4
---

## Obstructions

- At the independent-residual endpoint $\nu=1$, the workers reported the exact maximum $S(U)/(2\pi)$ for the squared-density expression. This endpoint did not yield a violation.
- In the singular aligned family with $N=1$, $\nu\downarrow0$, and $w=U+\nu^{1/4}$, the reported asymptotic ratio of the squared-density expression to $\sqrt{2/\pi}\,\phi(U)/\sqrt\nu$ is $1/(2\sqrt2)$. This tested endpoint family did not yield a violation despite its diverging density scale.
- Decreasing the true-null mean weakens its conditional tail pointwise. The workers reported that varying an alternative mean translates the deterministic density level; those mean changes did not produce a new violating mechanism.

## Limitations

- All five workers returned NONE, with no candidate files. These outcomes report the scope of this search, not a proof of the target.
- Small-$N$ numerical exploration covered selected $N=1$ and $N=2$ cases only. It was exploratory, with no certified global optimization or exhaustive enumeration over parameters, covariance matrices, or dimensions.
- The reported boundary checks do not establish the full uniform inequality, its mixed-density extension, or the interpolation integral assertion. No independent proof verification was performed in this summary.
- Random levels, matrix aggregation, and a main FDR order bound are outside this deterministic-level target and were not established in this round.
