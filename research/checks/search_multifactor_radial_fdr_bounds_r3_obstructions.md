---
type: search_round
title: Round 3 obstructions for finite-level radial Gaussian multifactor BH bounds
target_asset: multifactor_radial_fdr_bounds
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates: []
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:49:45.106Z'
extension_version: 0.0.4
---

## Obstructions

- With exactly one true null and arbitrary total number of tests, its BH rejection implies its valid null p-value is at most $q$. Since the false discovery proportion is at most the indicator of that rejection, FDR is at most $q$. Such configurations cannot violate the displayed radial bound, whose right-hand side is at least $q$ on the permitted range.
- Introducing correlated residuals without supplying an admissible factor representation with conditionally independent residuals leaves the stated representation hypothesis. This perturbation is not a counterexample to that representation-specific bound. If the same Gaussian covariance admits a different admissible factor representation, its dimension, loadings, and radial bound must be checked afresh; it is not excluded merely because one chosen representation has correlated residuals.
- Perturbing coordinate variances away from the required unit standardization fails the standardized model hypothesis. Such a perturbation cannot refute the claim while retaining the original p-value calibration and bound. Rescaling to restore standardization requires recomputing the model parameters and does not inherit a putative violation automatically.

## Limitations

- Four directions ran, with no new candidate files and no survivor. The supplied search report found no additional plausible small-instance or known Gaussian counterexample beyond the existing board. This does not certify the target or add independently checked exclusions to the earlier candidate calculations.
- General mixed multidirectional configurations remain unclassified. In particular, the single-null observation does not resolve interactions among several true nulls with heterogeneous intermediate loadings and unrestricted alternatives.
- This record uses the supplied pack and root handoffs only. It provides no general radial tail-strip proof, no exhaustive search over admissible factor representations, and no independent verification of the earlier regression or full-loading calculations.
