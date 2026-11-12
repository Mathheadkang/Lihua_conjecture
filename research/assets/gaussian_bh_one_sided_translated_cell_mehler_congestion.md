---
type: lemma
title: Mehler congestion of translated one-sided Gaussian BH rejection cells
status: deprecated
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_ornstein_uhlenbeck_semigroup
tags: []
---

## Statement

Let S be the standard normal survival function. For every finite positive N,d, take arbitrary theta in R^N and deterministic unit vectors a_1,...,a_N in R^d. With Z~N_d(0,I_d), put T_i(z)=theta_i+<a_i,z>, p_i(z)=S(T_i(z)), and I_0={i:theta_i<=0}. This includes every finite PSD unit-diagonal Gaussian covariance and all its singular cases via a Gram representation. Alternative means and directions are unrestricted.

For q in (0,S(1)] use ordinary BH on all N PHYSICAL p-values: its rank is the largest r with p_(r)<=qr/N, or zero if none, and rejection thresholds are non-strict. For each i let R_i(z) be the rank of the SAME BH procedure after replacing ONLY its i-th p-value by zero; every other original p-value and every original null label is retained. Thus R_i(z) lies in {1,...,N}. Write
$$
u_r=S^{-1}(qr/N),\qquad c_{ir}=u_r-\theta_i\quad(i\in I_0),
$$
and define the nonnegative translated density, relative to standard Gaussian measure gamma_d,
$$
H_q(y)=\sum_{i\in I_0}\sum_{r=1}^{N}
\frac1r\,\mathbf1\!\left\{
R_i(y+c_{ir}a_i)=r,\ \langle a_i,y\rangle\ge0
\right\}
\exp\!\left\{-c_{ir}\langle a_i,y\rangle-\frac{c_{ir}^2}{2}\right\}.
$$
The empty sum is zero. There is no removal or renormalization of physical multiplicities. Let V_q and R_q be the actual original true-rejection and total-rejection counts.

(a) The exact mass identity holds:
$$
\int H_q\,d\gamma_d=\mathbb E[V_q/(R_q\vee1)].
$$
In particular the formula must use the full forced-rank mask displayed above, not independently selected or optimized rank cells.

(b) There exist UNIVERSAL constants C<infinity and 0<q_0<=min{S(1),e^{-1}} such that for EVERY such finite model and EVERY 0<q<=q_0, with L_q=log(1/q), tau_q=1/L_q and an independent G~N_d(0,I_d),
$$
\sup_{x\in\mathbb R^d}
\mathbb E\left[
H_q\!\left(e^{-\tau_q}x+\sqrt{1-e^{-2\tau_q}}G\right)
\right]
\le C q\sqrt{L_q}.
$$
The same C and q_0 work for all N,d,theta,Gram matrices,null proportions and direction counts; these model parameters may vary arbitrarily with q. No covariance regularization, lower residual-variance assumption, or bound on correlation rank is imposed. The Mehler smoothing parameter is the explicit function tau_q above and its cost cannot be left uncontrolled.

Part (b) is a new, stronger and potentially false quantitative gate, not an approved consequence of standard OU bounds. Its motivation is the integrable exponential half-line kernel and the reciprocal-threshold factor gained at smoothing width of order 1/sqrt(log(1/q)); this is different from summing positive boundary fluxes. The first falsification checkpoints are arbitrary rank-one mixed-label arrays and small rank-two correlated arrays. Independent-score and scalar diagnostic checks are evidence only, not a proof of the full statement. Together (a), (b), and Gaussian invariance of the Mehler operator would imply the ORIGINAL one-sided universal-order BH bound without changing its quantifiers. This promoted node remains draft.
