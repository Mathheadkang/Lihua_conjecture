---
type: candidate
title: Fully loaded null with an adversarial positive alternative
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

Fix any $0<q<1/2$ and put $u=\overline\Phi^{-1}(q)$, $v=\overline\Phi^{-1}(q/2)$. Take $m=2$, $d=1$, $\theta=(0,u+v)$, $a_1=1$, $a_2=-1$, and independent standard normals $Z,\varepsilon_1,\varepsilon_2$. Then $T_1=Z$ and $T_2=u+v-Z$. Use track $s=1$.

## Checks

### H1

Pass. Both loadings have norm one, and the finite positive alternative mean $u+v$ is permitted. The means may depend on $q$ in the uniform assertion.

### H2

Pass. The true-null set is exactly $I_0=\{1\}$, so $\pi_0=1/2$. Use the one-sided Gaussian p-values and ordinary BH.

### H3

Pass. The chosen level is in the asserted one-sided range.

### H4

Pass. The radial quantile is $b=v>u$, $\Delta_1=\log2$, and the null loading coefficient is $\gamma_1=0$.

### NOT

Fail. Both coordinates are rejected exactly when $u\leq Z\leq v$; this has probability $q/2$ and FDP $1/2$. For $Z>v$, only the null is rejected; this has probability $q/2$ and FDP one. No other event rejects the null. Therefore
$$
\operatorname{FDR}=\tfrac12\,(q/2)+q/2=3q/4.
$$
The claimed bound is
$$
q\left(\frac54+\frac{\log2}{2}\right)>3q/4.
$$
Its cap is inactive because $q<1/2$ and $5/4+(\log2)/2<2$. More generally, replacing the alternative mean by any $c>0$ gives, with $x=c-u$,
$$
\operatorname{FDR}(c)=\frac12[\Phi(x)-\Phi(u)]_++\overline\Phi(\max\{v,x\}).
$$
This increases up to $x=v$ and decreases thereafter, so $3q/4$ is the maximum over this entire anti-aligned alternative family.

## Failure

NOT fails: optimizing the unrestricted positive alternative in this two-test singular family gives FDR only $3q/4$.
