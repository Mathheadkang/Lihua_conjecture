---
type: definition
title: >-
  Definition (Simes function and global-null uniform p-values in
  Chi-Ramdas-Wang)
status: approved
source:
  kind: paper
  paper_id: chi2024_negative_dependence
  location: >-
    Author manuscript dated 8 May 2024, Section 3.1, printed p. 7, before
    equation (13)
depends_on: []
tags:
  - simes
  - global_null
  - pvalues
---

# Definition (Simes function and global-null uniform p-values in Chi-Ramdas-Wang)

Let $K\ge1$ be an integer. The source denotes by $\mathcal U$ the standard uniform random variables on the underlying probability space, and by $\mathcal U^K$ the random vectors $P=(P_1,\ldots,P_K)$ whose coordinates are each uniform on $[0,1]$. Independence is not required.

For $p=(p_1,\ldots,p_K)\in[0,1]^K$, let $p_{(1)}\le\cdots\le p_{(K)}$ be the order statistics including multiplicities. The Simes function $S_K:[0,1]^K\to[0,1]$ is
$$
S_K(p)=\min_{1\le k\le K}\frac{K}{k}p_{(k)}.
$$
At a fixed level $\alpha\in(0,1)$, the Simes test rejects the global null on the non-strict event $\{S_K(P)\le\alpha\}$. Its type-I error is the probability of that event.
