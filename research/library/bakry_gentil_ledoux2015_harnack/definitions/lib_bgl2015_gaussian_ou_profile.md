---
type: definition
definition_kind: convention
title: >-
  Convention (Gaussian OU normalization and isoperimetric profile for
  Bakry-Gentil-Ledoux)
status: approved
depends_on: []
source:
  kind: paper
  paper_id: bakry_gentil_ledoux2015_harnack
  location: >-
    Author manuscript, Gaussian OU curvature example on p. 2; Gaussian profile
    preceding Proposition 2.1 on p. 8
tags:
  - gaussian
  - ornstein_uhlenbeck
  - isoperimetry
  - analytic_input
---

## Definition

For an integer $d\geq1$, let $\gamma_d$ be standard Gaussian probability measure on $\mathbb R^d$. The Gaussian specialization uses the OU generator $L=\Delta-x\cdot\nabla$ and its Markov semigroup, with the explicit normalization
$$
P_th(x)=\int_{\mathbb R^d}h(e^{-t}x+\sqrt{1-e^{-2t}}\,y)\,\gamma_d(dy),\qquad t>0,
$$
for bounded measurable $h$. Spatial gradients and $\|\cdot\|_2$ use the Euclidean structure. This explicit Mehler expression records the convention of the Gaussian specialization; it is not claimed to be a displayed quotation from the cited manuscript.

Set
$$
\varphi(u)=(2\pi)^{-1/2}e^{-u^2/2},\qquad
\Phi(u)=\int_{-\infty}^u\varphi(v)\,dv,
$$
$$
I(p)=\varphi(\Phi^{-1}(p))\quad(0<p<1),\qquad I(0)=I(1)=0.
$$
The letter $I$ denotes this profile, not a null-index set. The source calls the profile density $\varphi$; it agrees with the standard normal density denoted $\phi$ elsewhere in the project. No project node is a dependency of this Library convention.
