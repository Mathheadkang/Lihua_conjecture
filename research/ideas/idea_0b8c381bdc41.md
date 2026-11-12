---
type: idea
title: >-
  Residual-uniform one-factor strip envelope obstructs shallow-null
  counterexamples
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Consider the concrete hypothesis-edge family T_i=theta_i+rho_i Z+sqrt(1-rho_i^2) epsilon_i, where Z,epsilon_1,...,epsilon_N are mutually independent standard Gaussians, rho_i in [-1,1], theta_i arbitrary, and all parameters and N may depend on q. In particular negative null means may lie anywhere in the shrinking strip and residual variances may vanish at unrelated rates; rho_i=+-1 is allowed. This is not a universal-model reduction.

Let U=barPhi^{-1}(q)>=1. Given Z=z with |z|<U, write t=barPhi(u), u>=U. For every true null theta_i<=0 and |rho_i|<1, its conditional rejection probability is at most barPhi((u-rho_i z)/sqrt(1-rho_i^2)). The identity (u-rho_i z)^2-(1-rho_i^2)(u^2-z^2)=(rho_i u-z)^2 and positivity imply this is at most barPhi(sqrt(u^2-z^2)). Degenerate rho_i=+-1 give conditional probability zero in this strip and obey the same bound.

Using barPhi(v)<=phi(v)/v for v>0 and barPhi(u)>=phi(u)u/(u^2+1), the individual conditional tail ratio is at most 2 exp(z^2/2) u/sqrt(u^2-z^2), hence at most B_U(z)=2 exp(z^2/2)/sqrt(1-z^2/U^2). Summing over nulls before taking the level supremum shows the actual-rank compound-calibration envelope M_q(z)<=B_U(z), independently of all means, loadings, residual variances and N.

The Gaussian integral is finite exactly at the boundary: E[B_U(Z) 1{|Z|<U}]=(4/sqrt(2pi)) integral_0^U (1-z^2/U^2)^(-1/2) dz=sqrt(2pi) U. Conditional independence given Z meets the approved compound-calibration lemma, even for degenerate coordinates. Since K_q<=1+M_q, bounding its clipped contribution by 1 outside the strip gives actual full BH FDR <=2q+2q sqrt(2pi)U+P(|Z|>=U)=q[4+2sqrt(2pi)U]. This retains the original largest rank, all alternatives, all null labels and the same denominator.

Consequently this entire one-common-factor conditionally independent family cannot refute the universal q sqrt(log(1/q)) upper order, including simultaneous q-dependent shallow null means, heterogeneous signed loadings and vanishing independent noise. This does not compare the full FDR with a centered-null FDR, does not establish such a comparison for general covariance, and does not control unrestricted growing factor count. It gives no candidate for the unrestricted theorem.
