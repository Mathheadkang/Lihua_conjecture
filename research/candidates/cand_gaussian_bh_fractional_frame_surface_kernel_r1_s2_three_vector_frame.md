---
type: candidate
title: Three distinct vectors forming a fractional tight frame in dimension two
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

Take d=2, n=3, G=(G_1,G_2) standard Gaussian in R^2, v_1=w=(1,0), v_2=(1/2,sqrt(3)/2), v_3=(1/2,-sqrt(3)/2), c_1=c_2=c_3=2/3, beta=2, u=a_1=a_2=a_3=1, and y=3.

## Checks

### H1

Pass: d and n are positive integers. d=2 and n=3 are positive integers.

### H2

Pass: G has the standard Gaussian law in dimension d. G has the standard Gaussian law in R^2.

### H3

Pass: all constraint vectors and the exposure vector have norm one. For v_2 and v_3 the squared norm is 1/4+3/4=1. The vectors v_1 and w equal e_1.

### H4

Pass: all weights are nonnegative. All three weights are 2/3 and are nonnegative.

### H5

Pass: the weighted frame matrix is at most I_d in PSD order. The sum of the three unweighted outer products is diag(3/2,3/2): the two off-diagonal entries cancel. Multiplication by 2/3 gives I_2, so the PSD condition holds with equality.

### H6

Pass: u=1 satisfies u>=1.

### H7

Pass: every threshold a_i is the deterministic number 1 and satisfies a_i>=u.

### H8

Pass: y is real and conditioning uses the stipulated canonical Gaussian law. The canonical conditional vector is (3,Z), with Z standard normal. The first constraint holds. The other two constraints read 3/2+sqrt(3)Z/2>=1 and 3/2-sqrt(3)Z/2>=1. Hence the conjunction is |Z|<=1/sqrt(3), whose probability is 2 Phi(1/sqrt(3))-1.

### NOT

Fail: the conclusion is not violated. The exact left side is phi(3)[2 Phi(1/sqrt(3))-1], numerically 0.0019336027797261187. The right side is sqrt(e) phi(1) S(1)=phi(0) S(1), numerically 0.06329428880108384. An elementary strict bound also certifies the comparison: the left side is at most phi(3), whereas S(1)>integral_1^2 phi(2) dz=phi(2). Thus the right side exceeds phi(0)phi(2), and phi(3)/(phi(0)phi(2))=sqrt(2 pi) exp(-5/2)<1. The conclusion holds strictly.

## Failure

NOT is the first failed check: this object satisfies the hypotheses but obeys the claimed surface-kernel inequality.
