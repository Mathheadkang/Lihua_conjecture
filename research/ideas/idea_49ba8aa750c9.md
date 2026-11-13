---
type: idea
title: >-
  Near-boundary transfer reduces to tracking of the leave-one-out BH cutoff
  inside the thin layer
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_near_boundary_frozen_ray_transfer
tags: []
---

Plan-stage analysis of 12 Nov 2026, UNVERIFIED. (1) Mixture identity: for w>0, exp(wz-w^2/2)=int 1{z>=x}/barPhi(x) nu_w(dx) with the probability density nu_w(dx)=w barPhi(x) exp(wx-w^2/2)dx, which is approximately N(w,1). So L_w is the unit-scale average over levels of the indicator tail-ratio field F(x)=(1/N)sum_{i in B}1{Z_i>=x}/barPhi(x), and the target asks that the BH-selected level x* not see the structure of F at scale 1/x*. (2) Far layer: 1{z>=x}/barPhi(x) <= C exp(xz-x^2/2) as soon as z>=x+log(Cx)/x, so only near-boundary nulls with T_i in [x*,x*+O(log x*/x*)] (width of order a_q) can lose the hazard factor. (3) With the leave-one-out count R_i^0 (p_i set to 0) and Z_{-i}=s Sigma_{.i}+W, W independent of Z_i=s, the contribution of null i is (q/N)E_W int phi(s)1{s>=c(s)}/barPhi(c(s))ds with c(s)=barPhi^{-1}(q R_i^0/N). Integrating by parts in s, the excess over the baseline 1 is a sum over the upward jumps of c(s) taken while s>=c(s), each weighted by barPhi(s)(1/barPhi(c_+)-1/barPhi(c_-))<=1. For fixed W, a cutoff that tracks s within 1/x over a range of length l gives an excess of order x l but an exponential-kernel term of order l only, so every per-(i,W) comparison loses the factor x (this is the BY-tight case). A proof must gain by averaging over W (Cameron-Martin smoothing along the part of Sigma_{.i} of finite Cameron-Martin norm relative to Cov(W), which fails for clone or antithetic alternatives) or by summing over i (a Gram budget: alternatives j with sum_{i in B}Sigma_{ji}^2<=1 for orthonormal nulls can each steer only O(1/beta^2) nulls at correlation beta, and steering at speed 1 needs alternative density at the cutoff within a factor 1+|beta| of the BH line). Turning either into a bound runs into crossing-flux counting along moving lines, close to the obstructed idea_c23fac250465 and the failed flux plans of the main target.
