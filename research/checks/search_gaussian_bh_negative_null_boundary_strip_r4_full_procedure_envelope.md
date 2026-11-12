---
type: search_round
title: Round 4 search summary for the Gaussian negative-null boundary strip
target_asset: gaussian_bh_negative_null_boundary_strip
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_negative_null_boundary_strip_r4_s2_independent_mixed_means
statement_digest: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
performed_by: unknown
created_at: '2026-11-11T19:47:22.256Z'
extension_version: 0.0.4
---

## Obstructions

- The original full-procedure BH inequality bounds each rejected coordinate's contribution by its inverse-p-value envelope, with the actual rejection count and every rank-affecting coordinate retained. The board's reported Gaussian marginal integral therefore obstructs dependence-based attacks that preserve the stated marginals; the reported tie/rank argument also preserves this envelope under multiplicities and singular covariance.
- Allowing both rejection ranks to occur does not itself defeat the bound: the round's independent two-coordinate mixed-mean candidate satisfies H1–H6 but fails NOT because its exact original BH contribution is strictly below the claimed bound. Together with the earlier mixed tied-cutoff example, this rules out the proposed mechanisms in these checked examples, without excluding every mixed-mean model.
- The reported shrinking-strip endpoint and positive mean-gap limit checks retain slack in the stated coefficient. Setting the gap to zero or changing the unit-variance Gaussian marginals instead leaves the hypothesis class and supplies no counterexample.

## Limitations

The pack records one new failed candidate this round, the independent mixed-mean example; its body was not needed because its failure line is unambiguous. Endpoint and hypothesis-edge outcomes are available only through the supplied reports and board. No candidate survived, but the round does not exhaust all finite models or q-dependent parameter choices. The marginal-envelope reasoning remains search evidence pending a written proof and independent verification; the target remains draft. This record gives no control of the remaining near-boundary contribution and proves neither universal-order target. All calculations concern the unmodified full BH procedure; no deletion, recentering, relabeling, or covariance replacement is licensed.
