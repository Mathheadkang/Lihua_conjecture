---
type: candidate
title: Nonunit marginal variance at the scalar model edge
status: failed
target_asset: gaussian_bh_signed_label_halfline_stein_identity
checks:
  H1: pass
  H2: pass
  H3: fail
  H4: unknown
  H5: unknown
  NOT: unknown
mode: refute
round: 4
slot: 3
direction: drop_hypothesis
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:33:07.676Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $\theta_1=0$, and $Z_1=2g$ for $g\sim N(0,1)$, so $\Sigma=[4]$. Specify $q=S(1)$ and the original label set $I_0=\{1\}$.

## Checks

### H1

Pass: $N=1$ is finite and positive, and $\theta_1=0$ is a finite real mean.

### H2

Pass: $Z_1$ is exactly jointly Gaussian in the one-dimensional sense, with the displayed mean and covariance.

### H3

Fail: $\Sigma=[4]$ is positive definite because $4x^2>0$ for nonzero real $x$, but its diagonal is $4$, not the required $1$. This object therefore violates the unit-diagonal part of the covariance hypothesis.

### H4

Unknown: checking stopped at H3; the level and threshold conditions were not evaluated.

### H5

Unknown: checking stopped at H3; the fixed-label auxiliary path was not evaluated.

### NOT

Unknown: checking stopped at H3; no conclusion or failure of the identity is asserted for this out-of-scope model.

## Failure

H3 fails first: the scalar covariance is positive definite but has nonunit diagonal.
