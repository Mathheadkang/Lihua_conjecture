---
type: candidate
title: Zero-weight exposure constraint at an oblique supporting vertex
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
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:00:40.088Z'
extension_version: 0.0.4
---

## Object

Take d=2, n=3 and G=(X_1,X_2) with independent standard Gaussian coordinates. Let
$$
v_1=(1,0),\qquad v_2=(0,1),\qquad v_3=w=2^{-1/2}(1,1),
$$
and let c_1=c_2=1, c_3=0, beta=2. Set u=a_1=a_2=a_3=1 and evaluate the canonical conditional law at y=sqrt(2). This differs from the board's axis-exposed orthonormal family: the exposure is oblique, and the third constraint has zero frame weight. Its conditional event is the supporting vertex of the positive orthant.

## Checks

### H1

Pass. The dimensions d=2 and n=3 are positive integers.

### H2

Pass. The vector G has law N(0,I_2).

### H3

Pass. Each of v_1,v_2,v_3,w has Euclidean norm one.

### H4

Pass. All frame weights are nonnegative, including c_3=0.

### H5

Pass. The frame operator is
$$
\sum_{i=1}^3 c_i v_i v_i^T=e_1e_1^T+e_2e_2^T=I_2.
$$
Thus the positive-semidefinite hypothesis holds at equality despite the redundant third constraint.

### H6

Pass. The prescribed value beta=2 equals c_1+c_2+c_3.

### H7

Pass. The value u=1 is the permitted endpoint.

### H8

Pass. All three deterministic thresholds equal u. They can also be written as u-theta_i with theta_i=0.

### H9

Pass. The exposure value y=sqrt(2) is real. Under the specified canonical conditional law,
$$
G\mid(w\cdot G=\sqrt2)\ \stackrel{d}{=}\ (1,1)+\frac{Z}{\sqrt2}(1,-1),\qquad Z\sim N(0,1).
$$
Indeed the second summand is the orthogonal projection of a standard Gaussian onto w-perp.

### NOT

Fail. The first two conditional constraints give Z>=0 and Z<=0. The third constraint is deterministic and satisfied because v_3 dot G=sqrt(2)>=1. Thus the conjunction is exactly {Z=0}, which has probability zero. The left-hand surface kernel is zero. The proposed right-hand side is strictly positive:
$$
\sqrt e\,h(1)S(1)^2=\sqrt e\,\phi(1)S(1)=\phi(0)S(1)>0.
$$
The conclusion is therefore satisfied, so this object does not refute it. More generally, at the supporting value y=sqrt(2)u, equal orthogonal thresholds u>0 likewise force Z=0; a zero-weight exposure constraint does not introduce an atom into this canonical slice.

## Failure

NOT is the first failed check: the oblique supporting slice collapses the event to a Gaussian-null singleton, so its surface kernel is zero.
