---
type: idea
title: >-
  Isotropic weak-loading many-factor nulls do not beat the one-factor constant,
  for any factor dimension
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - counterexample-search
  - isotropic
---

Candidate counterexample family examined 2026-11-05 and found NOT to exceed the conjecture (diagnostic, not a proof). Nulls T=r b.W+s eps with b uniform on S^{D-1}, W~N(0,I_D), r->0, all nulls sharing the optimal BH tilt w=rv (it depends only on rho=|W|, so a single BH threshold serves every aligned null; this is where the common-threshold relaxation is most plausibly attainable). Population null likelihood ratio at tilt w is M_D(w rho)exp(-w^2/2), M_D the MGF of one coordinate of a uniform unit vector. Relaxation J_D(q)=E_rho[min(1,q sup_w M_D(w rho)e^{-w^2/2})], rho~chi_D. Exact large-deviation identity: with rho^2=yD, (1/D)log sup_w[...] -> (1/2)(y-1-log y) while (1/D)log chi_D density -> -(1/2)(y-1-log y); the exponents cancel for every y>1, so only prefactors matter. Laplace regime (D<<log(1/q)): integrand q/sqrt(2pi) per unit rho; Gaussian regime (D>>log(1/q)): the sup is exp(xi^2/2) with xi=(|W|^2-D)/sqrt(2D), i.e. a one-factor model in xi. Numerics (Debye-asymptotic Bessel, grid quadrature) for q=1e-32..1e-256 and D=0.25L..64L, L=2log(1/q): ratio J_D/(q sqrt(log(1/q))/sqrt(pi)) is always below the one-factor value at the same q (q=1e-256: one-factor 1.037, isotropic 0.952..1.013) and tends to 1. Conclusion: isotropy with residual noise and growing D is extremal-equivalent to one factor, not worse. A counterexample would need anisotropic or clustered structure with genuine threshold adaptation.
