---
type: theorem
title: Föllmer drift and entropy-energy identity for finite-entropy Wiener densities
status: draft
source:
  kind: paper
  paper_id: lehec2013_entropy
  location: Theorem 2, Section 2.2, printed pp. 887-888 (PDF pages 3-4)
depends_on: []
uses_definitions: [wiener_path_entropy_drift]
tags: [follmer-process, entropy-energy, finite-entropy, discontinuous-density]
---

## Statement

Let $d$ be a positive integer and use [Wiener entropy and adapted finite-energy drifts](../definitions/wiener_path_entropy_drift.md). If the probability measure $\mu$ on $\mathcal W_d$ satisfies $\mu\ll\gamma_d^{\mathrm W}$ and
$$
\mathsf{Ent}(\mu\mid\gamma_d^{\mathrm W})<\infty,
$$
there is an adapted rate $u$ with $U_t=\int_0^t u_s\,ds$ such that $U\in\mathscr H_d$ almost surely under $\mu$, the process
$$
Y_t=X_t-U_t
$$
is standard Brownian motion under $\mu$ with respect to $(\mathcal G_t)$, and
$$
\frac12\mathbb E_\mu\int_0^\infty\|u_s\|^2\,ds
=\mathsf{Ent}(\mu\mid\gamma_d^{\mathrm W}).
$$
No differentiability or finite Fisher information of $L=d\mu/d\gamma_d^{\mathrm W}$ is assumed. No strong solution on a separately prescribed probability space is asserted.

## Source scope

This is the finite-entropy case of Lehec's Theorem 2; the source states the identity more generally. The published statement and formulas were visually checked on printed pp. 887–888. The source attributes the result to Föllmer and labels its proof a sketch. This node imports the statement; it does not claim a self-contained proof adaptation or approval of the source's cited prerequisites.

For a bounded terminal density, this theorem can supply the finite-entropy drift representation. Identifying that rate with a heat-gradient expression for a discontinuous density still needs its own argument. In particular, the separate regularity assumptions in §2.5 are not silently transferred or discarded. No Gaussian BH trace budget follows from this statement alone.
