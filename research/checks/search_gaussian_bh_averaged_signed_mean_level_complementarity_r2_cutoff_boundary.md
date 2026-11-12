---
type: search_round
title: >-
  Round 2 summary of fixed-regularizer escape searches and level-boundary
  reduction
target_asset: gaussian_bh_averaged_signed_mean_level_complementarity
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates: []
statement_digest: e3dcfc508ee344fb52d4454b0676313187354eefcb69339fb28a33f503d7f350
performed_by: unknown
created_at: '2026-11-09T08:13:56.675Z'
extension_version: 0.0.4
---

## Obstructions

- The previously certified singleton obstructions remain in force: a strictly negative true singleton improves its normalized penalized objective when its mean moves toward zero, and a strictly positive false singleton improves it when its mean shrinks while its FDP payoff stays zero. These are failures of actual global maximality, not refutations of the fixed-law conclusions.
- This round supplies no candidate files. Its search report says that extreme-mean and posterior-concentration explorations produced no new counterexample with positive private noise and cutoff fixed, and that the level-zero exploration encountered a cutoff bound. The pack supplies no explicit objects or calculations for those explorations, so they are not promoted here to certified whole-family impossibility statements. In particular, lack of a survivor does not prove uniform absolute continuity or complementarity.
- A useful proof-step obstruction to level-zero escape is the following conditional reduction. If the approved model gives rank-R discovery cutoff qR, true discovery mass V_R, FDP D=V_R/R, 0≤χ_a≤1 vanishing on R≤a, and unconditional true-tag marginal validity E[V_q]≤q at deterministic cutoff q, then V_R≤V_q and χ_a(R)D≤V_q/a pathwise. Hence F^a≤q/a and F^a/(qU)≤1/(aU). For fixed δ>0 this upper-bounds the unpenalized objective by 1/(aU)−δ log(1/q), tending uniformly to minus infinity as q tends to zero. Comparison with one fixed finite-moment lawful pair would then confine maxima with bounded η to a common positive level interval. The stated model identities must be verified from the approved dependencies: this pack does not reproduce them. This conditional route and the elementary subsequent value/penalty comparison are recorded as draft approach idea_fd90b2fd8168; they do not assert a proved target conclusion.

## Limitations

No candidate reached a checked conclusion failure, and no actual canonical normalized maximizing law was constructed or independently verified. The reported extreme-mean, posterior-concentration and level-boundary explorations do not cover all multitype or diffuse directing laws. A law varying with an escape parameter would in any case not automatically contradict the target's compactness assertion, which fixes the law and all private regularizers.

The round does not establish joint measurability, representative invariance, uniform absolute continuity of posterior gradients for a fixed law, weak compactness, exact active support representation, nested-intersection support limits, total-flux survival integration, lawful-velocity extension to K, weak closedness and separation of C^-+K^circ, or averaged cone matching. The fixed-cutoff boundary reduction still requires the explicit dependency checks stated above, and the common level interval and penalty limit have not been certified here as target results. There is no passage to vanishing cutoff/private noise, no unrestricted extremal flux estimate, and no conclusion about either main Gaussian BH bound.
