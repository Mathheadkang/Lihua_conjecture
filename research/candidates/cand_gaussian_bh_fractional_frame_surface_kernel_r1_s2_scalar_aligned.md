---
type: candidate
title: Scalar aligned exposure at the threshold
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

Take d=n=1, G standard normal, v_1=w=1, c_1=1, beta=1, u=a_1=1, and y=1.

## Checks

### H1

Pass: d and n are positive integers. d=n=1 are positive integers.

### H2

Pass: G has the standard Gaussian law in dimension d. G is standard normal in R.

### H3

Pass: all constraint vectors and the exposure vector have norm one. Both v_1 and w equal 1 and have norm one.

### H4

Pass: all weights are nonnegative. c_1=1 is nonnegative.

### H5

Pass: the weighted frame matrix is at most I_d in PSD order. The frame matrix is c_1 v_1 v_1^T=1=I_1.

### H6

Pass: u=1 satisfies u>=1.

### H7

Pass: every threshold a_i is the deterministic number 1 and satisfies a_i>=u.

### H8

Pass: y is real and conditioning uses the stipulated canonical Gaussian law. The canonical conditional vector is G=1 almost surely. Thus the event G>=1 has probability one.

### NOT

Fail: the conclusion is not violated. The left side is phi(1). The right side is sqrt(e) h(1) S(1)=sqrt(e) phi(1)=phi(0). Since phi(1)=exp(-1/2)phi(0)<phi(0), the asserted inequality holds strictly. Numerically the sides are 0.24197072451914337 and 0.3989422804014327. This remains the maximal left side among all real exposures for this object: phi(y) 1_{y>=1} is maximized at y=1.

## Failure

NOT is the first failed check: this object satisfies the hypotheses but obeys the claimed surface-kernel inequality.
