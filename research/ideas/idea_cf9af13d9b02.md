---
type: idea
title: >-
  Average a logarithmic null envelope over a uniformly admissible cutoff
  interval
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
tags:
  - spherical-population
  - cutoff-envelope
  - search-obstruction
---

Round-five candidate cand_spherical_isotropic_population_bh_bound_r5_s3_weak_positive_sparse_null supplies an analytic logarithmic cutoff-interval envelope for spherical_isotropic_population_bh_bound.

Assume a deterministic finite b>=u is admissible at every radius r>=u, so the actual smallest contact obeys u<=x_r<=b there. At r<=u the null FDP is zero. For each r and x in [u,b], monotonicity of H_r yields H_r(x)/Q(x)<=H_r(u)/Q(u)+integral_u^b H_r(t)*phi(t)/Q(t)^2 dt. This follows by integrating the derivative of 1/Q and bounding H_r(x)<=H_r(t) for t<=x.

The exact contact FDP formula, Tonelli, and E[H_R(t)]=Q(t) give FDR_pop<=q*pi_0*(1+integral_u^b phi(t)/Q(t) dt)=q*pi_0*(1+log(Q(u)/Q(b))). The argument bounds the actual contact uniformly and does not differentiate contact branches.

At d=4,u=104, choosing Q(b)=Q(u)/2048 makes b-u<1/13. The cap bound H_u(b-1)>49/99440 and (1023/1024)*(49/99440)>1/2048 show that b is admissible for every r>=u whenever W=p*delta_0+(1-p)*nu, 0<p<=1/1024, and nu([1,infinity))=1. Hence FDR_pop<8.7*q*p for that whole family, below the target coefficient (>9). This distributional extension uses monotonicity in mu and allows unbounded nu.

The unresolved step for arbitrary mixtures is to find a suitable b with sufficiently small log(Q(u)/Q(b)), or replace this cutoff assumption. This is a draft approach, not a proof of the full target.
