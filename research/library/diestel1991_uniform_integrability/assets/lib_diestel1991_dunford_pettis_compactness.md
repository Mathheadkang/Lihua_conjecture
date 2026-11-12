---
type: theorem
title: >-
  Dunford-Pettis weak compactness criterion for scalar L1 on an arbitrary
  probability space
status: approved
source:
  kind: paper
  paper_id: diestel1991_uniform_integrability
  location: 'Theorem 3, statement p. 46; proof p. 47 and pp. 47-50 via Theorem 4'
depends_on:
  - lib_diestel1991_ui_absolute_continuity
uses_definitions:
  - lib_diestel1991_scalar_l1_ui_weak_topology
tags:
  - functional_analysis
  - uniform_integrability
  - weak_compactness
---

## Statement

Let $(\Omega,\Sigma,P)$ be an arbitrary fixed probability space and $K\subset L_1(P)$ a family of real scalar functions. In the [scalar L1 weak topology](../definitions/lib_diestel1991_scalar_l1_ui_weak_topology.md),
$$
K\text{ is relatively }\sigma(L_1(P),L_\infty(P))\text{-compact}
\quad\Longleftrightarrow\quad K\text{ is uniformly integrable}.
$$
Thus the closure is compact precisely under this criterion. The theorem concerns the scalar Banach space $L_1(P)$; there is no countable-generation, separability, atomlessness or nonnegativity hypothesis. It does not assert a corresponding theorem for arbitrary Banach-valued $L_1$ functions.

## Proof sketch from the source

The [uniform absolute continuity criterion](lib_diestel1991_ui_absolute_continuity.md) controls every weak-star closure point in $L_\infty(P)^*$ on small measurable sets. Such points are countably additive and $P$-absolutely continuous; Radon-Nikodym identifies them with $L_1(P)$ densities. This gives relative weak compactness. Conversely, extract a weakly convergent subsequence from any proposed obstruction to uniform integrability, subtract its limit, and apply the source's Theorem 4 (Lebesgue-Vitali), proved by a gliding-hump argument on pp. 47-50.

## Source boundary

The complete proof is retained in the untouched source PDF, not reproduced in this sketch. Finitely additive functionals occur only as intermediate ambient closure points and are eliminated by uniform absolute continuity. No finitely additive substitute for an L1 density, product-space cone separation, selector measurability, or Gaussian BH complementarity conclusion is extracted.
