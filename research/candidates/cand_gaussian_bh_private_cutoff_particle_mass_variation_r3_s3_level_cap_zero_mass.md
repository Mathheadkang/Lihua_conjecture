---
type: candidate
title: >-
  Level-cap decrease with zero particle-mass intensity and an all-true normal
  kernel
status: failed
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 3
slot: 3
direction: drop_hypothesis
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:12:22.506Z'
extension_version: 0.0.4
---

## Object

Take the Hilbert space to be the real line, and set
$$
\sigma=s=1/4,\qquad a=1/5,\qquad q=S(1),\qquad
\pi=\nu=\delta_{(0,0,1)},\qquad \rho=0,\qquad \lambda=-1.
$$
For $a<r<2a$, put $t=(r-a)/a$ and $\chi_a(r)=3t^2-2t^3$; extend it by zero below $a$ and one above $2a$. The proposed obstruction is the simultaneous boundary case of zero particle-mass intensity and a one-sided decrease from the maximal allowed level. There is genuine level-driven rank response, unlike the board's zero-mean tag swaps.

Write $c=\sqrt{15}/4$, $u(r)=S^{-1}(r)$ and
$$
B_\epsilon(r)=\{S^{-1}(q(1-\epsilon)r)-c u(r)\}/\sigma.
$$
The background drops out: $H_X(z)=V_X(z)=S(z/c)$ for every $X$.

## Checks

### H1

The fixed parameters satisfy $\sigma,s>0$, $\sigma^2+s^2=1/8<1$, $0<a<1/4$, and $q=S(1)$. The specified cutoff is nondecreasing and continuously differentiable, with derivative zero at both joins and the required constant regions.

### H2

Both laws are deterministic probability laws on the closed lawful domain: the sole particle has true tag and zero mean, and zero Hilbert loading. Both second mean moments are zero. All parameters are chosen before Gaussian innovations.

### H3

For every sufficiently small positive $\epsilon$, $\epsilon\rho=0<a/2$, $\epsilon|\lambda|\le1/2$ and $q_\epsilon=q(1-\epsilon)\le q_{\max}$. The level direction is permitted at the cap. The mixture remains exactly $\pi$.

### H4

Use the approved actual largest non-strict rank and full fractional FDP conventions, as required in the pack. Here the conditional score kernel has strictly positive Gaussian density, its upper quantile is $Q(r)=c u(r)$, and the full FDP is one at every positive rank. Thus $f(r)=1$ for $0<r\le1$, and $f(0)=0$ under the stipulated zero-rank payoff convention. No conditional-background extremum or alternative rank optimization is substituted.

### NOT

The proposed obstruction fails: the exact cutoff derivative agrees with the displayed signed formula.

First, $B_\epsilon$ is strictly increasing on $[a,1)$. Indeed
$$
B_\epsilon'(r)=\frac{c m(u(r))-m(S^{-1}(q(1-\epsilon)r))}{\sigma r}.
$$
The Mills ratio $m(x)=\int_0^\infty e^{-xt-t^2/2}\,dt$ is decreasing. For $r\ge a$, $u(r)\le u(a)$, whereas $S^{-1}(q(1-\epsilon)r)\ge1$. The numerical inequalities used below have wide margins and can be checked directly from the Gaussian integral: $S(0.8)>0.2$, $\phi(0.8)<0.29$, $c>0.96$ and $m(1)<0.656$. Consequently
$$
c m(u(a))>0.96\frac{0.2}{0.29}>0.662>0.656>m(1).
$$
Hence $M_\epsilon(r)=B_\epsilon(r)$ for $r\ge a$. Also $B_\epsilon(r)\to+\infty$ as $r\uparrow1$, so there is no endpoint atom or escaping suffix minimum in the cutoff range.

The exact actual-rank survival formula and the integral representation of a bounded increasing cutoff now give
$$
\mathcal F^a_\epsilon=\int_a^{2a}\chi_a'(r)S(B_\epsilon(r))\,dr.
$$
On this compact interval implicit differentiation is uniform and
$$
\dot B(r)=\frac{m(u_q(r))}{\sigma},\qquad
\dot{\mathcal F}^a=-\frac1\sigma\int_a^{2a}\chi_a'(r)\phi(B(r))m(u_q(r))\,dr.
$$
This is exactly the target: its bulk term is zero because $\rho=0$, its active minimum on the cutoff range is $r$ itself, and $w=\chi_a'$. The level boundary does not introduce an extra term.

For completeness, the fixed-rank mass estimates and mass derivatives are identically zero here. The level displacement obeys
$$
0\le B_\epsilon(r)-B(r)\le\frac{2\epsilon m(1)}\sigma=\Delta_z
$$
by integrating the level derivative for $\epsilon\le1/2$; this yields the asserted survival brackets with zero horizontal displacement. All derivative exchanges just used are over the fixed compact interval $[a,2a]$, without an $X$ expectation to control. The moment derivative is zero. This object does not assert that its law is an attained global maximizer, so the maximum-conditional comparisons supply no contrary prediction. The approved finite endpoint recovery applies to the unchanged lawful, canonical zero-mean true law at each fixed decreased level.

## Failure

NOT fails: decreasing the level from its allowed cap with zero mass intensity gives precisely the claimed signed rank derivative, with no additional boundary term.
