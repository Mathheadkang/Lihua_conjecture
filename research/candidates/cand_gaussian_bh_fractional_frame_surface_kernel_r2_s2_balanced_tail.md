---
type: candidate
title: Balanced orthogonal exposure in the large-threshold tail
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

Take d=n=2, G standard Gaussian in R^2, v_1=e_1, v_2=e_2, c_1=c_2=1, beta=2, and w=(e_1+e_2)/sqrt(2). Set u=a_1=a_2=10 and y=sqrt(2)u+1/(sqrt(2)u). This changes the exposure geometry from the board's axis exposure to a balanced diagonal exposure; its conditional conjunction is an interval rather than an independent tail times a deterministic indicator.

## Checks

### H1

Pass: d=n=2 are positive integers.

### H2

Pass: G has law N(0,I_2).

### H3

Pass: v_1,v_2,w are unit vectors.

### H4

Pass: both weights equal 1 and are nonnegative.

### H5

Pass: sum_i c_i v_i v_i^T=I_2.

### H6

Pass: beta=c_1+c_2=2.

### H7

Pass: u=10>=1.

### H8

Pass: deterministic thresholds a_1=a_2=u.

### H9

Pass: y is real. Under the specified canonical conditional law, for Z standard normal, the coordinates are (y+Z)/sqrt(2) and (y-Z)/sqrt(2).

### NOT

Fail. Put delta=y-sqrt(2)u=1/(sqrt(2)u). The exact kernel is
$$
K=\phi(y)[2\Phi(\delta)-1].
$$
Since phi(z)<=phi(0), the interval probability is at most 2 delta phi(0)=1/(sqrt(pi)u). The elementary Mills lower bound S(u)>=phi(u)u/(u^2+1) yields
$$
\frac{K}{\sqrt e\,h(u)S(u)^2}
\le \sqrt{2}(1+u^{-2})\exp\{-3/2-1/(4u^2)\}.
$$
At u=10 the right side is sqrt(2)(101/100)exp(-601/400), strictly below 1. For example, sqrt(2)<3/2 and exp(3/2)>1+3/2+(3/2)^2/2=29/8 already prove this strictly. Thus the purported counterexample satisfies the conclusion.

## Failure

NOT is the first failed check: the exact balanced-exposure kernel has ratio at most sqrt(2)(101/100)exp(-601/400)<1.
