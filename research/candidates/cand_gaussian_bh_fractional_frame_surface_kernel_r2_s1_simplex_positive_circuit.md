---
type: candidate
title: Regular simplex positive circuit with singular Gaussian covariance
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
slot: 1
direction: known_counterexamples
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:00:40.088Z'
extension_version: 0.0.4
---

## Object

Let d=2, n=3, and let G=(X,Z) have the standard Gaussian law on R^2. Set
$$
v_1=(1,0),\qquad v_2=(-1/2,\sqrt3/2),\qquad v_3=(-1/2,-\sqrt3/2),\qquad w=(1/\sqrt2,1/\sqrt2).
$$
Take c_1=c_2=c_3=2/3, beta=2, u=a_1=a_2=a_3=1, and y=0. Use the canonical conditional law specified in the target. This tests a singular three-coordinate Gaussian covariance arising from a positive linear dependence, with no opposite pair of constraint vectors. It is different from the board's opposite-pair family and its three-vector family whose vectors all have positive first coordinates.

## Checks

### H1

Pass. The dimensions d=2 and n=3 are positive integers.

### H2

Pass. G has the standard Gaussian law N(0,I_2).

### H3

Pass. Every displayed v_i and w has Euclidean norm one: the squared norms are 1, 1/4+3/4, 1/4+3/4, and 1/2+1/2.

### H4

Pass. All c_i=2/3 are nonnegative, and their sum is beta=2.

### H5

Pass. The outer products sum to diag(3/2,3/2), so
$$
\sum_{i=1}^3c_iv_iv_i^T=\frac23\operatorname{diag}(3/2,3/2)=I_2.
$$

### H6

Pass. The common lower threshold parameter is u=1, satisfying u>=1.

### H7

Pass. Each threshold is the deterministic number a_i=1>=u. Equivalently, theta_i=0 satisfies theta_i<=0.

### H8

Pass. The exposure value y=0 is real.

### H9

Pass. For an independent G_0 with law N(0,I_2), the conditional vector is exactly yw+(I_2-ww^T)G_0=(I_2-ww^T)G_0, as required by the canonical convention.

### NOT

Fail. The vectors satisfy v_1+v_2+v_3=0. If a vector g satisfied all three inequalities v_i dot g>=1, summing them would give 0>=3, a contradiction. Thus the conjunction is empty under every probability law and at every exposure value; its surface kernel is exactly zero. The proposed right side is strictly positive:
$$
\sqrt e\,h(1)S(1)^2=\sqrt e\,\phi(1)S(1)>0.
$$
The conclusion therefore holds. More generally, any strictly positive linear dependence among the constraint vectors, with all corresponding thresholds strictly positive, makes the conjunction empty. No antipodal pair is necessary for this obstruction.

## Failure

NOT is the first failing check: the positive linear dependence makes the conditional conjunction empty, so its kernel is zero and cannot exceed the positive claimed bound.
