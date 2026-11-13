---
title: Universal order bound for one-sided Gaussian BH under ultrametric covariance
type: lemma
status: draft
source:
  kind: original
  note: Route lemma of the researcher-selected ultrametric route (idea_b808cca5bf7f, content idea_ae102c56085d), parallel round of 12 November 2026 -- the "chaining on trees" step. Unproved restriction of the target to tree (hierarchical) covariances.
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - parallel-round-20261112
  - route-3
  - ultrametric
  - gaussian-tree
---

# Universal order bound for one-sided Gaussian BH under ultrametric covariance

## Statement

Call a symmetric matrix $\Sigma\in\mathbb R^{N\times N}$ a *nonnegative ultrametric correlation matrix* if it is positive semidefinite, $\Sigma_{ii}=1$ for all $i$, $\Sigma_{ij}\ge0$ for all $i\ne j$, and
$$
\Sigma_{ij}\ge\min\{\Sigma_{ik},\Sigma_{jk}\}\qquad\text{for all pairwise distinct }i,j,k\in\{1,\ldots,N\}.
$$
Singular matrices are allowed; for $N\le2$ the last condition is vacuous. Equivalently these are the correlation matrices of Gaussian vectors indexed by the leaves of a finite rooted tree, with nonnegative correlation determined by the most recent common ancestor; this reformulation is not part of the hypothesis.

There exist finite universal constants $A>0$ and $\widetilde q\in(0,1)$ such that the following holds. For every positive integer $N$, every $\theta\in\mathbb R^N$, every $N\times N$ nonnegative ultrametric correlation matrix $\Sigma$, and every $0<q\le\widetilde q$, let $T\sim\mathcal N_N(\theta,\Sigma)$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), use the [one-sided p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$, $I_0=\{i:\theta_i\le0\}$, and apply [ordinary BH](../definitions/benjamini_hochberg_step_up.md) with its largest qualifying rank, non-strict comparisons and multiplicities. Then its [false discovery rate](../definitions/false_discovery_rate.md) satisfies
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)\le A\,q\left[1+\sqrt{\log(1/q)}\right].
$$
The logarithm is natural. The constants $A,\widetilde q$ are independent of $N$, $\theta$, $\Sigma$, the depth and branching of the tree, the null proportion, and every other model parameter; all of these may vary with $q$. No sharp constant is asserted.
