---
type: candidate
title: Negative one-sided null means with antipodal full loadings
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

For any fixed $c\geq0$, take $m=2$, $d=1$, $\theta=(-c,-c)$, $a_1=1$, $a_2=-1$, and independent standard normals $Z,\varepsilon_1,\varepsilon_2$. Thus $T=(Z-c,-Z-c)$. Use track $s=1$ and $q=1/4$. Put $v=\overline\Phi^{-1}(q/2)$.

## Checks

### H1

Pass. This is an admissible singular Gaussian multifactor representation with full loading norms and deterministic finite means.

### H2

Pass. Every $c\geq0$ gives two true one-sided nulls, including strictly negative null means when $c>0$. Therefore $\pi_0=1$. Use $p_i=\overline\Phi(T_i)$ and ordinary BH.

### H3

Pass. The one-sided level satisfies $0<q=1/4<1/2$.

### H4

Pass. For $d=1$, $2\overline\Phi(b)=q$, so $\Delta_1=\log 2$ and $b=\overline\Phi^{-1}(q/2)>u_1(q)$. Both $\gamma_i=0$.

### NOT

Fail. Both coordinates cannot have $p_i\leq q$, because this would imply $Z-c\geq u_1(q)>0$ and $-Z-c\geq u_1(q)>0$. Hence BH rejects exactly one coordinate precisely when $Z\geq v+c$ or $Z\leq-v-c$. All rejections are false, giving
$$
\operatorname{FDR}=2\overline\Phi(v+c)\leq2\overline\Phi(v)=q.
$$
The claimed right side is $q(3/2+\log 2)>q$; it is below one for $q=1/4$. At the mean boundary $c=0$, the exact FDR is $q$; negative means only reduce it.

## Failure

NOT fails: antipodal singular dependence and negative true-null means still give FDR at most $q$.
