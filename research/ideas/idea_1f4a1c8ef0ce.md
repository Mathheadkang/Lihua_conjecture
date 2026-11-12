---
type: idea
title: 'Extend radial transport to uniformly regular, nonisotropic loading populations'
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
  - gaussian_bh_two_sided_sharp_upper
tags:
  - unproved-extension
  - bounded-angular-density
  - diffuse-directions
---

UNVERIFIED extension beyond isotropic means/directions, not a main-conjecture proof. Conditional on each nonnegative mean mu, let unit-loading directions have a jointly measurable continuous sphere density f_mu(v), with uniform 0<kappa<=f_mu<=K<infinity. Includes null density f_0. Fix latent Gaussian orientation w=Z/||Z||; conditional radial projection density g_mu,w,r(y) is bounded above by K*g_sphere,r(y), below by kappa*g_sphere,r(y), and continuous for d>=4 (continuity of f_mu and dominated latitude integration). Folded actual mixture F_w(r,x) retains these nonisotropic densities and is C1 in r,x. Exact D=rF_r has terms (x-mu)g_mu,w,r(x-mu)+(x+mu)g_mu,w,r(-(x+mu)); B=-F_x is sum of the same two densities without multipliers.

If a component D_mu is negative then mu>x and its folded rejection probability >=P(v·w>=0)>=kappa/2; its negative derivative magnitude <=K*M_d. Thus -D<=2(K/kappa)M_d F whenD<=0. Splitting mu<=x-ell as in isotropicproof gives B/F <=(K/kappa)[2M_d/ell+2g_sphere(0)/H_sphere(ell)]. These bounds yield a radial all-pairs firstroot comparison with positive-variation constant 8(K/kappa)M_d on r>=C(K/kappa)sqrt d/u. Null foldedcdf <=2K*pi0*H_sphere,r(x); so conditionalFDP <=q*pi0*K H/Q. GaussianR remains independent ofw; for eachfixedw use SAME base radial conditionalCDF transport and then averagew. If cutoffs and C1/globalrootdetails survive, expectO_{K,kappa}(q log u)=o(qu), uniformd, for smooth bounded angular densities even though alternatives are nonisotropic. Lower oraclecost acquires K, middlebudget K*(K/kappa), highradialtail unchanged. No finiteN inference until a separately proved empiricalCDF transfer; point masses/atomic loadings have no such fixedK,kappa, hence this does not cover arbitraryGaussiancovariance. Need independently verify projectionregularity, exactsigns, constants and measurable orientationwise transport. This might isolate angular concentration rather than ambient factor dimension as necessary for worstcaseleadinginflation.
