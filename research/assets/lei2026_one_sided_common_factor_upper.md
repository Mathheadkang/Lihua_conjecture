---
type: theorem
title: Lei sharp composite-null one-sided BH upper bound with one common factor
status: draft
source:
  kind: paper
  paper_id: lei2026_gaussian_bh
  location: Theorem 4.10, p. 87; Corollary 4.11, p. 88; proofs in Section 4.3, pp. 88-90
depends_on: [lei2026_conditional_fdp_bound, lei2026_one_sided_fdr_lower]
uses_definitions: [gaussian_one_common_factor_model, gaussian_test_pvalues, benjamini_hochberg_step_up, false_discovery_rate, gaussian_worst_case_bh_fdr]
tags: [gaussian, benjamini_hochberg, one_sided, composite_null, upper_bounds, one_common_factor, paper_source]
---

## Statement

In the [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md), test $H_i:\theta_i\leq0$ using $P_i=\overline\Phi(T_i)$ and the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md). Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md); put $m_0=|\{i:\theta_i\leq0\}|$, $\pi_0=m_0/m$ and $u_q^+=\overline\Phi^{-1}(q)>0$ for $0<q<1/2$. If $m_0=0$ the [false discovery rate](../definitions/false_discovery_rate.md) is zero. Otherwise
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;m,\theta,\Sigma(a))\leq q\left\{2+\pi_0\left(\frac12+\frac{u_q^+}{\sqrt{2\pi}}\right)\right\}.
$$
Uniformly over dimension, all means and scalar loadings, the source's Corollary 4.11 and the [Lei finite Gaussian lower bound for one-sided BH](lei2026_one_sided_fdr_lower.md) give
$$
F_{1,\mathrm{cf}}(q)=\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+O(q),\qquad q\downarrow0.
$$
All negative true-null means are included in the upper bound.

## Source proof route and composite-null check

This is a source-based paraphrase of Theorem 4.10 and Corollary 4.11. Split true nulls by the sign $\sigma\in\{-1,1\}$ of their loading (put loading zero in the positive group), set $r=|a_i|$ and condition on $Y_\sigma=\sigma Z=y$. The actual conditional null law is $N(\theta_i+ry,1-r^2)$. Since $\theta_i\leq0$, its conditional rejection CDF is at most the boundary-mean CDF $F^0_{r,y}(t)$. Apply this domination inside the [Lei conditional leave-one-out FDP bound](lei2026_conditional_fdp_bound.md), without changing the actual leave-one-out distribution.

For each nonempty sign group, the integrated boundary tail ratio on $y\leq u_q^+$ is at most $1/2+u_q^+/\sqrt{2\pi}$; the complementary group contribution is at most $q$. There are at most two groups. This proves the displayed upper bound in the source. It does not rely on a general claim that the full BH false discovery proportion is monotone when negative means are raised to zero.

The supremum here is restricted to one common factor. The [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md) over arbitrary correlation matrices is a different, unresolved target.
