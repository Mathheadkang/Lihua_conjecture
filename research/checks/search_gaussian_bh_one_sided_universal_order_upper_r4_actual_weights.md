---
type: search_round
title: >-
  Round 4: auxiliary divergences retain bounded actual BH payments in the tested
  models
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 4
directions:
  - idea_47b8626c3e53
  - idea_47c7d6819637
  - idea_52a020fe86cd
candidates: []
statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
performed_by: unknown
created_at: '2026-11-10T20:47:04.550Z'
extension_version: 0.0.4
---

## Obstructions

- The tested two-test family associated with `idea_47b8626c3e53` defeats the proposed contraction monotonicity, but its actual BH FDR is strictly below q. Loss of this monotonicity therefore fails to refute the target: a failure of an intermediate comparison is not an unbounded actual-FDR ratio. This statement concerns the reported two-test model and its tested parameter range only.
- The localized moving-q fold family associated with `idea_47c7d6819637` has uncontrolled positive auxiliary flux while its actual BH FDR is bounded by q/2 through the PRDS structure of that specific model. Thus positive-flux growth alone cannot supply the target's NOT check. The PRDS argument applies to the tested fold model; it makes no claim that arbitrary signed Gaussian covariance satisfies PRDS.
- The mean-ordered alternative-insertion family associated with `idea_52a020fe86cd` has a divergent auxiliary insertion quantity, but the exact coefficient retained in its actual FDR calculation is bounded by 1/2. The unweighted or otherwise relaxed insertion divergence therefore does not imply divergence of actual BH FDR. This coefficient bound is restricted to the reported insertion construction and is not a general alternative-insertion theorem.
- Across these three assigned directions, any proof step replacing the actual BH contribution by a contraction modulus, positive flux, or relaxed insertion increment must justify the replacement with the activation conditions and exact BH weights intact. The reported auxiliary failures establish an obstruction to those proposed estimates, while the tested actual FDR remains of order q. No candidate was produced this round.

## Limitations

This is a summary of the supplied round-4 search report and context pack, with zero candidates. The pack lists the three idea dispositions but does not include their detailed model definitions or calculations. The quantitative two-test, fold-model, and insertion-coefficient statements above record the supplied search conclusions; this summary does not independently reverify them or extend their parameter ranges.

The round supplies no admissible q-dependent Gaussian model sequence with an unbounded ratio of actual BH FDR to q sqrt(log(1/q)). It does not address arbitrary dimension growth, arbitrary means and true-null proportions, general signed covariance including singular matrices, or unbounded rank and direction complexity. In particular, the PRDS bound for the fold model cannot be transferred to arbitrary signed Gaussian dependence.

The inherited harmonic bound excludes only sequences with bounded log N / sqrt(log(1/q)), with a sequence-dependent growth constant. The growing-depth construction still lacks a verified actual-FDR asymptotic lower bound. Neither the absence of candidates nor these bounded special-model payments proves the universal target or changes its draft status.
