---
type: definition
title: Definition (scalar L1 uniform integrability and weak topology in Diestel)
status: approved
source:
  kind: paper
  paper_id: diestel1991_uniform_integrability
  location: >-
    Definition preceding Theorem 1, p. 41; dual pairing preceding Theorem 3's
    proof, p. 46
depends_on: []
tags:
  - functional_analysis
  - uniform_integrability
  - weak_compactness
---

## Definition

Let $(\Omega,\Sigma,P)$ be a probability space. The real space $L_1(P)$ consists of measurable real functions modulo equality $P$-almost everywhere, with norm $\|f\|_1=\int_\Omega|f|\,dP$. Its dual is $L_\infty(P)$, paired by $\langle f,g\rangle=\int_\Omega fg\,dP$; the weak topology is $\sigma(L_1(P),L_\infty(P))$. Relative weak compactness means compactness of the closure in this topology.

A family $K\subset L_1(P)$ is uniformly integrable when
$$
\lim_{c\to\infty}\sup_{f\in K}\int_{\{|f|>c\}}|f|\,dP=0.
$$
It has uniformly absolutely continuous integrals when
$$
\forall\epsilon>0\ \exists\delta>0\ \forall E\in\Sigma:\quad
P(E)\le\delta\ \Longrightarrow\ \sup_{f\in K}\int_E|f|\,dP\le\epsilon.
$$
These are normalized mathematical definitions for the source's real scalar setting. The measure is fixed; no countable-generation, atomlessness or separability assumption is imposed.
