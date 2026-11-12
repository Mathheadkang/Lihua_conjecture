---
type: definition
title: Definition (isotropic spherical directional population)
status: approved
source:
  kind: original
depends_on: []
tags:
  - gaussian_bh
  - spherical_population
  - isotropic_directions
---

## Definition

Let $d\geq4$ be an integer, let $\mathbb S^{d-1}=\{v\in\mathbb R^d:\|v\|_2=1\}$, and let $\sigma_{d-1}$ be the uniform probability measure on $\mathbb S^{d-1}$. Let $W$ be any Borel probability measure on $[0,\infty)$; no bounded-support or moment assumption is imposed. The population of tests has the product probability measure
$$
W(d\mu)\,\sigma_{d-1}(dv).
$$
Here $\mu\geq0$ is an absolute mean. At every absolute mean, directions have the same uniform law: the conditional directional kernel is $\sigma_{d-1}$ for every $\mu$, and is independent of $\mu$. A negative signed mean gives the same two-sided population law by the change $v\mapsto-v$.

Let $Z\sim N(0,I_d)$, where $I_d$ is the $d\times d$ identity matrix. This is the only sampling randomness. For a population index $(\mu,v)$ define
$$
T_{\mu,v}(Z)=\mu+v^\top Z,\qquad
Q(t)=\overline\Phi(t)=\frac{1}{\sqrt{2\pi}}\int_t^\infty e^{-s^2/2}\,ds,
\qquad p_{\mu,v}(Z)=2Q(|T_{\mu,v}(Z)|).
$$
There is zero residual variance: no additional observation noise is present after conditioning on $Z$. The true-null population consists exactly of $\mu=0$ and has mass $\pi_0=W(\{0\})$.

Put $R=\|Z\|_2$. For $r>0$ and $t\in\mathbb R$, define the spherical upper tail
$$
H_r(t)=\sigma_{d-1}\{v\in\mathbb S^{d-1}:rv_1\geq t\},
$$
where $v_1$ is the first coordinate of $v$. Rotational invariance makes $H_r(t)$ the directional upper tail of $v^\top Z$ at any fixed $Z$ of norm $r$. At a Gaussian-statistic cutoff $x\geq0$, the conditional null rejection probability is $2H_r(x)$, and the conditional total rejection mass is
$$
F_r(x)=\int_{[0,\infty)}\{H_r(x-\mu)+H_r(x+\mu)\}\,W(d\mu).
$$
Equivalently, $F_r(x)$ is the population mass with $p_{\mu,v}\leq2Q(x)$. The two tail events overlap only on a directional set of measure zero. The symbol $F_r$ denotes a tail in the Gaussian-statistic coordinate, or a p-value distribution function evaluated at $2Q(x)$; it is not a finite empirical distribution.

This definition specifies a continuous directional population. It does not identify this population with a finite Gaussian test vector or assert a finite-vector approximation.
