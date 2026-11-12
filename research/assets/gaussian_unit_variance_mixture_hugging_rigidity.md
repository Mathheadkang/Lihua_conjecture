---
type: lemma
title: Unit-variance Gaussian mixture mean-curve rigidity
status: draft
source:
  kind: original
depends_on: []
uses_definitions: []
tags: []
---

## Statement

Let S and phi be the standard normal survival function and density. Put p(u)=2S(u) for u>=0. For theta in R and epsilon~N(0,1), define
$$
L_\theta(u)=\frac{P(|\theta+\varepsilon|\ge u)}{p(u)}
=\frac{S(u-\theta)+S(u+\theta)}{2S(u)},\qquad
f_\theta(u)=\log L_\theta(u).
$$
All logarithms are natural. The lemma has these two quantitative conclusions.

(i) For every theta in R, f_theta(u)>=0 and f_theta is differentiable on u>=1, with
$$
f_\theta'(u)\ge0,\qquad u f_\theta'(u)\ge f_\theta(u)\quad(u\ge1).
$$
Equivalently, u -> f_theta(u)/u is nondecreasing on [1,infinity). For theta=0 both sides vanish. This states the star-shaped property precisely; it is a draft mathematical claim, not a consequence of the numerical checks alone.

(ii) For EVERY finite integer M>=1, deterministic theta_1,...,theta_M in R and weights w_l>=0 with sum_l w_l<=1, let
$$
\psi(u)=q\sum_{\ell=1}^M w_\ell L_{\theta_\ell}(u),\qquad U=p^{-1}(q)=S^{-1}(q/2).
$$
Suppose 0<q<=2S(3), 0<eta<=1/2 and U<=u_a<u_b satisfy
$$
\psi(u_a)\ge1-\eta,\qquad \psi(u_b)\le1.
$$
Then psi is nondecreasing and
$$
u_b-u_a\le16\,\eta\,u_b/U^2.
$$
In particular, for any r in [0,1] and A>=1 satisfying r u_b<=A U, the tilt interval obeys r(u_b-u_a)<=16 A eta/U. The condition r u_b<=A U is part of this last corollary; no uniform tilt-length bound of order eta/U is asserted without it.

The unit residual variance in L_theta is essential to the scope: the mixture is a deterministic ratio of MEAN counts from N(theta,1) marginals. It is not a realized-count statement, a per-cell return-probability bound, or a claim for factor-conditioned components of variance less than one. The finite weights, means and M may vary with q. This promoted node remains draft and its numerical provenance is not independent proof.
