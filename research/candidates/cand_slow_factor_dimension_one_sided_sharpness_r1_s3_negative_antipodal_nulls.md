---
type: candidate
title: Negative composite nulls with antipodal unit loadings
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

For $0<q<e^{-2}$ set $\ell=\log(1/q)$, $D(q)=1$, $d=1$, $n(q)=\lceil e^{\ell^2}\rceil$, and $m(q)=2n(q)$. The first group of $n(q)$ observations has $T_i=-\sqrt\ell+Z$ and the second has $T_i=-\sqrt\ell-Z$, where $Z\sim N(0,1)$. Thus every null mean is strictly negative, every loading has norm one, and every residual variance is zero. Apply ordinary one-sided BH at level $q$.

## Checks

### H1

$D=1$ is a deterministic finite budget with $\lfloor D\rfloor=1$.

### H2

$\log\ell=o(\sqrt\ell)$ verifies the slow-growth requirement.

### H3

The representation is jointly Gaussian with $d=1$, unit marginal variances, singular covariance, saturated antipodal loadings, and finite $m(q)$. All these endpoints and arbitrarily negative $q$-dependent null means are permitted.

### H4

The true-null set is the entire coordinate set because each mean equals $-\sqrt\ell<0$. The p-values are $\overline\Phi(T_i)$, and the largest-rank ordinary BH rule, including ties, is used.

### NOT

For a given $Z$, each group has a constant p-value. Let $p_{\rm small}$ and $p_{\rm large}$ be the smaller and larger group p-values. No rank beyond $n$ can qualify unless $p_{\rm large}\leq q$: its threshold is at most $q$. This latter event is impossible, since it would require both $-\sqrt\ell+Z$ and $-\sqrt\ell-Z$ to be at least the positive number $\overline\Phi^{-1}(q)$. Among ranks at most $n$, a rank qualifies exactly when $p_{\rm small}\leq q/2$. Consequently
$$
\operatorname{FDR}=\mathbb P(R>0)
=2\overline\Phi\!\left(\sqrt\ell+\overline\Phi^{-1}(q/2)\right)\leq q.
$$
Its ratio to $q\sqrt\ell$ tends to zero. This exact calculation uses the composite-null labels directly and makes no monotonicity claim about FDR when null means change.

## Failure

NOT fails: the singular, saturated, negative-null family has FDR at most $q$ and cannot violate the uniform upper bound.
