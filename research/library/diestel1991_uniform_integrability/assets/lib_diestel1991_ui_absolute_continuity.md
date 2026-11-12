---
type: theorem
title: Uniform integrability and uniform absolute continuity on a probability space
status: approved
source:
  kind: paper
  paper_id: diestel1991_uniform_integrability
  location: 'Theorem 1, statement p. 41, proof pp. 42-43'
depends_on: []
uses_definitions:
  - lib_diestel1991_scalar_l1_ui_weak_topology
tags:
  - functional_analysis
  - uniform_integrability
  - weak_compactness
---

## Statement

On an arbitrary fixed probability space $(\Omega,\Sigma,P)$, a family $K\subset L_1(P)$ is uniformly integrable if and only if it is bounded in $L_1(P)$ and has uniformly absolutely continuous integrals, in the [scalar L1 conventions](../definitions/lib_diestel1991_scalar_l1_ui_weak_topology.md).

No assumption of nonnegativity, separability, atomlessness or countable generation is required. Uniform absolute continuity alone does not replace the boundedness hypothesis.

## Proof

The source splits at level $c>0$:
$$
\int_E|f|\,dP\le cP(E)+\int_{\{|f|>c\}}|f|\,dP.
$$
For a uniformly integrable family, $E=\Omega$ gives boundedness; then choose $c$ to make the second term small and $P(E)$ to control the first. Conversely, if $M=\sup_{f\in K}\|f\|_1<\infty$, Markov's inequality gives $P(|f|>c)\le M/c$. Uniform absolute continuity applied to these sets makes the tail integrals vanish uniformly.

## Source boundary

This is the source's general probability-space theorem. Verifying uniform absolute continuity for a project-specific family remains a separate proof obligation.
