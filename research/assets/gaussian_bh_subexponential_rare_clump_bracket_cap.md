---
type: lemma
schema_version: 2
title: >-
  Compound-Poisson cap for the clump-bracket charge of sub-exponentially rare
  null clumps
status: deprecated
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_multifactor_representation
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
tags:
  - current_phase
  - universal_order
  - one_sided
  - compound_poisson_route
---

# Compound-Poisson cap for the clump-bracket charge of sub-exponentially rare null clumps

## Statement

Let $m,d$ be positive integers, $\theta\in\mathbb R^m$, let $w_1,\ldots,w_m$ be unit vectors in $\mathbb R^d$, let $Z\sim\mathcal N_d(0,I_d)$, and put $T_i=\theta_i+w_i^{\mathsf T}Z$. This is the [Gaussian multifactor representation](../definitions/gaussian_multifactor_representation.md) with unit loadings $a_i=w_i$ and no residual, hence a [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) with $\Sigma_{ij}=w_i^{\mathsf T}w_j$; singular covariance is allowed. Use the one-sided [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$, $I_0=\{i:\theta_i\le0\}$. For $0<q<1/2$ put $u=\overline\Phi^{-1}(q)$ and, when $u>1$,
$$
\tau_q=e^{-u},\qquad a_q=\frac{2\log u}{u}.
$$
All [ordinary Benjamini-Hochberg](../definitions/benjamini_hochberg_step_up.md) counts below are at level $q$ on all $m$ coordinates, with largest qualifying rank, multiplicities and non-strict comparisons.

For $\kappa>0$, a $\kappa$-sparse rare clump system is a set $S\subseteq\{i:-a_q<\theta_i\le0\}$ together with nonempty sets $K_1,\ldots,K_L$ partitioning $S$ and centers $c_l\in K_l$ such that

1. (clump radius) $\|w_i-w_{c_l}\|\le\kappa/u$ for every $i\in K_l$;
2. (sub-exponential sparsity) for every $j\in S$,
$$
\bigl|\{i\in S:\|w_i-w_j\|\le\kappa/u\}\bigr|\le\tau_q\,m .
$$

In particular every clump satisfies $|K_l|\le\tau_q m$. For $i\in K_l$ let $R_{i,0}$, $R_{i,*}$, $D_i$ and
$$
\Psi_i=\frac{\mathbf 1\{p_i\le qR_{i,*}/m\}}{\max\{R_{i,0},\,D_i,\,mp_i/q\}}
$$
be defined from the random vector $p=(p_1,\ldots,p_m)$ exactly as follows: $R_{i,0}$ is the BH rejection count after replacing $p_i$ by $0$ and $p_j$ by $1$ for $j\in K_l\setminus\{i\}$; $R_{i,*}$ is the BH rejection count after replacing $p_j$ by $0$ for every $j\in K_l$; and $D_i=|\{j\in K_l:p_j\le p_i\}|$. All other coordinates keep their original values.

There exist universal constants $\kappa_3\in(0,1]$, $A_3<\infty$ and $q_3\in(0,\overline\Phi(e)]$ such that for every $0<q\le q_3$, every such $m,d,\theta,w_1,\ldots,w_m$ (alternative means and directions arbitrary), and every $\kappa_3$-sparse rare clump system,
$$
\mathbb E\Bigl[\sum_{i\in S}\Psi_i\Bigr]\le A_3\,q\,(1+u).
$$
The constants are independent of $m$, $d$, $\theta$, the directions, the number $L$ of clumps, $|S|$, and the null proportion. The bound is at scale $q(1+u)$, not $O(q)$, and no per-clump or per-coordinate bound is asserted. Here $\log$ is natural and $e$ is the base of the natural logarithm.
