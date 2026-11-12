---
type: candidate
title: Single-null scalar population tests the complete inward loading response
status: failed
target_asset: gaussian_bh_actual_radial_loading_signed_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 7fdc4735d0d5e381ad9fbb0ee8f7ab5df233763c161d5f77194d54300e4e7cac
performed_by: unknown
created_at: '2026-11-09T18:19:30.254Z'
extension_version: 0.0.4
---

## Object

Take the Hilbert space $\mathcal H=\mathbb R$, $\pi=\delta_{(0,1,1)}$, $\sigma=2/5$, $s=3/10$, $a=1/10$, and $q=S(1)$. Thus $\tau_s^2=3/4$. Set $\chi_a(r)=0$ for $r\le a$, $\chi_a(r)=3y^2-2y^3$ for $a<r<2a$, where $y=(r-a)/a$, and $\chi_a(r)=1$ for $r\ge2a$. This smallest nonstationary scalar population tests a possible mismatch between the direct cutoff-response derivative and the all-minima signed formula; it is not claimed to be an extremum.

## Checks

### H1

The fixed parameters satisfy $\sigma,s>0$, $\sigma^2+s^2=1/4<1$, $0<a<1/4$, and $0<q=q_{\max}$. The displayed cutoff is nondecreasing and $C^1$ with the required constant endpoint pieces.

### H2

The singleton law is deterministic Borel, has unit-ball loading, true tag $\ell=1$ with lawful mean $\theta=0$, and $M_2=0$. It is chosen before the independent standard Gaussians $X=X(1)$ and $Z$. The underlying Hilbert space is nonzero and separable.

### H3

Use exactly the physical transport $v_\epsilon=1-\epsilon$ and

$$
c_\epsilon^2=s^2+\tau_s^2(2\epsilon-\epsilon^2),\qquad \alpha_\epsilon=\tau_s(1-\epsilon).
$$

The private and common variances satisfy $c_\epsilon^2+\alpha_\epsilon^2+\sigma^2=1$. Here $\dot c=\tau_s^2/s$ and $\dot\alpha=-\tau_s$.

### H4

Retain the actual globally largest non-strict rank and full FDP. Since every particle is true-tagged, $f_{\epsilon,X}(r)=1$ for $r>0$ and the payoff is $\chi_a(R_\epsilon)$. For $u(r)=S^{-1}(r)$ and

$$
b_\epsilon(t)=u(qt)-c_\epsilon u(t),
$$

one has $Q_{\epsilon,X}(t)=\alpha_\epsilon X+c_\epsilon u(t)$ and $B_{\epsilon,X}(t)=[b_\epsilon(t)-\alpha_\epsilon X]/\sigma$. This is an exact conditional Gaussian calculation, not a replacement of the largest-rank selector. No extremality assumption or extremal sign conclusion is invoked.

### NOT

The tested response mismatch does not occur. Put $c=s$. The function $\kappa(t)=q\phi(u(t))/\phi(u(qt))$ decreases strictly from one to zero. Indeed $\kappa=m(u(qt))/m(u(t))$ and

$$
\frac{d}{dt}\log\kappa(t)=\frac{u(t)m(u(t))-u(qt)m(u(qt))}{t}<0.
$$

For this inequality, $(zm(z))'=(1+z^2)m(z)-z=\int_0^\infty y^2e^{-zy-y^2/2}\,dy>0$. Thus $b_0$ has its unique global minimum at the unique $t_*$ satisfying $\kappa(t_*)=c$. The suffix minimizer is $\max(r,t_*)$, with no discarded branch. Elementary normal-CDF evaluation and bisection give $t_*\approx0.6882190445>2a$; the strict inequality also follows directly from $\kappa(2a)>c$.

Consequently, for sufficiently small $\epsilon$, the actual rank is either zero or at least $t_{*,\epsilon}>2a$, up to the Gaussian-null tangent level. The cutoff payoff is exactly the event of any positive rank. Write $b_*=u(qt_*)-cu(t_*)$ and $\beta=\sqrt{1-c^2}$. Integrating the two independent Gaussian common terms gives

$$
\mathcal F^a(\pi_\epsilon)=S\!\left(\frac{b_\epsilon(t_{*,\epsilon})}{\sqrt{1-c_\epsilon^2}}\right),
$$

and hence the direct derivative is

$$
\dot{\mathcal F}^a=-\phi(b_*/\beta)\frac{\tau_s^2\{cu(qt_*)-u(t_*)\}}{c\beta^3}.
$$

On the support $(a,2a)$ of $w_X=\chi_a'$, the target's all-minima quantities are exactly

$$
M_X(r)=\frac{b_*-\tau_sX}{\sigma},\qquad
\dot M_X(r)=\frac{\tau_sX-(\tau_s^2/c)u(t_*)}{\sigma}.
$$

The bulk term is zero because $\dot f_X=0$, and $\int_a^{2a}\chi_a'(r)\,dr=1$. Gaussian convolution therefore makes the target's rank term equal to the direct derivative displayed above. Differentiation under this one-dimensional Gaussian integral is justified by the bound $C(1+|X|)$ on its differentiated integrand, for a finite parameter-dependent $C$. Numerically both expressions give approximately $-0.3480485316$. The numerical values are diagnostics; the equality follows from the displayed exact Gaussian formulas. This check addresses this proposed response mismatch, not the general theorem or the extremal comparison clause.

## Failure

NOT: the direct derivative of this lawful one-atom scalar cutoff payoff agrees exactly with the asserted complete signed actual-rank formula.
