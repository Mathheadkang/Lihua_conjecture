---
type: candidate
title: High-dimensional nearly aligned cap with simplex residuals
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
slot: 2
direction: extremal
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:00:40.088Z'
extension_version: 0.0.4
---

## Object

Take d=n=1000, G standard Gaussian in R^n, and w=(1,...,1)/sqrt(n). Let P=I_n-ww^T and
$$
z_i=\sqrt{n/(n-1)}(e_i-w/\sqrt n),\qquad
v_i=\sqrt{9/10}\,w+\sqrt{1/10}\,z_i.
$$
Set c_i=1/900, beta=10/9, u=a_i=1 for every i, and y=11/10. The distinct vectors form a high-dimensional positive-correlation cap with simplex residuals. In particular beta>1, so the board's aligned rank-one obstruction does not apply.

## Checks

### H1

Pass: d=n=1000 are positive integers.

### H2

Pass: G has law N(0,I_n).

### H3

Pass: w is unit; each z_i is perpendicular to w with norm 1, so each v_i has squared norm 9/10+1/10=1.

### H4

Pass: c_i=1/900>0.

### H5

Pass: sum_i z_i=0 and sum_i z_i z_i^T=nP/(n-1). Consequently
$$
\sum_i c_i v_i v_i^T=ww^T+\frac{1}{9(n-1)}P\preceq I_n.
$$

### H6

Pass: sum_i c_i=1000/900=10/9=beta.

### H7

Pass: u=1>=1.

### H8

Pass: every threshold is deterministic and equals u.

### H9

Pass: y=11/10 is real; use the canonical conditional vector yw+PG_0 with G_0 standard Gaussian.

### NOT

Fail. Summing all n inequalities shows that the event is empty unless sqrt(9/10)y>=1, because sum_i z_i=0. Thus for every exposure value its kernel is either zero or at most phi(sqrt(10/9)); this includes y=11/10. The asserted right side is sqrt(e)phi(1)S(1)^(1/9). Since S(1)>=phi(1)/2 by the Mills lower bound,
$$
\frac{\phi(\sqrt{10/9})}{\sqrt e\,\phi(1)S(1)^{1/9}}
=e^{-5/9}S(1)^{-1/9}
\le [2\sqrt{2\pi}e^{-9/2}]^{1/9}<1.
$$
For the last strict inequality, pi<4 and e>2 give 2sqrt(2pi)<6 and exp(9/2)>16. Hence even the universal density bound on the allowed exposure region is below the claimed right side; no numerical integration is required.

## Failure

NOT is the first failed check: the simplex support condition forces y>=sqrt(10/9), where phi(y) is already below sqrt(e)phi(1)S(1)^(1/9).
