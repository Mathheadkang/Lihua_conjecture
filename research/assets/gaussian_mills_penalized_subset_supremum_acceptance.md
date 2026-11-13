---
type: lemma
title: Uniform positive acceptance for the Mills-normalized penalized Gaussian subset supremum
status: draft
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
tags:
  - gaussian_bh
  - one_sided
  - global_null
  - simes
  - hinge_form
  - gibbs_variational
---

# Uniform positive acceptance for the Mills-normalized penalized Gaussian subset supremum

## Statement

Write $\phi$ for the standard normal density, $\overline\Phi(x)=\int_x^\infty\phi$, and $h=\phi/\overline\Phi$. For a positive integer $N$, a real $A\ge2$ and a nonempty $K\subseteq\{1,\ldots,N\}$ put $\kappa_K=|K|/N$, $z_K=\overline\Phi^{-1}(\kappa_K/A)\ge0$ and $\tau_A(K)=h(z_K)$. For $t\in\mathbb R^N$ put $X_K(t)=|K|^{-1}\sum_{i\in K}t_i$ and
$$
M_A(t)=\max_{\varnothing\ne K\subseteq\{1,\ldots,N\}}\tau_A(K)\bigl(X_K(t)-\tau_A(K)\bigr).
$$
There exist universal constants $A\ge2$, $s_0\ge0$ and $\delta_0\in(0,1]$ such that, for every positive integer $N$ and every $\Sigma\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), singular matrices and correlations of either sign included, the vector $T\sim\mathcal N_N(0,\Sigma)$ satisfies
$$
\mathbb P_{N,0,\Sigma}\bigl(M_A(T)\le s_0\bigr)\ge\delta_0 .
$$
The constants are independent of $N$, $\Sigma$, its rank and every other model parameter.

## Motivation

$M_A$ is a penalized supremum of the Gaussian process $K\mapsto X_K(T)$ over null sub-populations, in the Mills normalization that makes each index's one-dimensional tail comparable to $e^{-s}\kappa_K/A$: since $\operatorname{Var}X_K\le1$, $\mathbb P(\tau_A(K)(X_K-\tau_A(K))\ge s)\le\overline\Phi(\tau_A(K)+s/\tau_A(K))$. Only a positive acceptance probability at one fixed penalty level is asked, not a bounded mean or a summable tail over scales. The weaker form matters: the [clones-plus-independents countercheck](../ideas/idea_b57684f6c514.md) rules out a nonpositive mean for the unnormalized penalized supremum, and [the scalar hinge calculation](../ideas/idea_4d3b81529002.md) rules out a bounded mean of the hinge ratio. The intended attack is the Gibbs variational (Donsker-Varadhan) form of $\max_K$ with priors on sub-populations adapted to $\operatorname{Var}X_K$, combined with the dense-rank log-convex tilt recorded in [the dense-crossing observation](../ideas/idea_a2ee64f07126.md).
