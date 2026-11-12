---
type: candidate
title: Two-rank interior saturation with minimal large loadings
status: failed
target_asset: gaussian_bh_two_sign_curve_exclusion_large_u_exq
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 6
slot: 2
direction: small_cases
statement_digest: 422a8915f80d37bc2594b42629202589fe6eb5d11efe2e43269d21df06b3e719
performed_by: unknown
created_at: '2026-11-06T22:12:48.545Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $q=p(1000)$, $r=1/2$, and $D^*(1)=0$, $D^*(2)=32$. Use exactly 32 mates, each with $\theta_j=2000$, $a_j=1/2000$, and $\varepsilon_j=0$. Thus $Y_j(z)=2000+z/2000$.

Unlike the board's unit-loading endpoint-tie object, this uses the smallest admissible large loading and strict exceedances throughout two positive-measure interior tracked intervals. Its mechanism is saturation by the fixed means, rather than a threshold tie.

## Checks

### H1

$N=2$ is a positive integer.

### H2

$0<p(1000)<1$ and $r=1/2\in(0,1)$, giving exactly $U=1000$.

### H3

Here $J=32$, $K=8\log(1000)\in(55,56)$, and $L=K+\sqrt{1000}<88<1000=U$. Also $U\ge1$ and $r^2=1/4<U$.

### H4

The integer curve $(0,32)$ is nondecreasing.

### H5

There are finitely many mates; their means and fixed noises are real, and their loadings lie in $[-1,1]$. The same zero noises are used at every $z$. Every mate is large, since $|a_j|=1/2000=r/U$.

### H6

For every real $z$, rank 1 qualifies because $M_z(1)\ge0=D^*(1)$, so $R(z)$ is defined. For $|z|\le1000$, every $Y_j(z)\ge1999.5>1000=u_2$. Consequently $M_z(2)=32$, $R(z)=2$, and $v(z)=1000$ throughout this range.

The level extension is 32 on $[U,u_1)$ and zero on $[u_1,\infty)$. Writing $\delta=u_1-U>0$, its quarter distance on that interval is $Q(v)=u_1-v$. Since the interval is bounded, $\widetilde\Lambda$ and $B$ are finite. All extension conventions are respected.

### NOT

For each sign, the tracked set is exactly
$$
S_\sigma=[500-K,500+K].
$$
This interval lies inside $[L,U]$, since $500-K>444>88>L$ and $500+K<556<U$. On it the deficit is $32=J$, and all 32 mates contribute to the large-carrier count, exceeding the required 16. Thus $|S_+|+|S_-|=4K$.

Conclusion (a) holds: throughout $[L,U]$ the tilt conditions themselves hold exactly on this same interval, whose diameter is $2K$. The first term in $B$ is strictly larger than $2K$, so a later tilted point at distance greater than $B$ from any tracked point is impossible.

Conclusion (b) holds as well: $\ell=500+K$, while $3K<168<500$ gives $4K<\ell\le\ell+\min\{B,\ell\}$. Therefore NOT fails.

## Failure

NOT fails: the two positive-measure interior tilt intervals have diameter below $B$, and their combined length is already below $\ell$.
