---
type: definition
title: Definition (Gram-de Finetti matrix in Panchenko)
status: approved
source:
  kind: paper
  paper_id: panchenko2009_dovbysh_sudakov
  location: 'arXiv:0905.1524v1, Section 1, printed p. 1, opening paragraph'
depends_on: []
tags:
  - exchangeability
  - positive_semidefinite
  - representation
---

# Definition (Gram-de Finetti matrix in Panchenko)

An infinite real random array $R=(R_{ll'})_{l,l'\in\mathbb N}$, with $\mathbb N=\{1,2,\ldots\}$, is a Gram-de Finetti matrix if it is symmetric almost surely, each finite principal submatrix $(R_{ll'})_{1\le l,l'\le n}$ is positive semidefinite almost surely, and it is weakly exchangeable: for every $n\ge1$ and every permutation $\rho$ of $\{1,\ldots,n\}$,
$$
(R_{\rho(l),\rho(l')})_{1\le l,l'\le n}
\overset{d}{=}(R_{ll'})_{1\le l,l'\le n}.
$$
Every entry is a finite real random variable. No boundedness, moment, fixed-diagonal, or strict positive-definiteness condition is included. The paper's phrase “positive definite” uses the nonnegative-definite convention explicitly set in this opening paragraph.
