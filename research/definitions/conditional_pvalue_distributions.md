---
type: definition
title: Definition (conditional p-value distributions and independence)
status: approved
source:
  kind: paper
  paper_id: lei2026_gaussian_bh
  location: 'Section 4.1 immediately before Lemma 4.1, p. 59'
depends_on: []
tags:
  - conditional_independence
  - p_values
  - paper_source
---

## Definition

Let $P_1,\ldots,P_m\in[0,1]$ be random p-values, let $Z$ be a real random variable, and fix a true-null index set $\mathcal H_0\subseteq\{1,\ldots,m\}$. A regular conditional CDF for coordinate $i$ is
$$
F_{i,z}(t)=\mathbb P(P_i\leq t\mid Z=z),\qquad 0\leq t\leq1.
$$
Conditional independence given $Z$ means that, for almost every $z$, the joint conditional distribution of $(P_1,\ldots,P_m)$ given $Z=z$ is the product of its coordinate conditional distributions. Equivalently, for Borel sets $B_i\subseteq[0,1]$,
$$
\mathbb P(P_1\in B_1,\ldots,P_m\in B_m\mid Z)=\prod_{i=1}^m\mathbb P(P_i\in B_i\mid Z)
$$
almost surely. Degenerate conditional coordinate distributions are permitted. Conditional superuniformity is not part of this definition.
