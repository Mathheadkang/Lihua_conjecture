---
type: candidate
title: Independent nullspace exposure of a singular tight frame
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
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:16:54.623Z'
extension_version: 0.0.4
---

## Object

Take d=3 and n=3, G=(X,Z,T) with independent standard Gaussian coordinates, and
$$
v_1=(1,0,0),\qquad v_2=(1/2,\sqrt3/2,0),\qquad v_3=(1/2,-\sqrt3/2,0),\qquad w=(0,0,1).
$$
Set c_1=c_2=c_3=2/3, beta=2, u=a_1=a_2=a_3=1, and y=0. This tests an exposure in the nullspace of the saturated frame operator, at the maximal exposure density. The round-1 estimate for the same three constraint directions exposed along v_1 only applies at y>=3. Its tail-density mechanism does not apply here: w is orthogonal to all constraints and y=0. Embedding the active frame in one more dimension changes the conditional law from a line slice of the active plane to the full active plane.

## Checks

### H1

Pass: d=3 and n=3 are positive integers.

### H2

Pass: G=(X,Z,T) has the standard Gaussian law on R^3.

### H3

Pass: each v_i has squared norm 1; w has squared norm 1.

### H4

Pass: every c_i=2/3 is nonnegative.

### H5

Pass: direct summation gives
$$
\sum_{i=1}^3 c_i v_i v_i^T=\operatorname{diag}(1,1,0)\preceq I_3.
$$

### H6

Pass: beta=sum_i c_i=2.

### H7

Pass: u=1 satisfies u>=1.

### H8

Pass: all a_i=1 equal u and are deterministic. Equivalently all theta_i=0.

### H9

Pass: y=0 is real. Under the specified canonical conditional law, G given w.G=0 is (X,Z,0), where X,Z are independent standard Gaussians. Its covariance diag(1,1,0) is exactly I_3-ww^T.

### NOT

Fail: the second and third inequalities are equivalent to
$$
X\ge 2+\sqrt3|Z|.
$$
They imply the first inequality X>=1, so the conditional kernel is exactly
$$
K=2\phi(0)\int_0^\infty\phi(z)S(2+\sqrt3 z)\,dz.
$$
In particular K<=phi(0)S(2). The proposed upper bound is
$$
\sqrt e\,h(1)S(1)^2=\sqrt e\,\phi(1)S(1)=\phi(0)S(1).
$$
Because S(2)<S(1), K is strictly below the proposed bound. Thus the maximal density in an independent nullspace exposure does not yield a counterexample for this singular tight frame.

## Failure

NOT is the first failing check: the active conjunction forces X>=2, giving K<=phi(0)S(2)<phi(0)S(1), the claimed bound.
