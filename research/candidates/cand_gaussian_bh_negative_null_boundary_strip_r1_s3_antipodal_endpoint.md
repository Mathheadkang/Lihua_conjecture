---
type: candidate
title: >-
  Singular antipodal pair at the largest testing level and inclusive
  negative-mean boundary
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
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
performed_by: unknown
created_at: '2026-11-11T19:32:43.257Z'
extension_version: 0.0.4
---

## Object

Take N=2, theta=(-2,-2), Sigma=[[1,-1],[-1,1]], q=barPhi(1), and a=2. For a standard normal Z, set T=(Z-2,-Z-2). Use p_i=barPhi(T_i) and the original ordinary BH procedure. Then U=1, I_0=D_a={1,2}. This probes singular covariance, the largest permitted q, and equality at the D_a boundary simultaneously.

## Checks

### H1

N=2 is a finite positive integer.

### H2

theta=(-2,-2) belongs to R^2; both coordinates are original true nulls.

### H3

Sigma has diagonal entries 1 and eigenvalues 0 and 2, so it is positive semidefinite and admissible. The displayed representation gives the required exactly joint Gaussian law, including singularity.

### H4

q=barPhi(1) is positive and equals the permitted upper endpoint. Hence U=1.

### H5

The full original BH has rank-2 rejection only if both T_i>=1. This would require simultaneously Z>=3 and Z<=-3, which is impossible. Write t=barPhi^{-1}(q/2). Rank 1 qualifies exactly when Z>=2+t or Z<=-2-t. Consequently R is either 0 or 1, and the actual unmodified-procedure contribution is exactly

$$
E[V_{D_a}/(R\vee1)]=2\bar\Phi(2+t).
$$

No coordinate or rank has been changed.

### H6

a=2>0 and theta_i=-a, so the inclusive definition gives D_a={1,2}. Thus |D_a|/N=1.

### NOT

The claimed upper bound is exactly

$$
\frac54\bar\Phi(1)e^{-4}.
$$

The candidate does not violate it. To verify this without relying on the decimal calculation, put x=2+t. Since t>1, x>3. The standard tail inequality barPhi(x)<=phi(x)/x yields

$$
2\bar\Phi(2+t)<\frac23\phi(3)=\frac23\phi(1)e^{-4}.
$$

For the denominator, integration by parts twice gives

$$
\bar\Phi(1)=\phi(1)-\int_1^\infty\frac{\phi(u)}{u^2}\,du.
$$

A direct sharper lower bound suffices here: on [1,3/2], phi(u)>=phi(3/2), and on [3/2,2], phi(u)>=phi(2), so

$$
\bar\Phi(1)\geq\tfrac12[\phi(3/2)+\phi(2)].
$$

For transparent numerical checking, evaluation of the exact tail expressions gives t=1.4096087092934546, LHS=0.00065056144661714953, and RHS=0.0036323404235112386. An entirely analytic comparison is available directly from t>1 and the elementary lower Mills bound at 1 improved by the positive integral on [1,3/2]; alternatively the following elementary integral bound avoids any tail approximation. For 0<=v<=1, exp(-v^2/2)>=1-v^2/2, hence

$$
\frac{\bar\Phi(1)}{\phi(1)}
=\int_0^\infty e^{-v-v^2/2}\,dv
\geq\int_0^1 e^{-v}(1-v^2/2)\,dv
=\frac{3}{2e}>\frac8{15}.
$$

It follows that (5/4)barPhi(1)e^{-4}>(2/3)phi(1)e^{-4}>LHS. Thus NOT fails strictly. The final two conclusions follow from the target's stated specialization/decomposition and are not challenged by this object; q here is outside the narrower special-level range.

## Failure

NOT fails: the exact original BH contribution is 2 barPhi(2+barPhi^{-1}(barPhi(1)/2)), strictly below (5/4)barPhi(1)e^{-4}.
