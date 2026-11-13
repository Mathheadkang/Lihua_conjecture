---
type: lemma
title: Rare-direction cap for one-sided Gaussian BH
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

There exist universal constants $\kappa_2>0$, $C_2\ge1$, $A_2<\infty$ and $q_2\in(0,1/2)$ with the following property.

Take any [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md)
$T_i=\theta_i+a_i^{\mathsf T}Z+\sqrt{1-\|a_i\|^2}\,\varepsilon_i$, $1\le i\le m$, with any factor dimension $d$, any means and any loadings. Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$, $I_0=\{i:\theta_i\le0\}$, and the [Gaussian null loading coefficients](../definitions/gaussian_null_loading_coefficients.md) $r_i=\|a_i\|$. Run the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $0<q\le q_2$ with its largest qualifying rank and non-strict comparisons; let $\mathcal R_q$ be its rejection set, $R=|\mathcal R_q|$, and $u=\overline\Phi^{-1}(q)$.

For $i\in I_0$ with $r_i>0$ put $w_i=a_i/r_i$ and define the local null mass at angular scale $\kappa_2/u$,
$$
\mu_i=\frac1m\,\#\bigl\{k\in I_0:\ r_k>0,\ w_k^{\mathsf T}w_i\ge\cos(\kappa_2/u)\bigr\}.
$$
Let the rare set be $I_{\mathrm{rare}}=\{i\in I_0:\ r_i>0,\ \mu_i<q^{C_2}\}$. Then the contribution of the rare nulls to the [false discovery rate](../definitions/false_discovery_rate.md) of the same unmodified procedure satisfies
$$
\mathbb E\!\left[\frac{|\mathcal R_q\cap I_{\mathrm{rare}}|}{R\vee1}\right]\le A_2\,q\,(1+u).
$$
The constants are independent of $m$, $d$, the means, the loadings, the null proportion and the covariance rank; every model parameter may depend on $q$. The denominator is the actual rejection count of the full procedure, with all coordinates and the original labels kept. The sharper form with right side $A_2q$ would also suffice for every use of this lemma.
