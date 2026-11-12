---
type: idea
title: >-
  Joint BH rank masks and Hermite tensors: an actual-selector first-chaos bound
  and higher-chaos gate
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - one-sided
  - native-plan-first-tests
  - joint-counts
  - hermite-tensors
---

## Mechanism and provenance

This calculation develops a joint null-count/actual-rank-mask chaos architecture, not a null-count supremum or an arbitrary-alternative replacement. It was developed in the same native delegation as the other first tests, with the root agent supplying the first-chaos rank-mask Cauchy-Schwarz observation. It is not independent verification. Native library searches for Hermite, Mehler, Gaussian covariance and rank discrete differences returned no directly applicable proof.

Let T_i=theta_i+v_i dot G with ||v_i||=1. Set t_k=qk/N, u_k=barPhi^{-1}(t_k), and retain the full-model event Q_k=1{R_q=k}, including all alternatives and the actual largest nonstrict BH rank. Let V_k=sum_{i in I0}1{T_i>=u_k}. Exactly,
$$
FDR=sum_{k=1}^N k^{-1} E[V_k Q_k].
$$
The baseline from replacing V_k by E V_k is at most q |I0|/N, since theta_i<=0 gives E V_k<=|I0|t_k. All remaining terms are signed cross-chaos pairings with the actual Q_k.

## Exact tensor first step

Let H_l be the probabilists' Hermite polynomial. Repeated differentiation of phi gives, for l>=1,
$$
\int_a^\infty H_l(x)phi(x)dx=phi(a)H_{l-1}(a).
$$
Thus the lth homogeneous Gaussian chaos of V_k has symmetric tensor
$$
A_{k,l}=\frac1{l!}\sum_{i in I0}
phi(u_k-theta_i)H_{l-1}(u_k-theta_i)v_i^{\otimes l}.
$$
Its squared L2 norm is
$$
\frac1{l!}\sum_{i,j in I0}
phi(u_k-theta_i)phi(u_k-theta_j)
H_{l-1}(u_k-theta_i)H_{l-1}(u_k-theta_j)Sigma_{ij}^{\,l}.
$$
This is a nonnegative tensor Gram quadratic form, despite signed individual summands. It is valid for singular covariance. The lth FDR correction pairs this tensor, divided by k, with the lth chaos of Q_k. No null-only envelope has been substituted.

## A genuinely paid first intermediate assertion

In the centered independent-null submodel, the null vectors are orthonormal even when alternatives are arbitrarily correlated with them and with one another. Write m=|I0|. The first-chaos V_k tensor is phi(u_k) S, S=sum_{i in I0}v_i, with ||S||^2=m. Consequently
$$
sum_k ||P_1(V_k/k)||_2^2
=m\sum_k \frac{phi(u_k)^2}{k^2}
\le q^2\frac mN\{4log(1/q)+6\}
$$
for q<=barPhi(1). To check the bound, use phi(u)/barPhi(u)<=u+1 for u>=1, u(t)^2<=2log(1/t), and N^{-1}sum_k log(N/k)<=1. On the actual masks, orthogonal projection and their disjointness give
$$
sum_k||P_1Q_k||_2^2<=sum_k Var(Q_k)<=1.
$$
Therefore their entire signed first-chaos contribution is bounded in absolute value by
$$
q\sqrt{(m/N)\{4log(1/q)+6\}}.
$$
This is an O(q sqrt(log(1/q))) estimate for the actual selector, uniform in the alternative count process, in this restricted null-covariance submodel. It is not the full FDR estimate or a reduction of the unrestricted target to that submodel.

The same estimate allows all negative true-null means: the first-chaos vector is now sum_i phi(u_k-theta_i)v_i, and orthogonality gives its squared norm as sum_i phi(u_k-theta_i)^2<=m phi(u_k)^2 because u_k>=1 and theta_i<=0. More generally, if the true-null correlation matrix Gamma_00 has operator norm at most L, its Gram quadratic form gives squared norm at most L m phi(u_k)^2. The resulting first-chaos bound is
$$
q\sqrt{L(m/N)\{4log(1/q)+6\}}.
$$
The negative-mean and operator-norm extensions were suggested by the root agent and checked directly here; no independent audit is claimed. This controls only the first-chaos contribution, and no universal bound on L is imposed in the actual target.

## First higher-order test

For centered independent nulls the lth rank-energy is
$$
E_l=\frac m{l!}\sum_{k=1}^N
\frac{phi(u_k)^2H_{l-1}(u_k)^2}{k^2}.
$$
At m=N, fixed q and fixed l, its N->infinity limit is the Riemann integral
$$
\frac q{l!}\int_{u(q)}^\infty
\left[\frac{phi(x)}{barPhi(x)}\right]^2
H_{l-1}(x)^2phi(x)\,dx.
$$
For q->0 with l fixed this is asymptotic to q^2 u(q)^{2l}/l!. In particular the same unweighted Cauchy-Schwarz allocation at l=2 pays order q u(q)^2, already larger than the desired q u(q) scale. This is a failure of that energy allocation, not a lower bound for the actual second-chaos FDR correction: the actual mask pairing can be much smaller and can cancel across chaos degrees.

For general null covariance the first-chaos vector S can have norm m rather than sqrt(m), so the independent-null estimate itself loses a dimension factor if extended by that same Cauchy-Schwarz step. A valid continuation needs both a correlation-sensitive treatment of low chaos and a joint-mask control of higher chaos; neither follows from a trace-one covariance condition or from orthogonality alone.

## Exact two-test joint check and discrete cancellation

Take one centered null and one alternative of mean mu, N=2, correlation rho. Let a=q/2, b=q, c=u_b-mu. Forcing the null p-value to zero gives R_1=2 exactly when Z_2>=c, otherwise R_1=1. Directly,
$$
FDR_\rho=a-P_\rho(Z_1>=u_a,Z_2>=c)
+\tfrac12P_\rho(Z_1>=u_b,Z_2>=c).
$$
For |rho|<1, the bivariate Mehler expansion yields
$$
FDR_\rho=a+\sum_{l>=1}\frac{rho^l}{l!}
\{\tfrac12phi(u_b)H_{l-1}(u_b)
-phi(u_a)H_{l-1}(u_a)\}
phi(c)H_{l-1}(c).
$$
This converges as an L2 Hermite inner product. The first coefficient is negative:
$$
\tfrac12phi(u_b)-phi(u_a)
=\tfrac q2\{h(u_b)-h(u_a)\}<0,
\qquad h=phi/barPhi.
$$
For q->0 it is asymptotic to -q log(2)/(2u_b). Thus the actual adjacent-rank cancellation is visible before summing covariance effects; bounding the two terms separately loses a factor of order u_b^2. Alternative-only terms cancel in the independent-endpoint covariance derivative when all nulls are centered: integrating any other null contribution first gives the constant q/N.

## Status

The tensor identity, actual-mask first-chaos bound in the stated submodel, higher-order energy calibration and two-test cancellation are concrete new first steps. They suggest seeking chaos-weighted rank-difference estimates rather than an absolute face budget. They do not yet provide such an estimate for arbitrary covariance and negative null means. Writing a main-target plan that simply postulates the sum of all these unknown pairings would be a filler budget; no such plan is asserted here. The unrestricted target remains unchanged and unproved.

## Correlated-null caution after the first tests

The [exact cross-chaos cancellation test](idea_b5466535b0cc.md) gives a legal rank-one Gaussian model whose actual FDR tends to q/2, whereas its complete first-chaos contribution grows like a positive fixed-q constant times q sqrt(log N). I rechecked its rank partition and displayed first-chaos formula in the same delegation; this is a scoped agent check, not native independent verification. Thus the independent-null assertion above cannot be extended to all covariance matrices by paying the first chaos separately: cross-degree cancellation is essential in the full model. The proposed continuation must retain the whole signed generating function or another exact resummation. This caution does not refute the independent-null bound, the main target, or every resummation approach.
