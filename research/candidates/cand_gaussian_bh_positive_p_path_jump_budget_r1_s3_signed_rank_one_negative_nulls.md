---
type: candidate
title: >-
  Signed rank-one all-null families with arbitrary negative means have no
  positive jump charge
status: failed
target_asset: gaussian_bh_positive_p_path_jump_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:26:24.010Z'
extension_version: 0.0.4
---

## Object

For arbitrary finite integer N >= 1, choose signs s_j in {-1,1}, arbitrary real means theta_j <= 0, and 0 < q <= S(1). Set Sigma = s s^T and Z_j = s_j X for a single standard normal X. Allow every parameter to vary along a family, including unbounded dimension and arbitrarily negative means. Use the original one-sided Gaussian p-values and actual ordinary BH on all N coordinates. Every coordinate is a true null. This extends the antipodal clone calibration by allowing different, strictly negative means within each sign group.

## Checks

### H1

pass. Each model has a positive finite integer N; no dimension bound is imposed on the family.

### H2

pass. All means are real and nonpositive, hence I_0 = [N]. Strictly negative means are retained as nulls.

### H3

pass. Sigma is symmetric, its diagonal is one, and x^T Sigma x = (s^T x)^2 >= 0. The exactly jointly Gaussian vector Z = s X has this singular covariance.

### H4

pass. The testing level satisfies 0 < q <= S(1) as required.

### H5

pass. For any selected null i, rho_ij = s_i s_j and xi_j = Z_j - rho_ij Z_i = 0. Consequently the full original conditional path is

$$
T_j^i(t)=\begin{cases}
u(t)+\theta_j-\theta_i,&s_j=s_i,\\
\theta_j+\theta_i-u(t),&s_j=-s_i.
\end{cases}
$$

No coordinate or label is omitted. For 0 < t < q, u(t) > 1. Every opposite-sign coordinate has T_j^i(t) <= -u(t) < 0, whereas every ordinary-BH score threshold u(qk/N) is at least u(q) >= 1. Thus opposite-sign coordinates never satisfy a BH threshold. Every same-sign coordinate decreases as t increases. At each rank k, the number of coordinates meeting the non-strict threshold is therefore nonincreasing in t. The set of qualifying ranks can only shrink, so its actual largest member R_i(t) is nonincreasing. This also covers ties, multiplicities, and simultaneous crossings.

### NOT

fail. Since R_i(t) is nonincreasing, A_i(t) is nondecreasing. Indeed, on any positive-rank interval it equals min{Nt/(qR_i(t)),1}, whose numerator increases while its denominator cannot increase; a transition to rank zero sets it to one. In particular every actual net jump satisfies A_i(t^-) <= A_i(t^+). With the exact original negative-null weight

$$
g_i(t)=\exp\{\theta_i u(t)-\theta_i^2/2\},
$$

all positive-part charges vanish identically: B_i = 0. Hence every member of this unrestricted rank-one all-null family has normalized budget zero, regardless of dimension, signs, or the sizes of negative means. This family cannot yield the required unbounded normalized budget.

## Failure

NOT fails: every actual conditional A_i path is nondecreasing and every B_i is exactly zero, including heterogeneous negative null means.
