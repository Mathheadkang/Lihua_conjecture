---
type: candidate
title: Zero loadings at the two-sided level endpoint
status: failed
target_asset: multifactor_radial_fdr_bounds
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:39:44.119Z'
extension_version: 0.0.4
---

## Object

Take $m=2$, $d=1$, $\theta=(0,0)$, $a_1=a_2=0$, and independent standard normals $Z,\varepsilon_1,\varepsilon_2$. Thus $T=(\varepsilon_1,\varepsilon_2)$. Use track $s=2$ and $q=q_*=2\overline\Phi(1)$.

## Checks

### H1

Pass. Zero loadings are permitted, including the resulting unused but positive-dimensional factor. The residual coordinates are independent standard normals.

### H2

Pass. Both coordinates are true nulls, so $\pi_0=1$. Their two-sided p-values $U_1,U_2$ are independent uniforms, and the procedure is ordinary BH.

### H3

Pass. The level is exactly the two-sided upper endpoint.

### H4

Pass. The one-dimensional radial quantile gives $b=u_2(q_*)=1$ and $\Delta_2=0$. Both loading coefficients satisfy $\gamma_i=1$.

### NOT

Fail. The all-null rejection event is the disjoint union of $\min(U_1,U_2)\leq q_*/2$ and $U_1,U_2\in(q_*/2,q_*]$. Its probability is
$$
1-(1-q_*/2)^2+(q_*/2)^2=q_*.
$$
Thus the exact FDR is $q_*$. Each entry of the minimum defining the asserted bound is strictly larger than $q_*$: one entry is $1$, and the other is $q_*(3/2+1/\sqrt{2\pi})$. The conclusion holds strictly.

## Failure

NOT fails: the zero-loading boundary yields exact independent-null FDR $q_*$.
