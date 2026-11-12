---
type: candidate
title: Two orthogonal constraints exposed along one axis
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

Take d=n=2, G=(G_1,G_2) with independent standard normal coordinates, v_1=w=(1,0), v_2=(0,1), c_1=c_2=1, beta=2, u=a_1=a_2=1, and y=1.

## Checks

### H1

Pass: d and n are positive integers. d=n=2 are positive integers.

### H2

Pass: G has the standard Gaussian law in dimension d. The independent standard normal coordinates make G standard Gaussian in R^2.

### H3

Pass: all constraint vectors and the exposure vector have norm one. v_1, v_2, and w are standard basis vectors and have norm one.

### H4

Pass: all weights are nonnegative. Both weights equal 1 and are nonnegative.

### H5

Pass: the weighted frame matrix is at most I_d in PSD order. The frame matrix is e_1 e_1^T+e_2 e_2^T=I_2.

### H6

Pass: u=1 satisfies u>=1.

### H7

Pass: every threshold a_i is the deterministic number 1 and satisfies a_i>=u.

### H8

Pass: y is real and conditioning uses the stipulated canonical Gaussian law. The canonical conditional vector is (1,Z), with Z standard normal. The conjunction is Z>=1, with probability S(1).

### NOT

Fail: the conclusion is not violated. The left side is phi(1) S(1). The right side is sqrt(e) h(1) S(1)^2=sqrt(e) phi(1) S(1). Their ratio is exp(-1/2)<1. Numerically the sides are 0.03838992674256333 and 0.06329428880108384. For these fixed constraints, the conditional probability is S(1) when y>=1 and zero otherwise, so y=1 also maximizes the left side over all exposures.

## Failure

NOT is the first failed check: this object satisfies the hypotheses but obeys the claimed surface-kernel inequality.
