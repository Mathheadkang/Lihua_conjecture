---
type: idea
title: Gaussian tail payment confines supernominal FDR to a shrinking null-mean strip
status: resolved
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - negative-null-means
  - expected-fdr
resolved_by: gaussian_bh_negative_null_boundary_strip
---

Agent-derived expected-FDR diagnostic for the unchanged one-sided universal-order target; this is not a centering comparison, not an assumed lemma, and not a new required root.

## Exact actual-rank tail payment
Let Q be the standard normal survival function, h=phi/Q, U=Q^{-1}(q)>=1, and let R be the actual largest-qualifying-rank BH rejection count in any finite admissible Gaussian model, with original labels I_0={i:theta_i<=0}. For any null with theta_i=-a_i<0, the non-strict rejection threshold gives, samplewise,
$$
\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}
\le \frac{q}{Np_i}\mathbf1\{p_i\le q\}.
$$
Indeed a rejection has p_i<=qR/N and hence 1/R<=q/(Np_i). Since T_i=Z-a_i marginally with Z standard normal, exact change of variable t=Q(u) gives
$$
\mathbb E\!\left[\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}\right]
\le\frac qN e^{-a_i^2/2}\int_U^\infty h(u)e^{-a_i u}\,du
\le\frac qN e^{-a_i^2/2-a_iU}
\left[\frac{U+1}{a_i}+\frac1{a_i^2}\right].
$$
The last bound uses h(u)<=u+1 for u>=1. For completeness, integration by parts yields Q(u)=phi(u)/u-int_u^infty phi(t)/t^2 dt>=phi(u)/u-Q(u)/u^2, so h(u)<=u+1/u<=u+1. No joint density, independence, covariance inverse, count concentration, face charging, or limiting model is used; singular covariance is included.

## Shrinking near-boundary window
For every q<=Q(e), put U=Q^{-1}(q)>=e and a_q=2 log(U)/U. Define D_q={i in I_0:theta_i<=-a_q} and let V_D be the number of rejected original labels in D_q, in the original unmodified procedure. The integral bound is decreasing in a_i>0, so
$$
\mathbb E[V_D/(R\vee1)]
\le \frac{q|D_q|}{N}
\left[\frac{1+1/U}{2\log U}+\frac1{4(\log U)^2}\right]
\le \left(\frac34+\frac1{2e}\right)\frac{q|D_q|}{N}
\le\frac{q|D_q|}{N}\le q.
$$
Here e^{-a_q U}=U^{-2}, and e^{-a_q^2/2}<=1 was discarded. Thus the original total FDR is at most q plus the expected contribution of original labels with -2 log(U)/U<theta_i<=0. Every model coordinate and the actual BH rank remain present.

## Unpaid centering gate
This contribution split does not justify deleting D_q, removing them from the BH denominator, relabeling them as alternatives, or replacing any null mean by zero. Such changes can alter recruitment of alternatives and the full rejection rank. The proposed comparison FDR(q;theta,Sigma)<=C_0 FDR(cq;theta^0,Sigma)+C_1 q for fixed c>=1 is neither proved nor refuted here. The approved three-test negative-null-mean nonmonotonicity has only O(q) FDR and does not refute that coarse comparison. A useful next proof obligation would have to control the shallow strip while retaining arbitrary deeply negative coordinates as rank-affecting background; that obligation is recorded as unpaid, not assumed.

## Resolution

Promoted to the lemma gaussian_bh_negative_null_boundary_strip, a dependency of gaussian_bh_one_sided_universal_order_upper.
