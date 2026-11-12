---
type: idea
title: >-
  Exact centering rank-expansion reduction and dimension loss after forgetting
  its selected rank
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Couple the original full Gaussian model T_i=theta_i+X_i and the comparison model T_i^0=theta_i^0+X_i using exactly the same centered Gaussian vector X with covariance Sigma. Set theta_i^0=0 for the original true nulls and leave all alternative means unchanged. Keep the original labels, all coordinates, and each full ordinary BH largest crossing. Write their counts as (R,V) and (R_0,V_0). Coordinatewise monotonicity of BH gives R_0>=R and V_0>=V. Therefore for every fixed K>1,
FDR(theta)<=K FDR(theta^0)+E[(V/(R vee 1)) 1{R_0>K R}].
This is an exact rank-stability reduction; a uniform O(q) bound for its displayed remainder would suffice for a coarse expected-FDR centering comparison. No such bound is asserted here.

There is an exact newly-crossed-null certificate at the selected centered rank. On an outcome with R=r>=1 and R_0=s>r, put t_s=qs/N and u_s=barPhi^{-1}(t_s). The centered count at t_s equals s, whereas the original count is at most s-1; otherwise rank s would qualify in the original procedure. Alternatives have unchanged p-values. Thus at least one original null i satisfies u_s<=X_i<u_s-theta_i. More precisely, the number of newly crossed nulls at this same threshold equals s-C_theta(t_s), where C_theta(t)=#{i:p_i(theta)<=t}. There need not be s-r newly crossed nulls: the larger threshold can admit many unchanged alternatives. This distinction prevents replacing the original denominator r by s merely by counting triggering nulls.

The immediate unsigned marginal payment loses dimension. Dropping both the selected-rank condition and the original FDP weight gives the bound sum_{i in I0} P{X_i in union_{s=1}^N [u_s,u_s-theta_i)}<=|I0|q. This can be of order Nq in a shrinking-strip, jointly growing-q,N Gaussian model, even when the actual expected FDP is O(q). It is a proof loss, not an obstruction to the exact remainder or to coarse centering.

Here is an explicit calculation of that loss. Take q_j=barPhi(j), N_j=j^2, Sigma_j=I, and all theta_i=-a_j with a_j=log(2)/j. These null means are in the shallow strip for large j; all models have growing full Gaussian rank. Since the Gaussian hazard h(x)=phi(x)/barPhi(x)>=x>=j for x>=j,
u(q(s-1)/N)-u(qs/N)<=log(s/(s-1))/j<=a_j
for every 2<=s<=N. Therefore the N rank strips overlap and their union is exactly [j,u(q/N)+a_j). Its marginal Gaussian probability p_j equals q_j-barPhi(u(q_j/N_j)+a_j). The Gaussian shift tail bound yields barPhi(u(q/N)+a_j)<=barPhi(u(q/N)) exp(-a_j u(q/N)-a_j^2/2)<=q/(2N), so q(1-1/(2N))<=p_j<=q. Because N_j q_j tends to zero and the centered X_i are independent, the probability that at least one null lies in this rank-forgotten union is 1-(1-p_j)^{N_j}, asymptotic to N_j q_j.

By contrast, both original and centered p-values are independent and individually superuniform, so the approved conditional compound-calibration lemma with a constant conditioning variable has M_q<=1 and bounds each actual full BH FDR, and the displayed weighted expansion remainder, by 2q_j. Thus even replacing a sum by the exact union probability cannot rescue the rank-forgotten boundary-strip payment: its loss here is a factor of order N_j. A useful next proof must keep the selected centered rank and the original FDP weight jointly, or identify a signed cancellation before applying marginal strip bounds. No main-theorem candidate or refutation is obtained.
