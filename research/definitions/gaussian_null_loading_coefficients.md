---
type: definition
title: Definition (Gaussian null loading coefficients)
status: approved
source:
  kind: original
depends_on:
  - gaussian_multifactor_representation
  - gaussian_test_pvalues
tags:
  - gaussian
  - multifactor
  - null_loadings
---

## Definition

In a [Gaussian multifactor representation](./gaussian_multifactor_representation.md), select one of the [Gaussian test p-values and true nulls](./gaussian_test_pvalues.md) tracks $s\in\{1,2\}$. Write $I_0=I_0^{(s)}(\theta)$, $m_0=|I_0|$, and $\pi_0=m_0/m$. For every coordinate define
$$
r_i=\|a_i\|\in[0,1],\qquad \gamma_i=\sqrt{\frac{1-r_i}{1+r_i}}\in[0,1].
$$
Thus $\gamma_i=1$ at $r_i=0$ and $\gamma_i=0$ at $r_i=1$. The average null loading coefficient, normalized by the total number of tests, is
$$
\overline\gamma_0=\frac1m\sum_{i\in I_0}\gamma_i.
$$
An empty sum is zero, so $\pi_0=\overline\gamma_0=0$ when $m_0=0$. In particular $0\leq\overline\gamma_0\leq\pi_0\leq1$. The null set and these quantities depend on the testing track.
