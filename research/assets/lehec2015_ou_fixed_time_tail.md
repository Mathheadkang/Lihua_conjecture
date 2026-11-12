---
type: theorem
title: Dimension-free fixed-time Gaussian OU tail bound of Lehec
status: approved
uses_definitions:
  - lehec2015_gaussian_ou_semigroup
source:
  kind: paper
  paper_id: lehec2015_ou_regularization
  location: 'Section 2, Theorem 1, printed/PDF p. 3; normalization equation (1), p. 1'
tags:
  - gaussian
  - ornstein_uhlenbeck
  - fixed_time
  - source_import
---

## Statement

Use the [Gaussian measure and OU semigroup of Lehec](../definitions/lehec2015_gaussian_ou_semigroup.md). There exists a finite universal constant $C>0$ such that for every integer $n\geq1$, every nonnegative measurable $f:\mathbb R^n\to[0,\infty)$ satisfying $\int f\,d\gamma_n=1$, every $t>0$, and every $r>1$,
$$
\gamma_n\bigl(\{x:Q_t f(x)>r\}\bigr)
\leq C\,\frac{\max(1,t^{-1})}{r\sqrt{\log r}}.
$$
This is a mathematical paraphrase of the cited Theorem 1; $C$ is independent of $n,f,t,r$, with the displayed dependence on $t$ retained.

## Source and applicability boundary

The source theorem controls one fixed positive time. It supplies no estimate for a supremum over times, frozen-ray parameter, or data-dependent choice. In particular, it does not supply a normalized input representing a frozen-ray maximal function, nor the sharp truncated-moment coefficient or a BH bridge. Mean-one, integrability, and any smoothing-transfer hypotheses must be checked independently before use. The source citation and transcription are draft for fresh independent source verification; no proof is imported.
