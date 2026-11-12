---
type: definition
title: Definition (Gaussian measure and OU semigroup in Lehec 2015)
status: approved
source:
  kind: paper
  paper_id: lehec2015_ou_regularization
  location: 'Introduction, equation (1), printed/PDF p. 1'
tags:
  - gaussian
  - ornstein_uhlenbeck
  - source_import
---

## Definition

For an integer $n\geq1$, let $\gamma_n$ denote standard Gaussian probability measure on $\mathbb R^n$. For nonnegative measurable $f:\mathbb R^n\to[0,\infty)$ and $t>0$, Lehec writes
$$
Q_t f(x)=\int_{\mathbb R^n}f\!\left(e^{-t}x+\sqrt{1-e^{-2t}}\,y\right)\,\gamma_n(dy).
$$
The integral is understood as a nonnegative integral wherever needed. The kept fixed-time theorem assumes $\int f\,d\gamma_n=1$; it does not restrict $f$ to bounded test functions. The existing project OU convention restricts its test-function domain to $[0,1]$, so this source-specific domain is recorded separately without changing that convention. Natural logarithms are used.
