---
type: candidate
title: Mixed null means at the shrinking-strip endpoint with singular common noise
status: failed
target_asset: gaussian_bh_negative_null_boundary_strip
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
performed_by: unknown
created_at: '2026-11-11T19:36:33.070Z'
extension_version: 0.0.4
---

## Object

Set N=2, q=barPhi(e), a=2/e, theta=(-a,0), and Sigma=[[1,1],[1,1]]. For Z standard normal let T=(Z-a,Z). Here U=e, a=a_q, D_a=D_q={1}, B_q={2}, and I_0={1,2}. This is a mixed-mean, common-noise model with one mean exactly at the shrinking-strip cutoff and the other at the null boundary; unlike the earlier antipodal example it has simultaneous full-rank rejections and is in the specialized q range.

## Checks

### H1

N=2 is a finite positive integer.

### H2

theta=(-2/e,0) is real and both coordinates are original one-sided true nulls.

### H3

Sigma has unit diagonal and eigenvalues 0 and 2. The representation by one standard normal gives the required singular joint Gaussian law.

### H4

q=barPhi(e) belongs to (0,barPhi(1)] and is exactly the specialized range's upper endpoint. Thus U=e and a_q=2 log(e)/e=2/e.

### H5

The p-values are always ordered p_2<p_1. Put t=barPhi^{-1}(q/2). Rank 2 qualifies exactly when Z>=e+a. The tail-shift identity yields

$$
\frac{\bar\Phi(e+a)}{\bar\Phi(e)}
=e^{-ae-a^2/2}\frac{\int_e^\infty e^{-a(u-e)}\phi(u)\,du}{\bar\Phi(e)}
\leq e^{-2-2/e^2}<\frac12.
$$

Hence t<e+a. The original full BH therefore has R=0 for Z<t, R=1 with rejection set {2} for t<=Z<e+a, and R=2 with rejection set {1,2} for Z>=e+a. The non-strict comparisons and the full original denominator are retained throughout. In particular, writing b=barPhi(e+a),

$$
E[V_{D_q}/(R\vee1)]=b/2,\qquad
E[V_{B_q}/(R\vee1)]=q/2-b/2,\qquad
FDR=q/2.
$$

### H6

a=2/e>0. Equality theta_1=-a puts coordinate 1 in D_q and excludes it from B_q; theta_2=0 puts coordinate 2 in B_q. Both sets use the target's exact strict/non-strict boundaries and partition the original true nulls.

### NOT

All three asserted conclusions hold for this object. First, with

$$
K=\frac{e+1}{a}+\frac1{a^2}=\frac{3e^2}{4}+\frac e2>1,
$$

the tail-shift inequality already displayed gives

$$
\frac b2\leq\frac q2e^{-2-2/e^2}
<\frac q2e^{-2-2/e^2}K,
$$

which is the asserted general bound at these parameters. Second, if C=3/4+1/(2e), then

$$
\frac b2\leq\frac q2e^{-2-2/e^2}<\frac{Cq}{2}\leq q,
$$

because e^{-2}<1/4<C and C<1. Finally, the same-procedure decomposition is exact:

$$
FDR=q/2=b/2+(q/2-b/2)
\leq q+E[V_{B_q}/(R\vee1)].
$$

Thus the cutoff equality, the q=barPhi(e) endpoint, and the singular rank jump do not produce a violation. This mixed-mean calculation is distinct from rescaling the earlier homogeneous scalar or antipodal family: the rank-1 region rejects only the boundary coordinate, and the rank-2 region changes the far-null denominator.

## Failure

NOT fails: the exact far-null contribution is barPhi(e+2/e)/2, which obeys both asserted bounds, and the exact same-procedure FDR decomposition also holds.
