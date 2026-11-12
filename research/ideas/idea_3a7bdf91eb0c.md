---
type: idea
title: Global first-contact transport for isotropic spherical Gaussian populations
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - candidate-complete-proof
  - population-only
  - all-pairs-comparison
---

Candidate for the separately approved supporting population goal spherical_isotropic_population_bh_bound. This draft idea contains the local candidate argument so native proof stages can request its full text with show rather than scan local notes. Source: research-local/spherical_radial_bh_global_population_bound_20261104.md, SHA8fa9133ab87e6f718f36e1b368b7619999d338341562fca0f6822c11a6385188. Independent local first-contact reconstruction: research-local/radial_first_contact_viability_gate_20261104.md. Independent transport-hypothesis audit: research-local/radial_tail_transport_hypothesis_exact_audit_20261104.md. The latter proves that a.e. derivative control alone is insufficient; the all-pairs comparison is essential to exclude positive Cantor variation. No finite Gaussian vector approximation, unrestricted theorem or approval is asserted.

# Candidate global bound for the radial isotropic population class

Date: 2026-11-04. Local mathematical continuation of
`spherical_radial_bh_gate_20261104.md`; no research node, loop state,
settings, or approval record is changed. This is a self-contained
candidate argument, not an independently verified theorem verdict.

## Restricted class and claimed bound

Let d >= 4 and let Z be standard Gaussian in R^d, with radius R. The null
loading population is uniform on the unit sphere. For each absolute
alternative mean mu, its loading directions are also uniform on that
sphere, with zero residual variance. The distribution of mu is fixed
with respect to R and independent of loading direction. It can depend
on q and d, have infinitely many atoms, or have unbounded support.

Let W be the resulting probability distribution of absolute means,
including true-null mass pi_0 at zero. Let U be uniform on the sphere and

$$
H_r(y)=P(rU_1\geq y),\qquad
g_r(y)=\frac{c_d}{r}\left(1-\frac{y^2}{r^2}\right)_+^{(d-3)/2},
\qquad c_d=\frac{\Gamma(d/2)}{\sqrt\pi\Gamma((d-1)/2)}.
$$

Extend H_r to one below -r and zero above r, and g_r to zero outside
(-r,r). Put

$$
A_\mu(r,x)=H_r(x-\mu)+H_r(x+\mu),\qquad
F(r,x)=\int A_\mu(r,x)\,dW(\mu).
$$

Write Q=bar-Phi, h=phi/Q, u=Q^{-1}(q/2). Define the population BH
selection x(r) as the smallest x >= u for which

$$
F(r,x)\geq \frac{2Q(x)}q.
$$

When no such finite x exists there are no rejections. A finite minimum
exists whenever the feasible set is nonempty, by continuity on a compact
interval containing any feasible point. Its boundary satisfies equality,
including the endpoint x=u, where equality means F=1. The largest BH
p threshold is 2Q(x(r)); hence the smallest x convention is essential.
Define the population conditional FDP to be

$$
q\pi_0\frac{H_r(x(r))}{Q(x(r))}
$$

when the selection is finite, and zero otherwise. It is at most one.

The candidate bound, uniform over this population class, is: for u>=104,

$$
\operatorname{FDR}_{\rm pop}
\leq q\pi_0\left\{2+4M_d(1+u^{-2})\log(3u)\right\}
+e^{-2u^2},
$$

where

$$
M_d=\frac{c_d}{\sqrt{d-2}}
\left(\frac{d-3}{d-2}\right)^{(d-3)/2}\leq1.
$$

Thus this restricted class has FDR O(q log u)=o(q u), uniformly in d>=4.
This is a population statement. No finite-vector approximation theorem,
or statement for nonisotropic alternatives, is asserted.

## Pointwise differential budget, including D=0

Set

$$
b_\mu=g_r(x-\mu)+g_r(x+\mu),\quad
d_\mu=(x-\mu)g_r(x-\mu)+(x+\mu)g_r(x+\mu),
\quad B=\int b_\mu\,dW,\quad D=\int d_\mu\,dW.
$$

Then F_x=-B and F_r=D/r. These derivatives are continuous on compact
r>0,x>0 rectangles, even for unbounded W: the density terms vanish
unless mu lies in a bounded interval depending on the rectangle, and
the displayed integrands have uniform bounds. The density g_r is
continuous at its support endpoints because d>3.

For any 0<ell<r and x>=ell, put

$$
K=\frac{2M_d}{\ell}+\frac{2g_r(0)}{H_r(\ell)}.
$$

If D<=0, then

$$
-D\leq 2M_dF,\qquad B\leq KF.
$$

Indeed, a negative d_mu requires mu>x; then A_mu>=1/2 and
(d_mu)_-<=M_d. Consequently integral (d_mu)_- dW<=2M_dF.
When D<=0 the positive part has no larger integral. For mu<=x-ell,
b_mu<=d_mu/ell. For the complementary means, A_mu>=H_r(ell) and
b_mu<=2g_r(0). Integrate these bounds. This proof includes D=0.

Let f(r,x)=F(r,x)-2Q(x)/q. At a zero of f,

$$
f_x=h(x)F-B,\qquad f_r=D/r.
$$

On any radius interval where ell<=u and K<=u/2, every zero with D<=0
satisfies f_x>=xF/2>0. In particular a tangency f_x=0 has D>0.

## Global first-selection comparison

On such a radius interval, if x(r_1) is finite and r_2>=r_1, then
x(r_2) remains finite and

$$
x(r_2)^2\leq x(r_1)^2+8M_d\log(r_2/r_1).
$$

Proof. Start X(r_1)=x(r_1), and for epsilon>0 solve

$$
X'(r)=\frac{4M_d}{rX(r)}+\varepsilon.
$$

Consider the continuous compact-domain maximum
M(r)=max_{u<=x<=X(r)} f(r,x). Initially M>=0. At any radius where M=0,
choose a maximizer. There are three possibilities.

1. At an interior maximizer f_x=0. The preceding pointwise budget
   forces D>0, so f_r>0. Keeping that x fixed gives f>0 immediately
   to the right.
2. At the upper endpoint x=X(r), f_x>=0. If D>0, then
   f_r+X'f_x>0. If D<=0, then f_x>=xF/2 and -D<=2M_dF, so
   f_r+(4M_d/(rx))f_x>=0. The additional epsilon f_x is strictly
   positive. Moving along X again gives f>0 immediately to the right.
3. The lower endpoint x=u cannot be a maximizer when X>u: f(r,u)=0
   implies F(r,u)=1. Since F<=1 globally and is differentiable,
   F_x=F_r=0 there; hence f_x=2phi(u)/q>0. At the initial degenerate
   interval X=u, the upper-endpoint argument applies instead.

Therefore M cannot have a negative open component to the right: its
left endpoint would have M=0 and the preceding argument would give
M>0 immediately to its right. Thus the moving compact interval always
contains a feasible point. Let epsilon decrease to zero. Solutions X
converge to sqrt(x(r_1)^2+8M_d log(r/r_1)); compactness and continuity
preserve a feasible point below this limit. The comparison follows.

This also handles arbitrary root switches, tangencies, and escape to
infinity: after any finite first selection, feasibility persists and
the comparison supplies a finite upper bound. The radii with finite
selection therefore form an upper interval, possibly with its left
endpoint omitted. No separate regular-root assumption is needed.
For a finite radius interval [a,b], choose T>max{b,u}, set x=+infinity
when there is no selection, and put y(r)=min{x(r),T}. The all-pairs
comparison implies

$$
y(r_2)^2-y(r_1)^2\leq8M_d\log(r_2/r_1)\qquad(a\leq r_1\leq r_2\leq b).
$$

Indeed, if x(r_1)<T use the comparison and truncate its upper bound;
otherwise y(r_1)=T and the claim is immediate. Thus
y(r)^2-8M_d log r is nonincreasing throughout [a,b], including before
the first finite selection. It follows that y is of bounded variation,
all its jumps are downward, and

$$
(y'(r))_+\leq\frac{4M_d}{ry(r)}
$$

almost everywhere; there is no positive singular variation. The
all-pairs comparison is crucial here: an almost-everywhere slope bound
and absence of positive jumps alone would not exclude a singular
continuous increase.

## Conditional radial transport

For finite x>0, define

$$
C(r,x)=P(\|Z\|\leq r\mid Z_1\geq x),\qquad
k(r,x)=\frac{f_R(r)H_r(x)}{Q(x)}.
$$

Then C_r=k. Writing V as chi-square_(d-1), direct differentiation
of the conditioning integral gives

$$
C_x(r,x)=h(x)\{C(r,x)-P(V\leq r^2-x^2)\}\in[-h(x),0],
$$

where the chi-square CDF is zero at negative arguments. The sign
follows because conditioning Z_1>=x averages the decreasing function
z -> P(V<=r^2-z^2) over z>=x.

On a radius interval [a,b] from the previous section, take the truncated
y with T>max{b,u}. Whenever x(r)>=T, both C(r,T) and k(r,T) are zero
because T>r. Thus k(r,y(r)) equals the selected density, with zero used
for no selection. The BV chain rule for C(r,y(r)) gives

$$
\int_a^b k(r,y(r))\,dr
\leq 1+\int_a^b h(y(r))(y'(r))_+\,dr
\leq 1+4M_d(1+u^{-2})\log(b/a).
$$

For completeness, downward jumps of y cause nonnegative jumps of C;
its continuous singular decrease likewise contributes nonnegatively
because C_x<=0. These terms only reduce the required upper bound on
the density integral. Positive variation of y is absolutely continuous
and has the preceding derivative bound. Finally use 0<=C<=1 and the
normal Mills inequality h(y)<=y+1/y. Point values at countably many
jumps do not affect the density integral.

The truncation handles root birth from infinity and absence of roots
without a separate limiting argument at a birth radius.

## Uniform cutoffs and end of the bound

Choose

$$
r_0=\max\{u,52\sqrt d/u\},\qquad L=\sqrt d+2u,
\qquad \ell=r/(2\sqrt d).
$$

On r_0<=r<=L and u>=104, ell<=u. Let
a_d=P(U_1>=1/(2sqrt(d))). The sphere moments give
E(dU_1^2)=1 and E[(dU_1^2)^2]=3d/(d+2)<=3. Paley-Zygmund and symmetry
therefore yield a_d>=3/32. Also c_d<=sqrt(d): for Y~Gamma((d-1)/2,1),
c_d=E sqrt(Y)/sqrt(pi)<=sqrt((d-1)/(2pi)) by Jensen. The same bound in
the explicit formula for M_d shows M_d<=1 for d>=4. Consequently

$$
K=\frac{4M_d\sqrt d}{r}+\frac{2c_d}{ra_d}
\leq \frac{26\sqrt d}{r}\leq u/2.
$$

Thus the global comparison and transport apply over [r_0,L], and
L/r_0<=3u. Their middle-region FDR contribution is at most

$$
q\pi_0\{1+4M_d(1+u^{-2})\log(3u)\}.
$$

For r<=u the null tail is zero. If r_0>u, then u>=104 gives
r_0^2-u^2<=d-3. The exact envelope from the preceding local note,
or its direct Bayes-density proof, gives

$$
\int_0^{r_0} f_R(r)\frac{H_r(x(r))}{Q(x(r))}\,dr
\leq P(V\leq r_0^2-u^2)\leq1
$$

on finite selections, with zero contribution otherwise. The lower
region therefore contributes at most q pi_0.

Finally chi-square Chernoff gives, for any t>=0,

$$
P(R\geq\sqrt d+t)
\leq\exp\left[-\frac{2\sqrt d\,t+t^2-2d\log(1+t/\sqrt d)}2\right]
\leq e^{-t^2/2}.
$$

At t=2u, the upper-region FDR is at most e^{-2u^2}. Summing the three
regions proves the displayed candidate population bound. Since
q=2Q(u), e^{-2u^2}=o(q), while log u=o(u).

## Remaining scientific boundary

This calculation globalizes the restricted spherical-mixture gate;
it does not establish the unrestricted conjecture, and supplies no
counterexample. Arbitrary Gaussian alternatives need not have isotropic
loading distributions conditional on each mean, and their conditional
population tail can depend on the direction of Z. No transfer from
this continuum population to finite deterministic Gaussian vectors is
proved here. An independent cold verification of the global argument
and the BV chain step is still appropriate before promoting it to a
research asset.
