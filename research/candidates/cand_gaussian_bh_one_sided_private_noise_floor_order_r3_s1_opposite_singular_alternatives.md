---
type: candidate
title: Oppositely loaded singular alternatives at a fixed half-noise null floor
status: failed
target_asset: gaussian_bh_one_sided_private_noise_floor_order
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  NOT: fail
mode: refute
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:22:49.027Z'
extension_version: 0.0.4
---

## Object

Fix $s_0=1/2$. For every $0<q<1/4$, set $n=\lceil q^{-1}\rceil$, $N=2n$, $d=1$, $r=\sqrt{3}/2$, and $z_q=\overline\Phi^{-1}(q)>0$. Let $G,\varepsilon_1,\ldots,\varepsilon_{2n}$ be mutually independent standard normals. Set
$$
T_i=rG+\tfrac12\varepsilon_i\quad(1\le i\le n),\qquad
T_{n+j}=2z_q-G\quad(1\le j\le n).
$$
Thus the alternative block is singular and tied, but its factor loading has the opposite sign to every null loading. The alternative means diverge as $q\downarrow0$. Unlike the previous nonnegative conditional-shift candidate, increasing the common factor decreases every alternative test statistic while increasing the null conditional means. That previous proof mechanism therefore does not apply. The calculation below supplies a different obstruction for this family.

## Checks

### H1

The floor $s_0=1/2$ is fixed independently of $q$ and belongs to $(0,1]$. The family is defined for arbitrarily small positive $q$.

### H2

The integers $n=\lceil q^{-1}\rceil$, $N=2n$, and $d=1$ are positive, and $N\to\infty$ as $q\downarrow0$.

### H3

The deterministic mean vector is $0$ on $[n]$ and $2z_q>0$ on the remaining coordinates. Therefore $I_0^{(1)}(\theta)=[n]$ exactly.

### H4

Take $a_i=r$, $s_i=1/2$ for $i\le n$, and $a_{n+j}=-1$, $s_{n+j}=0$. These define a real $N\times1$ loading matrix and a diagonal matrix with nonnegative entries.

### H5

For every null, $a_i^2+s_i^2=3/4+1/4=1$. For every alternative, $a_i^2+s_i^2=1+0=1$.

### H6

Every true null has $s_i=s_0=1/2$. The zero alternative noise levels are permitted by the statement.

### H7

The specified independent standard normals give exactly $T=\theta+AG+D\varepsilon$. Hence $\Sigma=AA^{\mathsf T}+D^2$ is positive semidefinite with diagonal one. Repeated alternative coordinates merely make the admissible covariance singular.

### H8

Use $p_i=\overline\Phi(T_i)$ and the largest qualifying rank with multiplicities and the non-strict inequalities $p_{(k)}\le qk/N$ exactly as in the target. No replacement or modified BH rule is used.

### NOT

NOT fails. Conditional on $G=g$, all null p-values are independent of each other and of the conditionally deterministic alternative block. Their density on $(0,1)$, writing $z_t=\overline\Phi^{-1}(t)$, is
$$
f_g(t)=\frac{1}{s}\exp\!\left\{\frac{z_t^2}{2}-\frac{(z_t-rg)^2}{2s^2}\right\},\qquad s=\tfrac12.
$$
Completing the square using $r^2+s^2=1$ gives
$$
\frac{z^2}{2}-\frac{(z-rg)^2}{2s^2}
=\frac{g^2}{2}-\frac{r^2}{2s^2}(z-g/r)^2
\le\frac{g^2}{2}.
$$
Thus $F_g(t)\le L_g t$ for every $t\in[0,1]$, where $L_g=2e^{g^2/2}$.

For completeness, the conditional BH bound uses the finite procedure including its ties. Set a selected null p-value to zero and let $R_i$ be the resulting largest-rank BH rejection count. It satisfies $R_i\ge1$ and depends only on the other p-values. The standard step-up identity, valid with multiplicities and non-strict inequalities, says that this null is rejected in the original vector if and only if $p_i\le qR_i/N$, and on this event the original rejection count equals $R_i$. Conditional independence therefore gives its expected FDP contribution at most
$$
\frac{F_g(qR_i/N)}{R_i}\le\frac{L_g q}{N}.
$$
Summing over $n=N/2$ nulls and using the deterministic FDP bound one obtains
$$
\mathbb E[\operatorname{FDP}\mid G=g]\le\min\{1,q e^{g^2/2}\}.
$$
Let $b=\sqrt{2\log(1/q)}$. Integrating against the standard Gaussian density and using $\overline\Phi(b)\le\phi(b)/b$ yields
$$
\operatorname{FDR}\le\frac{2qb}{\sqrt{2\pi}}+2\overline\Phi(b)
\le\sqrt{\frac2\pi}\,q\,(b+b^{-1}).
$$
Consequently
$$
\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}
\le\frac{2}{\sqrt\pi}+\frac{1}{\sqrt\pi\log(1/q)},
$$
which stays bounded as $q\downarrow0$. This family cannot refute the target order. The calculation is a family-specific upper bound, not an evaluation of its exact FDR and not a proof for arbitrary factor dimension.

## Failure

NOT is the first failing check: the conditional density envelope and exact finite BH leave-one-out identity bound the normalized FDR uniformly, even with opposite singular alternatives and growing dimension.
