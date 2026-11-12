---
type: search_round
title: >-
  OU bridge round 4: independent antipodal folding and unresolved dense
  directions
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_ou_integrated_signed_budget_bridge_r4_s2_independent_antipodal_tensor
  - >-
    cand_gaussian_bh_ou_integrated_signed_budget_bridge_r4_s3_independent_antipodal_fold
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T22:15:19.931Z'
extension_version: 0.0.4
---

## Obstructions

- Independent all-null antipodal pairs with zero means cannot refute the bridge, even when the number of pairs and effective rank grow. For scores $(G_a,-G_a)$, the full largest-count BH rejection event at level $q\leq S(1)$ reduces exactly to BH on the independent folded values $U_a=2S(|G_a|)$, which are iid uniform. Hence $F=q=q\pi_0$, the positive excess and bridge ratio vanish, and the first failing candidate check is NOT. This is a family obstruction, not a restriction on arbitrary interacting mixed-sign models.
- The same exact largest-count fold excludes the tested negative-mean perturbation $(G_a-1/m,-G_a-1/m)$ with independent coordinates: $U_a=\min\{1,2S(|G_a|-1/m)\}$ are independent superuniform variables, so $F\leq q=q\pi_0$. These legal growing-rank, growing-null-count models with means approaching zero again fail NOT because their positive excess and bridge ratio are zero. Treating independent copies of a local antipodal gadget as interacting blocks does not evade this obstruction.

## Limitations

The dense growing-direction / nearly constant FDP direction produced no candidate with both checked positive FDR excess and complete signed-budget asymptotics; its NOT check remains unknown. It is not a failed counterexample. The two written candidates fail NOT by their exact folding calculations. The count simulations with 15,000 and 3,600 samples are diagnostics only: they provide no error certificate, uniform bound, or proof of the bridge.

Generic interacting mixed-sign covariance with growing null count and effective rank remains open. This round supplies neither an unbounded bridge ratio nor a universal BH gate. The generic analytic estimate, source verification, general signed-mixture reduction, and full BH-specific gate remain proof obligations, and the proposed FDR consequence remains conditional. The exact independent antipodal fold is recorded separately as a draft, restricted-family proof approach; it is not an approved black box and gives no control of dependent folded variables, mixed labels, or general rank-switch interactions.
