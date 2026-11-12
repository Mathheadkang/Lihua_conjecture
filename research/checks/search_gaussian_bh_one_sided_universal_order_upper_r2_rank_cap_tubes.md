---
type: search_round
title: 'Round 2 alternative-rank, spherical-cap, and radial-tube obstructions'
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_one_sided_universal_order_upper_r2_s1_signed_edge_rank_budget
  - >-
    cand_gaussian_bh_one_sided_universal_order_upper_r2_s2_spherical_null_grid_rare_gate
  - cand_gaussian_bh_one_sided_universal_order_upper_r2_s3_full_rank_radial_tube
statement_digest: 3c8469d532aa9402f4344908d13239599c8095bb84400073c3ab736714a30a4f
performed_by: unknown
created_at: '2026-11-11T20:05:59.955Z'
extension_version: 0.0.4
---

## Obstructions

- Signed-edge rare alternatives cannot force a violating BH crossing in the tested regime where their total count $M$ is below one independent null block's size $L$. The exact alternative rank budget $M<L$ reduces any actual false-rejection crossing to a shifted independent-uniform rank event and yields the reported bound $\operatorname{FDR}_j\le3q_j$. This obstruction depends on the rank-budget condition, rather than on discarding the signed edges or changing the full-procedure denominator. The argument is already recorded in `idea_e3b2d2c10133`.
- For the tested finite null grid on $S^2$, exact spherical-cap counting requires an actual null-only BH crossing to occur beyond radius $\sqrt{U^2+2\log U}$, where $U=\overline\Phi^{-1}(q)$. The remaining rare alternative gate has probability below $3q$, and the reported bound for the original FDR is $5qU=O(q\sqrt{\log(1/q)})$. Thus the null-span-three grid and single rare gate do not evade the target order merely through growing finite angular resolution. This restricted cap-counting argument is recorded in `idea_4e2baeb4b9e7`.
- Growing full null rank does not by itself defeat the target order when the nulls lie in the quantified shrinking residual tubes around the tested two-factor span. The reported finite-model radial-tube bound is $8q_j\sqrt{\log(1/q_j)}$ even with shallow negative null means, shrinking residuals, and rare alternatives. The obstruction retains the actual BH rank and uses the quantitative tube conditions; it is not a bound for arbitrary full-rank perturbations. The argument is recorded in `idea_7e90535f1fac`.

## Limitations

All three round 2 candidates satisfy H1–H5 and fail NOT; none survives. This summary relies on the supplied failure lines, reports, and observation titles, not an independent reconstruction of the candidate proofs. Their proof-step observations already exist natively and need no duplicates.

Unrestricted angular geometry and rank remain unresolved. The rank-budget argument does not control arbitrary alternative masses, the $S^2$ cap count does not cover arbitrary angular distributions or increasing null-span dimension, and the residual-tube argument does not cover noise outside its quantified shrinking regime. Arbitrary q-dependent means and covariance degeneracies remain admissible in the main theorem. None of these restricted bounds pays the unrestricted signed Gaussian BH flux or replaces the missing uniform control of the original largest BH crossing. The shallow-null contribution remains in the original procedure; no centering, deletion, or denominator replacement is authorized. The complete finite-model supremum and independent proof verification remain outstanding, and the main theorem remains draft and untouched.
