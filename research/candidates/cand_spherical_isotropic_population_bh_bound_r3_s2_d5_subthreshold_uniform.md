---
type: candidate
title: Dimension 5 with a uniform subthreshold alternative law
status: failed
target_asset: spherical_isotropic_population_bh_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 3
slot: 2
direction: small_cases
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:10:07.214Z'
extension_version: 0.0.4
---

## Object

Take $d=5$, $u=104$, $q=2Q(u)$, and
$$
W=\frac12\delta_0+\frac12\operatorname{Unif}([u/2,u]),\qquad \pi_0=\frac12.
$$
For every absolute mean use the uniform directional law on $\mathbb S^{d-1}$, independent of the mean. Sample $Z\sim N(0,I_d)$ and use $T_{\mu,v}=\mu+v^\top Z$, with no residual noise. Use exactly the population BH threshold and FDP in the target definition. The alternative law is continuous and supported entirely at or below $u$, outside the board's strong-mean support restriction.

## Checks

### H1

The statistic has the specified spherical directional-population form, and its additional residual variance is zero by construction.

### H2

The dimension $5$ is an integer at least four.

### H3

The displayed $W$ is a Borel probability law on $[0,\infty)$, and its atom at zero has mass $\pi_0=1/2$.

### H4

Choose the conditional directional kernel to be the uniform probability measure on $\mathbb S^{d-1}$ at every mean, including means outside the support of $W$. This is independent of the mean, as required.

### H5

The Gaussian survival function satisfies $0<2Q(104)<1$, so $q\in(0,1)$ and $Q^{-1}(q/2)=104$.

### H6

For each radius use the smallest finite $x\ge u$ with $F_r(x)\ge Q(x)/Q(u)$, if one exists; otherwise use FDP zero. At a finite contact use $q\pi_0H_r(x_r)/Q(x_r)$. These are precisely the prescribed threshold and FDP conventions.

### NOT

The proposed inequality does not fail. The following exact estimate gives
$$
\operatorname{FDR}_{\mathrm{pop}}\le 7q\pi_0.
$$

Put $x_k=Q^{-1}(Q(u)/k)$ with $k=7$. Gaussian tail translation gives
$$
\frac{Q(u+1)}{Q(u)}
=\frac{\int_u^\infty e^{-t-1/2}\phi(t)\,dt}{Q(u)}
<e^{-u-1/2}<\frac1k,
$$
so $u<x_k<u+1$. The first coordinate of a uniform direction has density
$$
g_d(z)=c_d(1-z^2)^{(d-3)/2},\quad |z|<1,\qquad c_d=3/4.
$$
In particular, $g_d(z)\le c_d$. For $r\ge u$ and $\mu\in[u/2,u]$, the number $(x_k-\mu)/r$ lies in $[0,1]$. Therefore
$$
H_r(x_k-\mu)\ge\frac12-c_d\frac{x_k-\mu}{r}.
$$
Keeping only this positive alternative tail and averaging the uniform mean, whose expectation is $3u/4$, gives
$$
F_r(x_k)
\ge\frac14-\frac{c_d}{2}\frac{x_k-3u/4}{r}
>\frac14-\frac{c_d}{2}\left(\frac14+\frac1u\right)
=\frac14-\frac{81}{832}=\frac{127}{832}>\frac17.
$$
The last comparison is $889>832$.
Thus $x_k$ is admissible for every $r\ge u$, and the globally first contact satisfies $u\le x_r\le x_k$. Consequently
$$
\operatorname{FDP}_{\mathrm{pop}}(r)
\le kq\pi_0\frac{H_r(u)}{Q(u)}\quad(r\ge u).
$$
For $r<u$, every cutoff is at least $u>r$, so the null rejection mass and FDP are zero. Rotational invariance and $v^\top Z\sim N(0,1)$ for each fixed unit vector give the exact identity $\mathbb E[H_R(u)]=Q(u)$. Taking expectations proves the displayed FDR upper bound without any numerical first-contact approximation.

For this dimension $M_d=1/(2\sqrt3)$. Write the target's coefficient of $q\pi_0$ as
$$
B_d=2+4M_d(1+104^{-2})\log312.
$$
$\log312>5$ and $\sqrt3<2$ give $B_5>2+5=7$. Here $e<3$ implies $e^5<243<312$.
Hence $B_d>7$ and the target right side $q\pi_0B_d+e^{-2u^2}$ strictly exceeds the upper bound just proved. All calculations deciding NOT are exact; floating-point diagnostics are unnecessary.

## Failure

NOT is the first failed check: the uniform subthreshold alternative law has FDR at most $7q\pi_0$, strictly below the proposed right side.
