---
type: candidate
title: Empty true sector with simultaneous inward level perturbation
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
slot: 1
direction: boundary_degenerate
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:12:22.506Z'
extension_version: 0.0.4
---

## Object

Take the one-dimensional Hilbert space, $\sigma=s=1/2$, $a=1/8$, $q=S(1)$, $\rho=1$, and $\lambda=-1$. Set
$$
\pi=\delta_{(1,0,0)},\qquad \nu=\delta_{(0,0,1)},\qquad
\pi_\epsilon=(1-\epsilon)\pi+\epsilon\nu,\qquad q_\epsilon=q(1-\epsilon).
$$
Use the admissible cutoff $\chi_a(r)=p((r-a)/a)$ on $[a,2a]$, zero below $a$, and one above $2a$, where $p(t)=3t^2-2t^3$. All parameter choices precede the innovations. The residual background disappears because $v=0$. Write $c=\sqrt3/2$,
$$
A(z)=S((z-1)/c),\qquad C(z)=S(z/c).
$$
Thus
$$
H_\epsilon=(1-\epsilon)A+\epsilon C,\qquad V_\epsilon=\epsilon C,\qquad C\le A.
$$
The proposed failure mechanism is a first-order rank contribution at the boundary where the initial true sector and initial payoff vanish, coupled to a nonzero inward level change. Unlike the board's coincident-kernel tag swaps, $A\ne C$ and both total kernels and levels change.

## Checks

### H1

The fixed regularizers satisfy $\sigma,s>0$, $\sigma^2+s^2=1/2<1$, $0<a<1/4$, and $q=q_{\max}$. The polynomial cutoff is nondecreasing and $C^1$, with derivative zero at its joining endpoints and with exactly the prescribed constant parts.

### H2

Both laws are deterministic Borel probability measures on the lawful marked unit ball: the false atom has strictly positive mean one, and the true atom has mean zero. Their second mean moments are $M_2(\pi)=1$ and $M_2(\nu)=0$. No false-tagged zero or representative ambiguity occurs.

### H3

The direction is fixed before all Gaussian observations, $\rho=1\ge0$, and $\lambda=-1$ is allowed at $q=q_{\max}$. For $0<\epsilon<1/16$, $\epsilon\rho<a/2$, $\epsilon|\lambda|<1/2$, and $0<q_\epsilon<q_{\max}$. The entire mixture is lawful and $M_2(\pi_\epsilon)=1-\epsilon$.

### H4

The integrated private variance is $s^2+\tau_s^2=3/4=c^2$ and each ordinary conditional score has variance $c^2+\sigma^2=1$. The kernels above are smooth, have strictly positive total densities, and are jointly measurable without any background version choices. Use their unique upper quantiles and the actual globally largest non-strict ranks from the stated definition, with the rank-one endpoint convention. In particular,
$$
Q_0(r)=1+cS^{-1}(r),\qquad
B_0(r)=2\{u_q(r)-1-cS^{-1}(r)\}.
$$
Since $C\le H_\epsilon\le A$,
$$
cS^{-1}(r)\le Q_\epsilon(r)\le1+cS^{-1}(r).
$$
Consequently the barriers diverge to $+\infty$ as $r\uparrow1$, uniformly for small $\epsilon$. Their convergence to $B_0$ is uniform on every compact interior rank interval, by strict positivity of the density and the implicit inverse. Thus the actual rank is well-defined, with no rank-one atom; this uses the actual suffix-minimum representation, rather than selecting a crossing branch.

### NOT

Fail: the full signed derivative equals the target formula, despite the vanishing initial true sector and the joint level change. Indeed $f_0=w_0=0$, while fixed-rank differentiation gives
$$
\dot f_0(r)=\frac{C(Q_0(r))}{r}.
$$
For every positive rank,
$$
f_\epsilon(r)=\epsilon\frac{C(Q_\epsilon(r))}{r},\qquad
0\le\frac{C(Q_\epsilon(r))}{r}\le1,
$$
because $H_\epsilon\ge C$. Hence $0\le\chi_a(R_\epsilon)f_\epsilon(R_\epsilon)/\epsilon\le1$.

Here is the needed rank-limit justification, including births of the actual largest rank. For a fixed bounded interval of common-noise values, the preceding endpoint bounds exclude all sufficiently large ranks below one, uniformly in small $\epsilon$. On the remaining compact ranks $[a/2,1-d]$, $B_\epsilon\to B_0$ uniformly. For any $h>0$, this sandwiches the qualifying ranks at $Z$ between the baseline qualifying ranks at $Z-h$ and $Z+h$ once $\epsilon$ is small. Thus the cutoff-relevant actual ranks converge at every continuity point of the nondecreasing baseline map $Z\mapsto R_0(Z)$. This map has at most countably many discontinuities, a Gaussian-null set. When limiting ranks are at or below $a$, the cutoff makes the payoff quotient vanish; at $a$ this follows from continuity of $\chi_a$. At limiting ranks above $a$, uniform inverse convergence and the rank limit give the ordinary continuous composition limit. Dominated convergence therefore yields
$$
\left.\frac{d}{d\epsilon}\right|_{0+}\mathcal F^a(\pi_\epsilon;q_\epsilon)
=\mathbb E_Z\!\left[\chi_a(R_0)\frac{C(Q_0(R_0))}{R_0}\right].
$$
The integrand is defined as zero for $R_0\le a$. This is precisely the asserted bulk term; the signed rank term is zero because $w_0=0$. The moment derivative also equals $-1=\rho\{M_2(\nu)-M_2(\pi)\}$.

## Failure

NOT fails: the initially empty true sector gives a bounded exact factorization of the perturbed payoff, and its derivative agrees with the claimed signed formula even with simultaneous inward level motion and actual-rank births.
