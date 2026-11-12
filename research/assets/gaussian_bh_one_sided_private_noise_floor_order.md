---
title: One-sided Gaussian BH order bound with a fixed private-noise floor
type: theorem
status: draft
source:
  kind: original
  note: Researcher-authorized intermediate target of 10 November 2026; exact structured-class S with constants permitted to depend on the fixed floor.
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_multifactor_representation
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - cross-discipline-brainstorm-20261110
  - one-sided
  - private-noise-floor
  - structured-class-s
---

# One-sided Gaussian BH order bound with a fixed private-noise floor

## Statement

For each fixed real $s_0\in(0,1]$, there exist constants $0<C(s_0)<\infty$ and $q_0(s_0)\in(0,1)$ with the following property. Let $N,d$ be arbitrary positive integers, let $\theta\in\mathbb R^N$, let $A\in\mathbb R^{N\times d}$ have rows $a_i^{\mathsf T}$, and let $D=\operatorname{diag}(s_1,\ldots,s_N)$ have nonnegative diagonal entries. Suppose
$$
\|a_i\|^2+s_i^2=1\quad(1\leq i\leq N),\qquad
s_i\geq s_0\quad\text{for every }i\in I_0^{(1)}(\theta),
$$
where $\|\cdot\|$ is the Euclidean norm and $I_0^{(1)}(\theta)=\{i\in\{1,\ldots,N\}:\theta_i\leq0\}$. Let $G\sim\mathcal N_d(0,I_d)$ and $\varepsilon\sim\mathcal N_N(0,I_N)$ be independent, where $I_d,I_N$ are identity matrices, and set
$$
T=\theta+AG+D\varepsilon,\qquad \Sigma=AA^{\mathsf T}+D^2.
$$
This is the [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) of an admissible finite unit-variance [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md). The class consists of all models admitting at least one such representation. Apart from unit marginal variance and nonnegative $s_i$, no noise-floor restriction is imposed on alternative coordinates $i\notin I_0^{(1)}(\theta)$.

Use the [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), $p_i^{(1)}=\overline\Phi(T_i)$, with the standard normal survival function
$$
\overline\Phi(t)=(2\pi)^{-1/2}\int_t^\infty e^{-u^2/2}\,du.
$$
For any $0<q\leq q_0(s_0)$, apply the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md): include multiplicities in $p_{(1)}^{(1)}\leq\cdots\leq p_{(N)}^{(1)}$ and put
$$
\widehat k_q=\max\bigl(\{0\}\cup\{k\in\{1,\ldots,N\}:p_{(k)}^{(1)}\leq qk/N\}\bigr),
$$
$$
\mathcal R_q=\begin{cases}
\{i:p_i^{(1)}\leq q\widehat k_q/N\},&\widehat k_q>0,\\
\varnothing,&\widehat k_q=0.
\end{cases}
$$
Set $R_q=|\mathcal R_q|$ and $V_q=|\mathcal R_q\cap I_0^{(1)}(\theta)|$. Then the [false discovery rate](../definitions/false_discovery_rate.md) satisfies
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)
=\mathbb E_{N,\theta,\Sigma}\!\left[\frac{V_q}{R_q\vee1}\right]
\leq C(s_0)\,q\sqrt{\log(1/q)},
$$
where $R_q\vee1=\max\{R_q,1\}$ and logarithms are natural.

The constants may depend on the fixed $s_0$ only. They are uniform in $N,d,\theta,A,D$, covariance rank, number and geometry of loading directions, null proportion, and every other model parameter. All these parameters may vary arbitrarily with $q$ within the class. Negative null means, arbitrary positive alternative means, arbitrary loading orientations, ties, and any singular covariance allowed by the displayed conditions are included. The largest qualifying rank and non-strict BH inequalities are essential parts of the procedure. The target asserts neither a bound on $C(s_0)$ as $s_0\downarrow0$ nor a common positive lower bound for $q_0(s_0)$ in that limit.

## Motivation

This is exactly the fixed-floor structured target (S) in the [structured-class program](../ideas/idea_7727ae2d6679.md). Its proposed Mehler-kernel and finite-array aggregation steps remain unproved. The [frozen-ray conjecture](../ideas/idea_9f8ffb204424.md), [planted-SNR program](../ideas/idea_dc6cf14ab94d.md), [Gibbs variational form](../ideas/idea_c36aadbe5f06.md), [tail calibration](../ideas/idea_76d8bdfb8584.md), and [stress tests](../ideas/idea_57338934f2f7.md) are linked as research context, not proof dependencies.

Removing possible dependence on $s_0$ remains a further open problem in the [shell and leader-tracking program](../ideas/idea_9e08f52bc7c4.md). This asset contains no proof, no general BH reduction, and no two-sided assertion. It does not replace either unrestricted main target.
