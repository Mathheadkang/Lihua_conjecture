---
type: candidate
title: >-
  Antipodal rank-one all-null family with arbitrary nonpositive means has zero
  charge
status: failed
target_asset: gaussian_bh_positive_p_path_jump_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:26:24.010Z'
extension_version: 0.0.4
---

## Object

For arbitrary finite $N\geq1$, signs $s_j\in\{-1,1\}$, means $\theta_j\leq0$, and $0<q\leq\overline\Phi(1)$, let $G$ be standard normal and set $T_j=\theta_j+s_jG$. Both sign groups may be nonempty; either may also be empty. Zero-mean antipodal clone groups are a subfamily, but the means here need not coincide within a sign group.

## Checks

### H1

$N$ is a finite positive integer.

### H2

All means are real and nonpositive, so every original coordinate is a true null. Negative nulls are retained.

### H3

The actual joint law is Gaussian with unit-diagonal covariance $\Sigma=ss^{\mathsf T}$. It is positive semidefinite because $x^{\mathsf T}\Sigma x=(s^{\mathsf T}x)^2$. Its singular rank-one law is admissible.

### H4

The level is in the stipulated interval. BH uses all coordinates, their labels, and non-strict largest-rank comparisons.

### NOT

For a selected null $i$, $\rho_{ij}=s_is_j$ and the conditional residual is identically zero. On the opposite-sign coordinates,
$$
T_j^{\,i}(t)=\theta_j+\theta_i-u(t)\leq-u(t),\qquad
p_j^{\,i}(t)\geq1-t>1-q>q.
$$
Such coordinates cannot satisfy any BH threshold $qk/N\leq q$. They remain present in the full model and in the denominator $N$. On every same-sign coordinate,
$$
T_j^{\,i}(t)=\theta_j-\theta_i+u(t),
$$
which is nonincreasing in $t$. Hence all coordinates capable of rejection have nondecreasing p-values, so the actual largest rank $R_i(t)$ is nonincreasing. Therefore $A_i(t)$ is nondecreasing, including rank-zero transitions and simultaneous ties. No actual net downward jump exists and $B_i=0$, regardless of the nonconstant weight $g_i$ for a negative selected mean. The normalized budget is zero throughout the family.

## Failure

NOT fails: opposite-sign all-null paths remain above every BH p-value threshold, and the remaining paths give zero positive charge.
