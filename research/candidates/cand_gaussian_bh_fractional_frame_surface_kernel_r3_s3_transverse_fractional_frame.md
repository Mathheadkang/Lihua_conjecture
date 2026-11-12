---
type: candidate
title: Transverse exposure at a saturated fractional-frame boundary
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
slot: 3
direction: drop_hypothesis
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:16:54.623Z'
extension_version: 0.0.4
---

## Object

Take d=n=2, G=(X,Z) with independent standard normal coordinates,
v_1=(sqrt(3)/2,1/2), v_2=(sqrt(3)/2,-1/2),
w=(0,1), c_1=c_2=2/3, beta=4/3, u=a_1=a_2=1,
and y=0. The canonical conditional vector is (X,0).

This tests the endpoint u=1 and a frame with its top eigenvalue exactly one, with fractional weights and transverse exposure. Unlike the earlier aligned simplex-cap family, the exposure is perpendicular to the common constraint direction: summing the inequalities constrains the residual coordinate X, not the exposure y, so that board obstruction does not apply.

## Checks

### H1

The dimensions d=n=2 are positive integers.

### H2

By construction G is a standard Gaussian vector in R^2.

### H3

Both v_i have squared norm 3/4+1/4=1, and w has norm one.

### H4

The deterministic weights c_1=c_2=2/3 are nonnegative.

### H5

The frame operator is

$$
\sum_{i=1}^2 c_i v_i v_i^T
= \operatorname{diag}(1,1/3) \preceq I_2.
$$

### H6

The prescribed beta equals c_1+c_2=4/3.

### H7

The chosen u=1 satisfies u>=1 at equality.

### H8

The thresholds a_1=a_2=1 are deterministic and satisfy a_i>=u at equality.

### H9

The exposure y=0 is real. Since w=e_2, the specified canonical law at this exposure is (X,0), exactly the law used here.

### NOT

Under the canonical law both inequalities reduce to X>=2/sqrt(3), so the surface kernel is

$$
K=\phi(0)S(2/\sqrt{3}).
$$

At u=1, sqrt(e) phi(1)=phi(0), hence the asserted upper bound is

$$
B=\sqrt e\,h(1)S(1)^{4/3}=\phi(0)S(1)^{1/3}.
$$

Because 2/sqrt(3)>1 and 0<S(1)<1,

$$
S(2/\sqrt{3})<S(1)<S(1)^{1/3},
$$

and therefore K<B. The conclusion does not fail.

## Failure

NOT is the first failing check: the exact transverse surface kernel is strictly below the claimed bound by Gaussian-tail monotonicity.
