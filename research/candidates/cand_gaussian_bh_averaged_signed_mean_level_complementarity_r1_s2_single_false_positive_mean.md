---
type: candidate
title: >-
  Singleton false positive mean: apparent negative normal mass fails actual
  maximality
status: failed
target_asset: gaussian_bh_averaged_signed_mean_level_complementarity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: fail
  H9: unknown
  NOT: unknown
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: e3dcfc508ee344fb52d4454b0676313187354eefcb69339fb28a33f503d7f350
performed_by: unknown
created_at: '2026-11-09T07:57:20.716Z'
extension_version: 0.0.4
---

## Object

Take the nonzero separable Hilbert space $\mathcal H=\mathbb R$ and the deterministic singleton law
$$
\pi=\delta_{(\theta,v,\ell)=(1,0,0)}.
$$
Set $\sigma=s=1/2$, $a=1/10$, $q=1/10$, and $\eta=\delta=1$. Specify the cutoff by $\chi_a(r)=0$ for $r\le a$, $\chi_a(r)=3y^2-2y^3$ for $a<r<2a$ with $y=(r-a)/a$, and $\chi_a(r)=1$ for $r\ge2a$. Choose all these parameters before independent standard Gaussian innovations.

This is the smallest possible false-only population. It is tempting to use its positive mean to contradict the normal-mass assertion at a maximum. The actual-maximum hypothesis must be checked first.

## Checks

### H1

$0<\sigma=1/2<1$.

### H2

$s=1/2>0$ and $\sigma^2+s^2=1/2<1$.

### H3

$0<a=1/10<1/4$. The displayed cutoff takes values in $[0,1]$, is nondecreasing because its transition derivative is $(6y-6y^2)/a\ge0$, and is $C^1$ because that derivative vanishes at both transition endpoints. It has the required zero and unit plateaus.

### H4

$\pi$ is a deterministic Borel probability on the lawful marked unit ball: $v=0$ has norm at most one, and the false mark $\ell=0$ has $\theta=1\ge0$. Its second moment is $M_2(\pi)=1<\infty$.

### H5

$0<q=1/10<S(1)\simeq0.1586553=q_{\max}$.

### H6

The parameter law and all parameter choices above are deterministic and precede Gaussian innovations. With $v=0$, the residual isonormal background does not enter the conditional centre, and the stipulated independent Gaussian construction is lawful.

### H7

$\eta=\delta=1>0$.

### H8

**Fail:** $(\pi,q)$ is not an actual global maximizer of the normalized penalized objective. Because every mark is false, the true tail $V_X$ and the full FDP $D$ vanish identically. Consequently $\mathcal F^a=0$ for every possible actual rank, with no rank optimization or approximation required. At the fixed level $q=1/10$, its objective equals
$$
-1-\log 10.
$$
The lawful deterministic competitor $\widetilde\pi=\delta_{(1/2,0,0)}$ also has identically zero FDP and cutoff payoff, but has second moment $1/4$. At the same level its objective is
$$
-\tfrac14-\log 10,
$$
which is greater by $3/4$. This exact comparison disproves maximality regardless of the cutoff or rank behavior.

### H9

Unknown under fail-fast checking: the canonical-maximum hypothesis occurs after the failed actual-maximizer check and is not used.

### NOT

Unknown under fail-fast checking. No complementarity or normal-positivity conclusion is tested after failure of actual maximality. In particular an arbitrary singleton directing law cannot be substituted for the genuine normalized maximum required by clauses 4 and 5.

## Failure

H8: lowering the positive false mean preserves its zero payoff and strictly improves the normalized penalized objective, so the object is not an actual normalized maximum.
