---
type: candidate
title: Single negative null at the largest admissible level
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
slot: 2
direction: small_cases
statement_digest: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
performed_by: unknown
created_at: '2026-11-11T19:32:43.257Z'
extension_version: 0.0.4
---

## Object

Take N=1, theta=(-1), Sigma=(1), q=barPhi(1), and a=1. Thus U=1, D_a={1}, and T_1 is normal with mean -1 and variance 1. Use the original ordinary one-sided BH procedure.

## Checks

### H1

N=1 is a finite positive integer.

### H2

The mean theta=(-1) belongs to R^1. The original true-null set is I_0={1}.

### H3

Sigma=(1) is symmetric positive semidefinite with unit diagonal.

### H4

The level q=barPhi(1) satisfies 0<q<=barPhi(1), and U=barPhi^{-1}(q)=1.

### H5

For the full unmodified one-coordinate BH procedure, its only positive rank qualifies exactly when p_1=barPhi(T_1)<=q. Thus R=1 exactly when T_1>=1, and otherwise R=0. All comparisons remain non-strict.

### H6

The strip parameter a=1 is positive, and theta_1=-1<=-a, so D_a={1}. The count and denominator refer to the same full procedure.

### NOT

The actual contribution is

$$
E[V_{D_a}/(R\vee1)]=P(T_1>=1)=barPhi(2).
$$

The asserted right-hand side is

$$
q\exp(-a^2/2-aU)[(U+1)/a+1/a^2]=3\exp(-3/2)barPhi(1).
$$

Writing phi for the standard normal density gives the exact comparison

$$
barPhi(2)=\int_1^\infty phi(x+1)\,dx=\int_1^\infty phi(x)\exp(-x-1/2)\,dx<\exp(-3/2)barPhi(1).
$$

Consequently the actual contribution is strictly below one third of the proposed bound. The first displayed conclusion holds. The special a_q consequence applies only when q<=barPhi(e), which this object does not satisfy; it therefore cannot furnish a violation of that conditional consequence either.

## Failure

NOT fails: this actual one-coordinate BH contribution is strictly less than the claimed general strip bound.
