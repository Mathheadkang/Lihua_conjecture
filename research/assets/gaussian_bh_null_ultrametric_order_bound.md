---
title: Universal order bound for one-sided Gaussian BH when the null correlations form a tree
type: lemma
status: draft
source:
  kind: original
  note: Route lemma (slot 5) of the researcher-selected ultrametric route (idea_b808cca5bf7f, content idea_ae102c56085d), parallel round of 12 November 2026 -- the chaining-on-trees step. Unproved restriction of the target to models whose null-null correlations are nonnegative and ultrametric; alternatives are unrestricted.
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - parallel-round-20261112
  - ultrametric
  - gaussian-tree
---

# Universal order bound for one-sided Gaussian BH when the null correlations form a tree

## Statement

There exist finite universal constants $A_T>0$ and $q_T\in(0,1/2)$ such that the following holds.

Let $N$ be a positive integer, $\theta\in\mathbb R^N$, and $\Sigma\in\mathbb R^{N\times N}$ symmetric positive semidefinite with $\Sigma_{ii}=1$ for every $i$ (singular matrices allowed). Put $I_0=\{i:\theta_i\le0\}$ and assume the null-null correlations are nonnegative and ultrametric:
$$
\Sigma_{ij}\ge0\quad\text{for all distinct }i,j\in I_0,
\qquad
\Sigma_{ik}\ge\min\{\Sigma_{ij},\Sigma_{jk}\}\quad\text{for all pairwise distinct }i,j,k\in I_0.
$$
No condition is imposed on $\Sigma_{ij}$ when $i\notin I_0$ or $j\notin I_0$, nor on the alternative means. Let $T\sim\mathcal N_N(\theta,\Sigma)$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), use the [one-sided p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$, $I_0$, and apply [ordinary BH](../definitions/benjamini_hochberg_step_up.md) at level $q$ with its largest qualifying rank, non-strict comparisons and multiplicities. Then, for every $0<q\le q_T$, its [false discovery rate](../definitions/false_discovery_rate.md) satisfies
$$
\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)\le A_T\,q\left[1+\sqrt{\log(1/q)}\right].
$$
The logarithm is natural. The constants are independent of $N$, $\theta$, $\Sigma$, the null proportion, and the depth, branching and level values of the null tree; every model parameter may vary with $q$. No sharp constant is asserted.

## Notes

Equivalently (not part of the hypothesis), the null scores are the leaves of a finite rooted tree with nonnegative edge variances, null-null correlation being the variance accumulated down to the most recent common ancestor; this includes equicorrelated and one-factor null blocks, the independent case, and the GREM-type hierarchical models of idea_38a72ab5ee7e, so the lemma carries the full $q\sqrt{\log(1/q)}$ order.

Suggested inputs for its own plan (not route lemmas): the tree filtration with conditional independence of sibling subtrees given ancestors; chaining over the tree levels with the approved [directional-entropy bound](directional_entropy_one_sided_fdr_bound.md) as the per-level charge and the self-sustaining cap of idea_38a72ab5ee7e (a subtree of mass $\pi$ can be tracked by the BH level only over a level range of length about $\log(1/\pi)/U$); the depth-two case (TREE-2 of idea_38a72ab5ee7e) and the draft [two-level tree frozen-ray result](gaussian_frozen_ray_two_level_tree.md) as base cases; approved conditional calibrations ([compound](gaussian_bh_conditional_compound_calibration.md), [sub-Poisson](gaussian_bh_conditional_subpoisson_calibration.md)) once alternatives are conditioned on. Failure criterion: a tree family (for example many equal leaf groups) with FDR$/(q\sqrt{\log(1/q)})$ unbounded refutes this lemma; a proof that needs $\log(\#\text{leaves})$ is the entropy bound again.
