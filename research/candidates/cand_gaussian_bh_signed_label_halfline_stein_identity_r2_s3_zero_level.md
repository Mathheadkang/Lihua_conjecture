---
type: candidate
title: Zero-level endpoint of the half-line Stein formulation
status: failed
target_asset: gaussian_bh_signed_label_halfline_stein_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: fail
  H5: unknown
  H6: unknown
  NOT: unknown
mode: refute
round: 2
slot: 3
direction: drop_hypothesis
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:29:57.144Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $\theta=(0,0)$, $\Sigma=I_2$, and $q=0$. This tests the omitted lower endpoint of the level interval, rather than repeating the singular-covariance family from the previous round.

## Checks

### H1

Pass: $N=2$ is a finite positive integer.

### H2

Pass: $\theta=(0,0)\in\mathbb R^2$.

### H3

Pass: $I_2$ has unit diagonal and eigenvalues $1,1$, so is positive definite.

### H4

Fail: the statement requires $0<q\le S(1)$, while this object has $q=0$. Moreover, $S$ maps the real line to $(0,1)$, so $S^{-1}(0)$ and hence the prescribed finite real thresholds $U,u_r$ are not defined. This is a different obstruction from the preceding singular examples.

### H5

Unknown: Gaussian observation, one-sided p-values and original fixed null-label conventions were not checked after H4 failed.

### H6

Unknown: the complete record-path and half-line-potential conventions were not checked after H4 failed.

### NOT

Unknown: no conclusion check was performed after H4 failed; no claim is made about a limiting extension at zero level.

## Failure

H4 fails: zero level is excluded and does not give the finite inverse-survival thresholds required by this formulation.
