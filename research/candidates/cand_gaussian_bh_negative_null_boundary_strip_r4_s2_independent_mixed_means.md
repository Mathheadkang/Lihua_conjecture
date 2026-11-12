---
type: candidate
title: Independent mixed-mean pair with both BH ranks active
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
round: 4
slot: 2
direction: small_cases
statement_digest: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
performed_by: unknown
created_at: '2026-11-11T19:46:33.061Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $\theta=(-1,1)$, $\Sigma=I_2$, $q=\overline\Phi(1)$, and $a=1$. Thus $T_1=Z_1-1$ and $T_2=Z_2+1$ for independent standard normals. Retain both coordinates in ordinary one-sided BH. This differs from the previously recorded singular common-noise and antipodal pairs: independent heterogeneous marginals permit both the singleton and double rejection events with positive probability.

## Checks

### H1

$N=2$ is a finite positive integer.

### H2

$\theta=(-1,1)\in\mathbb R^2$, and the original true-null set is $I_0=\{1\}$.

### H3

$\Sigma=I_2$ is positive definite with unit diagonal, and $T\sim N_2(\theta,I_2)$.

### H4

$q=\overline\Phi(1)>0$ satisfies the upper endpoint of the permitted range, and $U=1$.

### H5

Set $p_i=\overline\Phi(T_i)$ and use the stated largest-rank BH rule, including both coordinates. Rank two is selected exactly when $p_1,p_2\le q$. Otherwise, the deep null is rejected alone exactly when $p_1\le q/2$ and $p_2>q$. All threshold comparisons are non-strict; equalities have probability zero.

### H6

$a=1>0$ and $D_a=\{1\}$, with equality $\theta_1=-a$ included.

### NOT

Write $F_i(t)=\Pr(p_i\le t)$ and $z=\overline\Phi^{-1}(q/2)>1$. Independence and the exact BH event partition give
$$
\mathbb E\!\left[\frac{V_{D_a}}{R\vee1}\right]
=F_1(q/2)(1-F_2(q))+\frac12F_1(q)F_2(q)
=\frac12\overline\Phi(z+1)+\frac14\overline\Phi(2).
$$
Since $z>1$, this is strictly less than $3\overline\Phi(2)/4$. For $t\ge1$, the standard normal density satisfies $\phi(t+1)=e^{-t-1/2}\phi(t)\le e^{-3/2}\phi(t)$; integration gives $\overline\Phi(2)<e^{-3/2}q$. Therefore
$$
\mathbb E\!\left[\frac{V_{D_a}}{R\vee1}\right]
<\frac34q e^{-3/2}
<\frac32q e^{-3/2}
=\frac{q|D_a|}{N}e^{-a^2/2-aU}
\left[\frac{U+1}{a}+\frac1{a^2}\right].
$$
For reproducibility, $z=1.4096087092934546$, the exact contribution is approximately $0.00967994240516$, and the stated bound is approximately $0.05310115832717$. The displayed strict inequalities, rather than numerical rounding, establish failure of NOT. The additional specialization requires $q\le\overline\Phi(e)$ and thus does not apply to this endpoint object.

## Failure

NOT fails: the exact original two-coordinate BH contribution is strictly below the claimed bound even though both rejection ranks occur with positive probability.
