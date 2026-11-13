---
type: lemma
title: Gaussian-width bound for few angular null clusters in one-sided Gaussian BH
status: draft
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multifactor_representation
  - gaussian_null_loading_coefficients
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - parallel-round-20261112
  - route-1
---

## Statement

For every $\kappa>0$ and every $C\ge1$ there exist finite $A_3=A_3(\kappa,C)$ and $q_3=q_3(\kappa,C)\in(0,1/2)$ with the following property.

Take any [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md)
$T_i=\theta_i+a_i^{\mathsf T}Z+\sqrt{1-\|a_i\|^2}\,\varepsilon_i$, $1\le i\le m$, with $Z\sim\mathcal N_d(0,I_d)$, any factor dimension $d$, any means and any loadings. Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$, $I_0=\{i:\theta_i\le0\}$, and the [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md) $r_i=\|a_i\|$. Run the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $0<q\le q_3$ with its largest qualifying rank and non-strict comparisons; let $\mathcal R_q$ be its rejection set, $R=|\mathcal R_q|$, and $u=\overline\Phi^{-1}(q)$.

Let $I_*\subseteq I_0$ be partitioned into nonempty sets $C_1,\ldots,C_J$ with
$$
J\le q^{-C},
$$
and let $v_1,\ldots,v_J\in\mathbb R^d$ be unit vectors such that every $i\in C_j$ with $r_i>0$ satisfies
$$
a_i^{\mathsf T}v_j\ge r_i\cos(\kappa/u).
$$
No condition is imposed on members with $r_i=0$. Then the contribution of $I_*$ to the [false discovery rate](../definitions/false_discovery_rate.md) of the same unmodified procedure satisfies
$$
\mathbb E\!\left[\frac{|\mathcal R_q\cap I_*|}{R\vee1}\right]
\le A_3\,q\left(1+u+\mathbb E\max_{1\le j\le J}v_j^{\mathsf T}Z\right).
$$
The constants depend only on $\kappa$ and $C$; they are independent of $m$, $d$, $J$, the cluster masses, the means, the loadings and the vectors. The last term is the Gaussian mean width of the cluster centres, which lies in $[0,\sqrt{2\log J}]$. The lemma replaces the one-scale entropy charge $\sum_j\pi_j\log(1/\pi_j)$, which can be of order $C\log(1/q)$ here, by this width, of order at most $\sqrt{C\log(1/q)}$.
