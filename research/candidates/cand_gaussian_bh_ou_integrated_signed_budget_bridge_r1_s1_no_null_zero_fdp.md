---
type: candidate
title: No-null zero-budget boundary fails the positive-F hypothesis
status: failed
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: fail
  NOT: unknown
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T21:56:18.237Z'
extension_version: 0.0.4
---

## Object

For every $0<q\leq S(1)$ take $N=d=1$, $\theta_1=1$, $v_1=1$, and $\Sigma=(1)$. Then $I_0=\varnothing$, and the full actual BH FDP is identically zero.

## Checks

### H1

$N=1$ is finite and positive.

### H2

The mean is real; there are no true nulls and $\pi_0=0$.

### H3

$\Sigma=(1)$ is positive semidefinite with unit diagonal.

### H4

$0<q\leq S(1)$ as required.

### H5

$T_1=1+G$ gives the required finite representation with a unit vector.

### H6

Whatever the actual BH rejection count, its false rejection count is zero; therefore its full FDP is $f=0$, $T_tf=0$, and $J(f)=0$. No surrogate FDP is used. There are no conditional null-path charges to sum.

### H7

Fails: $F=0$, whereas the quantitative gate requires $F>0$.

### NOT

Unknown, because H7 already fails; no positive-F zero-budget violation has been produced.

## Failure

H7 fails: the exact zero OU budget comes with zero FDR.
