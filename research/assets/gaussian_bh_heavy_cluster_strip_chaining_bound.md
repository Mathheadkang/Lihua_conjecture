---
type: lemma
schema_version: 2
title: Joint strip bound for heavy separated angular null clusters
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

# Joint strip bound for heavy separated angular null clusters

## Statement

Let $m,d$ be positive integers, $\theta\in\mathbb R^m$, let $w_1,\ldots,w_m$ be unit vectors in $\mathbb R^d$, let $Z\sim\mathcal N_d(0,I_d)$, and put $T_i=\theta_i+w_i^{\mathsf T}Z$. This is the [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) with unit loadings $a_i=w_i$ and no residual, hence a [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) with $\Sigma_{ij}=w_i^{\mathsf T}w_j$; singular covariance is allowed. Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$ and $I_0=\{i:\theta_i\le0\}$. For $0<q<1/2$ let $\mathcal R_q$ be the rejection set of the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) applied to all of $p_1,\ldots,p_m$ at level $q$ (largest qualifying rank, multiplicities, non-strict comparisons), $R=|\mathcal R_q|$, and $u=\overline\Phi^{-1}(q)>0$.

For $\kappa>0$ and $C\ge1$, a heavy separated angular family at scale $\kappa$ and exponent $C$ is a finite family $(G_1,v_1),\ldots,(G_H,v_H)$ of pairwise disjoint nonempty sets $G_h\subseteq I_0$ and unit vectors $v_h\in\mathbb R^d$ such that
$$
\|w_i-v_h\|\le\kappa/u\quad(i\in G_h),\qquad
\|v_h-v_k\|>\kappa/u\quad(h\ne k),\qquad
\pi_h=\frac{|G_h|}m\ge q^C .
$$
Put
$$
Y_h=v_h^{\mathsf T}Z,\qquad b_h=\overline\Phi^{-1}(q\pi_h)\ge u,\qquad V_h=|\mathcal R_q\cap G_h|.
$$
The family need not cover $I_0$; necessarily $H\le q^{-C}$.

For every $\kappa\in(0,1]$ and every $C\ge1$ there exist finite constants $A_3=A_3(\kappa,C)$ and $q_3=q_3(\kappa,C)\in(0,1/2)$, depending only on $\kappa$ and $C$, such that for every $0<q\le q_3$, every such $m,d,\theta,w_1,\ldots,w_m$, and every heavy separated angular family at scale $\kappa$ and exponent $C$,
$$
\sum_{h=1}^H\mathbb E\!\left[\frac{V_h\,\mathbf 1\{u<Y_h\le b_h\}}{R\vee1}\right]\le A_3\,q\,(1+u).
$$

Here $R\vee1=\max\{R,1\}$ with the [false discovery rate](../definitions/false_discovery_rate.md) conventions. The counts refer to the same unmodified BH procedure on all $m$ coordinates and the original null labels. The constants are independent of $m$, $d$, $\theta$, the directions, $H$, the masses $\pi_h$ (beyond $\pi_h\ge q^C$), and the null proportion. The bound replaces the one-scale charge $q\sum_h\pi_h\log(1/\pi_h)$, which can be of order $q\log(1/q)$ here, by the scale $q(1+u)$.
