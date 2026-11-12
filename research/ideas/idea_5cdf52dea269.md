---
type: idea
title: >-
  Forced-zero Gaussian likelihood identity and finite cost of initial rank
  calibration
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - original-vector
  - forced-zero-rank
  - stopped-calibration
  - rare-alternative
  - filtration-obstruction
---

## Status and provenance

Draft observation from the original-vector direction [Actual-rank stopped Gaussian likelihood mixtures instead of inherited-carrier compression](idea_fb31f384917f.md). This creates no result, proof plan or completion root. The rare-alternative singular family itself is already in [Exact BH peeling filtration and compensated Gaussian history-face kernel](idea_d0a95c94fab5.md) and was executed in plan_one_sided_order_peeling_history_kernel_20261107; it is not claimed as a new construction. The new calculation is its exact selected Gaussian tail-likelihood interpretation and explicit information-enlargement cost. The optional positive-definite bound below makes that cost robust without relying on conditional point masses.

## Exact original-label likelihood identity

Write S=barPhi, t_r=qr/N and u_r=S^{-1}(t_r). For every original null i let R_i be the ordinary largest qualifying BH rank with only its p-value forced to zero; R_i is a measurable function of T_{-i} and R_i>=1. Deterministically,
$$
\frac{\mathbf1_{\{i\in\mathcal R_q\}}}{R\vee1}
=\frac{\mathbf1_{\{T_i\ge u_{R_i}\}}}{R_i}.
$$
Indeed, if i is originally rejected, replacing its p-value by zero changes no count at any larger rank threshold, so no new larger rank qualifies. Conversely, if its original p-value is at most t_{R_i}, rank R_i still qualifies in the original vector, while monotonicity bounds the original rank above by R_i. This proves the identity with ties and non-strict inequalities.

Let C_i=Sigma_{-i,-i}, c_i=Sigma_{-i,i}, and C_i^+ be the Moore-Penrose inverse. Positive semidefiniteness gives c_i in range(C_i) and
$$
m_i=\theta_i+c_i^{\mathsf T}C_i^+(T_{-i}-\theta_{-i}),\qquad
v_i=1-c_i^{\mathsf T}C_i^+c_i\ge0.
$$
The canonical conditional law of T_i is N(m_i,v_i). For N=1 take m_i=theta_i and v_i=1. Define
$$
L_i(t,T_{-i})=
\begin{cases}
S\big((S^{-1}(t)-m_i)/\sqrt{v_i}\big)/t,&v_i>0,\\
\mathbf1_{\{m_i\ge S^{-1}(t)\}}/t,&v_i=0.
\end{cases}
$$
Finite-model conditioning then gives the exact identity
$$
\operatorname{FDR}=\frac qN\sum_{i\in I_0}
\mathbb E\,L_i(t_{R_i},T_{-i}).
$$
It holds directly for singular covariances; no density or limiting argument is needed. For every deterministic t,
$$
\mathbb E L_i(t,T_{-i})=\frac{S(S^{-1}(t)-\theta_i)}t\le1,
$$
with equality for theta_i=0. If all nulls are central and each is independent of all other coordinates, their L_i are identically 1 for every t, so the exact q|I0|/N baseline survives all alternative gates. If each null is independent of all other coordinates, negative null means give L_i<=1 pointwise. Selection of t_{R_i} is the sole additional issue in this identity; fixed-t calibration does not establish selected-t calibration.

## Exact finite rare-alternative calibration

Take N=2, 0<q<1/2, independent standard normals X,Z, u1=S^{-1}(q/2), u2=S^{-1}(q), mu=u1+u2, and
$$
T_1=X,\qquad T_2=\mu-\rho X+\sqrt{1-\rho^2}Z,\qquad I_0=\{1\}.
$$
Every original mean and label is retained. For rho=1 this is a legal singular Gaussian model. Its forced-zero rank is 2 iff X<=u1. Its null contribution is 1/2 on u2<=X<=u1 and 1 on X>u1, hence
$$
\operatorname{FDR}=\frac12(q-q/2)+q/2=3q/4,\qquad
\mathbb E L_1(t_{R_1},T_2)=3/2.
$$
Thus a cost-free mean-one stopped-likelihood claim already fails in a finite admissible model. The allowed target budget is C(1+S^{-1}(q)); a fixed factor 3/2 DOES NOT refute it or the main theorem.

For a fully explicit positive-definite version put rho=1-q^3/2^{16}. Let Y=T2-mu and compare its rank gate {Y>=-u1} with the singular gate {X<=u1}. Since Y+X is centered Gaussian of variance 2(1-rho), for a=q/16 the disagreement probability is at most
$$
\Pr(|X-u1|\le a)+\Pr(|Y+X|\ge a)
\le 2a/\sqrt{2\pi}+2(1-\rho)/a^2
\le q/16+q/128=9q/128.
$$
The null-contribution functions differ by at most one, and only on gate disagreement. Therefore
$$
\operatorname{FDR}\ge3q/4-9q/128=87q/128>5q/8,\qquad
\mathbb E L_1(t_{R_1},T_2)>5/4.
$$
Here the covariance [[1,-rho],[-rho,1]] is positive definite. This strengthening is not essential: singular models already belong to the target. It only rules out attributing the calibration defect to a degenerate conditional law.

## Actual innovation and reverse-information gates

Use an equivalent realization Y=W1 and X=-rho W1+sqrt(1-rho^2)Z, where W is standard Brownian motion and Z independent. Under F_s=sigma(W_t:0<=t<=s), 0<=s<=1,
$$
M_s(a)=\frac{S((a+\rho W_s)/\sqrt{1-\rho^2s})}{S(a)}
=\mathbb E[\mathbf1_{\{X\ge a\}}/S(a)\mid\mathcal F_s]
$$
is a bounded nonnegative mean-one martingale for each fixed deterministic a (use the obvious endpoint convention for rho=1). The rank gate is A={W1>=-u1}. For any s<1 its conditional probability given F_s is strictly between zero and one almost surely, so A is not F_s-measurable. A proposed time tau=s2 on R1=2 and s1 on R1=1, with distinct deterministic times and min(s1,s2)<1, is not a stopping time: its earliest-time event is A or its complement. Equal times make time selection harmless but leave the terminal random threshold a=u_{R1}; its expectation exceeds one as computed above.

Conditioning on the complete alternative observation W1, or initially enlarging by R1, makes the rank measurable, but the enlarged fixed-a martingale must start at
$$
\widetilde M_0(a)=\mathbb E[\mathbf1_{\{X\ge a\}}/S(a)\mid R_1]
$$
(or condition on W1). Its selected initial cost satisfies
$$
\mathbb E\,\widetilde M_0(u_{R_1})
=\mathbb E L_1(t_{R_1},T_2)>1.
$$
The tower property gives this equality because u_{R1} is measurable in the initial enlarged sigma-field. A standard backward Brownian filtration H_s=sigma(W_t:s<=t<=1) retains W1 throughout, so E[1{X>=a}|H_s]=E[1{X>=a}|W1]; it supplies no new mean-one selected calibration. Reverse information that actually discards the endpoint must separately prove rank measurability after discarding it. This addresses these concrete filtrations, not every conceivable stopped coupling.

## Remaining unpaid gate and failed-plan distinction

One needs a new uniform bound on the selected initial-calibration cost
$$
\frac1N\sum_{i\in I_0}\mathbb E L_i(t_{R_i},T_{-i})
\le C(1+S^{-1}(q)).
$$
As written this is exactly the normalized target FDR identity, so declaring it an optional-stopping lemma adds no information. An executable new route must first specify a genuine stopping rule plus an independently bounded enlargement/threshold-selection or frozen-vector-to-path transfer cost. Neither the deterministic-threshold Gaussian likelihood martingales, revealing all alternatives, nor the backward endpoint filtration supplies that cost.

Unlike the failed peeling plan's signed history-face budget, this observation isolates the defect before any boundary integration: original-label forced-zero rank selects the threshold in a family of martingales. No old signed budget, free frozen-ray supremum, conditional-variance envelope or entropy loss is claimed to have been paid. No pending proof plan is warranted by these identities alone.
