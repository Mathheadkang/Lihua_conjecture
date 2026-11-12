---
type: idea
title: >-
  Preserve BH ranks through Gaussian regression and clipped reciprocal-rank
  boundary jumps
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - gaussian-bh
  - common-cutoff
  - gaussian-regression
  - boundary-geometry
  - unproved-reduction
---

Proposed route, with an exact deterministic identity and an explicitly unproved Gaussian estimate. It addresses the loss of the common cutoff exposed by idea_e3cb787bf90f; it is not a proof of either target.

Fix q in (0,1/2), m and a=q/m. For null coordinate i write the centered standardized Gaussian vector as G_{-i}=rho_i G_i+W_i, where rho_i=Sigma_{-i,i} and W_i is independent of G_i with covariance Sigma_{-i,-i}-rho_i rho_i^T. Singular covariance is allowed. There is no assertion that the components of W_i are independent. For a fixed residual realization w and u in (0,1), put G_i=barPhi^{-1}(u) and let r_i(u,w) be the ordinary BH count after replacing p_i by zero and evaluating every other statistic at theta_j+rho_{ij}barPhi^{-1}(u)+w_j. This count is in {1,...,m} and has finitely many jumps: each other p-value crosses each BH grid level only finitely many times.

For any such finite step function r, let u_j be its jump locations and r_j^- and r_j^+ its left and right values. Integrating the derivative of H(u)=min{u/r(u),a} separately on every constant-r interval gives the exact identity
$$
\int_0^1\frac{\mathbf1\{u\leq ar(u)\}}{r(u)}\,du
=a-\sum_j\left[\min\{u_j/r_j^+,a\}-\min\{u_j/r_j^-,a\}\right].
$$
Indeed H(0+)=0, H(1-)=a, and away from jumps H'(u)=1{u<ar(u)}/r(u). Values at isolated ties do not affect the integral. Define the nonnegative harmful-jump functional
$$
D(r)=\sum_{j:r_j^+>r_j^-}\left[\min\{u_j/r_j^-,a\}-\min\{u_j/r_j^+,a\}\right].
$$
Then the integral is at most a+D(r). Using the pointwise BH leave-one-out identity, a zero-mean one-sided null has contribution exactly E_W of the integral for r_i. For a negative true-null mean theta_i<=0, its actual p-value at G_i=barPhi^{-1}(u) is at least u, giving an upper bound by the same integral with its unchanged r_i. Consequently
$$
\operatorname{FDR}^{(1)}\leq\frac{m_0q}{m}+\sum_{i\in I_0^{(1)}}\mathbb E D(r_i(\cdot,W_i)).
$$
For two-sided true nulls, use G_i=sigma barPhi^{-1}(u/2), sigma in {-1,1}; the sign is independent of the Uniform(0,1) two-sided p-value. Define r_i^sigma by this regression branch. The same formula gives the bound with D_i=(D(r_i^+)+D(r_i^-))/2.

This keeps each exact leave-one-out BH rank as a function of the null coordinate, rather than maximizing each conditional cdf over unrelated thresholds. In the independent Gaussian model all slopes rho_{ij} vanish and D=0, recovering FDR<=q; equality holds for all zero-mean nulls. With all one-sided slopes nonnegative, r is nonincreasing in u and again D=0. Thus the route correctly retains cancellation which the capped per-null envelope loses.

The exact missing sufficient Gaussian lemma is: uniformly over all dimensions, admissible covariance matrices and mean vectors, for the functionals just defined,
$$
\limsup_{q\downarrow0}\sup_{m,\theta,\Sigma}\frac{\sum_{i\in I_0^{(1)}}\mathbb E D(r_i)}{q\sqrt{\log(1/q)}}\leq\frac1{\sqrt\pi},
$$
and analogously the sign-averaged two-sided sum is at most 1/(2sqrt(pi)) in this normalization. Since m_0q/m<=q is lower order, these estimates would imply the respective target upper bounds. This positive-jump estimate is unproved and stronger than the FDR bound: it discards favorable downward-rank jumps. Its truth must be checked rather than assumed. If it fails, the exact signed-jump identity remains available and identifies the cancellation that a weaker Gaussian boundary estimate must preserve. The Gaussian Gram-matrix constraints, not marginal tail bounds alone, must control the aggregate boundary contributions.
