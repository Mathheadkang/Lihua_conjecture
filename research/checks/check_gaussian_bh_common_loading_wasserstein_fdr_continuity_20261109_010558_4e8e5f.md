---
type: falsification_check
title: 'Falsification check: gaussian_bh_common_loading_wasserstein_fdr_continuity'
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
outcome: no_counterexample_found
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T01:05:58.043Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r1_s1_mixed_zero_common_score failed — NOT fails: tied zero-mean scores with both labels have exact full FDR equal to $q$ times the true mass; positive alternative shifts and rational approximation preserve convergence.
- Round 1, small_cases: cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r1_s2_independent_two_block_completion failed — NOT fails: the mixed two-block FDR is exactly $qw$, and the completed limit is obtained by canonical rational finite arrays with $F_{\pi_n}\to F_\pi=q/2$; the other conclusion clauses also hold for this explicit family.
- Round 1, drop_hypothesis: cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r1_s3_canonical_zero_tag_boundary failed — H6 fails because changing the canonical tag costs one unit in the stipulated metric.
- Round 1, drop_hypothesis: cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r1_s3_vanishing_extreme_alternative_mass failed — NOT fails: the FDR difference equals $q\varepsilon_n$ and vanishes, while microscopic ranks reject only alternatives.
- Round 2, known_counterexamples: cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r2_s1_nonatomic_flat_crossing failed — NOT fails: the nonatomic flat-crossing pathology produces a discontinuity only at a Gaussian-null common score, and its exact full FDR converges under the Wasserstein perturbation.
- Round 2, extremal: cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r2_s2_diffuse_null_fold failed — NOT fails: a genuine interior fold produces a pathwise jump, but its switching level has Gaussian probability zero and the exact averaged full FDR is continuous under the proposed Wasserstein perturbation.
- Round 2, idea_9491db8dc586: cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r2_s3_uniform_mean_double_contact failed — NOT fails: the actual largest-root double contact yields F_pi=S(B), its exact canonical finite FDRs are S(B_n), B_n tends to B, and the remaining conclusion clauses hold on the tested laws, including the uniform microscopic estimate above.
- Round 3, idea_bef048aab3dc: cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r3_s2_circular_polygon failed — NOT fails: the circular population and canonical regular polygons satisfy all checked conclusion clauses, their actual largest ranks converge almost surely outside Gaussian-null conditional critical levels, and their full FDRs converge.
- Round 4, small_cases: cand_gaussian_bh_common_loading_wasserstein_fdr_continuity_r4_s2_antipodal_completed_pair failed — NOT fails: antipodal negative dependence strictly changes the completed FDR away from the independent-block value, but the exact full-FDR formula is continuous and all four conclusion clauses hold for the tested pair and its canonical approximations.
- Round 3, idea_8a445ee0b200: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: Coincident zero-mean scores with a mixture of true and alternative tags do not by themselves create a discontinuity: in the tested common-score family, the full FDR is exactly the true-tagged mass times $q$. The tested strictly positive alternative shifts and rational approximations preserve convergence. This family satisfies the checked hypotheses and fails NOT.
- Obstruction: The tested independent two-block completion also preserves the full mixed-label functional: its FDR is exactly $qw$, and canonical rational finite arrays converge to the completed value $q/2$. Thus this explicit independent-block family fails NOT; independence of these blocks supplies no counterexample.
- Obstruction: In the tested family with vanishing alternative mass and diverging alternative means, the FDR difference is $q\varepsilon_n\to0$, and microscopic ranks reject only alternatives. This escape of alternative means does not produce a nonvanishing FDR discrepancy in that family, so NOT fails.
- Obstruction: A sequence that changes the canonical tag across zero fails the stipulated Wasserstein-convergence hypothesis: changing a tag costs one unit in the parameter metric. For the tested canonical-zero-boundary candidate the first failure is H6, and NOT remains unknown. A mean approaching zero alone cannot establish convergence when its tag changes with nonvanishing mass.
- Obstruction: In the tested nonatomic flat-crossing family, the pathwise discontinuity occurs only at a common-score value of Gaussian probability zero. The exact full FDR converges under the specified Wasserstein perturbation, so this flat-crossing construction fails NOT.
- Obstruction: In the tested mixed-label diffuse-null fold family, an interior fold creates a pathwise jump, but its switching level has Gaussian probability zero. Exact Gaussian averaging of the original common-cutoff, mixed-label FDP preserves FDR continuity under the proposed perturbation, so this fold construction fails NOT.
- Obstruction: In the tested all-null uniform-mean double-contact family, the actual largest crossing yields the exact value $F_\pi=S(B)$, while the canonical finite approximations yield $S(B_n)$ with $B_n\to B$. Thus the double contact does not produce a discontinuity in the averaged full FDR and fails NOT; the other conclusion clauses also hold on the tested laws.
- Obstruction: In the tested family of circular continuous true-null directions and canonical regular-polygon approximations, H1--H6 pass and NOT fails. All four conclusion clauses hold for these tested laws: the population functional is well defined with the checked measurability, representative invariance and attained positive crossings; the stated microscopic-rank control holds; the full FDR is continuous along the specified Wasserstein approximation; and the canonical polygons yield ordinary finite Gaussian BH approximations with convergent FDR, including exact replication invariance. The ranks used are the actual largest non-strict crossings, retaining all competing crossings and endpoint possibilities; they converge almost surely outside Gaussian-null conditional critical levels. Thus replacing a continuous circular direction law by these polygons supplies no counterexample.
- Obstruction: In the tested antipodal correlated mixed-label two-block family and its canonical approximations, H1--H6 pass and NOT fails: recomputing the full FDR gives a continuous functional and all four conclusion clauses hold for the tested laws. Negative dependence changes the FDR from the independent-block value, so the independent-block identity cannot be used for this family; that change alone supplies no discontinuity or counterexample.
- Obstruction: Dimension growth alone does not violate the target hypotheses: finite-dimensional parameter laws can be embedded in the same fixed separable Hilbert space. Such a sequence remains eligible when its deterministic laws converge in the stipulated Wasserstein metric. However, a direction-escape construction whose unit directions remain separated and whose laws do not converge in that metric fails the convergence hypothesis; orthogonal escape without Wasserstein convergence cannot refute the continuity assertion.
- Obstruction: A sequence that varies the common loading instead of keeping the prescribed positive loading fixed does not test the asserted continuity implication. A singular limiting argument as the loading vanishes cannot supply a counterexample at the fixed loading required here.
- Obstruction: Choosing a parameter law using the realized isonormal process or common Gaussian violates the deterministic-law hypothesis. Such adaptive selections cannot refute the population functional defined for deterministic parameter laws.
- Obstruction: Constructions using nonunit directions or tags outside the closed tagged parameter domain violate the target's parameter hypotheses. In particular, a nonvanishing tag change is not an innocuous perturbation across zero mean under the stipulated tagged metric; alternative-tagged zero means must be approximated with their tag preserved.

## Limitations

Round 5 produced no candidate. These are hypothesis-screening obstructions, not a general proof of any of the four conclusions and not an exclusion of every admissible construction in the indicated broad directions.

The earlier calculations for common-score, two-block, flat-crossing, fold, double-contact and circular-direction families remain family-specific. This round does not establish general joint measurability or representative invariance, attainment and equality at every positive largest crossing, the dimension- and law-uniform microscopic-rank estimate, arbitrary-law Wasserstein continuity of the original common-cutoff mixed-label FDP, or canonical finite approximation and replication for arbitrary laws. In particular, the random-cutoff numerator must be controlled together with the actual largest non-strict crossing, including competing crossings, vanishing positive ranks and rank one.

Finite dimension growth inside a fixed Hilbert space remains admissible; only proposed sequences failing the actual Wasserstein hypothesis are excluded. No conclusion about continuity uniform in a vanishing common loading, exchange of atomization and variation limits, first-variation identities or optimization conditions follows. No genuinely new general proof step was established beyond the existing board, so no approach idea is recorded.

Object search: 9 candidate(s) in 5 round(s).
