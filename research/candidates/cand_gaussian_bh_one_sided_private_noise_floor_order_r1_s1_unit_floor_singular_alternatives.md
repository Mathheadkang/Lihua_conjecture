---
type: candidate
title: Unit noise floor with a singular block of identical alternatives
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
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:15:04.651Z'
extension_version: 0.0.4
---

## Object

Fix $s_0=1$. For each positive integer $m$, let $N=2m$, $d=1$, and set
$$
\theta_i=0,\ a_i=0,\ s_i=1\quad(1\leq i\leq m),
$$
$$
\theta_i=1,\ a_i=1,\ s_i=0\quad(m<i\leq2m).
$$
Take independent $G\sim\mathcal N(0,1)$ and $\varepsilon\sim\mathcal N_{2m}(0,I_{2m})$. Thus $T_i=\varepsilon_i$ on the null block and $T_i=1+G$ on the alternative block. Apply the exact ordinary BH rule to all $2m$ physical labels for any $0<q\leq e^{-1}$. The integer $m$ may vary arbitrarily with $q$.

## Checks

### H1

Pass: the noise floor is the fixed real number $s_0=1\in(0,1]$, independent of $q$ and $m$.

### H2

Pass: $N=2m$ and $d=1$ are positive integers, the means and loadings are real, and $D=\operatorname{diag}(s_i)$ has nonnegative diagonal entries.

### H3

Pass: each null coordinate has $a_i^2+s_i^2=0+1=1$, and each alternative coordinate has $a_i^2+s_i^2=1+0=1$.

### H4

Pass: the exact one-sided true-null set is $I_0^{(1)}(\theta)=\{1,\ldots,m\}$ because all remaining means equal $1>0$. Every null has $s_i=1=s_0$. No noise floor is required on the alternatives.

### H5

Pass: the displayed independent standard Gaussian factors give $T=\theta+AG+D\varepsilon$ and $\Sigma=AA^{\mathsf T}+D^2$. Its null block is $I_m$, its alternative block is the all-ones matrix, and its cross block is zero. It is positive semidefinite with unit diagonal, including when $m>1$ makes the alternative block singular.

### H6

Pass: use exactly $p_i=\overline\Phi(T_i)$. The null p-values $U_i=\overline\Phi(\varepsilon_i)$ are independent uniform variables and each is independent of the complete vector of all other p-values. The $m$ alternative p-values coincide with $\overline\Phi(1+G)$; all their physical multiplicities are retained.

### H7

Pass: the family is defined for every $q\in(0,e^{-1}]$, hence includes arbitrarily small positive levels and its intersection with any proposed $(0,q_0(1)]$. No conclusion about an unknown numerical value of $q_0(1)$ is assumed.

### H8

Pass: use the largest qualifying BH rank with non-strict inequalities, exactly as in the target, and reject all physical labels at its threshold.

### NOT

Fail: for every $m$ and every $0<q<1$, the FDR is exactly $q/2$. Here is an explicit calculation that allows the tied alternative block. For a null index $i$, let $R_i$ denote the BH rejection count after replacing $U_i$ by zero. It depends only on the other p-values, is independent of $U_i$, and is at least one. The largest-rank BH rule gives, for $r\geq1$,
$$
\{i\in\mathcal R_q,\ R_q=r\}
=\{U_i\leq qr/N,\ R_i=r\}.
$$
Indeed, decreasing an already rejected p-value to zero leaves every later order statistic unchanged, and hence leaves the largest qualifying rank unchanged. Conversely, increasing that zero to at most $qr/N$ preserves rank $r$ and cannot create a larger qualifying rank. This reasoning includes multiplicities and equality cases. Consequently,
$$
\mathbb E\!\left[\frac{\mathbf1\{i\in\mathcal R_q\}}{R_q\vee1}\right]
=\sum_{r=1}^N\frac1r\frac{qr}{N}\Pr(R_i=r)
=\frac qN.
$$
Summing over the $m$ nulls gives $\operatorname{FDR}=mq/N=q/2$. For $q\leq e^{-1}$ this is at most $q\sqrt{\log(1/q)}$. Thus $C(1)=1$ and $q_0(1)=e^{-1}$ work uniformly for this family, even when $m$ diverges arbitrarily quickly and the alternatives have zero private noise. It cannot violate the target's fixed-floor order bound.

## Failure

NOT fails: the unit-floor nulls are independent of all other coordinates, and exact BH FDR equals $q/2$ despite the singular, tied alternative block.
