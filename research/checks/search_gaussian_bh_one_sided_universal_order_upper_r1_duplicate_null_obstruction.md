---
type: search_round
title: >-
  Round 1 duplicated-null and fixed-dimension obstructions for the one-sided
  universal order bound
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - >-
    cand_gaussian_bh_one_sided_universal_order_upper_r1_s1_perfect_duplicate_nulls
statement_digest: 334aaf8c5303a807be8f3b8e641f2fb7a35d5a6a6a5fe8080f4f22262e996d7f
performed_by: unknown
created_at: '2026-11-06T23:27:52.512Z'
extension_version: 0.0.4
---

## Obstructions

- Perfectly duplicated true-null Gaussian coordinates do not refute the order bound: the reported family has exact FDR=q for every finite test count, including arbitrarily fast growth with decreasing q, so its normalization by q sqrt(log(1/q)) tends to zero.
- Families with a uniformly bounded finite test count cannot give the required divergence: any false rejection requires a true-null p-value at most q, so the union bound gives FDR<=Nq. This dimension-dependent observation does not control the supremum over N.

## Limitations

The saved boundary_degenerate candidate passed H1 through H5 and failed NOT; the other four reported directions produced no candidate files or new objects, and no survivor was reported. Candidate bodies were not independently reconstructed here. Refuting the existential universal constants requires an admissible family whose FDR/[q sqrt(log(1/q))] is unbounded along q tending to zero, rather than a single finite-level excess. Arbitrarily growing dimension, covariance rank and directional or other model complexity remain uncovered. Non-Gaussian arbitrary-dependence p-value constructions do not meet the joint-Gaussian hypotheses. This nonexhaustive round supplies no general proof or independent verification verdict.
