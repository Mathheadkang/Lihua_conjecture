---
title: >-
  Approximate Ghirlanda-Guerra identities along near-maximizing marked Gaussian
  BH arrays
type: lemma
status: deprecated
source:
  kind: original
  note: >-
    Route lemma of the researcher-selected ultrametric route (idea_b808cca5bf7f,
    content idea_ae102c56085d), parallel round of 12 November 2026. Unproved;
    high risk.
depends_on:
  - gaussian_bh_exchangeable_array_variational_compactification
uses_definitions:
  - gaussian_bh_marked_exchangeable_parameter_array
  - gaussian_worst_case_bh_fdr
tags:
  - parallel-round-20261112
  - route-3
  - ultrametric
---

# Approximate Ghirlanda-Guerra identities along near-maximizing marked Gaussian BH arrays

## Statement

Use the lawful jointly exchangeable [marked parameter arrays](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md) $\omega=((\theta_i,\ell_i)_{i\ge1},(C_{ij})_{i,j\ge1})$, their law space $\mathfrak P$, the completed conditional Gaussian FDR functional $\mathcal F(P;q,\sigma)=\lim_{n\to\infty}\mathcal F_n(P;q,\sigma)$ (which exists for every $P\in\mathfrak P$ and $0<q<1/2$ by item 1 of [the marked-array compactification](gaussian_bh_exchangeable_array_variational_compactification.md)), and the finite common-loading supremum $W_\sigma(q)$ of that definition. Put $q_{\max}=\overline\Phi(1)$.

For an integer $n\ge2$, a continuous function $f:[-1,1]^{n(n-1)/2}\to[-1,1]$ of the off-diagonal entries $C^{(n)}=(C_{ll'})_{1\le l<l'\le n}$, and a continuous function $\psi:[-1,1]\to[-1,1]$, define the Ghirlanda-Guerra defect of $P\in\mathfrak P$ by
$$
\Delta_P(n,f,\psi)=\mathbb E_P\!\left[f(C^{(n)})\,\psi(C_{1,n+1})\right]
-\frac1n\,\mathbb E_P\!\left[f(C^{(n)})\right]\mathbb E_P\!\left[\psi(C_{12})\right]
-\frac1n\sum_{l=2}^{n}\mathbb E_P\!\left[f(C^{(n)})\,\psi(C_{1l})\right].
$$
Only the residual correlation entries enter $f$ and $\psi$; the marks $(\theta_i,\ell_i)$ do not.

Fix $0<\sigma<1$ and $0<q\le q_{\max}$. Then there is a sequence $(P_k)_{k\ge1}$ in $\mathfrak P$ such that
$$
\lim_{k\to\infty}\mathcal F(P_k;q,\sigma)=W_\sigma(q),
$$
and, for every integer $n\ge2$ and all continuous $f:[-1,1]^{n(n-1)/2}\to[-1,1]$ and $\psi:[-1,1]\to[-1,1]$,
$$
\lim_{k\to\infty}\Delta_{P_k}(n,f,\psi)=0.
$$
The laws $P_k$ may be outer mixtures, may have unbounded second mean moment $M_2(P_k)$, and may depend on $\sigma$ and $q$. No exact maximizer, no finite support, no positive definiteness, and no ultrametricity is asserted. This lemma asserts no FDR order bound.
