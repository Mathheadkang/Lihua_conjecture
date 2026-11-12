---
type: candidate
title: Growing two-sign Gaussian null blocks have exact FDR q
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: small_cases
statement_digest: 334aaf8c5303a807be8f3b8e641f2fb7a35d5a6a6a5fe8080f4f22262e996d7f
performed_by: unknown
created_at: '2026-11-06T23:29:11.098Z'
extension_version: 0.0.4
---

## Object

For every $0<q<1/2$, let $N=2\lceil q^{-2}\rceil$, $m=\lfloor\sqrt N\rfloor$ and $n=N-m$. Let $Z\sim N(0,1)$ and define $T_i=Z$ for $1\le i\le m$ and $T_i=-Z$ for $m<i\le N$. Every mean is zero. This differs from a single duplicated block by including both opposed loadings with an increasingly unbalanced number of coordinates.

## Checks

### H1

$N$ is a positive finite integer for each $q$, and $m,n$ are both positive. Its growth as $q\downarrow0$ is allowed.

### H2

The vector is exactly jointly Gaussian with mean vector zero and covariance $aa^{\mathsf T}$, where $a$ has $m$ entries $1$ and $n$ entries $-1$. This covariance is symmetric positive semidefinite with unit diagonal; its rank-one singularity is admissible.

### H3

Every coordinate is a one-sided true null because its mean is zero. The p-values are $P=\overline\Phi(Z)$ in the first block and $1-P$ in the second, with $P$ uniform on $(0,1)$.

### H4

Use ordinary BH with the largest qualifying rank and non-strict threshold comparisons. If $P<1/2$, only the first block can have a p-value at most $q$, so the only possible positive maximal rank is $m$; it occurs exactly when $P\le qm/N$. If $P>1/2$, the corresponding maximal rank is $n$, occurring exactly when $1-P\le qn/N$. No rank containing both blocks can qualify, since its p-value is at least $1/2>q$. The event $P=1/2$ has probability zero and no rejection.

### H5

All model parameters are deterministic at each $q$; no complexity or null-proportion restriction is imposed. The chosen family has null proportion one and includes arbitrary growth of its dimension within the target scope.

### NOT

Since every hypothesis is a true null, FDP equals the indicator of any rejection. The two rejection events above are disjoint, and therefore
$$
\operatorname{FDR}=\Pr(P\le qm/N)+\Pr(P\ge1-qn/N)
=q(m+n)/N=q.
$$
Consequently the normalized FDR is $1/\sqrt{\log(1/q)}\to0$, and the family does not violate the existential universal order bound.

## Failure

NOT fails: the two opposed null blocks have exact FDR $q$, even with growing dimension and unbalanced block sizes.
