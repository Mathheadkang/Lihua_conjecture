---
type: lemma
title: Mixed square-root and entropy-linear coherence budget for the Gaussian BH Mills trace
status: draft
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_bh_fdp_mills_heat_fields
tags:
  - gaussian-bh
  - one-sided
  - mixed-coherence-budget
  - dimension-uniform
---

## Statement

There exist universal constants $0<C<\infty$ and $0<q_0\le\overline\Phi(3)$ such that the assertions below hold for every $0<q\le q_0$ and every finite one-sided [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), with no restriction on its dimension, mean vector, covariance rank or null proportion.

Precisely, let $N,d$ be positive integers, let $\theta\in\mathbb R^N$, and let $v_1,\ldots,v_N\in\mathbb R^d$ satisfy $\|v_i\|=1$. Set $\Sigma_{ij}=v_i\cdot v_j$ and $T_i=\theta_i+v_i\cdot G$ for $G\sim\gamma_d$, where $\gamma_d$ is standard Gaussian probability measure on $\mathbb R^d$. This includes every unit-diagonal positive-semidefinite covariance matrix, including singular matrices. Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md)
$$
p_i(z)=\overline\Phi(\theta_i+v_i\cdot z),\qquad
I_0=\{i\in\{1,\ldots,N\}:\theta_i\le0\}.
$$
Apply the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $q$, with its largest qualifying rank, non-strict inequalities and all multiplicities. Write $\mathcal R(z)$ for its rejection set, $R(z)=|\mathcal R(z)|$, $V(z)=|\mathcal R(z)\cap I_0|$, and use the [false discovery proportion and false discovery rate](../definitions/false_discovery_rate.md)
$$
f(z)=\frac{V(z)}{R(z)\vee1},\qquad
F=\int f\,d\gamma_d.
$$
Only models with $F>0$ require the following tilt; models with $F=0$ have no assertion involving a tilted measure.

Use the [FDP-tilted Gaussian Mills heat fields](../definitions/gaussian_bh_fdp_mills_heat_fields.md), with all conventions unchanged. In particular, writing $\phi(u)=(2\pi)^{-1/2}e^{-u^2/2}$,
$$
h(u)=\frac{\phi(u)}{\overline\Phi(u)},\qquad
u_r=\overline\Phi^{-1}(qr/N),\qquad
U=u_N=\overline\Phi^{-1}(q)\ge3,\qquad H=h(U),
$$
$$
B(z)=\begin{cases}
\displaystyle\frac{1}{R(z)h(u_{R(z)})}
\sum_{i\in\mathcal R(z)\cap I_0}v_i,&R(z)>0,\\
0,&R(z)=0,
\end{cases}
\qquad
\frac{dQ}{d\gamma_d}=\frac fF,\qquad
D=\int\frac fF\log\!\left(\frac fF\right)d\gamma_d,
$$
where $0\log0=0$ and logarithms are natural. Let $\mathbb P$ be standard Wiener measure for the canonical process $W$ on $[0,1]$ starting at zero, and let
$$
\frac{d\mathbb Q}{d\mathbb P}=\frac{f(W_1)}F.
$$
The law of $W_1$ under $\mathbb Q$ is $Q$; $W$ is not asserted to be Brownian motion under $\mathbb Q$. For the Gaussian heat semigroup
$$
(P_s\eta)(z)=\int\eta(z+\sqrt{s}\,y)\gamma_d(dy),
$$
define, for $0\le t<1$,
$$
\mathcal H(t,z)=P_{1-t}f(z),\qquad
a(t,z)=\frac{P_{1-t}B(z)}{\mathcal H(t,z)},\qquad
a_t=a(t,W_t),\qquad
K_t=\nabla_z a(t,W_t).
$$
Here $(K_t)_{jk}=\partial a_j/\partial z_k$ and $\operatorname{tr}K_t=\sum_j(K_t)_{jj}$; no symmetry or sign is imposed on $K_t$. Also set
$$
\beta_t=\nabla_z\log\mathcal H(t,W_t),\qquad
x=H^2\mathbb E_{\mathbb Q}\int_0^1\|a_t\|^2dt,\qquad
M_\tau=F\mathbb E_{\mathbb Q}\int_0^\tau\operatorname{tr}K_tdt
\quad(0\le\tau<1).
$$
The following well-posedness assertions are part of the lemma, not additional hypotheses on the model:
$$
0\le D\le\log(1/F)<\infty,\qquad 0\le x\le1,
$$
$$
\mathbb E_{\mathbb Q}\int_0^1\|\beta_t\|^2dt<\infty,\qquad
\mathbb E_{\mathbb Q}\int_0^1|a_t\cdot\beta_t|dt<\infty,\qquad
\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|dt<\infty.
$$
The endpoint integral and the drift integral in
$$
M_*:=\int_{\mathbb R^d}z\cdot B(z)\gamma_d(dz)
-F\mathbb E_{\mathbb Q}\int_0^1a_t\cdot\beta_tdt
$$
are finite, and this expression agrees with the signed heat trace:
$$
M_* =\lim_{\tau\uparrow1}M_\tau
=F\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_tdt=:M.
$$
Thus $M$ agrees with the existing heat-field definition, rather than extending that definition by an assumed integral identity. All integrals over $[0,1]$ above are over $[0,1)$; no endpoint value of $K_1$, $a_1$ or $\beta_1$ is required. These identities and integrability claims must be proved before either representation of $M$ is used in the estimate.

With $M_+=\max\{M,0\}$, the proposed mixed budget is
$$
M_+\le Cq\left\{\sqrt{1-x}+\sqrt{1+D}(1-x)\right\}.
$$
The same $C,q_0$ must work for every finite $N,d$, every $\theta$ and every choice of unit vectors above. In particular, negative true-null means and singular covariances are included, and all model parameters may depend arbitrarily on $q$. No complexity-dependent constant, fixed-factor assumption or order of limits is permitted.

## Provenance and scope

This new missing-step target is the two-scale repair proposed in [the mixed-budget idea](../ideas/idea_7b7e6c517ab6.md) and specified in the second autonomous reassessment of the project. It is distinct from the earlier pure entropy-linear budget. The square-root term and the entropy-linear term are both retained; neither is asserted to suffice alone. This draft supplies no proof of the budget, the well-posedness assertions or a main FDR upper bound. Prior failed plans and auxiliary counterexamples remain unchanged.
