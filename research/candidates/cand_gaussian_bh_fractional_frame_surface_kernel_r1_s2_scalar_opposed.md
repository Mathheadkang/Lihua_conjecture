---
type: candidate
title: Scalar opposing constraints with fractional weights
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
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T19:55:21.135Z'
extension_version: 0.0.4
---

## Object

Take d=1, n=2, G standard normal, v_1=1, v_2=-1, w=1, c_1=c_2=1/2, beta=1, u=a_1=a_2=1, and y=1.

## Checks

### H1

Pass: d and n are positive integers. d=1 and n=2 are positive integers.

### H2

Pass: G has the standard Gaussian law in dimension d. G is standard normal in R.

### H3

Pass: all constraint vectors and the exposure vector have norm one. Each of v_1, v_2, and w is a scalar of absolute value one.

### H4

Pass: all weights are nonnegative. Both weights are 1/2 and are nonnegative.

### H5

Pass: the weighted frame matrix is at most I_d in PSD order. The frame matrix is (1/2)(1)^2+(1/2)(-1)^2=1=I_1.

### H6

Pass: u=1 satisfies u>=1.

### H7

Pass: every threshold a_i is the deterministic number 1 and satisfies a_i>=u.

### H8

Pass: y is real and conditioning uses the stipulated canonical Gaussian law. The canonical conditional vector is G=1 almost surely. The conjunction G>=1 and -G>=1 is empty. Its conditional probability is zero.

### NOT

Fail: the conclusion is not violated. The left side is zero. The right side is sqrt(e) phi(1)=phi(0)>0. The conclusion therefore holds strictly. In fact the conjunction is empty for every exposure.

## Failure

NOT is the first failed check: this object satisfies the hypotheses but obeys the claimed surface-kernel inequality.
