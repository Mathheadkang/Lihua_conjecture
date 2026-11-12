---
type: search_round
title: One-sided Gaussian BH round 1 boundary and dimension limitations
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
performed_by: unknown
created_at: '2026-11-11T16:35:40.127Z'
extension_version: 0.0.4
---

## Obstructions

- Every model with an empty true-null set has false discovery rate zero, so this family cannot refute a positive upper bound.
- A rank-zero covariance cannot satisfy the unit-diagonal hypothesis for any positive number of tests. Singularity itself is admissible and is not excluded by this observation.
- For each finite admissible Gaussian model, every coordinate has variance one and hence a continuous marginal distribution. Each equality to any of the finitely many BH thresholds therefore has probability zero, even when the joint covariance is singular. A putative failure relying only on positive probability of such exact threshold equalities cannot work; this does not remove ties between coordinates or change the largest-rank BH convention.
- For valid null p-values under arbitrary dependence, the harmonic bound gives FDR <= (|I0|/N) q H_N, where H_N = sum_{k=1}^N 1/k. Consequently, for every fixed dimension ceiling M, all models with N <= M have FDR/[q sqrt(log(1/q))] <= H_M/sqrt(log(1/q)), which tends to zero as q decreases to zero. Bounded-dimensional families, including the checked cases N=1,2,3, cannot yield an asymptotically unbounded ratio. The dependence on H_N prevents this bound from proving the target's dimension-uniform conclusion.

## Limitations

All three workers reported no plausible new candidate and wrote no candidate files. The boundary checks and fixed-dimensional bounds above are search obstructions, not a proof of the main upper bound and not a confirmed absence of counterexamples.

No worker produced a new admissible growing-dimensional singular or negative-null-mean counterexample. Arbitrarily growing dimension, covariance rank or directional complexity, mixed null and alternative means, and their joint dependence on q remain unrestricted and unresolved. In particular, neither the Gaussian averaged-envelope estimate nor its uniform singular-limit gate was established in this round. The finite conditional compound-p calibration, its precise source theorem, and its independent verification are separate proof obligations and were not supplied by this search summary.
