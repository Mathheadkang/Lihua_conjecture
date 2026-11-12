---
type: lemma
title: Lei integrated conditional Gaussian tail-ratio bounds
status: approved
source:
  kind: paper
  paper_id: lei2026_gaussian_bh
  location: >-
    Section 4.2.1, integrated-tail-ratio-bound display, p. 61; Lemma 4.3, pp.
    62-64; Section 4.3, equations (287)-(289), pp. 88-89
depends_on: []
uses_definitions:
  - gaussian_one_common_factor_model
  - gaussian_test_pvalues
  - conditional_pvalue_distributions
  - lei2026_gaussian_lower_envelopes
tags:
  - gaussian
  - conditional_tail_ratios
  - upper_bounds
  - one_common_factor
  - paper_source
---

## Statement

Take a boundary-null coordinate of the [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md):
$$
X=rZ+\sqrt{1-r^2}\,\varepsilon,\qquad 0\leq r\leq1,
$$
where $Z$ and $\varepsilon$ are independent standard normal variables. Use $\phi,\Phi$ from the [Lei Gaussian BH lower-bound envelopes](../definitions/lei2026_gaussian_lower_envelopes.md) and $\overline\Phi$ from the [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md). Define the [conditional p-value distributions](../definitions/conditional_pvalue_distributions.md)
$$
F^{(1)}_{r,z}(t)=\mathbb P\{\overline\Phi(X)\leq t\mid Z=z\},\qquad F^{(2)}_{r,z}(t)=\mathbb P\{2\overline\Phi(|X|)\leq t\mid Z=z\},
$$
and set $\gamma_r=\sqrt{(1-r)/(1+r)}$.

For the one-sided track, let $0<q<1/2$ and $u=\overline\Phi^{-1}(q)>0$. Then
$$
\int_{-\infty}^{u}\phi(z)\sup_{0<t\leq q}\frac{F^{(1)}_{r,z}(t)}t\,dz\leq\frac12+\frac{\gamma_r u}{\sqrt{2\pi}}.
$$
For the two-sided track, let $0<q\leq2\overline\Phi(1)$ and $u=\overline\Phi^{-1}(q/2)\geq1$. If $r<1$, then
$$
\int_{-u}^{u}\phi(z)\sup_{0<t\leq q}\frac{F^{(2)}_{r,z}(t)}t\,dz\leq\Phi(u/\gamma_r)-\frac12+\frac{\gamma_r u}{\sqrt{2\pi}}\leq\frac12+\frac{\gamma_r u}{\sqrt{2\pi}}.
$$
When $r=1$, both integrals on the left are zero; their endpoints have Gaussian measure zero. Thus the final bound $1/2+\gamma_r u/\sqrt{2\pi}$ remains valid at $r=1$ without division by $\gamma_r$.

## Source proof route

These are the per-null integrated estimates explicitly derived in the cited proofs, retaining the loading-dependent factor before it is bounded by one. For $r<1$, put $s=\sqrt{1-r^2}$. In the one-sided calculation, the source bounds the integrand by
$$
\phi(z)\sup_{0<t\leq q}\frac{F^{(1)}_{r,z}(t)}t\leq\frac1{s\sqrt{2\pi}}\exp\left(-\frac{(ru-z)_+^2}{2s^2}\right),
$$
where $x_+=\max\{x,0\}$. Integration over $z\leq u$ gives $1/2+(1-r)u/(s\sqrt{2\pi})$, and $(1-r)/s=\gamma_r$.

For two-sided p-values, add the two conditional Gaussian tails and integrate over $[-u,u]$ as in the source's integrated-tail-ratio-bound display; it gives $\Phi((1+r)u/s)-1/2+(1-r)u/(s\sqrt{2\pi})$. The identities $(1+r)/s=1/\gamma_r$ and $(1-r)/s=\gamma_r$ yield the statement. At $r=1$ the conditional coordinate is deterministic and the central-region rejection probability is zero except at endpoints.

For a one-sided true-null mean $\theta\leq0$, the source additionally uses the pointwise CDF domination $F^{\theta}_{r,z}(t)\leq F^{(1)}_{r,z}(t)$ (p. 88). Therefore the same one-sided integral bound applies to the actual conditional null CDF. This is a paper-sourced estimate, not a theorem about arbitrary Gaussian covariance matrices or multidimensional factor truncation.
