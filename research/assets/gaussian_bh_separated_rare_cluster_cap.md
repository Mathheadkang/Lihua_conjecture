---
type: lemma
schema_version: 2
title: Rare-cluster cap for separated angular null clusters
status: draft
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_multifactor_representation
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - current_phase
  - universal_order
  - one_sided
  - angular_chaining_route
---

# Rare-cluster cap for separated angular null clusters

## Statement

Let $m,d$ be positive integers, $\theta\in\mathbb R^m$, let $w_1,\ldots,w_m$ be unit vectors in $\mathbb R^d$, let $Z\sim\mathcal N_d(0,I_d)$, and put $T_i=\theta_i+w_i^{\mathsf T}Z$. This is the [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) with unit loadings $a_i=w_i$ and no residual, hence a [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) with $\Sigma_{ij}=w_i^{\mathsf T}w_j$; singular covariance is allowed. Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$ and $I_0=\{i:\theta_i\le0\}$. For $0<q<1/2$ let $\mathcal R_q$ be the rejection set of the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) applied to all of $p_1,\ldots,p_m$ at level $q$ (largest qualifying rank, multiplicities, non-strict comparisons), $R=|\mathcal R_q|$, and $u=\overline\Phi^{-1}(q)>0$.

For $\kappa>0$, a separated angular partition at scale $\kappa$ is a finite family $(G_1,v_1),\ldots,(G_H,v_H)$ in which $G_1,\ldots,G_H$ are nonempty and partition $I_0$ (with $H=0$ if $I_0=\varnothing$), each $v_h\in\mathbb R^d$ is a unit vector, and
$$
\|w_i-v_h\|\le\kappa/u\quad(i\in G_h),\qquad
\|v_h-v_k\|>\kappa/u\quad(h\ne k).
$$
Put $\pi_h=|G_h|/m$ and $V_h=|\mathcal R_q\cap G_h|$.

There exist universal constants $\kappa_2\in(0,1]$, $C_2\ge1$, $A_2<\infty$ and $q_2\in(0,1/2)$ such that for every $0<q\le q_2$, every such $m,d,\theta,w_1,\ldots,w_m$, and every separated angular partition at scale $\kappa_2$, the rare clusters
$$
\mathcal H_{\mathrm{rare}}=\{h:\pi_h<q^{C_2}\}
$$
satisfy
$$
\sum_{h\in\mathcal H_{\mathrm{rare}}}\mathbb E\!\left[\frac{V_h}{R\vee1}\right]\le A_2\,q\,(1+u).
$$

Here $R\vee1=\max\{R,1\}$ with the [false discovery rate](../definitions/false_discovery_rate.md) conventions. The counts refer to the same unmodified BH procedure on all $m$ coordinates and the original null labels; the clusters are used only to group terms. The constants are independent of $m$, $d$, $\theta$, the directions, the number $H$ of clusters, the number of rare clusters, and the null proportion. The bound is at the scale $q(1+u)$, not $O(q)$; no per-cluster bound is asserted.
