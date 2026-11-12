---
type: search_round
title: Round 2 obstructions for slowly growing factor dimension
target_asset: slow_factor_dimension_one_sided_sharpness
mode: refute
round: 2
directions:
  - extremal
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 41c776b5ba7a93e0fc85e9c920013f0df855975e6702b5c0f76f09e9b822fd15
performed_by: unknown
created_at: '2026-11-04T07:14:45.689Z'
extension_version: 0.0.4
---

## Obstructions

The supplied handoff covers `boundary_degenerate`, `small_cases`, `drop_hypothesis`, and `known_counterexamples`. No new candidate file or surviving counterexample was reported. The following records supplied search outcomes without independently certifying them.

- **Near-edge admissible dimension growth still leaves a negligible reported radial remainder.** Put $L=\log(1/q)$. The tested budgets of the form $D(q)=\sqrt L/(\log L\,h(q))$, with $h(q)\to\infty$ and the required positive-dimension convention, still have reported remainder $\Delta=o(\sqrt L)$. Taking an arbitrarily slow divergence of $h$ does not, in the supplied boundary check, produce the asymptotic overshoot needed for a counterexample.
- **Budget oscillation and integer rounding do not remove the rank-one lower construction.** An admissible oscillating $D(q)\geq1$ always has $\lfloor D(q)\rfloor\geq1$, so the supplied rank-one common-factor construction remains available at every sufficiently small level. Neither nonmonotonicity nor floor discontinuities yielded a reported violation.
- **The tested fixed dimensions do not violate the upper constant.** The supplied checks at $d=1$ and $d=2$ obey the reported uniform radial upper estimate. These low-dimensional cases supplied no new candidate beyond the failed small-model and boundary families already on the board.
- **Deterministic level dependence stays within the target, while the proposed random-parameter and correlated-residual escapes change the model.** Allowing finite test counts, means, or loadings to depend deterministically on $q$ does not evade the stated uniform assertion. The supplied checks classify data-dependent parameters and correlated residuals as outside the specified Gaussian factor representation, so those proposals do not satisfy all target hypotheses.

## Limitations

- The context pack contains no round-2 candidate bodies or new candidate files. This record summarizes the supplied four-direction handoff and does not turn absence of a survivor into a proof.
- A general chi-quantile remainder estimate uniform over every integer $1\leq d\leq\lfloor D(q)\rfloor$ under the stated growth condition remains a proof obligation. The reported near-edge calculation and checks at $d=1,2$ do not independently certify that estimate.
- The complete argument must still handle the supremum over all admissible finite test counts, mean vectors including negative null means, and loading vectors. It must also justify the lower-construction embedding from its source; this summary performs no new source verification.
- No conclusion about the unrestricted Gaussian upper-bound target follows from these restricted-factor search outcomes.
