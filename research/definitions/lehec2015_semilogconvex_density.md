---
type: definition
title: Definition (normalized smooth semilogconvex density in Lehec 2015)
status: approved
depends_on:
  - lehec2015_gaussian_ou_semigroup
source:
  kind: paper
  paper_id: lehec2015_ou_regularization
  location: 'Section 2, Theorem 3 and equation (3), printed/PDF p. 3'
tags:
  - gaussian
  - semilogconvexity
  - source_import
---

## Definition

For $n\geq1$ and the [Gaussian measure](lehec2015_gaussian_ou_semigroup.md) $\gamma_n$, the retained hypothesis consists of a smooth function $f:\mathbb R^n\to(0,\infty)$ and a real number $\beta\geq0$ such that
$$
\int_{\mathbb R^n} f\,d\gamma_n=1,
\qquad
\nabla^2\log f(x)\succeq-\beta\,\operatorname{Id}_n
\quad\text{for every }x\in\mathbb R^n.
$$
Here $\nabla^2$ is the ordinary spatial Hessian, $\operatorname{Id}_n$ is the identity matrix, and $A\succeq B$ means $A-B$ is positive semidefinite. The title supplies a descriptive name for Theorem 3's displayed hypotheses; the source states those hypotheses directly. No nonsmooth extension or unnormalized maximal function is included.
