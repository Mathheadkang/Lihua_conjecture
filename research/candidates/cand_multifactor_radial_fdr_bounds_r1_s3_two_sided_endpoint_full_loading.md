---
type: candidate
title: Two-sided endpoint with antipodal full loadings
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

Take $m=2$, $d=1$, $\theta=(0,0)$, $a_1=1$, $a_2=-1$, and independent standard normals $Z,\varepsilon_1,\varepsilon_2$. Thus $T=(Z,-Z)$. Use track $s=2$ and $q=q_*=2\overline\Phi(1)$.

## Checks

### H1

Pass. The dimensions are positive integers; both loading norms equal one. The residual terms vanish, so the singular covariance matrix is admissible.

### H2

Pass. Both means are zero, so $I_0=\{1,2\}$ and $\pi_0=1$. The ordinary BH rule is applied to $p_1=p_2=U=2\overline\Phi(|Z|)$.

### H3

Pass. The two-sided level is exactly the allowed upper endpoint $q_*$.

### H4

Pass. Since $d=1$, the radial upper-$q_*$ quantile is $b=1=u_2(q_*)$. Thus $\Delta_2=0$ and both $\gamma_i=0$.

### NOT

Fail. The common p-value $U$ is uniform. BH rejects both coordinates exactly on $U\leq q_*$, so the FDR is $q_*$. The claimed bound is $3q_*/2$, because $q_*<1/2$ makes the cap inactive. Hence the conclusion holds strictly, including at the two-sided level endpoint and the singular-loading boundary.

## Failure

NOT fails: the exact FDR is $q_*$, strictly below $3q_*/2$.
