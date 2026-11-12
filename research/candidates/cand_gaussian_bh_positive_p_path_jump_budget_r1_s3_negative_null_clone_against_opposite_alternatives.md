---
type: candidate
title: >-
  A negative null clone group against arbitrary opposite alternatives has
  bounded positive budget
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

Choose finite integers 1 <= m <= N, a real a >= 0, 0 < q <= S(1), and arbitrary positive real numbers mu_j for m < j <= N. Let X be standard normal. The m null scores are T_i = -a + X, while every other score is T_j = mu_j - X. Repeated positive means are permitted, so alternative clone groups of arbitrary integer multiplicities are included. Put alpha = m/N. Allow N,m,a,mu,q to vary without restriction along the family.

## Checks

### H1

pass. N is a positive finite integer and m is an integer in [1,N].

### H2

pass. The real mean vector is (-a,...,-a,mu_{m+1},...,mu_N). Its exact true-null set is {1,...,m}, including all nulls when a > 0.

### H3

pass. With s_i = 1 for i <= m and s_j = -1 otherwise, Sigma = s s^T is a positive semidefinite unit-diagonal covariance. The full observation is exactly jointly Gaussian with this possibly singular covariance.

### H4

pass. 0 < q <= S(1).

### H5

pass. For each selected original null i, every residual xi_j vanishes. Its full original conditional path has T_l^i(t) = u(t) for every l <= m, and T_j^i(t) = mu_j - a - u(t) for every j > m. All coordinates and their original labels are retained. Define B_i from the actual largest ordinary-BH rank and actual merged net jumps, with its original weight g_i(t) = exp{-a u(t)-a^2/2}.

### NOT

fail. For the following calculation only, define K(t) as the ordinary-BH rejection count when the m null p-values are replaced by zero and all other conditional p-values are unchanged. This is an auxiliary rank, not a change to the candidate model or its B_i. Since the alternative scores increase with t, all their p-values decrease. Thus K(t) is nondecreasing and m <= K(t) <= N.

The actual original A_i is exactly

$$
A_i(t)=\min\{Nt/(qK(t)),1\}.
$$

To check this equality, decreasing the null p-values to zero gives R_i(t) <= K(t). If t <= qK(t)/N, the forced-zero rank K(t) still qualifies when every zero is restored to t, so R_i(t) = K(t). If t > qK(t)/N, then t > qR_i(t)/N whenever R_i(t)>0, and actual A_i(t)=1; its rank-zero definition is also one.

At any jump K(t^-) = k_- < k_+ = K(t^+), the resulting actual downward jump is at most log(k_+/k_-). Indeed for fixed c = Nt/q, the function f(x)=min{c exp(-x),1} is nonincreasing and 1-Lipschitz, and the jump is f(log k_-)-f(log k_+). This bounds actual net jumps, with any simultaneous crossings merged, and includes jumps at which clipping hides some or all of the auxiliary change. Monotonicity of K telescopes the bound over all its finitely many jumps:

$$
\sum_{t\in J_i}[A_i(t^-)-A_i(t^+)]_+
\leq \log\frac{K(q^-)}{K(0^+)}
\leq \log\frac{N}{m}=\log(1/\alpha).
$$

The original negative-null weight satisfies 0 < g_i(t) <= 1 because a >= 0 and u(t) > 1. No expectation over residuals is needed here. Therefore

$$
\frac1N\sum_{i\in I_0}\mathbb E B_i
\leq\alpha\log(1/\alpha)\leq 1/e,
$$

and the normalized budget is at most 1/(e sqrt{log(1/S(1))}) throughout this parameterized family. It cannot become unbounded by increasing dimension, shrinking the null fraction, sending alternative means to infinity, or making the null mean increasingly negative.

## Failure

NOT fails: the exact original weighted budget is bounded by alpha log(1/alpha) <= 1/e, even with strictly negative null means and arbitrary positive opposite-sign alternatives.
