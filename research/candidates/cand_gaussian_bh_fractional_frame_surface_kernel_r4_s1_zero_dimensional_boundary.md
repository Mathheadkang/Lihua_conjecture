---
type: candidate
title: Zero-dimensional canonical slice at a closed threshold boundary
status: failed
target_asset: gaussian_bh_fractional_frame_surface_kernel
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  H9: pass
  NOT: fail
mode: refute
round: 4
slot: 1
direction: boundary_degenerate
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:20:47.811Z'
extension_version: 0.0.4
---

## Object

Take d=n=1, G standard normal, v_1=w=1, c_1=1, beta=1, u=a_1=y=1. The canonical conditional Gaussian has zero-dimensional support. Unlike a positive-dimensional supporting slice, its threshold boundary has conditional probability one.

## Checks

### H1

The dimensions d=n=1 are positive integers.

### H2

G is a standard Gaussian vector in R^1.

### H3

Both v_1=1 and w=1 have unit norm.

### H4

The sole weight c_1=1 is nonnegative.

### H5

The frame operator is c_1 v_1 v_1^T=1=I_1, so the positive-semidefinite constraint holds with equality.

### H6

The specified exponent is beta=sum_i c_i=1.

### H7

The baseline u=1 satisfies u>=1, with equality.

### H8

The threshold a_1=1 is deterministic and satisfies a_1>=u, with equality.

### H9

At the real exposure value y=1, the stipulated canonical law is
$$
yw+(I_1-ww^T)G_0=1+0G_0=1.
$$
Consequently its closed threshold event has probability one.

### NOT

The surface kernel and proposed bound are respectively
$$
K=\phi(1),\qquad B=\sqrt e\,h(1)S(1)=\sqrt e\,\phi(1).
$$
Thus K/B=e^{-1/2}<1, so the conclusion does not fail.

This calculation also excludes every zero-dimensional canonical case: necessarily d=1 and v_i,w are signs. If the v_i include both signs, the conjunction is empty because all a_i>=u>0. Otherwise a nonempty conjunction forces |y|>=u, and the frame constraint gives 0<=beta<=1. Hence
$$
K\le\phi(u),\qquad
B=\sqrt e\,\phi(u)S(u)^{\beta-1}\ge\sqrt e\,\phi(u).
$$
The boundary atom therefore cannot violate the bound, including zero weights and unequal thresholds.

## Failure

NOT is the first failing check: the deterministic boundary event has probability one, but its kernel is smaller than the proposed bound by the factor e^{-1/2}.
