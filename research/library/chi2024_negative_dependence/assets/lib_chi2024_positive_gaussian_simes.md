---
type: theorem
title: >-
  Simes inequality for positive Gaussian dependence and its distributional
  mixtures
status: approved
source:
  kind: paper
  paper_id: chi2024_negative_dependence
  location: >-
    Author manuscript dated 8 May 2024, Section 3.3, Theorem 8(I) and Remark 10,
    printed p. 11
depends_on: []
uses_definitions:
  - lib_chi2024_gaussian_dependence
  - lib_chi2024_simes_function_uniform_pvalues
tags:
  - simes
  - gaussian_dependence
  - positive_correlation
  - mixture
---

# Simes inequality for positive Gaussian dependence and its distributional mixtures

## Statement

For every integer $K\ge1$, let $P\in\mathcal G_\Sigma\cap\mathcal U^K$ be [Gaussian dependent with latent correlation $\Sigma$](../definitions/lib_chi2024_gaussian_dependence.md), with [uniform marginal p-values and Simes function $S_K$](../definitions/lib_chi2024_simes_function_uniform_pvalues.md). If $\Sigma_{ij}\ge0$ for all distinct $i,j$, then
$$
\mathbb P\bigl(S_K(P)\le\alpha\bigr)\le\alpha
\qquad\text{for every }\alpha\in(0,1).
$$
The same inequality holds when the distribution of $P$ is any distributional mixture of $K$-dimensional laws satisfying these hypotheses, with the latent correlation matrix allowed to vary between mixture components. This is the extension stated in Remark 10.

## Source scope

This is a normalized paraphrase of Theorem 8(I) and its mixture extension. The matrix $\Sigma$ is any correlation matrix with nonnegative off-diagonal entries; the source assumes neither nonsingularity nor a joint density, so degenerate jointly Gaussian latent vectors with nondegenerate marginals are within its stated class. The uniform marginals and fixed finite $K$ remain hypotheses.

The author manuscript attributes part (I) to Benjamini and Yekutieli. It is kept here as a paper-sourced known result, without reproducing or reproving the regression-dependence argument. The inequality does not by itself treat arbitrary mixed-sign Gaussian correlations, composite-null shifts, arbitrary full-FDR mixtures, or two-sided Gaussian p-values. These adaptations are not part of this node. Independent extraction checking and researcher approval remain pending.
