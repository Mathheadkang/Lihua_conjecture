---
type: search_round
title: Round 4 obstructions for slowly growing factor dimension
target_asset: slow_factor_dimension_one_sided_sharpness
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates: []
statement_digest: 41c776b5ba7a93e0fc85e9c920013f0df855975e6702b5c0f76f09e9b822fd15
performed_by: unknown
created_at: '2026-11-04T07:21:02.664Z'
extension_version: 0.0.4
---

## Obstructions

The supplied round handoff reports four search directions, no new candidate files, and no survivor. The context pack likewise lists no round-4 candidates. This record summarizes those findings without independently certifying a proof.

- **Nonattainment of the finite-model supremum does not by itself obstruct the lower bound.** The supplied source-construction check allows a separate finite lower construction at each $q$. With $L=\log(1/q)$, choose its approximation error as $\delta(q)=q^2$; then $\delta(q)/(q\sqrt L)=q/\sqrt L\to0$. Thus the reported construction can approach its lower benchmark with negligible error at the target normalization, even if no single finite model attains the supremum. Its size and other deterministic parameters may depend on $q$, and the reported rank-one representation remains within $D(q)\geq1$.
- **The remaining directions supplied no new admissible object that violates the conclusion.** They did not produce a new candidate beyond the existing board's failed families or a new mechanism avoiding the recorded assumption checks. This is a report about the searched directions, not an impossibility claim for unsearched families.

## Limitations

- No new candidate body was supplied for independent recomputation. This summary does not verify the source construction, its approximation guarantee, or its factor embedding; it records the supplied lower-bound observation.
- The general chi-quantile estimate uniform over every integer $1\leq d\leq\lfloor D(q)\rfloor$ under the stated dimension-growth condition remains a proof obligation. Nonattainment of the lower supremum and repeated failure to find a counterexample do not discharge the upper-bound proof.
- The full upper argument must still cover all admissible finite test counts, mean vectors including negative one-sided null means, and loading vectors of norm at most one, including deterministic dependence on $q$.
- No conclusion about the unrestricted Gaussian upper-bound target follows from this restricted-factor search.
