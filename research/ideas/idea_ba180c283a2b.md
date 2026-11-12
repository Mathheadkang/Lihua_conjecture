---
type: idea
title: >-
  Represent the actual Gaussian BH rank by a suffix-minimum barrier with
  fractional tie labels
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
  - gaussian_bh_diffuse_fold_deformation_recovery
tags: []
---

Candidate exact value identity and later transport calculus; not yet proved/approved. Condition on residual Gaussian background x in an approved common-loading parameter population, obtaining a probability law mu_x of residual score A=theta+tau X(v) and a submeasure nu_x of its true-tagged scores. Write H_x(s)=mu_x([s,infinity)), Q_x(r)=sup{s:H_x(s)>=r}, 0<r<=1. Use the upper tail quantile and NONSTRICT conventions; Q(1) may be -infinity. Define v_x(r) as true mass in the top r score mass, splitting an atom proportionally to its true-tag fraction. Explicitly at t=Q(r), v(r)=nu((t,infinity))+(r-mu((t,infinity)))*nu({t})/mu({t}) when mu({t})>0; when no atom the correction is zero, and v(1)=nu(R). Check measurable versions. This should yield 0<=v(r')-v(r)<=r'-r and thus f(r)=v(r)/r absolutely continuous on [a,1] with |f'(r)|<=1/r.

Let B_x(r)=[S^{-1}(qr)-Q_x(r)]/sigma (possibly +infinity at r1), and M_x(r)=min_{s in [r,1]} B_x(s). Upper semicontinuity of Q should give lower semicontinuity of B and actual attainment of this suffix minimum for r<1. The largest actual crossing R_x(z) satisfies R_x(z)>=r iff z>=M_x(r), with no unique root assumption. Positive largest-rank self-consistency gives actual FDP=f_x(R_x(z)); artificial fractional labels inside ties must not be used at a non-self-consistent rank. Consequently the exact macroscopic signed FDR is
E[D 1{R>=a}]=E_x[f_x(a) S(M_x(a))+integral_a^1 f_x'(r)S(M_x(r))dr].
Endpoints, competing roots, flat portions, atoms and higher wells are included by the suffix min, rather than a free optimized rank. Full FDR is the a->0 limit, with error bounded by the APPROVED common-loading micro-FDP modulus A(a). Calibrations: a single score atom has constant M and f, giving exact all-or-none BH. A two-atom mixed-label model recovers both its high-rank dilution and its lower-rank true/false-only branch, with signed f' retained.

For later bounded deterministic mean transport with fixed labels/directions, scores change by <=epsilon K for EVERY background; therefore quantiles and suffix barriers should have uniform displacement bounds epsilon K and epsilon K/sigma even though the empirical CDF under moving atoms need not converge uniformly. At multiple active minima a smooth directional derivative of M is a minimum of barrier velocities; do not assume opposite transport signs give opposite fold shifts. Moreover v_epsilon need not converge uniformly when a mixed-tag score atom splits, so differentiating f alone can introduce spurious terms: retain the COMPLETE Stieltjes expression and cancellations across each tie interval. Generic differentiability, moving-minimum terms, derivative micro-tail control and q-scaled stationarity remain unproved. The identity could be established first for the approved population model, and only extended to a marked-array completion after a valid conditional-score representation is supplied; never choose the parameter perturbation after seeing x.
