---
type: definition
title: Definition (Gaussian test p-values and true nulls)
status: approved
source:
  kind: original
depends_on:
  - gaussian_multiple_testing_model
tags:
  - gaussian
  - p_values
  - null_hypotheses
---

## Definition

In the [Gaussian multiple-testing model](gaussian_multiple_testing_model.md), define the standard normal survival function by
$$
\overline\Phi(t)=\frac{1}{\sqrt{2\pi}}\int_t^\infty e^{-u^2/2}\,du,\qquad t\in\mathbb R.
$$
The track index $s\in\{1,2\}$ specifies the following p-values and true-null index sets:
$$
p_i^{(2)}=2\overline\Phi(|T_i|),\qquad I_0^{(2)}(\theta)=\{i\in[N]:\theta_i=0\},
$$
$$
p_i^{(1)}=\overline\Phi(T_i),\qquad I_0^{(1)}(\theta)=\{i\in[N]:\theta_i\leq0\}.
$$
Thus $s=2$ uses two-sided tests of $\theta_i=0$ against $\theta_i\ne0$, and $s=1$ uses one-sided tests of $\theta_i\leq0$ against $\theta_i>0$. Negative means are included among the one-sided true nulls. Each vector $p^{(s)}=(p_1^{(s)},\ldots,p_N^{(s)})$ is computed from the same exactly jointly Gaussian observation, without an independence assumption.
