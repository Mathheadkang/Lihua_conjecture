---
type: lemma
schema_version: 2
title: Null-side positive carrier with a square-root-log cluster intensity
status: draft
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - current_phase
  - universal_order
  - one_sided
  - sign_split_route
---

# Null-side positive carrier with a square-root-log cluster intensity

## Statement

There exist universal constants $0<C_3<\infty$ and $q_3\in(0,1)$ such that the following holds.

Let $n$ be a positive integer, $\mu\in(-\infty,0]^n$, and $\Sigma_0\in\mathcal C_n$ a unit-diagonal positive-semidefinite matrix as in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), singular matrices included. Let $X\sim\mathcal N_n(\mu,\Sigma_0)$ and $P_i=\overline\Phi(X_i)$, the one-sided [Gaussian test p-values](../definitions/gaussian_test_pvalues.md). Let $0<q\le q_3$.

Then there exist an integer $m\ge0$, a deterministic matrix $A\in\mathbb R^{m\times n}$, a diagonal positive-semidefinite matrix $D\in\mathbb R^{m\times m}$ and a partition $\mathcal C$ of $\{1,\ldots,n\}$ into nonempty clusters with the following properties. Put
$$
Y=A(X-\mu)+W,\qquad W\sim\mathcal N_m(0,D)\ \text{independent of }X,
$$
($Y$ constant when $m=0$) and let $Q=\operatorname{Cov}(X\mid Y)$ be the deterministic Gaussian conditional covariance matrix. Then

1. (sign split) $Q_{ij}\le0$ whenever $i$ and $j$ lie in distinct clusters of $\mathcal C$;
2. (cluster intensity) with the canonical Gaussian regular conditional law given $Y$,
$$
K_0(Y)=\max\Bigl\{1,\ \sup_{t\in(0,q]\cap(\mathbb Q\cup\{q\})}\frac1{nt}\sum_{c\in\mathcal C}|c|\;\mathbb P\Bigl(\min_{i\in c}P_i\le t\Bigm|Y\Bigr)\Bigr\}
$$
satisfies
$$
\mathbb E\bigl[\min\{1,\,q\,K_0(Y)\}\bigr]\le C_3\,q\sqrt{\log(1/q)} .
$$

The logarithm is natural. The objects $m,A,D,\mathcal C$ may depend on $n,\mu,\Sigma_0$ and $q$; the constants $C_3,q_3$ may not. The statement concerns the null vector only: no alternative coordinate and no BH procedure appear in it.

## Motivation

This is the refined-linking half of the sign-split route of [the researcher-selected direction](../ideas/idea_afb46a36a429.md) and [the route proposal](../ideas/idea_26f348b94400.md). Unrefined FDR linking loses $\log(1/q)$ already for independent nulls ([observation](../ideas/idea_e6e1f4c16f22.md)); here independent nulls take $Y$ constant and singleton clusters, so $K_0\equiv1$. Positive null-null association is absorbed into the carrier $Y$, which is built from null coordinates only so that alternatives that are positive copies of nulls are never revealed (the over-revealing warning in [the two-class test proposal](../ideas/idea_33e7435632a7.md)); exact or near comonotone groups are absorbed into clusters, where the cluster minimum replaces a sum of indicators.

Calibration checks, heuristic. For Lei's one-factor null family, conditioning on the null sample mean leaves residual covariance $-s^2/n$ off the diagonal, and $K_0$ is approximately $e^{z_+^2/2}$ in the factor $z$, which has the half-space tail behind $q\sqrt{\log(1/q)}$ in [the tail-calibration note](../ideas/idea_76d8bdfb8584.md). For independent comonotone blocks, $Y$ constant with the blocks as clusters gives $K_0\equiv1$. The intended Gaussian inputs are the Mills-ratio gain of the conditional tail ratio when the residual standard deviation is at least of order $1/\overline\Phi^{-1}(q)$, the [positive Gaussian Simes inequality](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) on positively associated revealed parts, and the [linear Simes bound](gaussian_simes_one_sided_uniform_linear_bound.md) for cluster minima. Multiscale positive structures, such as deep trees whose residual variance is small at every level, are the main risk to this statement.
