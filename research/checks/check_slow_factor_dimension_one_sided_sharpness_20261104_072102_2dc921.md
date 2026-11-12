---
type: falsification_check
title: 'Falsification check: slow_factor_dimension_one_sided_sharpness'
target_asset: slow_factor_dimension_one_sided_sharpness
outcome: no_counterexample_found
statement_digest: 41c776b5ba7a93e0fc85e9c920013f0df855975e6702b5c0f76f09e9b822fd15
performed_by: unknown
created_at: '2026-11-04T07:21:02.672Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, small_cases: cand_slow_factor_dimension_one_sided_sharpness_r1_s2_antipodal_pair failed — NOT fails: the exact antipodal two-test FDR is only $q$, even with an admissible growing representation dimension.
- Round 1, small_cases: cand_slow_factor_dimension_one_sided_sharpness_r1_s2_growing_small_family failed — NOT fails: every family with $m=o(\sqrt{\log(1/q)})$ has normalized FDR tending to zero, including this negatively correlated simplex family.
- Round 1, drop_hypothesis: cand_slow_factor_dimension_one_sided_sharpness_r1_s3_dense_saturated_budget_edge failed — NOT fails: the finite-level radial bound and an explicit uniform chi-square quantile estimate rule out overshoot even for this rapidly growing dense family.
- Round 1, drop_hypothesis: cand_slow_factor_dimension_one_sided_sharpness_r1_s3_independent_full_rank failed — NOT fails: full covariance rank and unrestricted $q$-dependent test count yield normalized FDR tending to zero in this admissible one-factor family.
- Round 1, drop_hypothesis: cand_slow_factor_dimension_one_sided_sharpness_r1_s3_negative_antipodal_nulls failed — NOT fails: the singular, saturated, negative-null family has FDR at most $q$ and cannot violate the uniform upper bound.
- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 2, small_cases: no plausible candidate.
- Round 2, drop_hypothesis: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 3, known_counterexamples: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 4, known_counterexamples: no plausible candidate.
- Obstruction: The supplied round handoff reports four search directions and no survivor. The context pack lists five failed candidates from `small_cases` and `drop_hypothesis`; the other direction-level findings below come from the supplied handoff. These are summaries of reported checks, not independent certifications.
- Obstruction: **Too few tests cannot sustain the proposed normalization.** The reported small-family check rules out every family with $m=o(\sqrt{\log(1/q)})$: its FDR divided by $q\sqrt{\log(1/q)}$ tends to zero. The antipodal two-test example has FDR exactly $q$, and the growing negatively correlated simplex family also fails the violation check. Increasing a representation's dimension without increasing the effective small-model FDR does not overcome this obstruction.
- Obstruction: **Full covariance rank does not exceed a factor-dimension budget by itself.** Independent residual noise can produce a full-rank covariance matrix in an admissible one-factor representation with zero loadings. The reported independent family has vanishing normalized FDR even when its finite test count depends on $q$. Conversely, the supplied source check reports that the rank-one common-factor lower construction embeds at $d=1$ despite a positive-definite full covariance matrix, so covariance positive definiteness does not obstruct the matching lower construction.
- Obstruction: **The tested saturated and negative-null boundaries do not yield overshoot.** The dense saturated family near the permitted budget edge was reported to fail the violation check through the finite-level radial bound and a uniform chi-square quantile estimate. The negative antipodal null family has reported FDR at most $q$. The supplied handoff also identifies $\Gamma_0=0$ in the radial bound when all null loadings have unit norm; this boundary therefore supplies no surviving counterexample in the reported search.
- Obstruction: **Oscillation of an admissible budget is not itself a counterexample.** The supplied check found no violation from a nonmonotone or oscillating $D(q)$ satisfying the stated rate condition. Any putative counterexample must produce an actual FDR violation along an admissible sequence; oscillation alone neither removes the available $d=1$ lower construction nor establishes failure of the required uniform upper estimate.
- Obstruction: The supplied handoff covers `boundary_degenerate`, `small_cases`, `drop_hypothesis`, and `known_counterexamples`. No new candidate file or surviving counterexample was reported. The following records supplied search outcomes without independently certifying them.
- Obstruction: **Near-edge admissible dimension growth still leaves a negligible reported radial remainder.** Put $L=\log(1/q)$. The tested budgets of the form $D(q)=\sqrt L/(\log L\,h(q))$, with $h(q)\to\infty$ and the required positive-dimension convention, still have reported remainder $\Delta=o(\sqrt L)$. Taking an arbitrarily slow divergence of $h$ does not, in the supplied boundary check, produce the asymptotic overshoot needed for a counterexample.
- Obstruction: **Budget oscillation and integer rounding do not remove the rank-one lower construction.** An admissible oscillating $D(q)\geq1$ always has $\lfloor D(q)\rfloor\geq1$, so the supplied rank-one common-factor construction remains available at every sufficiently small level. Neither nonmonotonicity nor floor discontinuities yielded a reported violation.
- Obstruction: **The tested fixed dimensions do not violate the upper constant.** The supplied checks at $d=1$ and $d=2$ obey the reported uniform radial upper estimate. These low-dimensional cases supplied no new candidate beyond the failed small-model and boundary families already on the board.
- Obstruction: **Deterministic level dependence stays within the target, while the proposed random-parameter and correlated-residual escapes change the model.** Allowing finite test counts, means, or loadings to depend deterministically on $q$ does not evade the stated uniform assertion. The supplied checks classify data-dependent parameters and correlated residuals as outside the specified Gaussian factor representation, so those proposals do not satisfy all target hypotheses.
- Obstruction: The supplied round handoff reports four search directions, no new candidate files, and no survivor. The context pack contains no round-3 candidates. These observations summarize supplied checks without independent proof certification.
- Obstruction: **The additional fixed dimensions retain negligible reported quantile remainders.** Writing $L=\log(1/q)$, the supplied exact chi-tail checks for $d=3$ and $d=4$ have reported remainders of order $O(\log L)$. These checks supplied no asymptotic overshoot and extend the previously tested low-dimensional cases without resolving general growing dimension.
- Obstruction: **Mixing unit and subunit loading norms does not enlarge the reported radial coefficient beyond its bound.** The supplied mixed-norm check gives $\Gamma\leq\pi_0$ in the radial notation. Singular or mixed loading configurations therefore produced no surviving violation through this proposed mechanism.
- Obstruction: **Changing the budget domain, null convention, or Gaussian law fails target assumptions.** Removing $D(q)\geq1$, relabeling true nulls outside the stated one-sided null convention, or replacing the required Gaussian factor/residual law does not produce an admissible counterexample. These proposals address different model classes rather than passing all hypothesis checks.
- Obstruction: **No new known counterexample was supplied inside the stated class.** The known-model direction reported no additional admissible model that violates the target. Together with the existing board's rank-one embedding and factor-versus-covariance-rank distinction, this leaves no reported survivor from that direction.
- Obstruction: The supplied round handoff reports four search directions, no new candidate files, and no survivor. The context pack likewise lists no round-4 candidates. This record summarizes those findings without independently certifying a proof.
- Obstruction: **Nonattainment of the finite-model supremum does not by itself obstruct the lower bound.** The supplied source-construction check allows a separate finite lower construction at each $q$. With $L=\log(1/q)$, choose its approximation error as $\delta(q)=q^2$; then $\delta(q)/(q\sqrt L)=q/\sqrt L\to0$. Thus the reported construction can approach its lower benchmark with negligible error at the target normalization, even if no single finite model attains the supremum. Its size and other deterministic parameters may depend on $q$, and the reported rank-one representation remains within $D(q)\geq1$.
- Obstruction: **The remaining directions supplied no new admissible object that violates the conclusion.** They did not produce a new candidate beyond the existing board's failed families or a new mechanism avoiding the recorded assumption checks. This is a report about the searched directions, not an impossibility claim for unsearched families.

## Limitations

- No new candidate body was supplied for independent recomputation. This summary does not verify the source construction, its approximation guarantee, or its factor embedding; it records the supplied lower-bound observation.
- The general chi-quantile estimate uniform over every integer $1\leq d\leq\lfloor D(q)\rfloor$ under the stated dimension-growth condition remains a proof obligation. Nonattainment of the lower supremum and repeated failure to find a counterexample do not discharge the upper-bound proof.
- The full upper argument must still cover all admissible finite test counts, mean vectors including negative one-sided null means, and loading vectors of norm at most one, including deterministic dependence on $q$.
- No conclusion about the unrestricted Gaussian upper-bound target follows from this restricted-factor search.

Object search: 5 candidate(s) in 4 round(s).
