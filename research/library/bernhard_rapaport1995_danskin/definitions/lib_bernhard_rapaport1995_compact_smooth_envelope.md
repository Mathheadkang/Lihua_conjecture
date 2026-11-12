---
type: definition
title: Definition (compact smooth envelope family in Bernhard and Rapaport)
status: approved
depends_on: []
source:
  kind: paper
  paper_id: bernhard_rapaport1995_danskin
  location: >-
    Introduction, hypotheses preceding Theorem 1, printed p. 1163 (PDF page 1);
    sufficient joint-gradient-continuous specialization
tags:
  - danskin
  - compactness
  - directional_derivative
  - envelope
---

# Definition (compact smooth envelope family in Bernhard and Rapaport)

Let $n\ge1$ be an integer and $V$ a nonempty compact topological space. A compact smooth envelope family here means a map $J:\mathbb R^n\times V\to\mathbb R$ such that the first-variable gradient $\nabla_uJ(u,v)$ exists everywhere, and both $J$ and $\nabla_uJ$ are jointly continuous. The Euclidean inner product is denoted by $\langle\cdot,\cdot\rangle$.

Its envelope and full active set at $u\in\mathbb R^n$ are
$$
\overline J(u)=\max_{v\in V}J(u,v),\qquad
V(u)=\{v\in V:J(u,v)=\overline J(u)\}.
$$
For any scalar function $f$ on $\mathbb R^n$, its right directional derivative at $u$ in direction $h\in\mathbb R^n$, when it exists, means
$$
Df(u;h)=\lim_{t\downarrow0}\frac{f(u+th)-f(u)}{t}.
$$
This is a sufficient smooth specialization of the source's introductory compact theorem. In particular, joint gradient continuity is explicit, rather than silently inferred from separate regularity. No uniqueness of the active point is assumed.
