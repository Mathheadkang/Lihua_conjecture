---
type: idea
title: OU orbit and envelope equation for frozen-ray Gaussian mixtures
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
tags:
  - ou-semigroup
  - frozen-ray
  - envelope-equation
  - unproved-global-gate
---

A candidate analytic mechanism, not an approved result or a BH certificate. Let G~N(0,I_d), let v_1,...,v_n be deterministic unit vectors, and let w_i>=0 sum to one. Write z_i=<v_i,x>,
$$
f_a(x)=\sum_i w_i\exp(a z_i-a^2/2),\quad a\ge0,\qquad
\Lambda(x)=\sup_{a\ge0}f_a(x).
$$
Mehler's formula gives the exact orbit identity, for every fixed A>0,
$$
P_t f_A(x)=f_{Ae^{-t}}(x),\qquad
\sup_{0\le a\le A}f_a(x)=\sup_{t\ge0}P_t f_A(x).
$$
Thus the dimension-free late-scale problem can be viewed as a maximal OU problem for this restricted, positive log-convex likelihood class; it is not a martingale in the frozen x variable.

There is also an explicit envelope equation. For L=Delta-x.grad one has
$$
L f_a=-a\,\partial_a f_a.
$$
At a point where the maximizing a=a_*(x)>0 is unique, smooth and strict, define posterior weights
$$
p_i=\frac{w_i e^{a_* z_i-a_*^2/2}}{f_{a_*}(x)},\quad
m=\sum_i p_i v_i,\quad
C=\sum_i p_i(v_i-m)(v_i-m)^T.
$$
Stationarity gives <m,x>=a_*, and strictness gives x^T C x<1. Direct envelope differentiation then yields
$$
\frac{L\Lambda}{\Lambda}
=\frac{\|m+a_*Cx\|^2}{1-x^TCx}.
$$
This is a local formula under the stated regularity/uniqueness hypotheses. On switching sets the envelope can have additional distributional curvature; on interior a_*=0 regions Lambda=1. Nothing here controls those contributions uniformly.

First unproved gate: obtain a level-set/flux estimate for this explicit nonnegative curvature that remains uniform as x^TCx approaches one and as maximizing branches switch. Simply bounding the denominator away from zero would impose an unauthorized restriction. A successful estimate would have to yield the proposed tail order 1/[alpha sqrt(log alpha)] (or a directly sufficient sharp truncated-moment estimate) uniformly in A,n,d,weights and correlations, and justify A->infinity. A generic L1 maximal inequality or a one-time Gaussian anti-concentration theorem is not assumed to provide this stronger maximal assertion. The ordinary BH link is still separate.

Possible literature search vocabulary: Gaussian log-convex anti-concentration, diffusion regularization, maximal OU operators. No external theorem is cited or claimed verified in this note.
