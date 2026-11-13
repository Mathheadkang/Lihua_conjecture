---
type: lemma
title: Few-block compression of the Schur-square downward variation of the Gaussian Simes size
status: draft
source:
  kind: original
depends_on: []
related_assets:
  - gaussian_simes_clone_block_schur_variation_bound
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - simes
  - global_null
  - one_sided
  - schur_square_variation
---

# Few-block compression of the Schur-square downward variation of the Gaussian Simes size

## Statement

The notation is that of the clone-block Schur-square variation bound, restated in full. For a positive integer $N$, $R\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) and $q\in(0,1)$, $F_q(R)$ is the probability, for $Z\sim\mathcal N_N(0,R)$ and the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(Z_i)$, that $p_{(k)}\le qk/N$ for some $k\in\{1,\ldots,N\}$ (order statistics with multiplicities, non-strict comparison). For $\Sigma\in\mathcal C_N$,
$$
f_{q,\Sigma}(t)=F_q\bigl((1-t)\Sigma+t(\Sigma\circ\Sigma)\bigr),\qquad 0\le t\le1,
$$
and $\mathcal V_-(f)=\sup\sum_{\ell=1}^m[f(t_{\ell-1})-f(t_\ell)]_+$ over all partitions $0=t_0<\cdots<t_m=1$. A clone-block covariance with at most $K$ blocks is a matrix $\Sigma'\in\mathcal C_{N'}$ with $\Sigma'_{ij}=\Gamma_{a(i)a(j)}$ for some $\Gamma\in\mathcal C_K$ and some map $a:\{1,\ldots,N'\}\to\{1,\ldots,K\}$. For $q\in(0,1)$ put
$$
K_\flat(q)=\max\Bigl\{1,\ \Bigl\lfloor\frac{\log(1/q)}{4\log4}\Bigr\rfloor\Bigr\},
\qquad
\mathcal M(q)=\sup\bigl\{\mathcal V_-(f_{q,\Sigma'}):N'\ge1,\ \Sigma'\in\mathcal C_{N'}\text{ clone-block with at most }K_\flat(q)\text{ blocks}\bigr\}.
$$

There exists a universal constant $q_2\in(0,1/4]$ such that for every $q\in(0,q_2]$, every positive integer $N$ and every $\Sigma\in\mathcal C_N$, singular matrices included,
$$
\mathcal V_-(f_{q,\Sigma})\le\mathcal M(q)+\frac18 .
$$
The constant $q_2$ does not depend on $N$, $\Sigma$, its rank, or the signs of its entries.

## Motivation

This is the reduction half of a model-first route through the [Schur-square tensor-lift approach](../ideas/idea_6b48b2fe25e1.md). It asserts that, at small levels, the downward variation of the Simes size along the Schur-square path is captured, up to an additive $1/8$, by configurations with about $\log(1/q)$ distinct Gaussian directions and arbitrary multiplicities. It concerns the variation itself, retaining the signed pair sum and the factors $\rho_{ij}(1-\rho_{ij})$; it is not a comparison of Simes sizes, since a size comparison would bypass the variation structure and the model bound would then give nothing beyond a crude union-type estimate for few-direction models. The block budget $K_\flat(q)$ is chosen so that the multiplicity-free model bound $K^24^Kq$ stays below $1/8$. A configuration where many distinct directions are needed to produce narrow oscillations of the profile in $t$ would refute this lemma without refuting the Simes conjecture.
