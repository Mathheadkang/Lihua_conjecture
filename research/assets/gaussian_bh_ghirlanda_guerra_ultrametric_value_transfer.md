---
title: Ghirlanda-Guerra arrays transfer their Gaussian BH value to ultrametric finite models
type: lemma
status: draft
source:
  kind: original
  note: Route lemma of the researcher-selected ultrametric route (idea_b808cca5bf7f, content idea_ae102c56085d), parallel round of 12 November 2026. Unproved. Its intended external input, Panchenko's ultrametricity theorem for Gram-de Finetti arrays satisfying the Ghirlanda-Guerra identities (Ann. of Math. 177 (2013) 383-393), is not yet imported into the library and must be imported and verified before use.
depends_on:
  - gaussian_bh_exchangeable_array_variational_compactification
uses_definitions:
  - gaussian_bh_marked_exchangeable_parameter_array
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - parallel-round-20261112
  - route-3
  - ultrametric
---

# Ghirlanda-Guerra arrays transfer their Gaussian BH value to ultrametric finite models

## Statement

Use the lawful jointly exchangeable [marked parameter arrays](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md), their law space $\mathfrak P$ and the completed conditional Gaussian FDR functional $\mathcal F(P;q,\sigma)=\lim_{n\to\infty}\mathcal F_n(P;q,\sigma)$, which exists for every $P\in\mathfrak P$ and $0<q<1/2$ by item 1 of [the marked-array compactification](gaussian_bh_exchangeable_array_variational_compactification.md). Put $q_{\max}=\overline\Phi(1)$.

Call a symmetric matrix $C\in\mathbb R^{n\times n}$ a *nonnegative ultrametric correlation matrix* if it is positive semidefinite, $C_{ii}=1$ for all $i$, $C_{ij}\ge0$ for all $i\ne j$, and
$$
C_{ij}\ge\min\{C_{ik},C_{jk}\}\qquad\text{for all pairwise distinct }i,j,k\in\{1,\ldots,n\}.
$$
Singular matrices are allowed; for $n\le2$ the last condition is vacuous. For $0<\sigma<1$ and $0<q\le q_{\max}$ define the ultrametric common-loading supremum
$$
U_\sigma(q)=\sup_{n\ge1}\ \sup_{\theta\in\mathbb R^n}\ \sup_{C}\
\operatorname{FDR}_{\mathrm{BH}}^{(1)}\bigl(q;n,\theta,(1-\sigma^2)C+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}\bigr),
$$
where $C$ ranges over the $n\times n$ nonnegative ultrametric correlation matrices, and $\operatorname{FDR}_{\mathrm{BH}}^{(1)}$ is the original one-sided [false discovery rate](../definitions/false_discovery_rate.md) of [ordinary BH](../definitions/benjamini_hochberg_step_up.md) with the [one-sided p-values and true nulls](../definitions/gaussian_test_pvalues.md) $\overline\Phi(T_i)$, $I_0=\{i:\theta_i\le0\}$, in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) with that covariance.

For $P\in\mathfrak P$, an integer $n\ge2$, and continuous $f:[-1,1]^{n(n-1)/2}\to[-1,1]$ and $\psi:[-1,1]\to[-1,1]$, let
$$
\Delta_P(n,f,\psi)=\mathbb E_P\!\left[f(C^{(n)})\,\psi(C_{1,n+1})\right]
-\frac1n\,\mathbb E_P\!\left[f(C^{(n)})\right]\mathbb E_P\!\left[\psi(C_{12})\right]
-\frac1n\sum_{l=2}^{n}\mathbb E_P\!\left[f(C^{(n)})\,\psi(C_{1l})\right],
$$
with $C^{(n)}=(C_{ll'})_{1\le l<l'\le n}$ the off-diagonal residual correlations of the first $n$ indices.

Fix $0<\sigma<1$ and $0<q\le q_{\max}$. Let $(P_k)_{k\ge1}$ be any sequence in $\mathfrak P$ such that $\Delta_{P_k}(n,f,\psi)\to0$ as $k\to\infty$ for every $n\ge2$ and all such continuous $f,\psi$. No bound on $M_2(P_k)$ is assumed. Then
$$
\limsup_{k\to\infty}\mathcal F(P_k;q,\sigma)\le U_\sigma(q).
$$
The marks of the arrays may escape to $\theta=\pm\infty$ along the sequence; the conclusion must hold regardless. This lemma asserts no FDR order bound.
