---
type: candidate
title: Full covariance rank with one zero-loading factor
status: failed
target_asset: slow_factor_dimension_one_sided_sharpness
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
statement_digest: 41c776b5ba7a93e0fc85e9c920013f0df855975e6702b5c0f76f09e9b822fd15
performed_by: unknown
created_at: '2026-11-04T07:10:23.174Z'
extension_version: 0.0.4
---

## Object

For every $0<q<e^{-2}$ let $\ell=\log(1/q)$, $D(q)=1$, and $m(q)=\lceil e^{\ell^2}\rceil$. Take $d=1$, $a_i=0$, and $\theta_i=0$ for all $i\leq m(q)$. Thus $T_i=\varepsilon_i$ are independent standard normals. Their covariance has rank $m(q)$, although this is a representation with factor dimension one. Apply ordinary one-sided BH at level $q$.

## Checks

### H1

The deterministic budget is finite and $D(q)\geq1$; $\lfloor D(q)\rfloor=1$, so the permitted positive dimensions form a nonempty set.

### H2

$D(q)\log\log(1/q)/\sqrt{\log(1/q)}=\log\ell/\sqrt\ell\to0$.

### H3

Every $m(q)$ is finite, every loading has norm zero, and $1\leq d\leq\lfloor D(q)\rfloor$. The independent residual covariance supplies full rank; the budget restricts the representation dimension, not the total covariance rank. Arbitrarily rapid growth of $m(q)$ is allowed.

### H4

The one-sided p-values are independent uniform random variables, all nulls are true, and the prescribed ordinary BH rule is used.

### NOT

This object does not violate the uniform upper assertion. In fact its FDR equals $q$ for every finite $m(q)$. To check this directly, let $R_i^0$ be the BH rejection count after replacing $p_i$ by zero. For $r\geq1$, the deterministic BH identity is
$$
\{i\text{ rejected},R=r\}=\{p_i\leq qr/m,R_i^0=r\}.
$$
Independence of $p_i$ and $R_i^0$ gives
$$
\mathbb E\frac{\mathbf 1\{i\text{ rejected}\}}{R\vee1}
=\sum_{r=1}^m\frac1r\frac{qr}{m}\mathbb P(R_i^0=r)=\frac qm,
$$
because $R_i^0\geq1$. Summing over $i$ gives FDR $q$, and the ratio to $q\sqrt\ell$ tends to zero. A suboptimal individual model cannot disprove the lower bound for a supremum.

## Failure

NOT fails: full covariance rank and unrestricted $q$-dependent test count yield normalized FDR tending to zero in this admissible one-factor family.
