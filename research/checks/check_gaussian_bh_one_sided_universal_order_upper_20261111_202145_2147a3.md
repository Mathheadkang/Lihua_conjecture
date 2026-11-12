---
type: falsification_check
title: 'Falsification check: gaussian_bh_one_sided_universal_order_upper'
target_asset: gaussian_bh_one_sided_universal_order_upper
outcome: no_counterexample_found
statement_digest: 3c8469d532aa9402f4344908d13239599c8095bb84400073c3ab736714a30a4f
performed_by: unknown
created_at: '2026-11-11T20:21:45.468Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_bh_one_sided_universal_order_upper_r1_s1_exponential_survival failed — NOT fails: the exact conditional-null density envelope bounds the actual FDR by 4q_j sqrt(log(1/q_j)), even for this exponentially varying finite rare-alternative survival profile.
- Round 1, small_cases: cand_gaussian_bh_one_sided_universal_order_upper_r1_s2_null_span_two_rare_alternative failed — NOT fails: the exact two-dimensional null-span radial event bounds the full actual FDR by $e^{-U^2/2}=O(q\sqrt{\log(1/q)})$, uniformly over growing null direction count and rare alternative multiplicities.
- Round 2, known_counterexamples: cand_gaussian_bh_one_sided_universal_order_upper_r2_s1_signed_edge_rank_budget failed — NOT fails: all signed-edge alternatives together fit below one independent null block, forcing a shifted independent-uniform rank event and FDR_j<=3q_j.
- Round 2, extremal: cand_gaussian_bh_one_sided_universal_order_upper_r2_s2_spherical_null_grid_rare_gate failed — NOT fails: exact spherical-cap counting forces an actual null-only BH crossing beyond radius $\sqrt{U^2+2\log U}$; the remaining rare alternative gate has probability less than $3q$, giving original FDR at most $5qU$.
- Round 2, boundary_degenerate: cand_gaussian_bh_one_sided_universal_order_upper_r2_s3_full_rank_radial_tube failed — NOT fails: a quantified two-factor radial-tube event bounds the actual FDR by 8q_j sqrt(log(1/q_j)), despite growing full null rank, shrinking residuals, shallow negative null means, and rare alternatives.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: In the tested conditional-independent common-factor regime with small shared null loading, exponentially varying finite rare-alternative survival profiles remain controlled by the reported exact conditional-null density envelope: the actual full-procedure FDR is at most $4q_j\sqrt{\log(1/q_j)}$. Changing the rare-alternative survival profile in this checked regime therefore does not provide the unbounded normalized FDR required by NOT. The native observation `idea_286740ee9cf8` records this argument.
- Obstruction: If the Gaussian null directions span at most two dimensions, any false rejection in the original full BH procedure requires a null statistic at least $U=\overline\Phi^{-1}(q)$. Nonpositive null means then force the norm of the two-dimensional null projection to be at least $U$. Its radial probability is $e^{-U^2/2}=O(q\sqrt{\log(1/q)})$, bounding the entire actual FDP expectation regardless of the number of null directions or the rank and multiplicities of the rare alternatives. Thus growing alternatives alone cannot evade this null-span obstruction. The native observation `idea_743989517bf4` records the argument.
- Obstruction: The reported heterogeneous one-factor residual-variance calculation gives an integrable conditional tail-probability envelope for shallow-null contributions. This obstructs the tested residual-degeneracy mechanism within that one-factor family. It is a tail-probability bound, not a uniform conditional density cap; no density cap is inferred as residual variance vanishes. The native observation `idea_0b8c381bdc41` records this separate argument.
- Obstruction: Signed-edge rare alternatives cannot force a violating BH crossing in the tested regime where their total count $M$ is below one independent null block's size $L$. The exact alternative rank budget $M<L$ reduces any actual false-rejection crossing to a shifted independent-uniform rank event and yields the reported bound $\operatorname{FDR}_j\le3q_j$. This obstruction depends on the rank-budget condition, rather than on discarding the signed edges or changing the full-procedure denominator. The argument is already recorded in `idea_e3b2d2c10133`.
- Obstruction: For the tested finite null grid on $S^2$, exact spherical-cap counting requires an actual null-only BH crossing to occur beyond radius $\sqrt{U^2+2\log U}$, where $U=\overline\Phi^{-1}(q)$. The remaining rare alternative gate has probability below $3q$, and the reported bound for the original FDR is $5qU=O(q\sqrt{\log(1/q)})$. Thus the null-span-three grid and single rare gate do not evade the target order merely through growing finite angular resolution. This restricted cap-counting argument is recorded in `idea_4e2baeb4b9e7`.
- Obstruction: Growing full null rank does not by itself defeat the target order when the nulls lie in the quantified shrinking residual tubes around the tested two-factor span. The reported finite-model radial-tube bound is $8q_j\sqrt{\log(1/q_j)}$ even with shallow negative null means, shrinking residuals, and rare alternatives. The obstruction retains the actual BH rank and uses the quantitative tube conditions; it is not a bound for arbitrary full-rank perturbations. The argument is recorded in `idea_7e90535f1fac`.
- Obstruction: In the tested fixed-dimensional isotropic small-loading null family, the reported angular dilution cancels the proposed radial gain, while rare alternatives can produce earlier crossings of the actual BH procedure. Increasing the radial contribution alone therefore does not establish a violating FDR sequence in this restricted family. The existing draft observation `idea_6785334fa9ae` records the calculation; this summary does not extend it to growing dimension or arbitrary angular measures.
- Obstruction: A pointwise FDP reversal under shallow-null centering is insufficient to establish a main-theorem counterexample or an expectation comparison. The diagnostic `idea_d4ddf73494dc` reports that centering changes the largest BH rank pointwise while the full expected FDR moves oppositely, with a reported increase only of order $q$. This calculation remains unverified, so it is a warning against the pointwise shortcut and not a verified family exclusion or a license to replace the original null means.
- Obstruction: The reported isotropic angular likelihood-ratio envelope is uniform in dimension, using noncentral chi radial density caps. Within that isotropic angular calculation, merely increasing dimension does not restore the proposed radial amplification after angular averaging. This is a draft restricted-family diagnostic recorded in `idea_5dfcc9a93a07`; it does not cover an arbitrary angular measure $\nu$. Its radial density caps also do not imply a uniform conditional density cap for vanishing residual variances.
- Obstruction: The reported exact centered-rank expansion retains the selected largest BH rank. Forgetting that selected-rank weight and applying a marginal union bound loses a factor $N$, so this relaxation cannot furnish the required universal constant. The draft diagnostic `idea_6a6dd5cbb6e1` records the reduction and the dimension loss. This obstructs that proposed proof shortcut, not the main theorem or every centering comparison.
- Obstruction: In the reported nonisotropic shrinking-latitude parabolic-limit likelihood, retaining the one common parameter shared by its two factors prevents the proposed amplification and keeps the limiting envelope at the target order. Maximizing the factors separately introduces a spurious logarithmic loss and does not demonstrate an actual violating finite BH model. This is the restricted limiting diagnostic already recorded in `idea_6273199a3ebd`; no duplicate idea is needed.

## Limitations

No worker wrote a candidate in round 5. The other directions identified no novel family beyond the board's existing obstructions. This absence does not exhaust the target's hypothesis class or establish its conclusion.

The nonisotropic calculation is draft limiting evidence, not a finite-model BH theorem, and was not independently re-audited in this summary. Transfer of its common-parameter envelope to the original largest qualifying crossing remains open. Arbitrary angular distributions, unrestricted signed covariance and growing rank, arbitrary alternative masses, and simultaneous q-dependent degeneracies remain unresolved. The selected-rank FDP weight and signed cancellations must remain in the actual full-procedure expectation; no separate-maximization proxy, null centering, or coordinate deletion is licensed. A universal bound on the entire finite-model supremum and fresh independent verification remain outstanding. The main theorem remains draft and untouched.

Object search: 5 candidate(s) in 5 round(s).
