---
type: idea
title: >-
  Tail calibration: the square-root-log scale is a Talagrand-type gain over
  Markov for FDP/q, with a tail-shape diagnostic for search rounds
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
  - lei2026_one_sided_fdr_lower
  - lei2026_two_sided_fdr_lower
  - gaussian_simes_one_sided_uniform_linear_bound
tags:
  - cross-discipline-brainstorm-20261110
  - tail-calibration
  - search-diagnostic
  - gate-screening
  - talagrand-l1-regularization
---

Observation from the cross-disciplinary brainstorm of 10 November 2026. Elementary; the formulas were checked in the chat by direct integration and are not natively verified. Companion of the conjecture idea_9f8ffb204424.

## Three tails

Write $\mathrm{FDP}=q\,\Lambda_{\rm BH}$, so $0\le\Lambda_{\rm BH}\le1/q$ and
$$
\frac{\mathrm{FDR}}{q}=\int_0^{1/q}\mathbb P\{\Lambda_{\rm BH}\ge\lambda\}\,d\lambda .
$$
- Markov scale. A majorant with tail $1/\lambda$ on $[1,1/q]$ integrates to $1+\log(1/q)$. This is the FDR-linking rate. It is attained by free-level relaxations of independent nulls (idea_d353cd54790b, idea_e6e1f4c16f22) and, in the Gaussian-channel picture, by the martingale coupling of the tilt family.
- Half-space scale. Lei's one-sided extremal construction has conditional FDP $q\exp(Z_+^2/2)\wedge1$, tail $\overline\Phi(\sqrt{2\log\lambda})\sim(\lambda\sqrt{4\pi\log\lambda})^{-1}$, integral $\sqrt{\log(1/q)/\pi}+O(1)$. The two-sided construction has $\Lambda_{\rm BH}\approx\tfrac12\exp(Z^2/2)$ on one sign of $Z$, tail $\overline\Phi(\sqrt{2\log(2\lambda)})$, integral $\tfrac12\sqrt{\log(1/q)/\pi}+O(1)$. Both conjectured sharp constants say that the half-space tail (one Gaussian direction) is extremal.
- Nominal scale: tail supported on $\lambda\le C$.

So the current phase asks exactly for this: uniformly over models, $\int_2^{1/q}\mathbb P\{\Lambda_{\rm BH}\ge\lambda\}\,d\lambda\le C\sqrt{\log(1/q)}$, which holds if $\mathbb P\{\Lambda_{\rm BH}\ge\lambda\}\le C/(\lambda\sqrt{\log\lambda})$ on $2\le\lambda\le1/q$. The square-root-log is the same gain over Markov as in Gaussian $L^1$-regularization (Talagrand's convolution conjecture in Gauss space, proved by Eldan-Lee and Lehec for a single regularized density; references in idea_9f8ffb204424).

## Use 1: screening of proposed gates

An intermediate majorant $M\ge\Lambda_{\rm BH}$ whose law can have a Markov tail on a range $[\lambda_0,\lambda_0^{1+\epsilon}]$ with $\lambda_0\to\infty$ cannot prove the target, whatever identity produced it. This single test explains the recorded failures of free empirical-tail envelopes, of capped per-null conditional envelopes under over-revealing conditioning (idea_e3cb787bf90f), and of unrefined linking. A new gate should come with the tail of its majorant in two calibration models: independent nulls (must be nominal) and Lei's one-factor family (must be half-space).

## Use 2: a tail-shape diagnostic for search rounds

For a candidate family at level $q$ define
$$
c(\lambda)=\lambda\sqrt{4\pi\log\lambda}\ \,\mathbb P\{\mathrm{FDP}\ge q\lambda\},\qquad \lambda=2^j,\quad 2\le\lambda\le1/q .
$$
Benchmarks: $c\to1$ for the one-sided extremal one-factor family, $c\to1/2$ for the two-sided one, $c(\lambda)=\sqrt{4\pi\log\lambda}$ for a Markov tail. A genuine counterfamily to the order target must make $\sup_\lambda c(\lambda)$ grow without bound as $q\downarrow0$; a family with bounded $c$ is dominated by one direction up to constants.

Why this is sharper than comparing means: at computable levels ($q$ between $10^{-2}$ and $10^{-4}$) the means $\sqrt{\log(1/q)}$ and $\log(1/q)$ differ by a factor $2$ to $3$ and are masked by additive constants, while a growth of $c(\lambda)$ by the factor $\sqrt{\log\lambda}$ over two or three decades of $\lambda$ is visible. The probabilities involved are of order $q/\sqrt{\log(1/q)}$ at $\lambda=1/q$ and larger below, so plain Monte Carlo with about $10^3/q$ draws gives a few percent; for population (clone) models, sampling the latent Gaussian from a mixture of null-direction shifts keeps the weights bounded (stress-test idea of the same date).

Recommendation: record $c(2^j)$ next to the FDR estimate for every candidate examined in search rounds for the two main targets. For the Simes sub-conjecture $\mathrm{FDP}\in\{0,1\}$ and the diagnostic is the rejection probability as a function of the level.
