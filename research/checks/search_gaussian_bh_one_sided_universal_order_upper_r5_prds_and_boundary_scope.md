---
type: search_round
title: One-sided Gaussian BH round 5 PRDS and boundary scope
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 5
directions:
  - idea_e2f38f5dda41
  - idea_ec6e01a9d5e2
  - boundary_degenerate
candidates: []
statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
performed_by: unknown
created_at: '2026-11-11T16:45:22.386Z'
extension_version: 0.0.4
---

## Obstructions

- The negative-mean cluster family of idea_e2f38f5dda41 has all means nonpositive and all covariances nonnegative. Centering increases its scores coordinatewise and can only increase the all-null rejection event; the centered Gaussian model is PRDS and has BH FDR at most q. Thus the original all-null family also has FDR<=q. The loss in the proposed cluster-comparison denominator is an obstruction to that auxiliary comparison, not a counterexample to the main FDR bound. This argument uses the all-null labels and nonnegative covariances of this family.
- In the finite-replica family of idea_ec6e01a9d5e2, every true-null-to-coordinate covariance equals the nonnegative common-loading variance sigma^2. Gaussian PRDS on the true-null coordinates therefore gives ordinary BH FDR<=pi0 q=q/2, even though some alternative-to-alternative covariances are negative. A fold or steep pointwise response in this family does not overcome its actual FDR bound. This obstruction concerns finite replicas with their original Gaussian null p-values and labels; it does not assert PRDS for arbitrary signed covariance or independence of conditional compound p-values.

## Limitations

All three workers wrote no candidate files. The boundary worker found no new admissible family, which is an absence of a constructed counterexample rather than an exclusion theorem. No unbounded ratio FDR/[q sqrt(log(1/q))] was established, and no main conjecture was resolved.

The simultaneous regime in which q tends to zero, regularizing noise vanishes, means change, and the number of tests or directions grows remains allowed and unresolved. Singular limits and q-dependent degenerations outside the stated PRDS families are not ruled out by these checks. The two special-family controls do not bound aggregate false discoveries under arbitrary signed Gaussian dependence.

The finite conditional compound-p calibration and its independent source verification, the Gaussian averaged-envelope estimate, and the uniform singular-limit gate were not established in this round. In particular, PRDS of individually valid Gaussian null p-values in the displayed finite families does not justify replacing independence by PRDS in a calibration theorem that assumes independence and only aggregate conditional validity. These family bounds are search obstructions, not a proof of the dimension-uniform upper bound or an approval of the draft ideas.
