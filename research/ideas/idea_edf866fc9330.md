---
type: idea
title: >-
  Original correlated alternatives can force full null revelation and
  logarithmic loss in every final-conditioning envelope
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_conditional_subpoisson_calibration
tags:
  - gaussian-bh
  - one-sided
  - conditional-calibration
  - actual-rank
  - envelope-obstruction
  - correlated-alternatives
---

## Scope and exact finite Gaussian family

This draft observation develops a distinct obstruction to the free-envelope use of [the approved actual-rank count calibration](../assets/gaussian_bh_conditional_subpoisson_calibration.md). In [the earlier spectral-envelope diagnostic](idea_e79c0b2007fd.md), complete-factor conditioning can expose too much. Here the ORIGINAL complete alternative p-value vector itself necessarily exposes every original null. The observation does not refute the helper, the unrestricted main target, or every possible actual-rank allocation.

Fix any mu>0, any positive integer m, and N=2m. Let X_1,...,X_m be independent standard normals and set
$$
T_i=X_i,\qquad T_{m+i}=X_i+\mu\quad(1\le i\le m).
$$
The original mean vector is (0_m,mu 1_m), its original true-null set is exactly I_0={1,...,m}, and its unit-diagonal PSD covariance is
$$
\Sigma=\begin{pmatrix}I_m&I_m\\I_m&I_m\end{pmatrix}.
$$
It is singular of rank m, which the main target expressly allows. The original nulls are independent, with zero off-diagonal null covariance. Keep all 2m original coordinates, their original means and labels, every alternative gate, multiplicities, non-strict inequalities, and the original largest qualifying BH rank R.

Write S=barPhi, U_i=S(X_i), and
$$
P_i=U_i,\qquad P_{m+i}=f_\mu(U_i),
\qquad f_\mu(u)=S(S^{-1}(u)+\mu),\quad0<u<1.
$$
The U_i are independent Uniform(0,1), and f_mu is strictly increasing. A fixed finite mu is sufficient for the entire diagnostic; no infinite means or deterministic zero alternatives are used.

## Every allowed final conditioning reveals all nulls

Let H be ANY sigma-field containing the complete original alternative p-value vector. Gaussian survival is invertible, and
$$
X_i=S^{-1}(P_{m+i})-\mu.
$$
Therefore every X_i, every U_i, the full original p-vector, R and V are H-measurable. Under H, the null score law is deterministic Gaussian with covariance Q=0. In particular, the helper's Gaussian nonpositive-residual sufficient condition is satisfied.

For 0<s<=q put
$$
C(s)=\sum_{i=1}^m\mathbf1_{\{U_i\le s\}},\qquad
K_0=\max\left\{1,\sup_{0<s\le q}\frac{C(s)}{2ms}\right\}.
$$
It is finite almost surely because the finite positive p-vector has a strictly positive minimum. It is exactly the prescribed conditional marginal envelope of the helper under every such H.

More strongly, it is the smallest possible H-measurable K>=1 satisfying the helper's conditional count-mgf hypothesis. Indeed the count is already H-measurable, so that hypothesis at a fixed s is equivalent to
$$
\lambda C(s)\le 2mKs(e^\lambda-1)\qquad(\lambda\ge0).
$$
Dividing by lambda and taking lambda down to zero gives C(s)<=2mKs. Conversely this last inequality implies the displayed inequality because lambda<=e^lambda-1. Rational s and lambda suffice to make these statements simultaneous on one full-measure set, and right continuity recovers every s, including empirical jumps. Thus EVERY admissible K is at least K_0 almost surely. Adding extra conditioning cannot reduce this obstruction.

## Exact logarithmic lower bound for the capped certificate

Assume 0<q<1/(2e) and m>=ceil(1/q). Put
$$
W=m\min_{1\le i\le m}U_i.
$$
Its density on [0,m] is
$$
g_m(w)=(1-w/m)^{m-1}.
$$
For 0<=w<=1 and m>=2 this is at least e^{-1}. To check this elementary bound, use log(1-x)>=-x/(1-x) at x=1/m, giving (m-1)log(1-1/m)>=-1.

On W<=1, the threshold s=min_i U_i=W/m is at most q, since mq>=1. Its non-strict comparison counts at least one null, hence
$$
K_0\ge\frac1{2W}.
$$
Consequently, on 2eq<=W<=1, every admissible calibration K gives
$$
\min\{1,4eqK\}\ge\frac{2eq}{W}.
$$
Integrating only this interval proves the exact finite-model lower bound
$$
\mathbb E\min\{1,4eqK\}
\ge\frac{2eq}{e}\int_{2eq}^1\frac{dw}{w}
=2q\log\frac1{2eq}.\tag{FC-envelope}
$$
In particular, taking m(q)=ceil(1/q) and any fixed mu>0, this free capped envelope budget cannot have a uniform O(q sqrt(log(1/q))) upper bound. This lower bound applies even though Q=0 and the count-mgf hypothesis holds exactly. Unlike the sign-flip diagnostic [idea_1256293060f9](idea_1256293060f9.md), the problem here is not a failed residual-sign or mgf hypothesis.

## Actual original BH FDR is at most q/2

The logarithmic cost is not an actual FDR lower bound. The following direct argument controls the original full BH procedure in this same family.

Fix a null label i, condition on all U_j for j!=i, and let u=U_i vary in (0,1). Only its original pair (u,f_mu(u)) changes, and both p-values increase with u. Therefore the actual largest BH rank R(u) is nonincreasing in u: each qualifying rank at a larger u also qualifies at any smaller u.

The original null i is rejected exactly on
$$
A_i=\{u\in(0,1):R(u)>0,\ u\le qR(u)/(2m)\}.
$$
Since R(u) is nonincreasing, A_i is an initial interval, with its possible endpoint included or excluded. If it is empty, the conditional null contribution is zero. Otherwise write a=sup A_i>0.

For fixed other blocks, the finitely many tests P_j<=qk/(2m), k=1,...,2m, show that R(u) is a finite step function: possible changing thresholds are u=qk/(2m) and f_mu(u)=qk/(2m). Thus there is a left neighborhood of a on which R(u) has a constant value r_*>=1. Taking u up to a within A_i gives a<=q r_* /(2m). Monotonicity also gives R(u)>=r_* for all 0<u<a. Endpoint conventions do not affect integration against the continuous uniform u. Hence the original conditional contribution satisfies
$$
\int_{A_i}\frac{du}{R(u)}
\le\frac{a}{r_*}\le\frac q{2m}.
$$
This uses the actual full rank at every u, not an auxiliary BH procedure or a falsely independent conditional residual law. Summing over the m original null labels and averaging over the other independent blocks proves
$$
\operatorname{FDR}_{\rm BH}(q;2m,\theta,\Sigma)
=\sum_{i=1}^m\mathbb E\frac{\mathbf1_{\{i\in\mathcal R_q\}}}{R\vee1}
\le\frac q2.\tag{FC-actual}
$$
The argument includes all original alternative gates, non-strict threshold comparisons, and the largest qualifying rank. All parameters are finite at each q.

## Precise implication for the main planning gate

The approved helper resolves calibration once a final count-mgf budget is available. It cannot by itself prove the main order bound by choosing H containing all alternatives and then trying to show E min(1,4eqK)=O(q sqrt(log(1/q))) uniformly: (FC-envelope) disproves that proposed universal certificate even when original nulls are independent and final residual covariance vanishes.

For this exact diagnostic, conditioning reveals the entire original rank too, so a rank-sensitive conditional expression can retain the cancellation that the free envelope discards. A future arbitrary-model route must keep such actual-rank/alternative-gate information, or use a different unconditional or partial-conditioning allocation that does not require this false uniform free-envelope estimate. Merely replacing conditional independence by the approved sub-Poisson hypothesis does not supply that missing allocation. No new main proof plan or completion root follows from this observation.

This is a draft mathematical diagnostic requiring independent checking before use as a verified supporting result. The unrestricted main target remains neither proved nor refuted.
