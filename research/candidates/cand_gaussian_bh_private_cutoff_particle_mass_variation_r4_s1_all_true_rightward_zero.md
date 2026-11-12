---
type: candidate
title: All-true rightward mass insertion at the zero-mean boundary
status: failed
target_asset: gaussian_bh_private_cutoff_particle_mass_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 4
slot: 1
direction: boundary_degenerate
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:17:51.845Z'
extension_version: 0.0.4
---

## Object

Take the one-dimensional Hilbert space, with all loading vectors zero, and set
$$
\sigma=s=\tfrac12,\qquad c=\sqrt{1-\sigma^2}=\tfrac{\sqrt3}{2},\qquad
q=S(1),\qquad a=\tfrac18.
$$
Use the cutoff zero on $[0,a]$, one on $[2a,1]$, and $3t^2-2t^3$ on the intervening interval, where $t=(r-a)/a$. Put
$$
\pi=\delta_{(-1,0,1)},\qquad \nu=\delta_{(0,0,1)},\qquad
\rho=1,\quad\lambda=0,\quad 0<\epsilon<1/16.
$$
This is an all-true, rightward contamination toward the lawful true-null boundary. Unlike a kernel-preserving tag swap, it changes every interior total quantile. Unlike the board's stochastically leftward contamination, it lowers the barriers; that earlier raising-barrier argument does not apply.

## Checks

### H1

The fixed parameters satisfy $\sigma,s>0$, $\sigma^2+s^2=1/2<1$, $0<a<1/4$, and $0<q=q_{\max}$. The specified cutoff is nondecreasing and $C^1$, since the transition derivative is $6t(1-t)/a$ and vanishes at both ends.

### H2

Both laws are deterministic probabilities on the lawful marked unit ball: their sole tag is $\ell=1$, and both means are nonpositive. Their second mean moments are $M_2(\pi)=1$ and $M_2(\nu)=0$. Zero loading makes the residual background irrelevant. The Gaussian private variance is $c^2=3/4\ge s^2$, and the total score variance is $c^2+\sigma^2=1$.

### H3

The perturbation is exactly $(1-\epsilon)\pi+\epsilon\nu$, chosen before innovations, with constant level $q_\epsilon=q$. The restrictions $\epsilon\rho<a/2$, $\epsilon\rho<1$, $\epsilon|\lambda|\le1/2$, and the one-sided level restriction at the cap all hold. In particular the inserted zero mean is true tagged, so no false-zero repair is being presumed.

### H4

The prerequisite actual-largest-rank identification applies to these finite-support directing laws. Its kernels are explicitly
$$
H_\epsilon(z)=V_\epsilon(z)
=(1-\epsilon)S((z+1)/c)+\epsilon S(z/c).
$$
They are smooth with strictly positive densities and are independent of the background representative. Consequently $f_\epsilon(r)=1$ for every $0<r\le1$, while the payoff is zero at rank zero. All ranks used below are the actual globally largest non-strict ranks, not a chosen crossing branch.

### NOT

The proposed failure of the full signed derivative does not occur. Write $z_r=S^{-1}(r)$. At the base law,
$$
Q_0(r)=-1+cz_r,\qquad
p(r):=\dot Q(r)
=c\frac{S(z_r-1/c)-r}{\phi(z_r)}>0.
$$
This follows by differentiating the displayed affine tail at its unique quantile; on every compact rank interval the differentiation is uniform. Also $\dot f(r)=0$, including its rank-one endpoint convention. Thus the asserted bulk term is exactly zero, despite the nonzero quantile response.

There is an elementary compact envelope calculation in this example, so no general endpoint/interchange assertion is needed to test the formula. Stochastic ordering gives, simultaneously for all $0<r<1$,
$$
-1+cz_r\le Q_\epsilon(r)\le cz_r,
\qquad
\frac{u_q(r)-cz_r}{\sigma}\le B_\epsilon(r)\le B_0(r).
$$
The lower barrier tends to $+\infty$ as $r\uparrow1$, uniformly in $\epsilon$. Comparison with $B_\epsilon(r)\le B_0(r)$ for $r\in[a,2a]$ therefore confines every suffix minimizer relevant to this interval to a single compact interval $[a,b]$, $b<1$. On it $B_\epsilon=B_0-\epsilon p/\sigma+o(\epsilon)$ uniformly. Taking minima on that compact set yields, for each $r\in[a,2a]$,
$$
\dot M(r)=-\frac1\sigma\max_{t\in\mathcal A_0(r)}p(t),
$$
with a uniformly bounded difference quotient. This retains every active minimizer, without assuming uniqueness.

Since all discoveries are true, the layer-cake identity and the actual-rank survival identity give exactly
$$
\mathcal F^a(\pi_\epsilon)
=\mathbb E\chi_a(R_\epsilon)
=\int_a^{2a}\chi_a'(r)S(M_\epsilon(r))\,dr.
$$
The preceding compact bound permits differentiation under this finite integral. Therefore
$$
\dot{\mathcal F}^a
=\frac1\sigma\int_a^{2a}\chi_a'(r)\phi(M_0(r))
\max_{t\in\mathcal A_0(r)}p(t)\,dr
=-\int_a^1w_0(r)\phi(M_0(r))\dot M(r)\,dr,
$$
because $w_0=\chi_a'$ vanishes outside $[a,2a]$. This is precisely the stated full signed formula with zero bulk term. Its value is positive: $p>0$, $\phi(M_0)>0$, and $\chi_a'>0$ inside the transition interval. Thus rank motion is present and is fully accounted for.

This calculation tests the full derivative in a nonempty all-true boundary family. It does not settle general-background domination, arbitrary competing-minimum configurations, attained-maximizer comparisons, or finite endpoint recovery.

## Failure

NOT fails: all-true rightward insertion at the lawful zero-mean boundary has a nonzero actual-rank response exactly equal to the asserted signed rank term, with zero bulk term.
