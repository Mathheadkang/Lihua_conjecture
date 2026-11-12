---
type: idea
title: 共享正交方向的复制扰动可检验非线性面变分与凸序配对
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_mixed_coherence_trace_budget
tags:
  - correlated-clone-split
  - convex-order
  - signed-boundary-pairing
---

New route to audit, distinct from adding private independent copy noise. No extremizer or main bound is claimed. In a fixed finite PD latent model, fix coordinate i with unit vector v_i and split each original coordinate into K exact copies. Perturb only i's copies with unit directions (v_i+epsilon w_b)/sqrt(1+epsilon²|w_b|²), where w_b is orthogonal to v_i, and means theta_i+epsilon c_b. Shared original orthogonal Gaussian coordinates Y now give the first-order group-minimum displacement g(Y)=min_b(w_b·Y+c_b), a concave piecewise-affine function; private independent noises would give only its constant expectation. For fixed N,K,q the expanded grid has a positive threshold gap, so the prior all-or-none completion argument applies outside a Gaussian range-tail event of probability exp(−c/epsilon²).

Candidate exact first variation to derive: (F_split−F)/epsilon -> integral g(y) dμ_i(y), where μ_i sums the original actual active i-face signed FDP jumps over all ranks, weighted by the Gaussian density at T_i=u_r and the orthogonal Gaussian density. All label and inverse-rank jumps remain, and the Gaussian marginal coordinate has unit norm. At a hypothetical finite global model maximum stable under all such expanded-model perturbations, every lawful concave PL g must have integral<=0. For free means (theta_i<0 or >0), ordinary mean and tangent-direction stationarity would also give μ_i(total)=0 and integral y dμ_i=0. After proving the PL testing/approximation step, normalized Jordan parts would satisfy μ_i^- <=cx μ_i^+. Thus a martingale coupling might pair positive and negative face charges before taking their Gaussian cost. At theta_i=0 the shifts c_b must be nonpositive; no free-mean equality or zero unmatched mass can be assumed.

Primary coupling source checked: Leskelä and Vihola, Conditional convex orders and measurable martingale couplings, Bernoulli23(4A)(2017)2784–2807, DOI10.3150/16-BEJ827, arXiv:1404.0999v3 https://arxiv.org/html/1404.0999v3. Theorem1.1 states convex order iff a martingale coupling for probability measures on R^d with finite first moments; Theorem1.3 gives measurable kernel couplings under pointwise convex order. Source §1.3 attributes the underlying existence proof to Strassen's Hahn–Banach argument; it is not a full proof to adapt here. No library dependency or source asset has been silently added.

Open obligations before a plan can use this: prove the correlated-clone first variation with actual rank faces; obtain usable approximate nonlinear variation inequalities for near-extremizers without assuming an attained finite PD maximum or choosing epsilon below a model-dependent grid gap while ignoring its FDR approximation error; handle zero-null boundary net mass; and prove a quantitative q-scaled cost for the martingale pairing. Mere existence of a coupling does not bound its cost. A clone-invariant metric/Ekeland first-order reduction is a possible way to investigate the approximation issue, but completeness, continuity and admissible comparison must be established, not assumed. The source's convex order is not established for arbitrary BH models.
