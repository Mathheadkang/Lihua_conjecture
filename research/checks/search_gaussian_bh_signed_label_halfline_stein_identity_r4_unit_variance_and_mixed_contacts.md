---
type: search_round
title: Unit-variance scope and mixed contacts in the fourth signed-label search
target_asset: gaussian_bh_signed_label_halfline_stein_identity
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates:
  - cand_gaussian_bh_signed_label_halfline_stein_identity_r4_s3_nonunit_variance
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:33:35.669Z'
extension_version: 0.0.4
---

## Obstructions

- Positive definiteness alone does not make a nonunit-variance Gaussian model admissible: the covariance must also have unit diagonal. The scalar variance-four object fails this hypothesis first, with later checks left unknown.
- FDR nonmonotonicity under changes in null means does not alone contradict the stated decomposition, which makes no monotonicity assertion.
- Strong nonnull padding alone does not contradict the fixed-label baseline budget or the unrestricted signed below-threshold remainder; no new admissible violating object was obtained in this direction.
- The examined mixed score-tie and record-contact intersection, and the mixed-sign-mean short chains with nonzero correlation, yielded no local coefficient or kernel mismatch. These are limited probes of the existing accounting mechanism, not a new proof approach.

## Limitations

Only the nonunit-variance object was developed into a failed candidate this round. The mixed-contact probe did not cover the full interface arrangement or general higher intersections. The small-case and extremal probes did not fully check heterogeneous-mean expectation identities. Near-singular and high-dimensional expectation identities, longer record cascades, and uniform behavior across models remain incompletely checked. The known-counterexample direction produced no new plausible object. No survivor was found; this round proves neither the lemma nor a singular extension, a uniform bound on the signed below-threshold remainder, or either unrestricted Gaussian BH order target.
