---
type: lemma
title: OU integrated signed budget bridge for full Gaussian BH FDR
status: draft
source:
  kind: original
depends_on:
  - gaussian_bh_finite_signed_p_path_identity
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_ornstein_uhlenbeck_semigroup
tags: [gaussian_bh, universal_budget, ornstein_uhlenbeck, signed_response, teaching_route]
---

## Statement: analytic prerequisite and distinct BH bridge

Use the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [one-sided Gaussian p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary BH](../definitions/benjamini_hochberg_step_up.md), [FDR](../definitions/false_discovery_rate.md), and the draft [OU semigroup convention](../definitions/gaussian_ornstein_uhlenbeck_semigroup.md). The [exact finite signed conditional p-path identity](gaussian_bh_finite_signed_p_path_identity.md) is a declared project prerequisite before the first search. No analytic library result is presumed approved by a teaching-window discussion.

For every finite $N\geq1$, $\theta\in\mathbb R^N$, positive semidefinite unit-diagonal $\Sigma$, and $0<q\leq S(1)$, where $S=\overline\Phi$, choose any finite representation
$$
G\sim\gamma_d,\qquad T_j(G)=\theta_j+v_j\cdot G,\qquad
\|v_j\|_2=1,\qquad v_j\cdot v_k=\Sigma_{jk}.
$$
Singular Gram matrices are allowed. Put $I_0=\{i:\theta_i\leq0\}$ and $\pi_0=|I_0|/N$. On this latent space let
$$
f(x)=\frac{|\mathcal R_q(T(x))\cap I_0|}{R_q(T(x))\vee1},\qquad
F=\int f\,d\gamma_d.
$$
This is the full original mixed-label actual-BH FDP, with no rank cutoff or smoothing of the testing procedure. The OU operator acts on this fixed function:
$$
T_t f(x)=\mathbb E f(e^{-t}x+\sqrt{1-e^{-2t}}G'),\qquad
J(f)=\int_0^\infty\mathbb E_{\gamma_d}\|\nabla T_t f\|_2\,dt.
$$

### Generic analytic estimate

Independently of BH, for every measurable $h:\mathbb R^d\to[0,1]$, with $m_h=\int h\,d\gamma_d$, establish ordinary spatial gradients for $t>0$ and
$$
J(h)\leq\frac\pi2 I(m_h)
\leq C\,m_h\sqrt{\log(e/m_h)}
$$
for a finite universal $C$. At $m_h=0$, interpret the last expression as zero and assert $J(h)=0$; the endpoints $m_h=1$ and $I(1)=0$ are included. Prove the gradient estimate, time integrability and all expectation interchanges from verified primary-source analytic results or by direct Mehler differentiation and one-dimensional Gaussian rearrangement. Finite latent dimension and singular covariance of the original scores must cause no restriction. This analytic estimate alone does not bound BH FDR by the target order.

### BH-specific quantitative gate

The new assertion to falsify, and prove only if an executable mechanism survives, is the existence of one finite universal $A$ such that every legal finite model above with $F>0$ satisfies
$$
(F-q\pi_0)_+\leq A\,\frac qF\,J(f),\qquad
[a]_+=\max\{a,0\}.
$$
All constants are independent of $N$, means, rank, latent dimension and covariance, and models may vary arbitrarily with $q$. Negative true-null means, singular models, simultaneous ties and $N=1$ remain in scope. No vector-field certificate, entropy argument, posterior-barycenter bound or generic semigroup regularity is an assumption establishing this bridge.

### Required consequence

If both the generic estimate and the BH gate hold, they imply a finite universal $K$ with
$$
F\leq Kq\sqrt{\log(1/q)}\qquad(0<q\leq S(1)).
$$
An eventual proof must explicitly solve the resulting inequality
$$
(F-q\pi_0)_+\leq ACq\sqrt{\log(e/F)},
$$
including $F=0$ and the case $F\leq q$. This conclusion is conditional on proving the BH gate and is not asserted by the generic analytic estimate alone.

## Decisive tests and stop rule

Test the ratio
$$
\frac{F(F-q\pi_0)_+}{qJ(f)}.
$$
For $J(f)=0$, assign value $+\infty$ if the numerator is positive, and zero if the numerator is zero; for $F=0$ assign zero. A legal family with unbounded ratio refutes this stronger bridge while leaving the main targets and finite identity open. A finite grid or unverified numerical truncation is neither proof nor refutation.

For a one-dimensional full actual-BH FDP that is a finite step function, let $b_j\in\mathbb R$ be its distinct jump locations and $\Delta_j=f(b_j^+)-f(b_j^-)$ its net jumps, with simultaneous events merged. Independently verify the proposed exact signed-mixture reduction
$$
J(f)=\int_0^1\left\|\sum_j\Delta_j\phi(b_j)
\varphi_{\sqrt{1-\rho^2}}(\,\cdot-\rho b_j)\right\|_{L^1(\mathbb R)}\,d\rho,
$$
where $\rho$ is the OU correlation parameter, $\phi$ and $\varphi_s$ are as in the OU convention, the norm uses Lebesgue measure, and $\rho=1$ is interpreted by a limit. Form the signed mixture before taking its norm. Track full FDR, exact net conditional-p-path charge, and positive conditional-p-path charge separately; include independent-null dust as a cancellation check. Only independently source-verified analytic library nodes actually used may be added as dependencies. Teaching-origin citations, calibrations and this mixture formula remain proof obligations at this draft stage.
