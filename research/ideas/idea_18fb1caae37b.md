---
type: idea
title: >-
  Complete candidate for finite-array transfer with spherical conditional CDF
  limits
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
  - gaussian_bh_two_sided_sharp_upper
tags:
  - candidate-complete-proof
  - fixed-q-large-N
  - finite-gaussian-transfer
---

Unverified full companion candidate, developed from idea_043d93c14802. Source research-local/spherical_finite_array_transfer_candidate_20261104.md SHAa7a651b3b44567449b3d966b33455074bd2960465d6f579b6885658bbd043ef4. Conditional on population CORE transport estimate(MT), not merely the final population upper bound. A future native plan must rederive/adapt the core estimate and explicitly preserve fixed q,d,W before N→infinity, null labels, exact largest rank and deterministic Gaussian covariance. No unrestricted theorem, no uniform finite-N rate, and no approval asserted.

# Candidate transfer from spherical populations to deterministic finite Gaussian arrays

Date: 2026-11-04. Independent bounded proof probe. This local candidate does
not change any research node, plan, definition, loop state, settings, or
approval record. It is not a native verification verdict. The explicit
constant below remains conditional on the population middle-region transport
estimate currently being checked separately.

## Frozen inputs and exact scope

- Native read-only `show idea_043d93c14802`: underlying file
  `research/ideas/idea_043d93c14802.md`, SHA-256
  `ce07ac96e56df9bf082fbe0ece8b881faf7de41819559102892294020ccf7e46`.
- Population model, differential budget, and proposed middle-region estimate:
  `research-local/spherical_radial_bh_global_population_bound_20261104.md`,
  SHA-256
  `8fa9133ab87e6f718f36e1b368b7619999d338341562fca0f6822c11a6385188`.
- The workspace has no Git repository; `git rev-parse HEAD` and `git status`
  both reported that fact. Only this previously nonexistent local file is
  written.

Fix q in (0,1), an integer d >= 4, and a probability measure W on finite
nonnegative means [0,infinity). All limits in N below hold with these three
objects fixed. Let pi_0 = W({0}), Q = bar-Phi, and u = Q^{-1}(q/2). Let
Z ~ N_d(0,I_d), R = ||Z||, and U uniform on S^{d-1}. Define

$$
H_r(y)=P(rU_1\ge y),\qquad
F(r,x)=\int[H_r(x-\mu)+H_r(x+\mu)]\,dW(\mu).
$$

For 0 < t < 1 put x_t = Q^{-1}(t/2), and set

$$
G_r(t)=F(r,x_t),\qquad G^0_r(t)=2\pi_0H_r(x_t).
$$

Extend G_r and G^0_r continuously to [0,1]. For r > 0 this extension is
valid even for an atomic or unbounded W: the sphere projection has no atoms,
every mean is finite, and mixing atomless conditional distributions remains
atomless. The exceptional Gaussian point Z=0 has probability zero.

For each N take deterministic means mu_{j,N} >= 0 and deterministic unit
vectors v_{j,N} in R^d, and define the exact Gaussian vector

$$
T_{j,N}=\mu_{j,N}+v_{j,N}^{\mathsf T}Z,
\qquad p_{j,N}=2Q(|T_{j,N}|),\quad 1\le j\le N.
$$

Its covariance V_N V_N^T is positive semidefinite with unit diagonal and
rank at most d. No positive-definiteness assertion is made. The null set is
I_{0,N}={j:mu_{j,N}=0}. Define total and null empirical sub-CDFs

$$
G_N(t;z)=\frac1N\sum_{j=1}^N1\{p_{j,N}(z)\le t\},\qquad
G_N^0(t;z)=\frac1N\sum_{j\in I_{0,N}}1\{p_{j,N}(z)\le t\}.
$$

The deterministic-array hypothesis is, for Gaussian-almost every z,

$$
\sup_{0\le t\le1}|G_N(t;z)-G_{\|z\|}(t)|\longrightarrow0,
\qquad
\sup_{0\le t\le1}|G_N^0(t;z)-G^0_{\|z\|}(t)|\longrightarrow0.\tag{UC}
$$

This hypothesis includes null-label convergence; convergence of means and
directions without a label condition is not silently substituted for it.
Section 7 proves that deterministic sequences satisfying (UC) exist.

## 1. Exact finite BH identities and positive threshold limits

Write

$$
K_N=\max\bigl(\{k\in\{1,\ldots,N\}:
  G_N(qk/N;Z)\ge k/N\}\cup\{0\}\bigr),
\qquad t_N=qK_N/N.
$$

BH rejects p <= t_N. If K_N > 0, exactly K_N p-values are <= t_N,
including when there are ties: if their number were l > K_N, then
p_(l) <= t_N <= ql/N would make l feasible, contradicting maximality.
Consequently

$$
G_N(t_N;Z)=t_N/q,\qquad
\operatorname{FDP}_N(Z)=q\,G_N^0(t_N;Z)/t_N\quad(t_N>0).\tag{1}
$$

Use FDP_N=0 if t_N=0. Fix a z for which (UC) holds and put r=||z||>0.
If a subsequence t_N converges to t>0, (UC), continuity, and (1) imply

$$
G_r(t)=t/q,\qquad
\operatorname{FDP}_N(z)\longrightarrow
q\frac{G^0_r(t)}t
=q\pi_0\frac{H_r(x_t)}{Q(x_t)}.\tag{2}
$$

Every positive threshold limit therefore solves the population equation.
It is not necessary to assume first-root convergence to obtain (2).

If instead t_N tends to zero along a subsequence, its FDP is eventually
exactly zero along that subsequence. Indeed every true null, uniformly in
j and N at this fixed z, satisfies

$$
|v_{j,N}^{\mathsf T}z|\le r,
\qquad p_{j,N}(z)\ge2Q(r)>0.\tag{3}
$$

Thus a threshold below 2Q(r) rejects no nulls. This argument uses zero
residual variance and unit loading norm; uniform CDF convergence alone
would not control FDP at thresholds tending to zero.

## 2. The critical-radius set has measure zero on the core

Put f(r,x)=F(r,x)-2Q(x)/q. We use the following local property on an open
radius interval J:

$$
f(r,x)=0,\ x\ge u,\ f_x(r,x)=0
\quad\Longrightarrow\quad f_r(r,x)>0.\tag{REG}
$$

The frozen population calculation supplies (REG) on the interior of its
core interval. Here is the needed argument and its regularity requirement.
For

$$
g_r(y)=\frac{c_d}{r}(1-y^2/r^2)_+^{(d-3)/2},\qquad
c_d=\frac{\Gamma(d/2)}{\sqrt\pi\Gamma((d-1)/2)},
$$

the density g_r is continuous including its support endpoints because
d>3. On compact rectangles with r>0, x>0, differentiating under W is
valid: all nonzero derivative terms involve a bounded interval of means
and are uniformly bounded. Thus F and f are C^1, including for unbounded
W. With

$$
B=\int[g_r(x-\mu)+g_r(x+\mu)]\,dW(\mu),
\qquad
D=\int[(x-\mu)g_r(x-\mu)+(x+\mu)g_r(x+\mu)]\,dW(\mu),
$$

we have F_x=-B and F_r=D/r. Let M_d=max_y |y|g_r(y), independent of r;
its explicit expression appears in Section 5. For 0<ell<r and x>=ell set
K=2M_d/ell+2g_r(0)/H_r(ell). The pointwise budget B<=KF when D<=0
can be checked directly. Write A_mu=H_r(x-mu)+H_r(x+mu), and let
d_mu be the integrand defining D. If d_mu<0, then mu>x, A_mu>=1/2,
and (d_mu)_-<=M_d. Hence the integrated negative part is <=2M_d F;
when D<=0 the integrated positive part is no larger. For mu<=x-ell,
b_mu=g_r(x-mu)+g_r(x+mu)<=d_mu/ell. For the complementary means,
A_mu>=H_r(ell) and b_mu<=2g_r(0). Integrating these two bounds gives
B<=KF, including D=0. At any zero f=0 with K<=u/2 this gives

$$
f_x=(\phi(x)/Q(x))F-B\ge xF/2>0
\qquad(D\le0),\tag{4}
$$

using x>=u>0 and the normal Mills inequality. Hence f_x=0 at a zero
forces D>0 and f_r>0. This includes D=0.

For the core constants in Section 5, ell=r/(2sqrt(d)) satisfies ell<=u.
If a_d=P(U_1>=1/(2sqrt(d))), the sphere moments and Paley-Zygmund give
a_d>=3/32: apply it to dU_1^2, with mean 1 and second moment <=3,
at level 1/4, then use symmetry. Also
c_d<=sqrt((d-1)/(2pi))<=sqrt(d) by Jensen applied to a
Gamma((d-1)/2,1) square root; the displayed formula for M_d gives
M_d<=1. Thus K<=26sqrt(d)/r<=u/2 throughout that core. This checks
(REG) there without using the population transport estimate.

For completeness, C^1 regularity is sufficient for the Sard step; C^2
regularity of the sphere density is not required. If rho:I->R is C^1,
then rho({s:rho'(s)=0}) has Lebesgue measure zero. To see this, restrict
the critical set to any compact J_0 contained in a bounded open interval
J_1 whose closure is contained in I. For epsilon>0, the open set
{s in J_1:|rho'(s)|<epsilon} is a countable union of disjoint intervals.
Their total length is at most |J_1|, and the mean value theorem bounds
the diameter of each image by epsilon times its interval length. These
images cover the image of the critical set in J_0, so its outer measure
is at most epsilon|J_1|. Let epsilon decrease to zero, then exhaust I by
countably many such compact intervals.

At each zero with f_x=0, (REG) and the C^1 implicit function theorem
express the local zero set as r=rho(x), where

$$
\rho'(x)=-f_x/f_r.
$$

Tangencies in this chart are critical points of rho. A countable subcover
of these local charts exists because the plane is second countable.
The preceding one-dimensional result therefore shows that

$$
E_J=\{r\in J:\text{some }x\ge u\text{ has }f(r,x)=f_x(r,x)=0\}
$$

is Lebesgue null. There are no such zeros at x=u: f(r,u)=0 means
F(r,u)=1; since F<=1 on an open neighborhood, F_x=0 there and
f_x(r,u)=2phi(u)/q>0. The unbounded x-domain and unbounded support of W
are handled by the countable chart cover, not by a finite root count.

## 3. First-selection convergence at every noncritical core radius

For r>0 let

$$
t_*(r)=\sup\bigl(\{t\in(0,q]:G_r(t)\ge t/q\}\cup\{0\}\bigr).
$$

If t_*>0, continuity shows that the supremum is attained and
G_r(t_*)=t_*/q. For t_*<q, strict inequality would extend feasibility
to a larger t; for t_*=q, G_r(q)<=1 gives equality directly. Its
x-coordinate x_*(r)=Q^{-1}(t_*/2) is exactly the smallest feasible
x>=u used by the population note.

Take r in J outside E_J. If t_*>0 and x_*>u, minimality gives
f(r,x)<0 for u<=x<x_*. The derivative f_x(r,x_*) is nonnegative;
it is nonzero outside E_J, so it is positive. If x_*=u, its derivative
is positive by the endpoint argument above. In either case f(r,x)>0
for x immediately larger than x_*, or equivalently G_r(t)>t/q for
t immediately smaller than t_*.

Fix one such t_0<t_*. Choose grid points s_N=q k_N/N tending to t_0.
Uniform convergence and continuity imply G_N(s_N;z)>s_N/q for all
sufficiently large N. Hence t_N>=s_N, so liminf t_N>=t_0. Letting
t_0 increase to t_* gives liminf t_N>=t_*. Every positive subsequential
limit is feasible by (2), so limsup t_N<=t_*. Thus t_N->t_* and (2)
identifies the limiting FDP.

If t_*=0, any positive subsequential threshold limit would be feasible
by (2), a contradiction. Compactness of [0,q] then gives t_N->0,
and (3) gives FDP_N(z)=0 eventually. In summary, for almost every z
with ||z|| in J,

$$
\operatorname{FDP}_N(z)\longrightarrow
\operatorname{FDP}_{\rm pop}(r):=
\begin{cases}
q\pi_0H_r(x_*(r))/Q(x_*(r)),&t_*(r)>0,\\
0,&t_*(r)=0.
\end{cases}\tag{5}
$$

The exceptional radii have zero Gaussian probability because R has a
density. Measurability of t_* follows, for example, by taking maxima of
the continuous function G_r(t)-t/q over compact intervals [a,q] with
a>0: {t_*>=a} is the closed-in-r condition that this maximum is >=0.

## 4. A lower-region envelope independent of root convergence

Define E_u(r)=sup_{x>=u} H_r(x)/Q(x). It is zero for r<=u; for r>u
the supremum can be restricted to the compact interval [u,r]. It is
measurable by taking the supremum over rational x>=u and using
continuity. The compact-subsequence argument in (2), together with the
zero-threshold argument (3), gives for every good z, with r=||z||,

$$
\limsup_N\operatorname{FDP}_N(z)\le q\pi_0E_u(r).\tag{6}
$$

No tangency or strict-crossing assumption is used in (6).

Let a>u satisfy a^2-u^2<=d-3. Write V~chi-square_(d-1), independent
of Z_1, and let f_V be its density. Bayes' formula, or differentiation
of the joint distribution of Z_1 and Z_1^2+V, gives

$$
f_R(r)\frac{H_r(x)}{Q(x)}
=\frac{2r}{Q(x)}\int_x^r\phi(z)f_V(r^2-z^2)\,dz
\quad (u\le x<r).\tag{7}
$$

The chi-square density is nondecreasing on [0,d-3]. For u<r<a and
x>=u, its argument r^2-z^2 lies in [0,r^2-u^2], so (7) implies

$$
f_R(r)\frac{H_r(x)}{Q(x)}
\le2r f_V(r^2-u^2).
$$

The same bound is immediate for x>=r. Taking the supremum and then
integrating yields the exact envelope estimate

$$
\int_0^a f_R(r)E_u(r)\,dr
\le P(V\le a^2-u^2)\le1.\tag{8}
$$

If a<=u, the left side is zero. Thus no population first-selection
regularity is needed in the lower region.

## 5. Transfer theorem and the explicit conditional corollary

Let 0<a<b. Suppose (REG) holds throughout (a,b), and either a<=u or
a^2-u^2<=d-3. Equations (5), (6), the bound FDP_N<=1, and reverse
Fatou give the transfer statement

$$
\limsup_{N\to\infty}\operatorname{FDR}_{\rm BH}(q;N)
\le q\pi_0\int_0^a f_R(r)E_u(r)\,dr
 +\int_a^b f_R(r)\operatorname{FDP}_{\rm pop}(r)\,dr
 +P(R>b).\tag{9}
$$

Indeed reverse Fatou applies to bounded measurable FDPs and says
limsup E FDP_N <= E limsup FDP_N. The three radial bounds just proved
then give (9). This is a transfer of actual finite Gaussian FDRs,
not a claim about an unconditional random-covariance mixture.

For the constants in the frozen population candidate, take u>=104,

$$
a=r_0=\max\{u,52\sqrt d/u\},\qquad
b=L=\sqrt d+2u,\qquad
M_d=\frac{c_d}{\sqrt{d-2}}
 \left(\frac{d-3}{d-2}\right)^{(d-3)/2}.
$$

That candidate establishes the differential-budget conditions for
(REG) on this core. Also a^2-u^2<=d-3 whenever a>u, as follows from
2704/u^2<=1/4 and d>=4. The only population integral input still
needed for the explicit corollary is its proposed estimate

$$
\int_{r_0}^{L} f_R(r)\operatorname{FDP}_{\rm pop}(r)\,dr
\le q\pi_0\{1+4M_d(1+u^{-2})\log(3u)\}.\tag{MT}
$$

Conditional on (MT), (8), (9), and the Gaussian radius tail bound
P(R>sqrt(d)+2u)<=exp(-2u^2) give

$$
\boxed{\displaystyle
\limsup_{N\to\infty}\operatorname{FDR}_{\rm BH}(q;N)
\le q\pi_0\{2+4M_d(1+u^{-2})\log(3u)\}+e^{-2u^2}.}\tag{10}
$$

The radius tail bound can be obtained directly from the chi-square
Chernoff bound at (sqrt(d)+t)^2. Its exponent is
[-2sqrt(d)t-t^2+2d log(1+t/sqrt(d))]/2 <= -t^2/2.

The displayed corollary does not certify (MT). The population global
comparison/BV transport proof is the separately frozen dependency; the
transfer proof does not repair or promote that dependency. In particular,
the whole population FDR bound by itself is insufficient for this proof:
we need the core estimate (MT), because the lower-region limiting FDP may
select a root other than the population first root.

## 6. Why the critical and zero-threshold cases are covered

The potentially troublesome cases have separate treatments:

- Finite tangencies on the core occur at a Lebesgue-null set of radii by
  C^1 one-dimensional Sard and (REG), with no finite-atom assumption.
- All core roots at every other radius are simple, and the first root is
  a strict upcrossing. Empirical uniform convergence plus the BH grid
  spacing q/N then gives the correct largest feasible p-threshold.
- A population with no finite feasible x forces t_N->0; the uniform
  positive lower bound on null p-values gives eventual zero FDP.
- Lower-region tangencies and root switches need not be controlled:
  all positive root limits are charged to (8), while zero limits have
  zero FDP.
- The upper region uses only FDP_N<=1 and its Gaussian radial probability.

No differentiability of the selected root function is used in this
transfer. The proof does not require any uniform empirical rate in z,
any finite number of roots, compact support of W, or a positive lower
bound on nonnull means.

## 7. Existence of deterministic arrays satisfying (UC)

On an auxiliary probability space draw an infinite iid sequence
(M_j,V_j) with law W times uniform(S^{d-1}). For each fixed z!=0, the
variables P_j(z)=2Q(|M_j+V_j^T z|) are iid with CDF G_{||z||}.
The null-labelled indicators
1{M_j=0}1{P_j(z)<=t} have expectations G^0_{||z||}(t).
For every rational t in [0,1], the strong law gives convergence of
both empirical means. Countably many rational t can be intersected
without losing auxiliary probability one at this fixed z.

The relevant indicator events are jointly measurable in the auxiliary
sequence and z. Fubini applied to the countable-rational convergence
event therefore shows that, for auxiliary-almost every sequence, all
these rational convergences hold for Gaussian-almost every z. Fix one
such sequence once and for all.

At each of its good z, both limiting sub-CDFs are continuous on [0,1].
Monotonicity upgrades rational pointwise convergence to uniform
convergence: given epsilon>0, choose a finite rational partition whose
successive increments in each continuous limit sub-CDF are <epsilon;
for large N, the empirical errors at all partition points are <epsilon.
Squeezing between adjacent points bounds the error everywhere by
2epsilon. The endpoints 0,1 cause no issue; all p-values are strictly
positive, and the rational strong law at 1 gives null-proportion
convergence. This proves (UC).

Now define mu_{j,N}=M_j and v_{j,N}=V_j for j<=N from this fixed
realization. These are deterministic coefficients. For every N the
joint distribution over Z is exactly N_N(mu_N,V_N V_N^T), with
variance one in every coordinate and precisely the null labels used
in (UC). We never average the Gaussian law over the auxiliary random
draw. The draw is only an existence argument for one deterministic
array sequence.

## Final scope and remaining dependency

The transfer argument (9) is a full candidate under its stated C^1
regularity and differential-budget interface; the explicit estimate (10)
additionally depends on the frozen population core transport estimate
(MT). The candidate gives no uniform error rate and no bound for every
finite N or for arbitrary finite Gaussian arrays. The constructed arrays
are isotropic in the empirical limit, have zero residual variance, and
have positive-semidefinite covariance of rank at most fixed d.

Only after taking N to infinity for each fixed (q,d,W) may one vary these
parameters. If (MT) survives its separate audit, a q-dependent choice of
d,W can be followed by an existentially sufficiently large deterministic
N(q) to approximate the limsup bound, with an arbitrarily prescribed
positive error at each fixed q. This is a diagonal choice, not an exchange
of limits or a quantitative approximation theorem. The unrestricted
conjecture is unaffected.
