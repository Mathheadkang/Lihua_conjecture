---
type: candidate
title: Joint mass and level cancellation at the smallest Gaussian BH fold
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
slot: 2
direction: small_cases
statement_digest: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
performed_by: unknown
created_at: '2026-11-09T09:12:22.506Z'
extension_version: 0.0.4
---

## Object

Work in the one-dimensional Hilbert space, with both loadings zero. Set
$\sigma=1/2$, $s=1/4$, $q=1/10$, $c=\sqrt{1-\sigma^2}=\sqrt3/2$,
$\pi=\delta_{(0,0,1)}$, $\nu=\delta_{(1,0,0)}$, and $\rho=1$.
Write $u(r)=S^{-1}(r)$ and
$$
B(r)=\frac{u(qr)-c u(r)}{\sigma}.
$$
Let $t_*$ be its unique minimizer on $(0,1)$, equivalently the solution of
$$
q\frac{\phi(u(t_*))}{\phi(u(qt_*))}=c.
$$
Set $a=t_*/4$. Use $\chi_a=0$ on $[0,a]$, $\chi_a=1$ on $[2a,1]$,
and $\chi_a(r)=3x^2-2x^3$ for $x=(r-a)/a\in[0,1]$.
For $A(r)=S(u(r)-1/c)$, put
$$
d(r)=\frac{c\{A(r)-r\}}{\phi(u(r))},\qquad
\lambda=-\frac{d(t_*)}{m(u(qt_*))}.
$$
Thus $\pi_\epsilon=(1-\epsilon)\pi+\epsilon\nu$ and
$q_\epsilon=q(1+\epsilon\lambda)$ are fixed before observations.

This tests a moderate distinct-kernel insertion with a simultaneous negative
level change chosen to cancel its first-order fold-height response. The
earlier fixed-level distant-insertion calculation does not cover this
cancellation, since the level change removes its monotone rank response.

## Checks

### H1

The fixed regularizers satisfy $\sigma^2+s^2=5/16<1$ and
$q=0.1<S(1)$. The scalar equation gives
$t_*\simeq0.000395058507654179$, so $a\simeq0.00009876462691354475$
lies in $(0,1/4)$. The specified cutoff is nondecreasing and $C^1$.

For completeness, uniqueness of $t_*$ follows by putting
$J(r)=q\phi(u(r))/\phi(u(qr))=m(u(qr))/m(u(r))$.
It decreases strictly from one to zero. Indeed
$$
(\log J)'(r)=\frac1r\left\{\frac{u(r)}{m(u(r))}
-\frac{u(qr)}{m(u(qr))}\right\}<0.
$$
When $u(r)<0$ the sign is immediate. For nonnegative arguments,
$x/m(x)$ is strictly increasing: its derivative has numerator
$(1-x^2)m(x)+x>0$, using $m(x)<1/x$ when $x>1$ and the immediate
positive expression when $0\le x\le1$.
Consequently $B'=(c-J)/(\sigma\phi(u(r)))$ changes sign only once.
Both endpoint limits of $B$ are $+\infty$.

### H2

Both laws are deterministic Borel probabilities with lawful marks and
loadings in the unit ball. Their second mean moments are respectively
zero and one. The residual conditional kernels, independent of $X$, are
$H_0(y)=V_0(y)=S(y/c)$ and $H_\nu(y)=S((y-1)/c)$, $V_\nu(y)=0$.
The private variance is $c^2=s^2+\tau_s^2$ as required.

### H3

The constants $\rho=1$ and
$\lambda\simeq-34.055926912543946$ are finite and deterministic.
For all sufficiently small positive $\epsilon$,
$\epsilon<a/2$, $\epsilon|\lambda|<1/2$, and
$0<q_\epsilon<q<q_{\max}$. The endpoint laws and levels are lawful.

### H4

Use the actual largest crossing. At the baseline its rank is zero for
$Z<B(t_*)$ and is the unique solution $r\ge t_*$ of $B(r)=Z$ for
$Z\ge B(t_*)$. Thus every positive baseline rank exceeds $2a$.
There is no background randomness in these kernels. The object is in the
approved privately smoothed directing class; all kernels are finite
Gaussian mixtures and hence jointly measurable, with no representative
issue.

### NOT

The attempted violation is that a fold-height cancellation might leave
an extra first-order rank term in the complete signed derivative.
It does not. Fixed-rank differentiation gives exactly
$$
\dot Q(r)=d(r),\qquad \dot f(r)=-A(r)/r.
$$
The baseline $f$ is identically one. Since $\chi_a'$ is supported on
$[a,2a]\subset(0,t_*)$, every suffix minimum relevant to the rank term
is the same interior fold. The definition of $\lambda$ gives
$$
\dot M(r)=\frac{-\lambda m(u(qt_*))-d(t_*)}{\sigma}=0
\quad(a\le r\le2a).
$$
The proposed derivative therefore equals
$$
-J_*=-\int_{t_*}^1\frac{A(r)}r\phi(B(r))B'(r)\,dr.
$$
This is also the direct derivative. One can recompute it without choosing
any rank other than the largest crossing as follows. Define
$$
H_\epsilon(y)=(1-\epsilon)S(y/c)+\epsilon S((y-1)/c),\qquad
z_\epsilon(y)=\{u(q_\epsilon H_\epsilon(y))-y\}/\sigma.
$$
Let $y_\epsilon$ be the interior minimizing fold near $c u(t_*)$.
Its persistence as the unique global minimum follows analytically.
The score coupling with shifts in $[0,1]$ gives
$c u(r)\le Q_\epsilon(r)\le1+c u(r)$, so $B_\epsilon$ tends to
$+\infty$ uniformly at both endpoints when $q_\epsilon$ stays in a
compact interval about $q$. On the remaining compact interval its
first two derivatives converge uniformly to those of $B$.
The baseline minimum is nondegenerate, since
$B''(t_*)=-J'(t_*)/(\sigma\phi(u(t_*)))>0$.
Thus the implicit function theorem and the strict baseline minimum give
one persistent global minimum. On the branch $y\le y_\epsilon$, no
extra turning point appears: on compact sets this follows from the
strict sign of the baseline derivative away from the fold, and as
$y\to-\infty$ one has $H_\epsilon(y)\to1$ and
$H_\epsilon'(y)\to0$ uniformly, hence
$z_\epsilon'(y)\to-1/\sigma$ uniformly.
On the upper-rank branch, $y\le y_\epsilon$, the full fractional payoff is
$(1-\epsilon)S(y/c)/H_\epsilon(y)$. For sufficiently small $\epsilon$
the fold rank remains above $2a$, so
$$
F_\epsilon^a=\int_{-\infty}^{y_\epsilon}
\frac{(1-\epsilon)S(y/c)}{H_\epsilon(y)}
\phi(z_\epsilon(y))[-z_\epsilon'(y)]\,dy.
$$
The upper-end boundary term vanishes since $z_\epsilon'(y_\epsilon)=0$.
At $\epsilon=0$ the payoff factor equals one. Its fixed-$y$ derivative is
$-S((y-1)/c)/S(y/c)$, while the integral of the remaining density is
$S(z_\epsilon(y_\epsilon))$, whose derivative is zero by the tuned fold
condition. Changing variables to $r=S(y/c)$ gives precisely $-J_*$.
Finite Gaussian tails justify differentiation in this particular scalar
integral; its lower tail has Gaussian decay, including the derivatives.

As a diagnostic, scalar composite Simpson quadrature on
$[-10,y_\epsilon]$ with 12000 panels gives
$F_0^a\simeq0.018690030759527073$ and $-J_*\simeq-0.13509669256956386$.
The respective full-payoff difference quotients for
$\epsilon=10^{-5},2\cdot10^{-6},4\cdot10^{-7}$ are
$-0.1347736461,-0.1350321562,-0.1350837882$.
These are numerical diagnostics, not a general domination argument.
The first-order cancellation agrees with the asserted full derivative;
this object does not exhibit the attempted violation. General competing
minima, endpoint interchange, and arbitrary-background uniform bounds
are outside this check.

## Failure

NOT fails: the simultaneous level countershift cancels the fold-height derivative exactly, leaving the asserted signed bulk derivative and no additional first-order rank contribution.
