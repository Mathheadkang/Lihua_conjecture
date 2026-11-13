---
type: lemma
title: Downward-variation budget for sparse Simes crossings along the Schur-square path
status: draft
source:
  kind: original
depends_on: []
related_assets:
  - gaussian_simes_sparse_crossing_fixed_level_cap
  - gaussian_simes_dense_crossing_tilt_bound
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - simes
  - global_null
  - one_sided
  - sparse_crossings
  - schur_square_path
---

# Downward-variation budget for sparse Simes crossings along the Schur-square path

## Statement

There exist universal constants $q_V\in(0,1/4]$ and $\eta\in(0,1)$ such that the following holds. Let $N$ be a positive integer and $\Sigma=(\rho_{ij})\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), singular matrices allowed. Write $\Sigma\circ\Sigma=(\rho_{ij}^2)$ for the entrywise (Schur) square and, for $t\in[0,1]$,
$$
R_t^\Sigma=(1-t)\Sigma+t\,(\Sigma\circ\Sigma).
$$
By the Schur product theorem $\Sigma\circ\Sigma\in\mathcal C_N$, so $R_t^\Sigma\in\mathcal C_N$ for every $t$. For $q\in(0,1)$ put $u_q=\overline\Phi^{-1}(q)$ and define the sparse-crossing set
$$
S_q=\Bigl\{x\in\mathbb R^N:\ \exists k\in\{1,\ldots,N\}:\ \frac{qk}{N}<\overline\Phi(u_q+1)\ \text{ and }\ \#\Bigl\{i\in\{1,\ldots,N\}:\overline\Phi(x_i)\le\frac{qk}{N}\Bigr\}\ge k\Bigr\},
$$
so that $\{T\in S_q\}$ is the sparse-crossing event for the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(T_i)$, with non-strict comparisons in the count. Let
$$
f_{q,\Sigma}(t)=\mathbb P_{N,0,R_t^\Sigma}(T\in S_q),\qquad 0\le t\le1,
$$
and define the downward variation of a real function $f$ on $[0,1]$ by
$$
\mathcal V_-(f)=\sup_{0=t_0<t_1<\cdots<t_m=1}\ \sum_{\ell=1}^m\bigl[f(t_{\ell-1})-f(t_\ell)\bigr]_+,\qquad a_+=\max(a,0),
$$
the supremum over all finite partitions; no continuity or absolute continuity of $f$ is assumed. Then for every $q\in(0,q_V]$, every $N\ge1$ and every $\Sigma\in\mathcal C_N$,
$$
\mathcal V_-(f_{q,\Sigma})\le1-\eta .
$$
The constants $q_V$ and $\eta$ do not depend on $N$, $\Sigma$, $q$, the signs of the correlations, or the rank of $\Sigma$.

## Motivation

This is the sparse-crossing form of the downward-variation assertion (SV) of the [Schur-square tensor-lift idea](../ideas/idea_6b48b2fe25e1.md), recorded as a separate, precisely quantified variant as that idea requests. It differs from (SV) in two ways. First, it concerns only the sparse part $S_q$ of the Simes event: the complementary dense part is already paid at order $q$ under every correlation by the approved [dense-crossing tilt bound](gaussian_simes_dense_crossing_tilt_bound.md), which applies at every point $R_t^\Sigma$ of the path. Second, its budget is any constant $1-\eta<1$ rather than $1/2$, which is all the approved [fixed-level amplification](gaussian_simes_fixed_level_amplification.md) needs. Neither form implies the other: the variation of the probability of a sub-event is not controlled by that of the whole event.

At $t=1$ the path reaches a matrix with nonnegative entries, where the [positive-Gaussian Simes theorem](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) gives $f_{q,\Sigma}(1)\le q$, because $S_q$ is contained in the full Simes event. Hence this lemma implies $\mathbb P_{N,0,\Sigma}(S_q)\le q+1-\eta$, the conclusion of the open [fixed-level sparse-crossing cap](gaussian_simes_sparse_crossing_fixed_level_cap.md) after shrinking the level, which is the shared crux of the earlier routes.

Structure available for a proof, none of it proved here:

- $S_q$ is an up-set in $x$, the union over the sparse ranks $k$ of the up-sets $\{\#\{i:\overline\Phi(x_i)\le qk/N\}\ge k\}$. The leave-two-out three-face reduction of [idea_ec681eb191fb](../ideas/idea_ec681eb191fb.md), with the ranks restricted to the sparse ranks, gives a Price formula $f'_{q,\Sigma}(t)=\sum_{i<j}\Delta_{ij}J_{ij,t}$ for positive-definite $\Sigma$, with $\Delta_{ij}=\rho_{ij}^2-\rho_{ij}=-\rho_{ij}(1-\rho_{ij})$. Every corner threshold then satisfies $x>y\ge\overline\Phi^{-1}(qk/N)>u_q+1$, so the corners lie strictly above the dense window. The pair terms must be summed with their signs, and with the actual factors $\rho_{ij}(1-\rho_{ij})$, before the positive part is taken.
- Along the path, a nonnegative entry stays at least $\rho_{ij}^2\ge0$; a negative entry $\rho_{ij}<0$ changes sign exactly at $t=1/(1-\rho_{ij})\in[1/2,1)$; and every entry satisfies $(R_t^\Sigma)_{ij}\ge-(1-t)^2/(4t)$ for $t\in(0,1]$. So the positive classes of $R_t^\Sigma$ only grow with $t$ and the negative part contracts uniformly.
- The path commutes with block-diagonal decompositions and keeps exact positive clones tied with their multiplicities, so it is compatible with the independent-block structure used by the amplification lemma.
- For singular $\Sigma$, regularize with $\Sigma^\varepsilon=(1-\varepsilon)\Sigma+\varepsilon I$, prove the bound uniformly in $\varepsilon$, and pass to the limit: for fixed $N$ the boundary of $S_q$ lies in finitely many coordinate hyperplanes $\{x_i=c\}$, each of probability zero, so $f_{q,\Sigma^\varepsilon}\to f_{q,\Sigma}$ pointwise, and $\mathcal V_-$ is lower semicontinuous under pointwise convergence.

The [partial variation calculations](../ideas/idea_a0805e98f90d.md) (two exact clone groups, signed rank one, all trivariate models) are draft side-chat observations for the full Simes event; they would need re-derivation for $S_q$ and independent checking before use. The main expected obstruction is the same as for (SV): many narrow oscillations of $f_{q,\Sigma}$ in $t$ when the number of distinct Gaussian directions grows.
