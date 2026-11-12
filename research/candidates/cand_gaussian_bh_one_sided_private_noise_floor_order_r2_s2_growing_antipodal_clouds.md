---
type: candidate
title: Growing antipodal Gaussian clouds with a fixed interior private-noise floor
status: failed
target_asset: gaussian_bh_one_sided_private_noise_floor_order
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:19:23.549Z'
extension_version: 0.0.4
---

## Object

For integers n >= 2, set q_n = exp(-n), m_n = ceil(exp(n^2)), N_n = 2m_n, d = 1, and s_0 = 1/2. All means are zero. The first m_n loading rows equal sqrt(3)/2 and the remaining m_n equal -sqrt(3)/2. Set every private standard deviation to 1/2. Use independent standard normal G and epsilon_1,...,epsilon_{N_n}, and apply the specified ordinary BH rule to p_i = barPhi(T_i) at q_n.

The number of tests grows faster than every fixed power of 1/q_n. Null coordinates in opposite clouds have correlation -3/4; coordinates within a cloud have correlation 3/4. Thus this is an interior-loading, growing-dimension family, rather than the full-private-noise or bounded-N families on the board.

## Checks

### H1

The floor s_0 = 1/2 is fixed independently of n and belongs to (0,1].

### H2

N_n and d are positive integers, theta is the zero vector in R^{N_n}, and A has the prescribed N_n by 1 dimensions.

### H3

D = (1/2)I has nonnegative diagonal entries.

### H4

Every row satisfies ||a_i||^2 + s_i^2 = 3/4 + 1/4 = 1.

### H5

Every coordinate is a true null and its private standard deviation equals the fixed floor 1/2.

### H6

The displayed independent standard normals give exactly T = AG + D epsilon and covariance AA^T + D^2, with unit marginal variances.

### H7

All theta_i are zero, so the specified one-sided p-values are marginally uniform and every hypothesis belongs to I_0^{(1)}(theta).

### H8

The levels q_n belong to (0,1) and tend to zero. BH uses the largest qualifying rank, non-strict inequalities, and all 2m_n tests.

### NOT

This check fails: the FDR is at most 2q_n, uniformly in m_n. Here is a direct justification, including the within-cloud bound.

Fix one cloud of m tests and apply ordinary BH at level q; write K for its rejection count. Its Gaussian correlations are all 3/4. Conditional on T_i = x, every other coordinate has mean (3/4)x and the residual Gaussian law does not depend on x. Consequently, for each integer r, the conditional probability of the increasing event {K >= r} is nondecreasing in x. Equivalently, its conditional probability given p_i = u is nonincreasing in u. Since p_i is uniform, the functions

$$
F_r(t) = P(K >= r \mid p_i <= t)
$$

are nonincreasing in t. Set F_{m+1} identically zero and t_r = qr/m. Ordinary BH self-consistency gives, for each i,

$$
E\left[\frac{1\{i\text{ rejected}\}}{K\vee1}\right]
=\sum_{r=1}^m\frac{P(p_i<=t_r,K=r)}r
=\frac qm\sum_{r=1}^m\{F_r(t_r)-F_{r+1}(t_r)\}
\le\frac qm\sum_{r=1}^m\{F_r(t_r)-F_{r+1}(t_{r+1})\}
=\frac qm F_1(t_1)
\le\frac qm.
$$

In the last sum, take any t_{m+1} in (0,1), since its coefficient is F_{m+1}=0. Summing over i, all nulls being true, proves P(K>0) <= q.

If the global BH procedure has a qualifying rank k, at threshold t = qk/(2m) the two clouds together contain at least k p-values. At least one cloud contains r >= k/2 such p-values. Its r-th ordered p-value is at most t <= qr/m, so that cloud's own BH procedure at level q rejects. This implication holds even with ties and with the largest-rank convention. A union bound over the two clouds therefore gives

$$
\operatorname{FDR}_{\rm global}=P(R>0)\le 2q.
$$

For the proposed sequence, the normalized ratio is at most 2/sqrt(n), which tends to zero. Thus no failure of the existential constant C(1/2) is produced.

## Failure

NOT fails: the two positively correlated clouds each satisfy the linear BH bound, and every global rejection forces rejection in one cloud, yielding FDR <= 2q despite growing N and negative correlations between clouds.
