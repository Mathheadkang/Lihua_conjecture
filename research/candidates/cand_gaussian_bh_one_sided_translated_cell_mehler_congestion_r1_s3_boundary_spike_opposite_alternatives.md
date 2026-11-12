---
type: candidate
title: Rank-one boundary spike with opposite-direction threshold alternatives
status: failed
target_asset: gaussian_bh_one_sided_translated_cell_mehler_congestion
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: d49b6ceedd94063add2326953562443ef9d47a5aaa10af748c68abcc336945a7
performed_by: unknown
created_at: '2026-11-10T22:52:57.718Z'
extension_version: 0.0.4
---

## Object

For every integer $N\ge3$, integer $2\le m<N$, and $0<q\le S(1)$, set $d=1$ and $u_r=S^{-1}(qr/N)$. Take $m$ identical true nulls with $a_i=1$, $\theta_i=0$ for $1\le i\le m$. For $m<j\le N$, take alternatives with $a_j=-1$ and $\theta_j=2u_j>0$. All $N$ physical tests are retained. Use the target's full forced-rank masks and its exact smoothing parameter.

The proposed violation is an arbitrarily large boundary value $H_q(0)$ arising from many valid forced ranks. The universally quantified conclusion being tested requires a single pair $C<\infty$, $0<q_0\le\min\{S(1),e^{-1}\}$ working for every finite $N,d,\theta,(a_i)$ and every $0<q\le q_0$, even when all parameters depend on $q$. Thus a violation would require unbounded $\sup_x T_{1/\log(1/q)}H_q(x)/(q\sqrt{\log(1/q)})$ as $q\downarrow0$ along admissible finite models, or failure of the mass identity. A large unsmoothed singleton value alone does not meet that requirement.

## Checks

### H1

Pass. $N,d$ are finite positive integers, and $Z\sim N(0,1)$.

### H2

Pass. Every direction has unit norm, all means are finite real numbers, and exactly the first $m$ tests are true nulls. The Gram covariance is positive semidefinite with unit diagonal and rank one. Opposite directions and positive alternative means are admissible edge cases of the stated hypotheses.

### H3

Pass. The level satisfies $0<q\le S(1)$, so $u_r\ge1$ for every physical rank $r$.

### H4

Pass. Use ordinary non-strict BH on all physical tests, forcing only the chosen null $i$ to zero. At $z=u_r+y$, $y\ge0$, all other $m-1$ null p-values satisfy the rank-$r$ threshold. If $r<m$, this implies $R_i(z)\ge m>r$.

For $r\ge m$, the rank-$r$ threshold has at least $r$ passing tests exactly when the first $r-m$ alternatives pass, with the empty alternative condition for $r=m$. For $r>m$, the last needed alternative has score $2u_r-z=u_r-y$, so it passes exactly when $y=0$. Hence for $y>0$ no $r>m$ can equal the forced BH rank at $z=u_r+y$.

At $z=u_m+y$, $y\ge0$, rank $m$ qualifies. No higher rank $k>m$ qualifies: its last needed alternative would require $2u_k-z\ge u_k$, or $u_k\ge z\ge u_m$, contrary to $u_k<u_m$. Thus $R_i(u_m+y)=m$.

At $y=0$, each $r\ge m$ does qualify at $z=u_r$, and no higher $k>r$ qualifies because that would require $u_k\ge u_r$. Consequently all those masks are valid exactly on the boundary, and
$$
H_q(0)=m\sum_{r=m}^N\frac{e^{-u_r^2/2}}r.
$$
For every $y>0$, however, only the $r=m$ terms survive, and their $m$ multiplicities cancel the $1/m$ factor:
$$
H_q(y)=e^{-u_m y-u_m^2/2},\qquad y>0.
$$
For $y<0$, $H_q(y)=0$ by the target's half-line mask.

### H5

Pass. Use an independent scalar standard normal $G$, $L=\log(1/q)$, $\tau=1/L$ and $\sigma^2=1-e^{-2/L}$. The Mehler argument has mean $\mu=e^{-1/L}x$ and positive variance $\sigma^2$. It assigns probability zero to the boundary singleton.

### NOT

Fail. The large boundary spike disappears under the required smoothing. Uniformly in $x$ and all parameters of this family,
$$
T_{1/L}H_q(x)
\le\frac{e^{-u_m^2/2}}{\sqrt{2\pi}\sigma}
\int_0^\infty e^{-u_m y}\,dy
=\frac{\phi(u_m)}{u_m\sigma}.
$$
Integration by parts gives the elementary Mills lower bound $S(u)\ge\phi(u)u/(u^2+1)$ for $u>0$. Since $u_m\ge1$, the last display is at most
$$
\frac{2S(u_m)}\sigma
=\frac{2qm}{N\sigma}
\le\frac{2}{\sqrt{1-e^{-2}}}\,q\sqrt L.
$$
Here $L\ge1$ because $q\le S(1)<e^{-1}$, and concavity of $s\mapsto1-e^{-2s}$ on $[0,1]$ gives $1-e^{-2/L}\ge(1-e^{-2})/L$. Thus this family satisfies part (b) with a universal constant even if $N,m$ vary arbitrarily with $q$.

Part (a) also holds in this family. The displayed almost-everywhere kernel integrates to $S(u_m)=qm/N$ by translating the Gaussian density. For the original BH procedure, if $z\ge u_m$, exactly the $m$ nulls are rejected. If any null is rejected at $z<u_m$, some qualifying rank $k>m$ must satisfy both $z\ge u_k$ (for the $m$ nulls) and $z\le u_k$ (for its last needed alternative), so $z=u_k$. This is a finite Gaussian-null set. Hence the original FDR is $P\{Z\ge u_m\}=qm/N$ as well.

## Failure

NOT fails: all extra translated rank cells occur only at the boundary singleton, while the positive-measure density is one exponential half-line kernel with a uniform Mehler bound.
