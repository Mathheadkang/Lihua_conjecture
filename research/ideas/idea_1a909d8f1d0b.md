---
type: idea
title: >-
  Replication-invariant Gaussian count variance and a heavy-light mass budget
  for independent carriers
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_simes_one_sided_uniform_linear_bound
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - global-null-simes
  - side-chat-20261112
  - unverified-derivation
---

Suggested by this chat; saved at the researcher's request. Draft derivation, not a verified project theorem. This refines the spectral-count milestone in [the fixed-level proof program](idea_10f14a1fa91d.md).

## Exact weighted identity

Let $T_i=v_i\cdot G$ for finitely many unit vectors $v_i$ and a standard finite-dimensional Gaussian vector $G$. Let deterministic masses $\omega_i>0$ sum to one, and set $\Sigma_{ij}=v_i\cdot v_j$. For $p=\bar\Phi(u)$ and the probabilists' Hermite polynomial $\mathrm{He}_r$ normalized by $\mathbb E\mathrm{He}_r(G_1)^2=r!$, Gaussian Hermite expansion gives
$$
\operatorname{Var}\!\left(\sum_i\omega_i1_{\{T_i\ge u\}}\right)
=\sum_{r\ge1}c_r(u)\,\omega^{\mathsf T}\Sigma^{\circ r}\omega,
\qquad
c_r(u)=\frac{\phi(u)^2\mathrm{He}_{r-1}(u)^2}{r!}.
$$
Here $\phi$ is the standard normal density and $\bar\Phi$ its survival function. Also $\sum_{r\ge1}c_r(u)=p(1-p)$. The identity follows from
$\mathbb E[1_{\{G_1\ge u\}}\mathrm{He}_r(G_1)]=\phi(u)\mathrm{He}_{r-1}(u)$.

Merging identical loading vectors and adding their masses, or splitting an atom into repeated copies with the same total mass, leaves both sides unchanged. This invariance is obscured by an operator-norm bound on the unweighted correlation matrix.

## Independent weighted carriers: elementary budget

For independent uniform p-values $p_i$, define $F(t)=\sum_i\omega_i1_{\{p_i\le t\}}$. The weighted rejection event is the existence of a cumulative mass $s$ at an ordered p-value with $p_i\le qs$. For rational masses this is the ordinary Simes event after exact replication; the same counting argument defines it for all masses.

For dyadic $\kappa_j=2^{-j}$, $j\ge0$, a crossing with cumulative mass $s\in[\kappa_j,2\kappa_j)$ implies $F(2q\kappa_j)\ge\kappa_j$. Treat atoms with $\omega_i\ge\kappa_j$ as heavy. The probability that any heavy atom is active is at most
$2q\kappa_j\#\{i:\omega_i\ge\kappa_j\}$.
If none is active, the light atoms must supply mass at least $\kappa_j$. For $q\le1/4$, their mean is at most $2q\kappa_j\le\kappa_j/2$, and independence gives variance at most
$2q\kappa_j\sum_{\omega_i<\kappa_j}\omega_i^2$.
Chebyshev bounds this light contribution by
$8q\kappa_j^{-1}\sum_{\omega_i<\kappa_j}\omega_i^2$.

The budgets are finite without a minimum atom size:
$$
\sum_{j\ge0}\kappa_j\#\{i:\omega_i\ge\kappa_j\}\le2,
\qquad
\sum_{j\ge0}\kappa_j^{-1}\sum_{\omega_i<\kappa_j}\omega_i^2\le2.
$$
Both follow by summing the geometric series for each atom separately. Thus this elementary argument gives size at most $20q$. The independent/replicated positive-Gaussian case already has a sharper bound from [the positive Gaussian Simes theorem](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md); the point is the explicit mass budget, not novelty or sharpness.

## Missing extension

One would like to treat near-copy Gaussian clusters as heavy atoms and use a variance argument for the remaining light part. No general such contraction with bounded total error has been proved. Cross-cluster dependence prevents simply adding variances. Likewise weak-$L^1$ estimates cannot in general be summed with only the sum of their coefficients: logarithmic losses may appear. Dense signed frames and correlations approaching $\pm1$ are essential tests.
