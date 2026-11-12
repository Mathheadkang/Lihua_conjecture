---
type: candidate
title: Three full-rank positively correlated constraints exposed along one constraint
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

Take d=n=3, G standard Gaussian in R^3,

$$
v_1=w=(1,0,0),\qquad
v_2=(1/4,\sqrt{15}/4,0),\qquad
v_3=(1/4,3/(4\sqrt{15}),3/\sqrt{10}).
$$

Set c_1=c_2=c_3=2/3 and u=a_1=a_2=a_3=y=1. Every distinct pair of constraint vectors has inner product 1/4. The exposure coefficients are 1,1/4,1/4, so this is not a common-alignment simplex-cap exposure.

## Checks

### H1

d=n=3 are positive integers.

### H2

G has law N(0,I_3).

### H3

v_1=w are unit. The squared norm of v_2 is (1+15)/16=1. The squared norm of v_3 is 1/16+9/240+9/10=1.

### H4

All three weights equal 2/3 and are nonnegative.

### H5

The Gram matrix has diagonal 1 and off-diagonal 1/4, with eigenvalues 3/2,3/4,3/4. Since the three vectors form a square full-rank matrix, their frame operator has the same eigenvalues. Multiplication by 2/3 gives 1,1/2,1/2, so the weighted frame operator is at most I_3.

### H6

beta=3(2/3)=2.

### H7

u=1 satisfies u>=1.

### H8

All thresholds are deterministic and equal to u; all corresponding theta_i equal zero.

### H9

y=1 is real. The canonical conditional vector is (1,Z_2,Z_3), with independent standard Gaussian Z_2,Z_3.

### NOT

The first constraint holds deterministically. Put R_j=v_j dot G-1/4 for j=2,3 under the conditional law. Their variances are 15/16 and their covariance is 1/4-1/16=3/16. The last two constraints require R_2>=3/4 and R_3>=3/4, hence R_2+R_3>=3/2. However R_2+R_3 is centered Gaussian with variance 2(15/16)+2(3/16)=9/4. Consequently their conjunction has probability at most S(1), and

$$
K\le\phi(1)S(1)
=e^{-1/2}\left[\sqrt e\,h(1)S(1)^2\right].
$$

Thus the kernel cannot exceed the claimed bound. This calculation concerns the stated exposure y=1 and does not claim control at other exposure levels.

## Failure

NOT fails first: summing the two residual constraints bounds their conditional probability by S(1), yielding a surface-kernel ratio at most e^(-1/2).
