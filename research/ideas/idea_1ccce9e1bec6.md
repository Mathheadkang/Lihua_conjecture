---
type: idea
title: Exact covariance-rank boundary below the one-sided square-root-log scale
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - multifactor_radial_fdr_bounds
tags:
  - exact-singularity
  - growing-rank
  - composite-null
  - radial-bound
  - partial-obstruction
---

Draft consequence of the approved finite-level radial bound, not a new asset or an unrestricted proof. It excludes exact low-rank covariance sequences even when their rank diverges and their means are heterogeneous. It is not a claim about small factor dimension with nonzero independent residuals.

Let L=log(1/q), and suppose an admissible Gaussian covariance has exact rank d=d(q) with d log L=o(sqrt L). Factor Sigma=AA^T in R^d. Since Sigma has unit diagonal, every row of A has norm one. Thus T=theta+AZ is a multifactor representation with ZERO independent residual variance, r_i=1 and gamma_i=0 for every true null. The approved multifactor_radial_fdr_bounds explicitly includes this endpoint, arbitrary loading directions, every nonpositive one-sided null mean, and arbitrary alternative means. It yields
$$
FDR^{(1)}\leq q+q\pi_0\{1/2+\Delta_1(d,q)\},\quad
\Delta_1(d,q)=\log[q/\PhiBar(b_d(q))].
$$
Here b_d(q) is the upper-q chi_d radius quantile; d is the actual covariance rank in this factorization.

The needed growing-d quantile estimate can be checked directly. For X~chi_d^2 choose t=(1-1/L)/2 and x=2L+2d log L+4. Its Gaussian mgf gives
$$
\log P(X\geq x)\leq-tx+(d/2)\log L
=-L-(d/2)\log L-1+(d\log L+2)/L\leq-L
$$
for large L, since d log L/L->0. Hence b_d(q)^2<=x. The lower Mills bound PhiBar(b)>=phi(b)b/(b^2+1) then gives
$$
\Delta_1(d,q)\leq-L+b_d(q)^2/2+\tfrac12\log(2\pi)
+\log[(b_d(q)^2+1)/b_d(q)]
\leq d\log L+O(\log L).
$$
The remainder is uniform in this regime because b_d(q)->infinity and b_d(q)^2<=2L+o(L). Therefore FDR^{(1)}=O(q[1+d log L])=o(q sqrt L), uniformly over the dimension N, means theta, and loading geometry satisfying this exact-rank constraint.

The new round3 slot1 failed candidate slow_rank_fourier_boundary uses d~4L^{1/4}, N=6ceil(exp(L^2)) and normalized Fourier rows
a_i=M^{-1/2}(cos alpha_i,sin alpha_i,...,cos M alpha_i,sin M alpha_i),
with M=2floor(L^{1/4})+1, alpha_i=2pi i/N. Fourier orthogonality gives exact rank d=2M and N-d zero eigenvalues. Means alternate between0, -(L+i/N), and +(sqrt L+i/N), preserving strictly negative true nulls and positive alternatives. Its FDR bound is O(q L^{1/4}log L), so NOT fails.

This supplies a rank-growth restriction on a possible counterexample: it cannot lie in a sequence whose exact covariance rank satisfies d log log(1/q)=o(sqrt(log(1/q))). It does not exclude higher rank, small but nonzero residual variances, or the unrestricted Gaussian supremum.
