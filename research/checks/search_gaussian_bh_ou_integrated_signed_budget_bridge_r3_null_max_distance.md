---
type: search_round
title: Round 3 obstructions from positive budget and null maximum distance
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T22:07:31.156Z'
extension_version: 0.0.4
---

## Obstructions

- Exact zero-budget degeneracy cannot refute the bridge in a finite legal model with nonempty true-null set and F>0. The full FDP vanishes on an open Gaussian ball on which no true null is rejected, and hence is nonconstant modulo Gaussian null sets. Its OU integrated gradient budget is therefore strictly positive. This excludes an exact positive-numerator/zero-J object, but supplies no uniform lower bound on J/F along varying models.
- At most three true nulls cannot yield an unbounded bridge ratio, irrespective of the number of alternatives or the latent rank. Write m0=|I0|, u_q=S^{-1}(q)>=1 and M(x)=max_{i in I0}(v_i dot x). The function g(x)=-(u_q-M(x))_+ is 1-Lipschitz and satisfies fg=0 because f>0 requires M>=u_q. The direct OU covariance identity gives J(f)>=F E[(u_q-M(G))_+]. The union bound and u_q>=1 give E[(u_q-M(G))_+]>=integral_0^1 [1-3S(t)]_+ dt>0.08002948. Also F<=P(f>0)<=m0 q. Consequently F(F-q pi0)_+/(qJ(f))<37.487 when 1<=m0<=3. This is a restriction on null count, not a generic rank bound or an approved analytic black box.

## Limitations

No candidate was written in this round. The growing-rank, noise-sensitive direction produced no legal family with verified persistent positive FDR excess and an unbounded bridge ratio; its NOT check remains unknown, rather than failed. Neither exact positivity of J nor the bound for at most three true nulls controls growing null-direction families. General mixed-sign covariance, growing effective rank and null count, varying means, rank switches and simultaneous ties remain uncontrolled. The generic analytic estimate, source verification, general signed-mixture reduction and BH-specific quantitative gate remain proof obligations, so the proposed FDR consequence remains conditional. The null-maximum distance test is a restricted-null-count proof approach distinct from the earlier fixed-rank hole-covariance obstruction; neither is approved here.
