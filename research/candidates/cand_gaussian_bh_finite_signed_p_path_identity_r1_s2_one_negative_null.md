---
type: candidate
title: Single strictly negative null at rank one
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:25:30.473Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $\theta_1=-1$, $\Sigma=(1)$, and $q=1/5$. The possible defect tested is the negative-null density baseline at the smallest size.

## Checks

### H1

$N=1$ is a finite positive integer.

### H2

$\theta=(-1)\in\mathbb R^1$, and $I_0=\{1\}$ includes this strictly negative mean.

### H3

$\Sigma=(1)$ is positive semidefinite with unit diagonal. Let $T_1=-1+Z_1$ for standard normal $Z_1$.

### H4

$q=1/5\in(0,1/2)$.

### NOT

Fail. The residual is zero, the path is $T_1^1(t)=u(t)$, and $R_1(t)=1$ throughout $(0,q)$. Thus $A_1(t)=t/q$, there are no interior events or jumps, and both endpoint and derivative assertions hold. The density is $g_1(t)=\exp\{-u(t)-1/2\}$, continuous, increasing, and bounded by one. Direct integration gives
$$
F_1=S(u(q)+1)=\int_0^q g_1(t)\,dt.
$$
Integration by parts with $A_1=t/q$ makes the asserted baseline exactly $q^{-1}\int_0^q g_1(t)\,dt$. Multiplication by $q/N=q$ recovers $F_1$. The baseline lies in $[0,1]$, the empty jump sum is absolutely integrable, and the FDR bound follows from $F_1\le q$.

## Failure

NOT fails: the exact negative-null baseline reproduces the direct one-dimensional rejection probability.
