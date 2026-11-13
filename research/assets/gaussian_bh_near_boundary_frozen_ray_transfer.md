---
title: Frozen-ray transfer for the near-boundary null contribution to one-sided Gaussian BH
type: lemma
status: draft
source:
  kind: original
  note: >-
    Route lemma (the BH transfer) of the researcher-selected route "frozen-ray
    maximal inequality via stopped density martingales, then transfer to BH"
    (idea_bc183ea2b6fa, write-up idea_2bb31516b09b).
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - frozen-ray
  - route-lemma
---

# Frozen-ray transfer for the near-boundary null contribution to one-sided Gaussian BH

## Statement

There are universal finite constants $A_{\mathrm T}>0$ and $q_{\mathrm T}\in(0,\overline\Phi(e)]$ with the following property. Let $N\geq1$ be an integer, $\theta\in\mathbb R^N$, and $\Sigma\in\mathcal C_N$ a unit-diagonal positive-semidefinite matrix, singular matrices included, in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md); let $T\sim\mathcal N_N(\theta,\Sigma)$ and $Z=T-\theta\sim\mathcal N_N(0,\Sigma)$. Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$ and $I_0=\{i:\theta_i\leq0\}$, where $\overline\Phi$ is the standard normal survival function and $e$ is the base of the natural logarithm.

For $0<q\leq q_{\mathrm T}$ put $U=\overline\Phi^{-1}(q)$, $a_q=2\log(U)/U$ and
$$
B_q=\{i\in\{1,\ldots,N\}:-a_q<\theta_i\leq0\}.
$$
Run the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $q$ on all $N$ p-values, with the largest qualifying rank, non-strict comparisons and multiplicities; let $\mathcal R_q$ be its rejection set, $R=|\mathcal R_q|$ and $V_{B_q}=|\mathcal R_q\cap B_q|$. Define the near-boundary frozen-ray field
$$
\Lambda_{B_q}(Z)=\sup_{w\geq0}\frac1N\sum_{i\in B_q}\exp\!\left(wZ_i-\frac{w^2}{2}\right),
$$
with $\Lambda_{B_q}=0$ when $B_q=\varnothing$ and the same realization of $Z$ for every $w$. Then
$$
\mathbb E\!\left[\frac{V_{B_q}}{R\vee1}\right]
\leq A_{\mathrm T}\,q\Bigl(1+\mathbb E\min\bigl\{1/q,\Lambda_{B_q}(Z)\bigr\}\Bigr),
$$
where $R\vee1=\max\{R,1\}$, in the sense of the [false discovery rate](../definitions/false_discovery_rate.md) of the full procedure. The constants are independent of $N$, $\theta$, $\Sigma$, its rank, the null proportion, $|B_q|$ and $q$; all model parameters may vary with $q$. No coordinate is deleted, relabeled or recentered in the BH procedure: $V_{B_q}$ and $R$ refer to the same unmodified procedure on all $N$ coordinates, and the alternatives $i\notin I_0$ are unrestricted.

## Motivation

On $\{R\geq1\}$, with BH cutoff $x^*=\overline\Phi^{-1}(qR/N)$, the pointwise relaxation $\mathbf 1\{t\geq x\}\leq e^{x(t-x)}$ yields this inequality only with an extra hazard factor $h(x^*)=\phi(x^*)/\overline\Phi(x^*)\geq U$ (idea_9f8ffb204424, item (b)); any pointwise exponential-mixture domination of the indicator loses that factor. The lemma therefore asks for a BH-sensitive comparison that keeps the actual largest crossing, the approach left open as gap (ii) of idea_2bb31516b09b. Free-threshold indicator envelopes are known to lose a logarithm even for independent nulls (idea_d353cd54790b); the field here is the exponential frozen-ray field, not an indicator envelope.
