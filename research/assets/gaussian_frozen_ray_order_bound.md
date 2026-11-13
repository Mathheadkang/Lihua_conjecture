---
title: Frozen-ray maximal likelihood-ratio order bound with subprobability weights
type: lemma
status: draft
source:
  kind: original
  note: >-
    Route lemma of the researcher-selected route "frozen-ray maximal inequality
    via stopped density martingales, then transfer to BH" (idea_bc183ea2b6fa,
    write-up idea_2bb31516b09b). Its content is the order assertion of the
    approved conjecture statement gaussian_frozen_ray_maximal_likelihood_ratio_conjecture,
    with subprobability weights; the sharp and maximal-tail assertions of that
    statement are not part of this lemma.
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
related_assets:
  - gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
tags:
  - frozen-ray
  - route-lemma
---

# Frozen-ray maximal likelihood-ratio order bound with subprobability weights

## Statement

There is a universal finite constant $C_{\mathrm{FR}}>0$ with the following property. Let $n\geq1$ be an integer, let $\Sigma\in\mathcal C_n$ be any correlation matrix of the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) (symmetric, positive semidefinite, unit diagonal; singular matrices and correlations of either sign allowed), and let $Z=(Z_1,\ldots,Z_n)\sim\mathcal N_n(0,\Sigma)$. Let $\omega_1,\ldots,\omega_n$ be deterministic weights with $\omega_i\geq0$ and $\sum_{i=1}^n\omega_i\leq1$. For real $w\geq0$ put
$$
L_w(Z)=\sum_{i=1}^n\omega_i\exp\!\left(wZ_i-\frac{w^2}{2}\right),\qquad
\Lambda(Z)=\sup_{w\geq0}L_w(Z),
$$
with the same realization of $Z$ for every $w$. Then, for every real $c\geq2$,
$$
\mathbb E\min\{c,\Lambda(Z)\}\leq C_{\mathrm{FR}}\sqrt{\log c}.
$$
The logarithm is natural. The constant $C_{\mathrm{FR}}$ is independent of $n$, $\Sigma$, its rank, the weights, their total mass and $c$.

## Motivation

For weights summing to one this is exactly the order assertion of [the frozen-ray maximal likelihood-ratio statement](gaussian_frozen_ray_maximal_likelihood_ratio_conjecture.md); a total mass $\beta\in(0,1]$ only multiplies $\Lambda$ by $\beta$, and $\min\{c,\beta x\}\leq\min\{c,x\}$. The intended proof is the stopped density-martingale argument of idea_2bb31516b09b: one stopping time controlling the whole family $(L_w)_{w\geq0}$, with the dimension-free $L^1$-regularization tail for the Ornstein-Uhlenbeck semigroup (Gaussian case of Talagrand's convolution conjecture: Eldan-Lee, Lehec) as the external input. That input is available as the approved results [lehec2015_ou_fixed_time_tail](lehec2015_ou_fixed_time_tail.md) and [lehec2015_semilogconvex_density_tail](lehec2015_semilogconvex_density_tail.md). It controls one fixed $w$ only; the supremum over $w$ is the content of this lemma.
