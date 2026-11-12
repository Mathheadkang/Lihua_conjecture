---
type: definition
title: Definition (Lei Gaussian BH lower-bound envelopes)
status: approved
source:
  kind: paper
  paper_id: lei2026_gaussian_bh
  location: >-
    Section 2.1, equations (3)-(5), p. 5; Section 3.1, equations (140)-(141),
    pp. 42-43; Lemma A.1, pp. 92-93
depends_on:
  - gaussian_test_pvalues
tags:
  - gaussian
  - lower_bounds
  - likelihood_ratio
  - paper_source
---

## Definition

Let $\overline\Phi$ be the survival function in the [Gaussian test p-values and true nulls](gaussian_test_pvalues.md), and set $\Phi(y)=1-\overline\Phi(y)$ and $\phi(y)=(2\pi)^{-1/2}e^{-y^2/2}$. For $a,y\geq0$, put
$$
L_a(y)=e^{-a^2/2}\cosh(ay),\qquad M(y)=\sup_{a\geq0}L_a(y).
$$
For each $q\in(0,1)$, let $y_q>1$ be the unique solution of $qM(y_q)=1$, and define
$$
\ell_{=}(q)=q\Phi(1)+q\int_1^{y_q}M(y)\phi(y)\,dy+\overline\Phi(y_q).
$$
The existence and uniqueness used in this definition are supplied by the source's Lemma A.1: $M=1$ on $[0,1]$ and $M$ is continuous, strictly increasing and unbounded on $(1,\infty)$. The source's maximizer $a(y)>0$ for $y>1$ is characterized by $a(y)=y\tanh(a(y)y)$.

For the one-sided construction, define
$$
y_q^+=\sqrt{2\log(1/q)},\qquad \ell_{\leq}(q)=\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+\frac q2+\overline\Phi(y_q^+).
$$
Here $\log$ is natural logarithm, $\cosh(t)=(e^t+e^{-t})/2$ and $\tanh(t)=(e^t-e^{-t})/(e^t+e^{-t})$. The subscripts distinguish lower-bound functions; they do not change the null definitions.
