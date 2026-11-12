---
type: search_round
title: Round 4 obstructions for finite-level radial Gaussian multifactor BH bounds
target_asset: multifactor_radial_fdr_bounds
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates: []
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:53:20.050Z'
extension_version: 0.0.4
---

## Obstructions

- Appending independent unused factor coordinates and zero columns to the loading matrix leaves the test-statistic law, FDR, loading norms, and residual coefficients unchanged. The chi cutoff is nondecreasing with the factor dimension, so $\Delta_s(d,q)$ and the proposed radial allowance are nondecreasing. Consequently, dimension padding alone cannot turn a configuration satisfying its original bound into a counterexample. This does not settle configurations whose additional factor directions actually carry loadings.
- Proposed constructions with random or sample-selected loading directions do not meet the deterministic-loading hypothesis as presented. Before they can test this statement, they must supply an admissible deterministic Gaussian factor representation and recompute its radial bound. Adaptive direction selection by itself is therefore not a counterexample within the displayed model; no exclusion of every Gaussian law admitting an alternative deterministic representation is asserted.

## Limitations

- Four directions ran, with no new candidate files and no survivor. The supplied search report identifies no additional plausible small-instance or known-model counterexample beyond the existing board. This is a nonexhaustive search outcome, not proof or certification.
- General mixed multidirectional configurations remain unclassified, including interactions among genuinely active factor directions, heterogeneous intermediate loading norms, several true nulls, and unrestricted alternatives. Padding unused coordinates does not address those interactions.
- This record uses only the supplied pack and root handoffs. It adds the two narrow obstructions above without independently rechecking earlier candidate calculations or establishing the proposed radial tail-strip estimate and uniform bound.
