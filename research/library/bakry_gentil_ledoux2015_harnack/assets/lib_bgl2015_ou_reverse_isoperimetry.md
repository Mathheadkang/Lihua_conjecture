---
type: proposition
title: Gaussian OU reverse isoperimetry from Bakry-Gentil-Ledoux Proposition 2.1
status: approved
depends_on:
  - lib_bgl2015_gaussian_profile_properties
uses_definitions:
  - lib_bgl2015_gaussian_ou_profile
source:
  kind: paper
  paper_id: bakry_gentil_ledoux2015_harnack
  location: >-
    Author manuscript, Proposition 2.1 equation (16), p. 8; proof and explicit
    gradient consequence, p. 9; OU curvature K=1, p. 2
tags:
  - gaussian
  - ornstein_uhlenbeck
  - reverse_isoperimetry
  - analytic_input
---

## Statement

Use the [Gaussian OU normalization and profile](../definitions/lib_bgl2015_gaussian_ou_profile.md). For every integer $d\geq1$, measurable $h:\mathbb R^d\to[0,1]$, $t>0$, and $x\in\mathbb R^d$, the Gaussian specialization of Proposition 2.1 states
$$
[I(P_th(x))]^2-[P_t(I\circ h)(x)]^2
\geq(e^{2t}-1)\|\nabla P_th(x)\|_2^2.
$$
The ordinary spatial gradient is that of the smoothed Gaussian semigroup. In particular, the explicit gradient consequence on source page 9 specializes to
$$
\|\nabla P_th(x)\|_2\leq\frac{I(P_th(x))}{\sqrt{e^{2t}-1}}.
$$

## Source proof sketch

For functions separated from $0$ and $1$, source pp. 8-9 interpolate $[P_s(I(P_{t-s}h))]^2$, use $II''=-1$ and kernel Cauchy-Schwarz, then apply the gradient commutation $\|\nabla P_sg\|_2\leq e^{-s}P_s(\|\nabla g\|_2)$ to obtain the factor $2\int_0^t e^{2s}ds=e^{2t}-1$. Source page 2 identifies curvature $K=1$ for the Gaussian OU example.

## Verification boundary

The source statement covers arbitrary measurable $[0,1]$-valued functions, but its displayed proof begins with $\varepsilon\leq h\leq1-\varepsilon$ and leaves the approximation step implicit. An independent source check must confirm the Gaussian normalization, ordinary-gradient interpretation and measurable endpoint extension before this node is used as known. No time-integrated gradient estimate or BH-specific budget is asserted in this node.
