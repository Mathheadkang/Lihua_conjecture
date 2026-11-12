---
type: search_round
title: 'Round 3: zero directions and infinite-dimensional correlation constraints'
target_asset: gaussian_bh_exchangeable_array_variational_compactification
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r3_s1_zero_direction_empty_numerator
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r3_s2_simplex_prefix
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r3_s3_residual_negative_equicorrelation
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:58:00.399Z'
extension_version: 0.0.4
---

## Obstructions

- Zero-vector directing parameters and an empty true-discovery numerator do not themselves refute the target: the tested boundary family has a lawful exact zero-vector representation, an explicitly coercive normalized objective, and an endpoint maximum strictly below a lawful comparator. This excludes the tested family as a counterexample without establishing general representation or coercivity.
- A finite simplex residual correlation prescription need not extend to a lawful infinite exchangeable array: the tested equilateral three-coordinate prescription already has a negative eigenvalue when extended to four coordinates. It fails H3 before any conclusion can be tested; its later checks remain unknown.
- Every constant strictly negative off-diagonal residual correlation fails positive semidefiniteness in sufficiently large dimension: the all-ones eigenvalue of the n-coordinate residual matrix is 1+(n-1)rho, which is negative for large n when rho<0. Such prescriptions cannot be lawful infinite-array competitors. The tested family fails H4; its later checks remain unknown. This does not exclude dimension-dependent correlations or heterogeneous lawful arrays.

## Limitations

All three round-3 candidates failed. Only the zero-direction family reached and failed NOT; the two negative-correlation prescriptions failed hypotheses and therefore provide no evidence that the target's conclusion holds on lawful arrays. This summary uses only the supplied context pack and candidate failure lines, without independent inspection of candidate bodies. Round-3 coverage comprises boundary_degenerate, small_cases, and drop_hypothesis; it does not cover every lawful family in those directions.

The finite-prefix failures do not establish a general marked directing representation or characterize all extendible exchangeable covariance arrays. General finite-subarray completion and joint continuity, continuity at arbitrary singular covariances, moment-sublevel compactness, faithful finite-supremum comparisons with moment control, and penalized attainment remain proof obligations. The existing collision-coupling approach remains separate; no new approach is recorded from these failures.

No general logarithmic estimate including terminal rank one, normalized coercivity or attainment, vanishing-penalty limit, lawful signed transport comparison, or removal-of-common-loading limit is proved by this round. No main universal-order FDR upper bound, uniformity as sigma tends to zero, or boundedness as delta tends to zero follows.

The independently verified and researcher-approved primary-source prerequisite for clause 6 remains in force. Measurable mark recovery, the unit-ball bound, a jointly measurable isonormal representative, and affinity/integrability for selecting a maximizing directing component remain uncovered. Outer parameter mixtures remain expectations of conditional Gaussian FDRs; these failures do not yield simultaneous deterministic finite FDR/moment approximation of an arbitrary mixture.
