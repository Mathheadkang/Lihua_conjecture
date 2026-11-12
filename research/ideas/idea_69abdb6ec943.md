---
type: idea
title: Use conditional spherical unimodality to bound population FDP by the null mass
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
tags:
  - spherical-population
  - conditional-fdp
  - search-obstruction
---

Round-five candidate cand_spherical_isotropic_population_bh_bound_r5_s4_ultrarare_null_weak_mean supplies an analytic step for spherical_isotropic_population_bh_bound, rather than a proof of that target.

For any allowed integer d>=4 and r>0, the spherical coordinate density f_r(t) is even and nonincreasing in |t|. Thus, for x>=0 and mu>=0, the function G(mu)=H_r(x-mu)+H_r(x+mu) has derivative f_r(x-mu)-f_r(x+mu)>=0, because |x-mu|<=x+mu. Consequently G(mu)>=2H_r(x), and integrating against any Borel absolute-mean law gives F_r(x)>=2H_r(x), without bounded-support or moment assumptions.

At any finite contact the exact mass ratio therefore gives FDP_pop(r)=2*pi_0*H_r(x_r)/F_r(x_r)<=pi_0. The no-contact and r=0 conventions satisfy the same bound. Hence FDR_pop<=pi_0 uniformly in d,W,q. For the proposed target this excludes every law with pi_0<=exp(-2u^2) using its additive remainder, including pi_0=0.

This estimate alone has no q factor and does not prove the proposed O(q log u) multiplier when pi_0 is larger. It does not justify contact derivatives, radial transport, or finite-vector BH claims.
