---
type: falsification_check
title: 'Falsification check: multifactor_radial_fdr_bounds'
target_asset: multifactor_radial_fdr_bounds
outcome: no_counterexample_found
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:53:20.064Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, drop_hypothesis: cand_multifactor_radial_fdr_bounds_r1_s3_antialigned_positive_alternative failed — NOT fails: optimizing the unrestricted positive alternative in this two-test singular family gives FDR only $3q/4$.
- Round 1, drop_hypothesis: cand_multifactor_radial_fdr_bounds_r1_s3_excluded_one_sided_level failed — H3 fails: the testing level is outside the one-sided range, so the object is excluded before the conclusion is tested.
- Round 1, drop_hypothesis: cand_multifactor_radial_fdr_bounds_r1_s3_independent_zero_loading failed — NOT fails: the zero-loading boundary yields exact independent-null FDR $q_*$.
- Round 1, drop_hypothesis: cand_multifactor_radial_fdr_bounds_r1_s3_one_sided_composite_antipodes failed — NOT fails: antipodal singular dependence and negative true-null means still give FDR at most $q$.
- Round 1, drop_hypothesis: cand_multifactor_radial_fdr_bounds_r1_s3_two_sided_endpoint_full_loading failed — NOT fails: the exact FDR is $q_*$, strictly below $3q_*/2$.
- Round 1, known_counterexamples: cand_multifactor_radial_fdr_bounds_r1_s4_antipodal_rank_one failed — NOT fails: both testing tracks have FDR exactly $q$, strictly below their finite-level radial bounds even though every null loading has norm one.
- Round 2, idea_bf23916c98ed: cand_multifactor_radial_fdr_bounds_r2_s1_four_test_mixed_prds failed — NOT fails: positive regression among the three null p-values gives the uniform bound $29q/24$, below the target's lower bound $11q/8$ for this family.
- Round 2, extremal: cand_multifactor_radial_fdr_bounds_r2_s2_orthogonal_unbalanced_unitblocks failed — NOT fails: the exact FDR is $q$, strictly below the finite-level radial bound for every finite member of the sequence.
- Round 2, small_cases: cand_multifactor_radial_fdr_bounds_r2_s4_three_interior_loadings failed — NOT fails: the dependence-free upper bound $11q/6$ is strictly smaller than this model's claimed finite-level radial bound.
- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, small_cases: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 3, known_counterexamples: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 4, known_counterexamples: no plausible candidate.
- Obstruction: A family with FDR at most $q$ cannot violate the proposed bound: the displayed right-hand side is at least $q$ on the permitted level range. The supplied candidate summaries place the tested rank-one antipodal configurations, their tested composite-null variant, the independent zero-loading boundary, and the tested two-sided full-loading endpoint in this class. Thus singularity, norm-one loadings, or zero loadings alone do not produce a violation in these examples. This obstruction applies to the configurations covered by those summaries, not to arbitrary models sharing one of these features.
- Obstruction: Within the investigated two-test singular antialigned family, optimizing the unrestricted positive alternative mean gives FDR only $3q/4$. Varying that mean within this family therefore cannot violate a bound whose right-hand side is at least $q$.
- Obstruction: A testing level outside the asserted one-sided range fails the level hypothesis before the conclusion is tested. Such examples cannot refute this finite-level statement, regardless of their behavior outside its domain.
- Obstruction: In the investigated unbalanced orthogonal unit-loading block sequence, the reported exact FDR remains $q$ for every finite member. Changing block imbalance within that sequence therefore cannot violate the radial bound, whose right-hand side is at least $q$. This does not exclude other multidirectional block constructions.
- Obstruction: A dependence-free FDR bound can already exclude an interior-loading family when the radial bound exceeds it. For the tested three-coordinate interior-loading family, the supplied calculation gives $11q/6$ strictly below its radial bound. Merely moving loadings away from the endpoints consequently does not produce a violation in that family.
- Obstruction: For the tested four-test mixed family, the supplied candidate summary reports that positive regression among its three null p-values yields the uniform upper bound $29q/24$, below the radial bound's lower bound $11q/8$. If that reported regression calculation is valid, the mechanism excludes this family even when its alternative varies. This summary does not independently confirm that calculation or extend the regression property to general mixed loading configurations.
- Obstruction: The root worker additionally reports that fully loaded multidirectional nulls admit the smaller upper bound $q+q\pi_0\Delta_s(d,q)$ by integrating deterministic projection tail ratios. Taken within that reported scope, this prevents direction changes among full-unit-loading nulls from violating the larger proposed bound. This is a reported boundary-family observation, not an independently verified proof here.
- Obstruction: With exactly one true null and arbitrary total number of tests, its BH rejection implies its valid null p-value is at most $q$. Since the false discovery proportion is at most the indicator of that rejection, FDR is at most $q$. Such configurations cannot violate the displayed radial bound, whose right-hand side is at least $q$ on the permitted range.
- Obstruction: Introducing correlated residuals without supplying an admissible factor representation with conditionally independent residuals leaves the stated representation hypothesis. This perturbation is not a counterexample to that representation-specific bound. If the same Gaussian covariance admits a different admissible factor representation, its dimension, loadings, and radial bound must be checked afresh; it is not excluded merely because one chosen representation has correlated residuals.
- Obstruction: Perturbing coordinate variances away from the required unit standardization fails the standardized model hypothesis. Such a perturbation cannot refute the claim while retaining the original p-value calibration and bound. Rescaling to restore standardization requires recomputing the model parameters and does not inherit a putative violation automatically.
- Obstruction: Appending independent unused factor coordinates and zero columns to the loading matrix leaves the test-statistic law, FDR, loading norms, and residual coefficients unchanged. The chi cutoff is nondecreasing with the factor dimension, so $\Delta_s(d,q)$ and the proposed radial allowance are nondecreasing. Consequently, dimension padding alone cannot turn a configuration satisfying its original bound into a counterexample. This does not settle configurations whose additional factor directions actually carry loadings.
- Obstruction: Proposed constructions with random or sample-selected loading directions do not meet the deterministic-loading hypothesis as presented. Before they can test this statement, they must supply an admissible deterministic Gaussian factor representation and recompute its radial bound. Adaptive direction selection by itself is therefore not a counterexample within the displayed model; no exclusion of every Gaussian law admitting an alternative deterministic representation is asserted.

## Limitations

- Four directions ran, with no new candidate files and no survivor. The supplied search report identifies no additional plausible small-instance or known-model counterexample beyond the existing board. This is a nonexhaustive search outcome, not proof or certification.
- General mixed multidirectional configurations remain unclassified, including interactions among genuinely active factor directions, heterogeneous intermediate loading norms, several true nulls, and unrestricted alternatives. Padding unused coordinates does not address those interactions.
- This record uses only the supplied pack and root handoffs. It adds the two narrow obstructions above without independently rechecking earlier candidate calculations or establishing the proposed radial tail-strip estimate and uniform bound.

Object search: 9 candidate(s) in 4 round(s).
