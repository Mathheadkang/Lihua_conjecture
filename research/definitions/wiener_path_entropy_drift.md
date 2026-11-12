---
type: definition
title: Definition (Wiener entropy and adapted finite-energy drifts)
status: draft
source:
  kind: paper
  paper_id: lehec2013_entropy
  location: Section 2, printed p. 886, and Section 2.2, printed pp. 887-888
depends_on: []
tags: [wiener-space, relative-entropy, adapted-drift]
---

## Definition

For a positive integer $d$, let $\mathcal W_d$ be the space of continuous functions $w:[0,\infty)\to\mathbb R^d$ with $w(0)=0$, equipped with the Borel sigma-field for uniform convergence on compact time intervals. Write $\gamma_d^{\mathrm W}$ for standard $d$-dimensional Wiener probability measure, $X_t(w)=w(t)$ for its canonical process, and $\mathcal G_t=\sigma(X_s:0\le s\le t)$ for its natural filtration. Brownian motions here are standard and start at zero.

For a probability measure $\mu\ll\gamma_d^{\mathrm W}$ with density $L=d\mu/d\gamma_d^{\mathrm W}$, define its relative entropy by
$$
\mathsf{Ent}(\mu\mid\gamma_d^{\mathrm W})
=\int_{\mathcal W_d} L\log L\,d\gamma_d^{\mathrm W},
$$
with $0\log0=0$ and natural logarithms. Set the entropy to $+\infty$ without absolute continuity.

The Cameron–Martin space $\mathscr H_d$ consists of paths $U$ of the form
$$
U_t=\int_0^t u_s\,ds,\qquad
\|U\|_{\mathscr H_d}^2=\int_0^\infty\|u_s\|^2\,ds<\infty.
$$
An adapted drift under a path measure $\mu$ has a jointly measurable, $\mathcal G_t$-adapted rate $u_t\in\mathbb R^d$ and an integral path $U$ belonging to $\mathscr H_d$ for $\mu$-almost every path. Its expected energy is $\mathbb E_\mu\|U\|_{\mathscr H_d}^2$, possibly infinite unless a result states otherwise. The norm on $\mathbb R^d$ is Euclidean.

## Notation qualification

The superscript $\mathrm W$ distinguishes Wiener measure from a terminal Gaussian measure. The symbols $\mathsf{Ent}$, $\mathscr H_d$ and $L$ rename the source's entropy, Cameron–Martin space and density, respectively, to distinguish them from the Mills-field notation used elsewhere in this project.
