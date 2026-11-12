---
type: theorem
title: >-
  Dimension-free tail bound for a normalized semilogconvex Gaussian density of
  Lehec
status: approved
uses_definitions:
  - lehec2015_semilogconvex_density
source:
  kind: paper
  paper_id: lehec2015_ou_regularization
  location: 'Section 2, Theorem 3 and equation (3), printed/PDF p. 3'
tags:
  - gaussian
  - semilogconvexity
  - normalized_density
  - source_import
---

## Statement

For a [normalized smooth semilogconvex density in Lehec](../definitions/lehec2015_semilogconvex_density.md), there exists a finite universal constant $C>0$, independent of $n,f,\beta,r$, such that for every $r>1$,
$$
\gamma_n\bigl(\{x:f(x)>r\}\bigr)
\leq C\,\frac{\max(\beta,1)}{r\sqrt{\log r}}.
$$
Precisely, $n\geq1$, $f:\mathbb R^n\to(0,\infty)$ is smooth, $\int f\,d\gamma_n=1$, and $\nabla^2\log f(x)\succeq-\beta\operatorname{Id}_n$ for all $x$ with $\beta\geq0$. This is a mathematical paraphrase of the cited Theorem 3, retaining positivity, smoothness, normalization, global Hessian hypothesis, and the factor $\max(\beta,1)$.

## Source and applicability boundary

This is a bound for a single normalized smooth density. Applying it to a frozen-ray supremum would first require its finite Gaussian integral and an admissible normalized smooth density with the required global log-Hessian bound. Neither taking a supremum nor capping at a finite level is an operation authorized by this theorem to preserve those hypotheses. No maximal frozen-ray estimate, sharp truncated-moment coefficient, or BH reduction follows here. The source citation and transcription are draft for fresh independent source verification; no proof is imported.
