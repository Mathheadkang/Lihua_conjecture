---
type: candidate
title: >-
  Zero directing vector and empty true numerator at the normalized level
  boundary
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:56:29.475Z'
extension_version: 0.0.4
---

## Object

Fix any sigma in (0,1), and any eta, delta > 0. Let P be the deterministic marked array with theta_i = 1, ell_i = 0, and C_ij = 1{i=j} for every positive integer i,j. Test the boundary where the directing vector is exactly zero and every true numerator is empty. Unlike finite orthogonal-atom approximations, this object is already the diagonal residual array, and the issue tested is the zero-vector/no-true-tag boundary of the directing representation and normalized objective.

Use independent standard normal variables Z,zeta_1,zeta_2,..., independent of the deterministic parameters, and observations T_i = 1 + sqrt(1-sigma^2) zeta_i + sigma Z. The levels for the normalized objective are 0 < q <= q_max = S(1).

## Checks

### H1

Pass. The common loading satisfies 0 < sigma < 1. Every normalized level satisfies 0 < q <= S(1) < 1/2; eta and delta are strictly positive.

### H2

Pass. The positive means with alternative tags belong to the closed lawful mark domain and are also canonical. Every finite residual matrix is the identity: symmetric, positive semidefinite, with diagonal one and entries in [-1,1].

### H3

Pass. Simultaneous finite permutations leave the deterministic marks and identity array unchanged. Thus P is jointly exchangeable. All Gaussian innovations are independent of the parameters. The observation covariance is (1-sigma^2) I + sigma^2 11^T, as prescribed.

### H4

Pass. M_2(P) = E theta_1^2 = 1, so P belongs to the finite-second-moment class used for the penalized and normalized objectives.

### NOT

Fail. The two degeneracies tested do not violate the conclusions. The deterministic directing measure mu = delta_(1,0,0) on R x B_R x {0,1} represents the array exactly: iid draws all have v_i = 0, hence off-diagonal inner products are zero, while the stipulated diagonal remains one. The isonormal term X(0) vanishes and the residual diagonal-correction term is exactly sqrt(1-sigma^2) zeta_i. Its mean moment is integral theta^2 dmu = 1.

For every n, every realization, and every level q, the tagged rejection numerator is zero. Therefore D_n = 0 and F_n(P;q,sigma) = F(P;q,sigma) = 0. In particular the limiting value is continuous in q and obeys the logarithmic upper bound. For this P,

$$
\mathcal L_{\eta,\delta}(P,q;\sigma)=-\eta-\delta\log(1/q).
$$

This expression tends to minus infinity as q decreases to zero and increases strictly with q. Its maximum over the allowed levels is attained at the included endpoint q_max. Thus empty true numerators do not obstruct level coercivity or attainment for this family.

This family also cannot be a global normalized maximizer. A lawful comparator with all means zero, all tags true, and C_ij = 1 has all observations equal to one standard normal variable. Its finite and completed FDR equal q and its moment is zero. At q_max its normalized objective is 1 - delta log(1/q_max), which exceeds this candidate's best value by exactly 1+eta. This comparison uses the all-copy comparator only to exclude the new zero-vector/empty-numerator object as an optimizer; it does not repeat an all-copy counterexample search.

These explicit calculations cover this boundary object only; they do not verify the target for arbitrary arrays.

## Failure

NOT fails: the exact zero-vector directing representation is lawful, and the empty numerator gives an explicitly coercive normalized objective whose endpoint maximum is strictly below a lawful comparator.
