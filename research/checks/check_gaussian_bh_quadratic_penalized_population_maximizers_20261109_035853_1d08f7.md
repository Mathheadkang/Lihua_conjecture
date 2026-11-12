---
type: falsification_check
title: 'Falsification check: gaussian_bh_quadratic_penalized_population_maximizers'
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
outcome: no_counterexample_found
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:58:53.667Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_bh_quadratic_penalized_population_maximizers_r1_s1_zero_mean_mixed_tags failed — NOT fails: the alternative-tagged zero, irrational mixing weights and zero second moment are compatible with explicit canonical finite approximation preserving all three required limits.
- Round 2, boundary_degenerate: cand_gaussian_bh_quadratic_penalized_population_maximizers_r2_s3_empty_null_unbounded_means failed — NOT fails: empty true-null mass and unbounded positive means admit explicit rational canonical approximation with vanishing Wasserstein error and convergent second moments; all FDRs are exactly zero.
- Round 3, boundary_degenerate: cand_gaussian_bh_quadratic_penalized_population_maximizers_r3_s1_zero_cap_antipodal_directions failed — NOT fails: in dimension one the entire zero-cap set is a compact four-atom simplex, and its weight convergence explicitly controls Wasserstein distance.
- Round 4, boundary_degenerate: cand_gaussian_bh_quadratic_penalized_population_maximizers_r4_s1_positive_cap_escaping_null_mass failed — NOT fails: the escaping second-moment mass costs only $1/n$ in $W_1$, gives a lawful strict lower-semicontinuity inequality, and has full BH FDR converging to the limit law's FDR.
- Round 4, small_cases: cand_gaussian_bh_quadratic_penalized_population_maximizers_r4_s2_escaping_positive_atom failed — NOT fails: the escaping atom has vanishing first-moment transport cost, so the sequence converges in $W_1$ inside the cap and its strict moment drop is consistent with lower semicontinuity.
- Round 5, boundary_degenerate: cand_gaussian_bh_quadratic_penalized_population_maximizers_r5_s1_diffuse_zero_circle failed — NOT fails: nearest-angle polygon quantization approximates diffuse zero-mean directional mass with vanishing Wasserstein error, exactly preserved second moment, and full FDR convergence.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: Finite zero-mean mixtures with both true-null and alternative tags, including irrational mixing weights, do not obstruct canonical finite approximation. Keep true-null means at zero, move alternative-tagged zero means to positive values tending to zero, retain the unit directions, and rationalize the finitely many positive weights while preserving total mass. These tag-respecting approximants converge in $W_1$, their second moments tend to the original zero moment, and the approved fixed-loading continuity theorem gives FDR convergence. Thus this boundary family fails the counterexample check NOT; the analytic completion itself creates no contradiction in part 2.
- Obstruction: Empty true-null mass cannot itself obstruct canonical finite approximation, even with unbounded positive mean support and finite second moment. All labels can remain alternative labels. Truncate positive means above a finite threshold and quantize them to strictly positive values; quantize unit directions on the compact sphere. The mean error tends to zero in second mean by the finite second-moment tail bound, so the resulting finite laws have convergent first and second mean moments. Rationalize their finitely many positive weights with total mass preserved, choosing the weight errors small relative to the largest retained mean and its square. This preserves Wasserstein and second-moment convergence. Every endpoint and approximant has FDP identically zero because its true-null mass is zero; hence its FDR is exactly zero, regardless of competing BH crossings. This entire empty-null family fails the counterexample check NOT. The round's single recorded candidate supplies this obstruction; it supplies no counterexample.
- Obstruction: In the fixed dimension-one, zero-second-moment-cap family, all mean parameters are zero, every unit direction is either +1 or -1, and the analytic completion permits both tags at zero. Thus the entire cap set consists of probability laws on four fixed tagged atoms. It is the image of the compact four-coordinate probability simplex. Matching common atom mass and transporting only unmatched mass gives Wasserstein distance at most one half the diameter of that finite set times the sum of the absolute coordinate-weight differences. Hence the simplex map is continuous in Wasserstein distance and its image is compact. Irrational weights, antipodal directions, and either tag do not produce noncompactness in this family. This explains the failed NOT check of the sole round-3 candidate; it is not a counterexample to the target.
- Obstruction: Escaping mean mass under a uniform finite second-moment cap cannot retain a nonvanishing first-moment tail: for every law in the cap and every R > 0, the integral of |theta| over |theta| > R is at most C/R. In particular, an atom of weight p at mean magnitude R with p R^2 <= C contributes at most C/R to the first-moment transport cost of moving its mean to zero while retaining its direction and tag; the completion permits zero means with either tag. Thus the positive- and negative-mean escape families tested this round cannot defeat Wasserstein compactness by carrying second moment to infinity. A strict drop in second moment at their Wasserstein limit is compatible with the claimed lower semicontinuity, and is not a failed conclusion. Both recorded candidates fail NOT; the candidate that also checked full BH FDR found its convergence compatible with the limit law. This is evidence about these escape mechanisms, not a proof of the complete target.
- Obstruction: Diffuse zero-mean mass on a circle of unit directions cannot obstruct finite directional approximation. Partition the circle into finitely many arcs and send each direction to a nearest polygon vertex, retaining its mean and tag. The maximum angular distance, and hence Euclidean directional displacement, tends to zero as the polygon mesh shrinks. The induced coupling has vanishing Wasserstein cost, and the second mean moment remains exactly zero. The round-5 candidate reports full largest-crossing FDR convergence, consistently with the approved fixed-loading continuity theorem. Thus diffuseness of this directional family fails the counterexample check NOT. Rationalization and any repair of alternative-tagged zero means must additionally respect the tag boundary, as in the earlier board obstruction; a positive repair has a vanishing, rather than identically zero, second mean moment.

## Limitations

- This round contains one failed boundary-degenerate candidate, involving diffuse zero-mean circular directions. It does not cover arbitrary joint distributions of means, directions and tags, unbounded means, or every finite ambient dimension.
- The reported directional quantization and moment preservation do not by themselves establish the full canonical rational approximation theorem with controlled weight errors and tag repairs for arbitrary finite-second-moment laws.
- No general proof of compactness, lower semicontinuity, penalized attainment, or applicability of FDR continuity along arbitrary maximizing sequences is supplied by this round. Nor does it establish vanishing-penalty limits, signed deterministic transport comparisons, or simultaneous finite endpoint recovery with errors of order o(epsilon).
- Failure to find a counterexample is not verification of the target. No conclusion is drawn about varying dimension, unpenalized attainment, convergence of maximizing laws, finite-model derivatives, or unrestricted Gaussian BH order bounds.

Object search: 6 candidate(s) in 5 round(s).
