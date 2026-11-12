---
type: idea
title: Integrate a null-only radial envelope before tracking contact branches
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
tags:
  - spherical-population-bh
  - radial-envelope
  - restricted-family
  - search-round-3
---

The failed round-3 candidate \`cand_spherical_isotropic_population_bh_bound_r3_s6_sparse_boundary_mass\` supplies a mean-law-independent upper-envelope step at the fixed parameters \(d=4\), \(u=104\), \(q=2Q(u)\). Its exclusion argument never uses the displayed alternative support or mass; only the final tail comparison uses \(\pi_0\geq1/2\).

For \(S(r)=\sup_{x\geq u}H_r(x)/Q(x)\), the contact identity gives \(\operatorname{FDP}_{\mathrm{pop}}(r)\leq\min\{1,q\pi_0S(r)\}\) for every Borel mean law, including unbounded laws. The bound is also valid with no contact, and FDP is zero for \(r\leq u\). The \(d=4\) spherical tail and Gaussian lower Mills bound give, for \(r\geq u\),
$$
S(r)\leq K(1+u^{-2})r^{-1/2}u^{-3/2}e^{r^2/2},
\qquad
K=\frac{8}{3\sqrt\pi}\left(\frac{3}{2e}\right)^{3/2}.
$$
With \(b=\sqrt{u^2+10\log u}\) and the exact \(\chi_4\) density, integrate this envelope only on \([u,b]\), and use FDP at most one above \(b\):
$$
\operatorname{FDR}_{\mathrm{pop}}
\leq q\pi_0\frac K2(1+u^{-2})(b/u)^{3/2}5\log u
+\mathbb P(R>b).
$$
At \(u=104\), the displayed exact comparisons in that candidate bound the integral coefficient by \(7.26\), and \(\mathbb P(R>b)/q<3/u^2\). Consequently \(\operatorname{FDR}_{\mathrm{pop}}<7.3q\pi_0\) for every Borel \(W\) with \(\pi_0\geq1/2\), while the proposed \(d=4\) coefficient \(2+(4/\pi)(1+u^{-2})\log(3u)\) exceeds \(9\).

Possible proof route: test whether a null-envelope/radial split can be sharpened in dimension and in its tail remainder, avoiding a direct analysis of births or switches of first-contact branches where possible. This is a draft approach based on a restricted fixed-parameter exclusion. It does not establish the target for all \(u\geq104\), for other dimensions, for smaller null proportions, or uniformly when \(d,W\) depend on \(q\). No proof-certification verdict is claimed.
