---
type: search_round
title: Fixed-floor growing-family obstructions in round 2
target_asset: gaussian_bh_one_sided_private_noise_floor_order
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - cand_gaussian_bh_one_sided_private_noise_floor_order_r2_s1_growing_simplex
  - >-
    cand_gaussian_bh_one_sided_private_noise_floor_order_r2_s2_growing_antipodal_clouds
  - >-
    cand_gaussian_bh_one_sided_private_noise_floor_order_r2_s3_vanishing_mean_tied_alternatives
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:20:45.413Z'
extension_version: 0.0.4
---

## Obstructions

- In the tested growing simplex family, the reported Gaussian upper-orthant comparison and BH rank union bound give $\operatorname{FDR}\le e q/(1-e q)$ for $0<q<1/e$, uniformly over the growing dimensions in that family with its fixed positive private-noise floor. Consequently the normalized ratio $\operatorname{FDR}/\{q\sqrt{\log(1/q)}\}$ is at most $e/\{(1-e q)\sqrt{\log(1/q)}\}$ and tends to zero as $q\downarrow0$. Thus this family fails NOT despite satisfying H1--H8; increasing its dimension does not supply the required divergence. This bound is specific to the reported simplex family.
- In the tested growing antipodal-cloud family, each of the two positively correlated clouds satisfies its linear BH bound, and the reported implication from global rejection to rejection in one cloud yields $\operatorname{FDR}\le2q$, uniformly within that family at its fixed positive noise floor. Its normalized ratio is at most $2/\sqrt{\log(1/q)}\to0$. Growing dimension and the negative correlations between the two clouds therefore do not make this family pass NOT. This two-cloud reduction is separate from the simplex bound and does not cover arbitrary collections of loading directions.
- In the tested family with vanishing positive alternative means and singular tied alternatives, the reported nonnegative Gaussian conditional-shift argument bounds the original finite largest-rank BH rule by $\operatorname{FDR}\le q/2$, uniformly along that growing family at its fixed positive null noise floor. Its normalized ratio is at most $1/\{2\sqrt{\log(1/q)}\}\to0$. Thus nontrivial null common loadings, increasing dimension, vanishing positive means, and tied alternatives in this particular configuration still fail NOT; the statement is not a bound for every singular alternative block with arbitrary dependence on the nulls.
- The earlier endpoint and bounded-dimension obstructions remain distinct: actual null private noise $s_i=1$ forces zero null loading and gives $\operatorname{FDR}\le(m_0/N)q$; a uniformly bounded total dimension $N\le M$ gives $\operatorname{FDR}\le Mq$ by null superuniformity and the union bound. They neither subsume nor prove the three growing-family reductions above. Their prior draft approach is [the endpoint and bounded-dimension obstruction approach](../ideas/idea_d7fe1abf6391.md). The new family-specific proof directions, with that earlier approach linked rather than duplicated, are recorded as [Three family-specific growing-dimension BH reductions at a fixed private-noise floor](../ideas/idea_3faef74c8989.md).

## Limitations

- All three round-2 candidates pass their reported H1--H8 checks and fail NOT; none survives as a counterexample. These are family-specific uniform linear bounds, not a proof of the target for general fixed $0<s_0<1$.
- No worker covered arbitrary growing-dimensional null loading geometry, arbitrary factor dimension, mixed private-noise levels, arbitrary null proportions, or arbitrary $q$-dependent alternatives under a single fixed positive null noise floor. In particular, the three reductions do not combine into an aggregation argument over the whole class.
- A refutation requires a fixed $s_0>0$ and admissible $q$-indexed models that violate every possible constant bound for the target order as $q\downarrow0$. Letting the floor vanish or changing the largest qualifying BH rank or its non-strict inequalities addresses a different statement.
- This record uses only the current stage context pack and its candidate failure lines. It does not independently audit candidate bodies, proof details, or the scope of each family beyond the supplied descriptions. The linked approaches remain draft; the proposed general Mehler-kernel and finite-array aggregation steps remain unproved.
- The separate draft [analytic secondary-transition divergence for inequality (K)](../ideas/idea_f57e24a559f1.md) is outside the candidate analysis. It supplies no BH counterexample and no refutation of (T) or of the present fixed-floor target (S).
