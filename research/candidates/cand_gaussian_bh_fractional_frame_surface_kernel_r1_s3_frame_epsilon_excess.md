---
type: candidate
title: Scalar frame weight just above the PSD boundary
status: failed
target_asset: gaussian_bh_fractional_frame_surface_kernel
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: fail
  H5: unknown
  H6: unknown
  H7: unknown
  NOT: unknown
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T19:55:21.135Z'
extension_version: 0.0.4
---

## Object

Set d=n=1, let G be a standard scalar Gaussian, set v_1=w=1, and let c_1=1000001/1000000. Set beta=c_1, u=a_1=y=1. The canonical conditional distribution at y is the point mass at y. This is a concrete object just outside the frame hypothesis, tested to locate its first obstruction; it is not a counterexample satisfying all hypotheses.

## Checks

### H1

Pass: d=n=1 are positive integers and G is standard Gaussian in R.

### H2

Pass: v_1=w=1 have Euclidean norm one.

### H3

Pass: c_1=1000001/1000000 is nonnegative.

### H4

Fail: the frame matrix is the scalar c_1 v_1 v_1^T=1000001/1000000>1=I_1. The positive-semidefinite constraint therefore fails by exactly 10^-6.

### H5

Unknown: the requirement u>=1 is not checked after H4 failed.

### H6

Unknown: determinism and the threshold requirement a_1>=u are not checked after H4 failed.

### H7

Unknown: the conditioning parameter and canonical conditional law are not checked after H4 failed.

### NOT

Unknown: the surface inequality is not evaluated after H4 failed.

## Failure

H4: the scalar frame weight exceeds the PSD upper bound by 10^-6.
