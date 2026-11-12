---
type: idea
title: >-
  Finite-amplitude angular likelihood payment and the exact late-parameter
  obstruction
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
tags:
  - angular-likelihood
  - plan-stage-partial
---

Draft mathematical partial from the current PLAN stage, not independently verified and not a proof of the unrestricted BH theorem or of the full frozen-ray conjecture. Exact model: finite unit vectors v_i in R^d, deterministic weights omega_i>=0 summing to one, G standard Gaussian; L_a(g)=sum_i omega_i exp(a v_i.g-a^2/2). The parameter a is shared by every summand. Source diagnostics idea_5dfcc9a93a07 and idea_6273199a3ebd motivated retaining that one parameter; neither is assumed as a theorem.

UNIFORM BOUNDED-AMPLITUDE PAYMENT. For every finite B>=0,
E sup_{0<=a<=B} L_a(G) <= 1+B/sqrt(2*pi).
Indeed L_0=1 and pathwise sup L<=1+integral_0^B (partial_a L)_+ da. For deterministic a, E partial_a L=0. Gaussian exponential tilting gives E |partial_a L| <= sum_i omega_i E |v_i.G-a| exp(a v_i.G-a^2/2)=sqrt(2/pi). Thus E(partial_a L)_+ <=1/sqrt(2*pi). Tonelli proves the displayed claim with no dimension, number-of-directions or covariance factor. Consequently E min(1,q sup_{a<=B}L_a)<=q[1+B/sqrt(2*pi)]. The same calculation works for any probability measure on a finite-dimensional unit sphere, by Tonelli and compact-a dominated differentiation.

EXACT CONTACT IDENTITIES, NOT A LATE-PARAMETER BOUND. Put K(g)=sup_{a>=0}L_a(g). At a positive smooth interior maximizing parameter a*, let nu be the tilted angular law proportional to exp(a* v.g-a*^2/2)omega(dv), m=E_nu v. The stationarity equation gives E_nu(v.g)=a*, so g.grad logK=a*^2, grad logK=a*m and ||grad logK||<=a*. Also D(nu||omega)=a*^2/2-logK, hence logK=a*^2/2-D. For fixed a, Delta L_a=a^2 L_a and the Gaussian generator (Delta-g.grad)L_a=-a partial_a L_a. At a nondegenerate smooth contact, the envelope Hessian adds the PSD correction -(grad_g partial_a L_a)(grad_g partial_a L_a)^T/(partial_aa L_a), so the generator of K is nonnegative there. These local formulas require the stated contact regularity; no unrestricted distributional envelope assertion is used as a black box.

A SEPARATE EXACT CONTRACTION MOMENT. For 0<=sigma<1, K(sigma g)<=sum_i omega_i exp(sigma^2(v_i.g)_+^2/2), by putting the supremum inside the angular integral. Hence E K(sigma G)<=1/2+1/[2sqrt(1-sigma^2)]. This bound is uniform, but it is at a strictly contracted Gaussian argument. It does not by itself bound E min(c,K(G)). Radial convexity gives K(sigma g)<=K(g)^(sigma^2), whose direction cannot transfer this estimate to an upper bound at variance one.

FIRST UNPAID GATE AND WHY NO MAIN PLAN IS CREATED. To use the bounded-amplitude payment for q sqrt(log(1/q)), B would have to be O(sqrt(log(1/q))) or one would have to bound the contribution of maximizing a>B. The isotropic diagnostic permits relevant amplitudes of order d^(1/4), so silently imposing this cutoff loses the required all-dimension quantifier. The contact identities provide no proved late-a tail or truncation inequality. Even proving the full finite angular envelope would still require a separate justified reduction from original finite Gaussian BH with arbitrary means and the actual largest crossing; the source conjecture explicitly records that gap. No statement, approved file, proof, or native loop state is changed by this observation.
