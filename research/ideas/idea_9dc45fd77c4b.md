---
type: idea
title: >-
  A single positive-measure convex hinge acceptance region suffices for the
  uniform Gaussian Simes bound
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_simes_one_sided_uniform_linear_bound
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - global-null-simes
  - side-chat-20261112
  - unverified-derivation
---

Suggested by this chat; saved at the researcher's request. Draft reduction, not a verified result. It sharpens the target in [the original hinge observation](idea_e1c816206945.md) and [the fixed-level proof program](idea_10f14a1fa91d.md).

## Definitions and subset geometry

Let $T=(T_1,\ldots,T_N)$ be centered jointly Gaussian with unit marginal variances. Let $\phi$ be the standard Gaussian density, $\bar\Phi$ its survival function, $h=\phi/\bar\Phi$, and
$$
\psi(x)=\mathbb E(G-x)_+=\phi(x)-x\bar\Phi(x),\qquad
X(x)=N^{-1}\sum_i(T_i-x)_+,\qquad
R_*=\sup_{x\ge0}X(x)/\psi(x).
$$
Here $G$ is a scalar standard normal and $y_+=\max(y,0)$.

For each $a\ge2$ and every nonempty subset $I$ with $\kappa=|I|/N$, optimizing
$x+(a/\kappa)\psi(x)$ over $x\ge0$ gives its minimum at
$x=\bar\Phi^{-1}(\kappa/a)$, since $\psi'(x)=-\bar\Phi(x)$.
The minimum is $h(\bar\Phi^{-1}(\kappa/a))$.
Also $X(x)$ is the maximum over subsets (including the empty subset) of $N^{-1}\sum_{i\in I}(T_i-x)$. Consequently
$$
\{R_*\le a\}
=
\bigcap_{\varnothing\ne I\subseteq[N]}
\left\{
\frac1{|I|}\sum_{i\in I}T_i
\le h\!\left(\bar\Phi^{-1}\!\frac{|I|}{aN}\right)
\right\}.
$$
Thus hinge acceptance is an explicit convex polyhedron in the finite Gaussian vector. This identity is exact and accommodates ties and singular covariance.

## Weaker sufficient target

The existing hinge calculation proposes a universal $c>0$ and a sufficiently small universal level range such that Simes rejection $E_q$ implies $R_*\ge c\sqrt{\log(1/q)}$. Its hazard/Mills estimates still need native formal verification.

Assuming that reduction, it suffices to find any universal finite $A\ge2$ and $\delta>0$ with $\Pr(R_*\le A)\ge\delta$ for every finite Gaussian model. Choose one small $\alpha_0$ with $c\sqrt{\log(1/\alpha_0)}>A$. Then $\Pr(E_{\alpha_0})\le1-\delta$, and [independent-block amplification](idea_7d0a17e5c13c.md) gives the desired linear small-level bound. Uniform tightness of $R_*$ is sufficient but stronger; a $C/a$ rate and a sum of individual dyadic-scale probabilities are not needed.

## Reverse comparison and remaining difficulty

Set $F(t)=N^{-1}\#\{i:T_i>t\}$. Layer cake gives
$X(x)=\int_x^\infty F(t)\,dt$ and $\psi(x)=\int_x^\infty\bar\Phi(t)\,dt$.
If $X(x)>a\psi(x)$ then some $t\ge x$ has $F(t)>a\bar\Phi(t)$, which implies a Simes crossing at level $1/a$. Therefore $\{R_*>a\}\subseteq E_{1/a}$. The hinge condition remains closely related to the original problem; changing its form does not solve the collective geometry.

Writing the polyhedron as $\{H_a\le0\}$ for the maximum of its affine constraint violations suggests Gaussian convexity tools. However a universal condition $\mathbb EH_A\le0$ is too strong and is defeated by [the clones-plus-independents countercheck](idea_b57684f6c514.md). A positive acceptance or median estimate, rather than that expectation inequality, is the live target. Straightforward Gaussian correlation products over all scales also fail to provide a dimension-uniform positive lower bound.
