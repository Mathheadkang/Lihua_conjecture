---
type: candidate
title: Finite-quarter-distance unit-loading threshold endpoint
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
round: 5
slot: 1
direction: boundary_degenerate
statement_digest: 422a8915f80d37bc2594b42629202589fe6eb5d11efe2e43269d21df06b3e719
performed_by: unknown
created_at: '2026-11-06T22:09:59.938Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $q=2\overline\Phi(100)$, $r=4/5$, and $D^*(1)=0$, $D^*(2)=10$. Take ten mates with $a_j=1$, $\theta_j=0$, and fixed $\varepsilon_j=0$. Thus $Y_j(z)=z$. This tests exact threshold inclusion at the upper endpoint with endpoint loadings and finite extended quarter distance.

## Checks

### H1

$N$ is positive, $0<q<1$, $0<r<1$, and the prescribed inverse threshold gives $U=100$, $u_2=100$, and a finite $u_1>100$.

### H2

$J=10$, $K=8\log100\approx36.84136149$, and $L\approx46.84136149\le100$. Also $U\ge1$ and $r^2=0.64<U$.

### H3

$D^*$ is integer valued and nondecreasing.

### H4

The mate set is finite, all means and noises are real, and all loadings belong to $[-1,1]$.

### H5

Rank 1 qualifies for every real $z$ because its deficit is zero. In fact $R(z)=2$ for $|z|\ge100$, and $R(z)=1$ for $|z|<100$.

### H6

The same zero noises are used for all $z$. The defined level extension is 10 for $100\le w<u_1$ and zero for $w\ge u_1$. Hence, whenever its deficit is at least $J$, $Q(v)=u_1-v$. The supremum defining $\widetilde\Lambda$ is finite, so $B$ is finite and positive; its first term is approximately $75.44557465$.

### NOT

For every $t\in[L,100)$ the deficit at $R(\pm t)$ is zero, so neither tracked set contains $t$. At $t=100$, both ranks equal 2, the tilt error is $20<K$, and all ten mates are large and meet the threshold, including equality. Thus $S_+=S_-=\{100\}$. Conclusion (a) has no later points for its only possible $t_1=100$, and the left side of (b) is zero. Neither conclusion fails.

## Failure

NOT fails: the finite-quarter-distance threshold tie gives two singleton tracked sets and no later points.
