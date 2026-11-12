---
type: theorem
title: Lei sharp two-sided BH upper bound with one common factor
status: draft
source:
  kind: paper
  paper_id: lei2026_gaussian_bh
  location: Theorem 4.2, p. 60; proofs in Sections 4.2.1-4.2.2, pp. 60-86; sharpness discussion, pp. 4 and 90
depends_on: [lei2026_conditional_fdp_bound, lei2026_two_sided_fdr_lower]
uses_definitions: [gaussian_one_common_factor_model, gaussian_test_pvalues, benjamini_hochberg_step_up, false_discovery_rate, gaussian_worst_case_bh_fdr]
tags: [gaussian, benjamini_hochberg, two_sided, upper_bounds, one_common_factor, paper_source]
---

## Statement

In the [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md), apply the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) to the two-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md). Put $m_0=|\{i:\theta_i=0\}|$ and $\pi_0=m_0/m$. For $0<q\leq2\overline\Phi(1)$, let $u_q\geq1$ solve $2\overline\Phi(u_q)=q$. If $m_0=0$ the [false discovery rate](../definitions/false_discovery_rate.md) is zero. Otherwise, uniformly over $m,\theta,a$,
$$
\operatorname{FDR}_{\mathrm{BH}}^{(2)}(q;m,\theta,\Sigma(a))\leq q\left\{1+\pi_0\left(\frac{1-q}{2}+\frac{u_q}{\sqrt{2\pi}}\right)\right\},
$$
and there is a universal $C<\infty$ such that
$$
\operatorname{FDR}_{\mathrm{BH}}^{(2)}(q;m,\theta,\Sigma(a))\leq q\left[1+\frac{\pi_0}{2\sqrt\pi}\sqrt{\log(1/q)}+C\pi_0\{\log(1/q)\}^{1/4}\right].
$$
Together with the [Lei finite Gaussian lower bound for two-sided BH](lei2026_two_sided_fdr_lower.md), this yields
$$
\lim_{q\downarrow0}\frac{F_{2,\mathrm{cf}}(q)}{q\sqrt{\log(1/q)}}=\frac1{2\sqrt\pi}.
$$

## Source proof route and scope

The source first applies the [Lei conditional leave-one-out FDP bound](lei2026_conditional_fdp_bound.md) and integrates Gaussian tail ratios over $|Z|\leq u_q$, bounding the complementary contribution by $q$. This gives the first inequality. Its leading constant alone is $1/\sqrt\pi$, twice the sharp target.

The second inequality retains leave-one-out rank weights. Small rejection ranks contribute $O(q\sqrt{u_q})$; conditional Poisson-binomial concentration controls bad events for larger ranks. On the good event, the first-crossing restrictions permit a deterministic integral bound (Lemma 4.7, pp. 80-82). Its ingredients are scalar reflected-sign range exclusion for larger loadings (Lemma 4.5, pp. 66-71) and adjusted log-convexity plus tail growth for small loadings (Lemma 4.6, pp. 71-80).

This is a paper-sourced paraphrase, not a checked unrestricted theorem. It does not establish the analogous bound for every positive semidefinite Gaussian correlation matrix in the [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md).
