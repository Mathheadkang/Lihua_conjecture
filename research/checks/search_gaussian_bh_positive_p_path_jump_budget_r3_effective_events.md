---
type: search_round
title: >-
  Round 3 positive jump budget search: effective event counts and boundary
  limits
target_asset: gaussian_bh_positive_p_path_jump_budget
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_positive_p_path_jump_budget_r3_s2_mixed_sign_triangular_clones
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:35:57.563Z'
extension_version: 0.0.4
---

## Obstructions

- Fixed dimension cannot yield a refutation merely by sending means, covariance, or admissible q to a boundary. The auxiliary event set has at most N squared events, and actual simultaneous crossings are merged into net jumps. For fixed N this gives a finite event-count budget, uniformly across the tested degenerations; the denominator is bounded below by the positive constant sqrt(log(1/S(1))). Such bounds may grow with N and do not control the universal statement. Slot 1 produced no candidate: failure to obtain checked divergence is not a failed NOT check for an otherwise unbounded family.
- The mixed-sign triangular clone family has positive semidefinite rank-two covariance and three effective groups with arbitrary integer multiplicities. Oppositely signed jumps can cancel in the net signed budget, but increasing multiplicities does not increase the number of effective crossing events. The checked family has at most seven positive-charge jumps for each group-1 null and zero for each group-2 null. The earlier bound of twenty-one total events is also a valid, looser finite obstruction. Thus the null-averaged normalized positive budget stays bounded throughout this family, and candidate cand_gaussian_bh_positive_p_path_jump_budget_r3_s2_mixed_sign_triangular_clones fails NOT. Neither mixed signs, cancellation, arbitrary multiplicities, nor rank two alone supplies divergence.
- Heterogeneous negative-null blocks must retain the original conditional weights: the relevant Gaussian density at the shifted score can suppress events that an unweighted crossing count makes look large. Slot 3 found no checked divergent sequence after retaining those weights. This is a limitation of the attempted construction, not a uniform theorem for all heterogeneous blocks; no candidate with an unknown NOT check is promoted to a failed candidate or a survivor.

## Limitations

No surviving counterexample was found. General mixed-sign covariance, heterogeneous means, and a number of effective groups growing with N remain uncontrolled. The fixed-N and fixed-three-group obstructions do not bound that growth, and no reduction of general models to the tested families is established. Small-q limits must be assessed jointly with changing dimension, means, and covariance using the original weights and actual net jumps.

A possible proof step suggested by the triangular family is to control effective group count together with weighted positive variation, rather than count clone multiplicities: first bound actual positive events per selected group, then determine whether averaging their original weights offsets a growing number of groups. This is an unproved approach, not a general event-count lemma or an established black box. The universal positive-budget claim and its finite signed-identity dependency remain unverified by this round.
