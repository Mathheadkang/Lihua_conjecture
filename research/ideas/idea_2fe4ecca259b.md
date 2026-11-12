---
type: idea
title: >-
  Use strong-mean radial truncation to exclude a restricted spherical population
  family
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
tags:
  - spherical-population
  - counterexample-search
  - restricted-family
---

Round 2 supplies a restricted-family obstruction, not a proof of the uniform target. Fix u=104 and q=2Q(u), and take one of the pairs (d, pi_0)=(5,1/4),(7,1/2),(9,3/4). The alternative part of W may be any probability law supported on [4u,infinity), while directions remain uniform independently of the absolute mean and residual variance is zero.

For 0<R<=2u, every alternative rejects throughout u<=x<=2u. Hence F_R(x)>=1-pi_0, and Q(2u)/Q(u)<1/4<=1-pi_0 makes 2u admissible. The first contact therefore satisfies x_R<=2u, and its FDP is at most 2 pi_0 H_R(u)/(1-pi_0). The identity E H_R(u)=Q(u), together with FDP<=1 on R>2u, gives

$$
\operatorname{FDR}_{\rm pop}\leq\frac{q\pi_0}{1-\pi_0}+\mathbb P(R>2u)\leq\frac{q\pi_0}{1-\pi_0}+2^{d/2}e^{-u^2}.
$$

For the three fixed pairs, the explicit tail comparisons in the round-2 candidate checks bound the final tail by q pi_0, yielding respectively less than (7/3)q pi_0, 3q pi_0, and 5q pi_0. Each is below the target's coefficient at u=104. This argument only uses the alternative support lower bound, so the two-atom examples represent the corresponding support-restricted families.

Provenance: cand_spherical_isotropic_population_bh_bound_r2_s7_d5_two_strong_means, cand_spherical_isotropic_population_bh_bound_r2_s7_d7_two_strong_means, and cand_spherical_isotropic_population_bh_bound_r2_s7_d9_two_strong_means, shown through the native CLI during search_summary. These checks are not a verification verdict. The argument does not control general mean laws, arbitrary dimensions or null proportions, contact births or switches, global positive variation, or conditional radial transport.
