---
type: definition
definition_kind: convention
title: Convention (finite-dimensional Gaussian Ornstein-Uhlenbeck semigroup)
status: approved
source:
  kind: original
depends_on: []
tags:
  - gaussian_bh
  - ornstein_uhlenbeck
  - signed_response
---

## Definition

For an integer $d\geq1$, let $\gamma_d$ be the standard Gaussian probability measure on $\mathbb R^d$, with independent vectors $G,G'\sim\gamma_d$. For a measurable function $h:\mathbb R^d\to[0,1]$ and $t>0$, the normalization used here is
$$
T_t h(x)=\mathbb E[h(e^{-t}x+\sqrt{1-e^{-2t}}\,G')].
$$
Write $m_h=\int h\,d\gamma_d$. When the ordinary spatial gradient is defined, write
$$
J(h)=\int_0^\infty\int_{\mathbb R^d}\|\nabla T_t h(x)\|_2\,d\gamma_d(x)\,dt,
$$
with the nonnegative integral allowed to be $+\infty$ pending a result establishing finiteness. All spatial norms are Euclidean. Define
$$
\phi(x)=(2\pi)^{-1/2}e^{-x^2/2},\qquad
\Phi(x)=\int_{-\infty}^x\phi(y)\,dy,\qquad
I(p)=\phi(\Phi^{-1}(p))\quad(0<p<1),
$$
and set $I(0)=I(1)=0$. For $s>0$, $\varphi_s(x)=s^{-1}\phi(x/s)$ denotes the centered one-dimensional Gaussian density with standard deviation $s$. This convention fixes notation only; no gradient estimate, finiteness result, or BH-specific bound is assumed.
