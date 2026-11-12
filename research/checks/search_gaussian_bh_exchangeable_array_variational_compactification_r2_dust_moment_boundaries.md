---
type: search_round
title: 'Round 2: orthogonal dust, escaping moments, and antipodal boundaries'
target_asset: gaussian_bh_exchangeable_array_variational_compactification
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r2_s1_orthogonal_dust
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r2_s2_dilute_escaping_alternatives
  - >-
    cand_gaussian_bh_exchangeable_array_variational_compactification_r2_s3_antipodal_zero_moment
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:54:29.319Z'
extension_version: 0.0.4
---

## Obstructions

- Orthogonal-atom dust of the tested family cannot refute finite-subarray or completed-FDR convergence: its collision-plus-compression bound forces both limits to agree. The general proof step suggested by this obstruction is to couple iid sampled indices to distinct indices, use exchangeability on the no-collision event, and bound the error of a bounded FDR functional by the repetition probability; uniform compression is a separate required input.
- Dilute diverging alternatives of the tested family cannot defeat continuity or positively penalized maximization by losing moment at the limit: their exact FDR remains continuous, while loss of their unit second moment strictly improves the penalized objective. More generally, conditional on the separate FDR-continuity claim, lower semicontinuity of the second moment makes moment loss favorable to upper semicontinuity of the penalized objective, rather than an obstruction to it.
- The tested zero-moment two-atom antipodal family cannot refute completion, lawful directing representation, or normalized small-level coercivity: its explicit continuous completion, representation, and coercivity calculation all satisfy those conclusions. Singularity and opposing directions alone do not supply a counterexample in this family.

## Limitations

All three round-2 candidates failed their NOT check. This record uses only the supplied context pack and candidate failure lines; it does not independently verify the candidate bodies or extend their calculations to every family with a similar name. Round-2 coverage comprises known_counterexamples, extremal, and boundary_degenerate.

The suggested collision coupling has been recorded as draft approach idea_80e457272a8f. Establishing its exact compatibility with the uniform-compression theorem, and then proving uniform completion and joint continuity, remain proof obligations. This round does not establish arbitrary heterogeneous-array continuity, singular-covariance continuity, moment-sublevel compactness, or the faithful finite-supremum comparisons with moment control. The escaping-moment example does not prove existence of an optimizer or simultaneous deterministic finite FDR/moment approximation of an arbitrary outer mixture.

No general terminal-rank-one logarithmic estimate, normalized coercivity theorem, attained normalized extremum, vanishing-penalty limit, lawful signed transport comparison, or removal-of-common-loading theorem follows from these failed families. The antipodal calculation does not establish any of those claims for general lawful arrays. No uniformity in sigma, boundedness as delta decreases to zero, or main universal-order FDR upper bound is established.

The general marked Dovbysh--Sudakov extension, measurable mark recovery, unit-ball bound, jointly measurable isonormal representative, and affinity/integrability for selecting a maximizing directing component remain uncovered. The independently verified and researcher-approved primary-source prerequisite for clause 6 remains in force. Outer parameter mixtures remain expectations of conditional Gaussian FDRs, and finite-second-moment attainment remains distinct from general value claims.
