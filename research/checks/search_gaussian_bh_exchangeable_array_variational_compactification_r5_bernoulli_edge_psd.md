---
type: search_round
title: 'Round 5: independent Bernoulli residual edges violate covariance positivity'
target_asset: gaussian_bh_exchangeable_array_variational_compactification
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r5_s2_bernoulli_edge_triple
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T06:03:10.002Z'
extension_version: 0.0.4
---

## Obstructions

- Independently assigned Bernoulli residual edges in the tested family cannot define a lawful covariance array: with probability $1/8$, three coordinates form a path whose residual quadratic form is $-1$, violating positive semidefiniteness (H7). The candidate fails a hypothesis, so NOT and subsequent conclusions remain untested; this obstruction does not rule out dependent edge constructions satisfying positive semidefiniteness.

## Limitations

Only one round-5 candidate is supplied, in the small_cases direction. This summary uses the context pack and its reported failure line without inspecting the candidate body or independently verifying its calculation. No other round-5 direction or family is covered, and no lawful counterexample survives the reported checks.

The failure supplies no new proof step beyond the required positive semidefiniteness of every finite residual subarray, so no further approach is recorded. It does not establish uniform completion, joint continuity, continuity at arbitrary singular covariances, moment-sublevel compactness, faithful finite-supremum comparisons with moment control, or penalized attainment.

The logarithmic bound including terminal rank one, uniform small-level coercivity, normalized attainment, vanishing-penalty limits, lawful signed transport comparisons, and removal of common loading remain uncovered. No main universal-order FDR upper bound, uniformity as $\sigma$ tends to zero, or boundedness as $\delta$ tends to zero follows.

Clause 6 remains subject to its independently verified and researcher-approved primary-source representation theorem. Measurable mark recovery, the unit-ball bound, a jointly measurable isonormal representative, and affinity/integrability for selecting a maximizing directing component are not established. Outer parameter mixtures remain expectations of conditional Gaussian FDRs; no simultaneous deterministic finite FDR/moment approximation of an arbitrary mixture is obtained.
