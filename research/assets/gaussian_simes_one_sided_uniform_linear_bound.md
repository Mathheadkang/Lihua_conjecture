---
type: lemma
title: Uniform linear bound for one-sided Gaussian Simes rejection probability
status: draft
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_worst_case_bh_fdr
tags:
  - gaussian_bh
  - one_sided
  - global_null
  - simes
  - necessary_condition
---

# Uniform linear bound for one-sided Gaussian Simes rejection probability

## Statement

There exist universal constants $0<C<\infty$ and $q_0\in(0,1/2)$ such that the following holds. For every positive integer $N$, every $\Sigma\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), including singular matrices, and every $0<q\le q_0$, let $T\sim\mathcal N_N(0,\Sigma)$ and form the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md) $p_i^{(1)}=\overline\Phi(T_i)$. Write $p_{(1)}^{(1)}\le\cdots\le p_{(N)}^{(1)}$ for their order statistics, including multiplicities. Then
$$
\mathbb P_{N,0,\Sigma}\!\left(\exists k\in\{1,\ldots,N\}:p_{(k)}^{(1)}\le\frac{qk}{N}\right)\le Cq.
$$
The event uses non-strict comparisons. Equivalently, if $R_q^{(1)}$ denotes the number of rejections under the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), the proposed bound is
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,0,\Sigma)
=\mathbb P_{N,0,\Sigma}(R_q^{(1)}\ge1)\le Cq,
$$
Here $\operatorname{FDR}_{\mathrm{BH}}^{(1)}$ uses the [Gaussian BH model notation](../definitions/gaussian_worst_case_bh_fdr.md); [false discovery rate](../definitions/false_discovery_rate.md) equals the rejection probability because all coordinates are true nulls. The symbol $\mathbb P_{N,0,\Sigma}$ denotes probability under the displayed centered Gaussian law. The constants are independent of dimension, covariance rank, correlations, and every other model parameter; $N$ and $\Sigma$ may vary arbitrarily with $q$.

## Motivation

This conjecture is extracted from the draft shared idea [Necessary sub-conjecture: one-sided Simes probability under arbitrary Gaussian correlation is O(q)](../ideas/idea_aba318ad3eee.md). It isolates the all-null Gaussian rejection event as a necessary test of the [universal order upper bound for one-sided Gaussian BH](gaussian_bh_one_sided_universal_order_upper.md), while leaving mixed true and false null configurations outside its statement.

The necessity uses the independently recorded [all-null independent-block amplification observation](../ideas/idea_8699fa13f1f6.md): a dimension-uniform all-null rejection bound strictly below one at a single fixed testing level forces a uniform linear bound at sufficiently small levels. Thus the main order target, which tends to zero, would imply this conjecture through amplification, rather than merely through restriction to centered models. Proving this conjecture alone would still leave the mixed-null FDR problem unresolved.

The source idea proposes Gaussian Gram geometry as a possible explanation for a linear bound. That motivation is heuristic. This node records the precise uniform conjecture, with no proof or counterexample, and does not adopt the source idea's snippet-level literature claims as verified facts.
