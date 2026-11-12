---
type: candidate
title: Two nonorthogonal constraints with exposure perpendicular to one constraint
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
slot: 2
direction: small_cases
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:16:54.623Z'
extension_version: 0.0.4
---

## Object

Take d=n=2, G standard Gaussian in R^2, v_1=(1,0), v_2=(1/3,2 sqrt(2)/3), w=(2 sqrt(2)/3,-1/3), c_1=c_2=3/4, u=a_1=a_2=y=1. This is a nonorthogonal frame with v_1 dot v_2=1/3; exposure w is perpendicular to v_2.

## Checks

### H1

d=n=2 are positive integers.

### H2

G has law N(0,I_2).

### H3

All three vectors are unit: the squared norms of v_2 and w are 1/9+8/9=1.

### H4

c_1=c_2=3/4 are nonnegative.

### H5

The eigenvalues of v_1 v_1^T+v_2 v_2^T are 1 plus or minus 1/3. Multiplication by 3/4 gives frame-operator eigenvalues 1 and 1/2. Therefore the operator is at most I_2.

### H6

beta=c_1+c_2=3/2.

### H7

u=1 satisfies u>=1.

### H8

a_1=a_2=1 are deterministic and at least u; equivalently both null means theta_i are zero.

### H9

y=1 is real. Since (w,v_2) is an orthonormal basis, the canonical conditional vector is w+Zv_2 with Z standard univariate Gaussian.

### NOT

Under this conditional law, v_2 dot G=Z and v_1 dot G=(2 sqrt(2)+Z)/3. Thus the conjunction is exactly Z>=max(1,3-2 sqrt(2))=1. Its surface kernel is K=phi(1)S(1), whereas the claimed upper bound is B=sqrt(e) phi(1) S(1)^(1/2). Hence

$$
K/B=e^{-1/2}S(1)^{1/2}<1.
$$

More generally, in this fixed frame and at u=1, every real exposure y gives K<=phi(y)S(1)<=phi(0)S(1), while B=phi(0)S(1)^(1/2). Thus changing only y cannot produce a counterexample in this configuration.

## Failure

NOT fails first: the exact kernel is below the proposed bound by the factor e^(-1/2) S(1)^(1/2).
