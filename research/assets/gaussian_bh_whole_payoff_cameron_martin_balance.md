---
type: lemma
title: Whole-payoff Cameron-Martin balance for the actual Gaussian BH cutoff payoff
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
  - gaussian_bh_actual_radial_loading_signed_variation
uses_definitions:
  - gaussian_bh_private_smoothed_directing_population
tags:
  - gaussian_bh
  - cameron_martin
  - actual_rank
  - signed_variation
  - fixed_regularizers
---

## Statement

The approved [private signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md) and [actual radial signed variation](gaussian_bh_actual_radial_loading_signed_variation.md) are declared prerequisites before search. Use the approved [private-smoothed directing population](../definitions/gaussian_bh_private_smoothed_directing_population.md). The conditional calculus below must be established for a fixed-tag background translation, without applying a lawful mean-model comparison outside its scope.

Fix a nonzero separable real Hilbert space $\mathcal H$, a lawful deterministic directing probability $\pi$ on its tagged unit-ball parameter space $E_{\rm ball}$ with $M_2(\pi)=\int\theta^2d\pi<\infty$, and
$$
\sigma,s>0,\qquad \sigma^2+s^2<1,\qquad
\tau=\sqrt{1-\sigma^2-s^2},\qquad 0<a<1/4,\qquad 0<q\le S(1).
$$
Here $S=\overline\Phi$, $\phi(y)=(2\pi)^{-1/2}e^{-y^2/2}$, and $s$ denotes private smoothing; all tests are one-sided. Fix the specified nondecreasing $C^1$ cutoff $\chi_a:[0,1]\to[0,1]$, zero on $[0,a]$ and one on $[2a,1]$. No maximizing, finite-support, finite-dimensional, or genericity hypothesis is imposed on $\pi$.

Write a parameter as $x=(\theta,w,\ell)$, where $\|w\|\le1$ and $\ell\in\{0,1\}$ is its fixed true-null tag. Use the approved isonormal series representative $X$ and an independent $Z\sim N(0,1)$. For each fixed deterministic direction $v\in\mathcal H$ and each $t\in\mathbb R$ put
$$
X_t(w)=X(w)+t\langle w,v\rangle,\qquad
c(w)^2=s^2+\tau^2(1-\|w\|^2),\qquad
A_{t,X}(x)=\theta+\tau X_t(w).
$$
The law, means, tags, private variances, level and cutoff remain fixed. This translates the argument of a conditional background function; it does not assert that changed conditional means give a lawful competitor or alter null labels.

For every fixed $v$, establish jointly measurable coherent versions along its Gaussian lines, outside a null exceptional set which may depend on $v$. All simultaneous-in-$t$ assertions below are for these versions and $\pi$-almost-everywhere field evaluations. No single exceptional set common to all directions is asserted. Representative changes leave the stated random quantities unchanged almost surely, for each fixed direction.

1. **Actual marked selection and joint sandwiches.** On the common particle/private-mark space with measure $\mu=\pi\otimes\gamma$, where $\gamma$ is standard normal measure in the mark $y$, define
$$
T_t(X,z;x,y)=A_{t,X}(x)+c(w)y+\sigma z,
\qquad u_q(r)=S^{-1}(qr).
$$
Let $R_t(X,z)$ be the actual globally largest non-strict BH population rank,
$$
R_t(X,z)=\sup\Bigl(\{0\}\cup
\{r\in(0,1]:\mu(T_t(X,z;\cdot)\ge u_q(r))\ge r\}\Bigr).
$$
If $R_t>0$, let $\mathcal R_t(X,z)=\{(x,y):T_t(X,z;x,y)\ge u_q(R_t)\}$; at $R_t=0$ use the empty set. Put
$$
\nu_t(X,z)=\int_{\mathcal R_t(X,z)}\ell\,d\mu,\qquad
D_t(X,z)=
\begin{cases}\nu_t(X,z)/R_t(X,z),&R_t(X,z)>0,\\0,&R_t(X,z)=0,\end{cases}
$$
$$
\mathfrak f_\pi(X_t)=\mathbb E_Z[\chi_a(R_t(X,Z))D_t(X,Z)].
$$
Prove attainment of a positive largest rank and the selected-mass identity $\mu(\mathcal R_t)=R_t$, including zero and rank-one conventions. In particular $0\le\nu_t\le R_t\le1$. For a fixed $u$, the selected sets are nested as $z$ increases, and for all real $z_1\le z_2$,
$$
0\le\nu_u(X,z_2)-\nu_u(X,z_1)
\le R_u(X,z_2)-R_u(X,z_1).
$$
For all real $t,u,z$, with $h=\tau|t-u|\|v\|/\sigma$, prove on this same marked space
$$
\mathcal R_u(X,z-h)\subseteq\mathcal R_t(X,z)
\subseteq\mathcal R_u(X,z+h),
$$
and consequently both sandwiches
$$
R_u(X,z-h)\le R_t(X,z)\le R_u(X,z+h),\qquad
\nu_u(X,z-h)\le\nu_t(X,z)\le\nu_u(X,z+h).
$$
Derive the set comparison from coordinatewise score comparison and global BH selection. A rank comparison by itself does not establish the numerator comparison. The private-mark space represents the integrated population kernels; it does not identify the private marks of distinct finite tests.

2. **Global line Lipschitz estimate.** Put
$$
W_a=\|\chi_a'\|_\infty+1/a,\qquad
C_{a,\sigma,\tau}=\frac{2\tau}{\sigma\sqrt{2\pi}}
\left(\frac1a+W_a\right).
$$
On the convex domain $\{(r,n):0\le n\le r\le1\}$, define $g_a(r,n)=\chi_a(r)n/r$ for $r>a$ and $g_a(r,n)=0$ for $r\le a$. Prove
$$
|g_a(r,n)-g_a(r',n')|
\le\frac1a|n-n'|+W_a|r-r'|.
$$
Using clause 1 and the monotone-rank translation estimate
$$
\mathbb E_Z[R_u(X,Z+h)-R_u(X,Z-h)]
\le\frac{2h}{\sqrt{2\pi}},
$$
prove, simultaneously for all real $t,u$ on each admissible line,
$$
|\mathfrak f_\pi(X_t)-\mathfrak f_\pi(X_u)|
\le C_{a,\sigma,\tau}|t-u|\|v\|.
$$
This explicit constant is independent of $\pi$, means, $q$, Hilbert dimension, direction count, and private smoothing except through $\tau$. No samplewise supremum of the isonormal field over a Hilbert ball is allowed.

3. **Conditional all-active signed response.** For a fixed admissible background abbreviate the $t=0$ kernels and density fields by
$$
K_{X,x}(z)=S\!\left(\frac{z-\theta-\tau X(w)}{c(w)}\right),\qquad
k_x(z)=\frac1{c(w)}\phi\!\left(\frac{z-\theta-\tau X(w)}{c(w)}\right),
$$
$$
H_X(z)=\int K_{X,x}(z)d\pi(x),\quad
V_X(z)=\int\ell K_{X,x}(z)d\pi(x),\quad
h_X(z)=\int k_x(z)d\pi(x),\quad
h_{0,X}(z)=\int\ell k_x(z)d\pi(x).
$$
Use the unique quantile $H_X(Q_X(r))=r$ for $0<r<1$, $f_X(r)=V_X(Q_X(r))/r$, $f_X(1)=\int\ell d\pi$, and zero FDP at zero rank. The translated objects $H_{t,X},V_{t,X},Q_{t,X},f_{t,X}$ are defined by the same formulas with $X_t$. At the actual positive rank, identify $D_t=f_{t,X}(R_t)$.

For this fixed $v$ put
$$
b_v(x)=\tau\langle w,v\rangle,\quad
h_b(z)=\int b_v(x)k_x(z)d\pi(x),\quad
h_{0b}(z)=\int\ell b_v(x)k_x(z)d\pi(x).
$$
A dot denotes $d/dt|_{0+}$, holding tags fixed. Prove the conditional differentiation directly, including $\dot H_X=h_b$, $\dot V_X=h_{0b}$, and, for $0<r<1$,
$$
\dot Q_X(r)=\frac{h_b(Q_X(r))}{h_X(Q_X(r))},\qquad
\dot f_X(r)=
\frac{h_{0b}(Q_X(r))-[h_{0,X}/h_X](Q_X(r))h_b(Q_X(r))}{r}.
$$
Establish local compact-uniform differentiation of $Q_{t,X}$ and the barrier inputs. Use $|b_v|\le\tau\|v\|$ and the positive private variance for the needed bounds; no conditional velocity is assumed to preserve the lawful mean domain. At rank one, the total true mass is unchanged and $\dot f_X(1)=0$; define $\chi_a(R)\dot f_X(R)=0$ when $R\le a$.

For $0<r<1$ set
$$
B_X(r)=\frac{u_q(r)-Q_X(r)}\sigma,\qquad B_X(1)=+\infty,
$$
$$
M_X(r)=\min_{\rho\in[r,1]}B_X(\rho),\qquad
\mathcal A_X(r)=\operatorname*{argmin}_{\rho\in[r,1]}B_X(\rho),
\qquad M_X(1)=+\infty.
$$
Define the translated quantities likewise. Prove the actual-rank survival identity $\mathbb P_Z(R_t\ge r\mid X)=S(M_{t,X}(r))$, its endpoint value zero at rank one, and common compact localization of all minimizers for small translations, excluding escapes to rank one. For each $0<r<1$, prove the pointwise right envelope derivative
$$
\dot M_X(r)=\frac1\sigma
\min_{\rho\in\mathcal A_X(r)}[-\dot Q_X(\rho)].
$$
Every active minimum is retained. Establish pointwise differentiation of the survival function and convergence of its difference quotients in $L^1(dr)$ on $[a,1]$ to $-\phi(M_X)\dot M_X$, with the endpoint interpreted through survival. Uniform convergence of minimum derivative quotients across tied minima is not asserted. Justify convergence of the actual ranks outside Gaussian-null jump levels and the required endpoint and domination arguments before using the signed integral below.

4. **Ordinary whole-function derivative.** For each fixed $v$, the coherent version $t\mapsto\mathfrak f_\pi(X_t)$ is absolutely continuous on every bounded real interval and ordinarily differentiable for Lebesgue-almost every $t$. Its ordinary directional derivative at $t=0$, denoted $D_v\mathfrak f_\pi(X)$, exists for almost every Gaussian background, with
$$
|D_v\mathfrak f_\pi(X)|\le C_{a,\sigma,\tau}\|v\|.
$$
At almost every point on almost every such Gaussian line, identify this derivative by the complete conditional signed response; at its baseline point the formula is
$$
D_v\mathfrak f_\pi(X)
=\mathbb E_Z[\chi_a(R)\dot f_X(R)]
-\int_a^1(\chi_af_X)'(r)\phi(M_X(r))\dot M_X(r)\,dr,
\qquad R=R_0(X,Z).
$$
Primes here mean ordinary rank derivatives. Prove measurability and absolute integrability of this complete expression and every exchange needed to obtain it. Retain the signed bulk and rank terms, all active suffix minima, the actual rank-zero cutoff, and the rank-one endpoint; the integral is over $a<r<1$, with no undefined rank-one product. The dimension-independent bound is for the complete expression; it does not require separate-term bounds uniform as $s\downarrow0$.

5. **Gaussian integration by parts and scope.** For every fixed deterministic $v$ and every bounded measurable test weight $\zeta(X)$ with coherent $C^1$ versions along $v$ and bounded $D_v\zeta$, prove
$$
\mathbb E[X(v)\zeta(X)\mathfrak f_\pi(X)]
=\mathbb E[\mathfrak f_\pi(X)D_v\zeta(X)
+\zeta(X)D_v\mathfrak f_\pi(X)].
$$
For $v\ne0$, condition on the orthogonal Gaussian field and integrate by parts in $X(v)/\|v\|$. Justify the absolutely continuous product, Gaussian boundary terms, versions and absolute integrability. In particular $\zeta=1$ gives
$$
\mathbb E[X(v)\mathfrak f_\pi(X)]
=\mathbb E[D_v\mathfrak f_\pi(X)].
$$
For $v=0$, prove that the line is constant and both sides vanish.

This checkpoint asserts regularity of the entire conditional payoff, not Gaussian Sobolev or bounded-variation regularity of each separate actual selector. It neither identifies an arbitrary matched dual pair with the nonlinear actual loading response nor supplies the missing uniform $q$ payment or a bound surviving $a,\sigma\downarrow0$. Its first falsification gate is the marked-set comparison, including a mixed-label multi-direction model. Failure of that gate stops this statement while preserving the original main goals.

## Proof

All parameters and the tagged probability law in the statement are fixed throughout. In particular, no comparison of lawful mean models is used. We write $K=\tau\|v\|$ and $L_s=(s\sqrt{2\pi})^{-1}$. The two declared prerequisites remain in force; the conditional arguments needed here are proved below rather than inferred from their lawful-transport assertions.

**1. Coherent scalar Gaussian disintegration.** First suppose $v\ne0$, and set $e=v/\|v\|$. In the approved series representation, write $a_k=\langle e,e_k\rangle$ and
$$
\eta=\sum_k a_k\xi_k,\qquad U_k=\xi_k-a_k\eta.
$$
The series for $\eta$ converges almost surely and in $L^2$, and $\eta$ is standard normal. Indeed, its partial sums are centered normal with variances tending to $\sum_k a_k^2=1$, and converge in $L^2$. For each finite list of indices, the vector consisting of $\eta$ and the corresponding $U_k$ is a limit in $L^2$ of Gaussian vectors, hence is jointly Gaussian: its characteristic function is the limit of the Gaussian characteristic functions. Its covariances satisfy $\mathbb E[\eta U_k]=a_k-a_k=0$. Its Gaussian characteristic function therefore factors between $\eta$ and that finite list. Cylinder events and the monotone-class theorem imply independence of $\eta$ and $\mathcal G=\sigma(U_k:k)$. This also proves independence from every measurable orthogonal field constructed from $U$. The same argument applies to finite-dimensional sums.

Define the jointly measurable residual field
$$
Y(w)=\sum_k\langle w,e_k\rangle U_k
$$
where the series converges, with value zero otherwise. Measurability follows by taking the measurable convergence set and the limit of its partial sums. For each fixed $w$, the series converges almost surely, because its partial sums are those for $X(w)$ minus $\eta\sum_{k\le n}\langle w,e_k\rangle a_k$, and the deterministic inner products converge to $\langle w,e\rangle$. Thus
$$
Y(w)=X(w)-\eta\langle w,e\rangle
$$
almost surely for each $w$. Fubini, applied to the parameter law, shows that on a full-probability set in the residual variable $U$ the series defining $Y(w)$ converges for $\pi$-almost every $x=(\theta,w,\ell)$. This set is $\mathcal G$-measurable. Fix such a residual background and use, for every real scalar $y$,
$$
X^{U,y}(w)=Y(w)+y\langle w,e\rangle.
$$
This is a single jointly measurable field on the whole line, finite on one fixed $\pi$-full set of parameters for every $y$. At $y=\eta$ it agrees with the approved representative for $\pi$-almost every parameter almost surely. Translating in direction $v$ replaces $y$ by $y+t\|v\|$. This construction uses no samplewise bound on the isonormal field over a ball.

For completeness, representative invariance here concerns versions of the same isonormal evaluations. Two jointly measurable such representatives agree almost surely for each fixed $w$, so Fubini gives equality for $\pi$-almost every $x$ at almost every Gaussian background. Adding the deterministic function $t\langle w,v\rangle$ then preserves that equality simultaneously for all $t$ on this parameter-full set. Equivalently, under the independent $(U,\eta)$ disintegration their induced functionals agree for almost every scalar coordinate on almost every residual line. The Lipschitz line versions proved below are continuous, so these equalities determine the same continuous functional on each such line. Kernels, ranks and numerators at the random baseline, and the almost-everywhere directional derivatives, are consequently unchanged almost surely. These full-measure sets may depend on $v$. When $v=0$, the approved representative itself gives constant lines; the following conditional arguments apply with $K=0$.

**2. Kernels, actual ranks, masses and measurability.** Work on any of the admissible lines just constructed and any of its scalar baselines. For every real translation $t$ the centers are finite for $\pi$-almost every $x$. Since $s\le c(w)\le\sqrt{s^2+\tau^2}$, the functions
$$
H_t(z)=\int S((z-A_0(x)-t b_v(x))/c(w))\,d\pi(x),
\qquad V_t(z)=\int\ell S((z-A_0(x)-t b_v(x))/c(w))\,d\pi(x)
$$
are jointly measurable in the background, $t$ and $z$. Dominated convergence shows that $H_t$ is continuous, strictly decreasing from one to zero and strictly between zero and one at every finite $z$. Strictness follows because each Gaussian kernel has these properties and $\pi$ is a probability. Consequently its inverse $Q_t(r)$ exists uniquely for $0<r<1$ and is continuous and strictly decreasing. Inverse measurability follows, for example, from $\{Q_t(r)<z\}=\{H_t(z)<r\}$.

Integrating the private mark gives exactly
$$
\mu\{T_t(X,z;\cdot)\ge u_q(r)\}=H_t(u_q(r)-\sigma z).
$$
For fixed $t,z$, let $F_{t,z}(r)=H_t(u_q(r)-\sigma z)-r$. This is continuous on every $[r_0,1]$, $r_0>0$, and $F_{t,z}(1)<0$. Its nonnegative set is therefore closed away from zero. If the supremum of its positive qualifying ranks is positive, a convergent sequence approaching that supremum proves attainment. It cannot be one, since $F_{t,z}(1)<0$. If $F_{t,z}(R_t)>0$ at a positive largest rank, continuity supplies a larger qualifying rank, a contradiction. Thus
$$
0<R_t<1\quad\Longrightarrow\quad
H_t(u_q(R_t)-\sigma z)=R_t.
$$
For measurability, for every $r_0\in(0,1]$ attainment gives
$$
\{R_t\ge r_0\}=\left\{\max_{r\in[r_0,1]}F_{t,z}(r)\ge0\right\}.
$$
The maximum is measurable: by continuity its value is the supremum over a countable dense subset of the compact interval, including its endpoints. Taking a supremum of values is legitimate even for an isolated contact; we have not replaced existence of a nonnegative value by existence of a nonnegative rational value. This proves joint measurability of $R_t$ using rational $r_0$ as thresholds for $R_t$, and then of its marked selected set and of $\nu_t,D_t$. Fubini proves measurability of all conditional payoffs below.

At positive rank the displayed identity is precisely $\mu(\mathcal R_t)=R_t$; at zero rank both the selected mass and numerator are zero by the prescribed empty-set convention. Hence $0\le\nu_t\le R_t\le1$. Rank one is absent for every finite $z$, not merely almost surely; its extended convention has full mass and true mass $\int\ell\,d\pi$. At a positive actual rank, uniqueness of the inverse implies $u_q(R_t)-\sigma z=Q_t(R_t)$, so
$$
\nu_t=V_t(Q_t(R_t)),\qquad D_t=f_t(R_t).
$$
The separate values at zero and one are exactly the conventions in the statement.

**3. The joint marked-set comparison.** Consider two finite score fields on this same marked probability space with $T\le T'$ almost everywhere. Every rank qualifying for $T$ qualifies for $T'$, so their largest ranks obey $R\le R'$. If $R=0$, its selected set is empty. If $R>0$, then $R'>0$, $u_q(R')\le u_q(R)$, and
$$
T\ge u_q(R)\quad\Longrightarrow\quad
T'\ge T\ge u_q(R)\ge u_q(R').
$$
Thus the selected set for $T$ is contained in that for $T'$, modulo the common null set. All the actual score fields considered here have the mass identity from step 2. In particular, increasing $z$ gives nested selected sets and
$$
0\le\nu_u(X,z_2)-\nu_u(X,z_1)
=\int_{\mathcal R_u(X,z_2)\setminus\mathcal R_u(X,z_1)}\ell\,d\mu
\le R_u(X,z_2)-R_u(X,z_1).
$$
On the fixed parameter-full set of the coherent line,
$$
|T_t(X,z;x,y)-T_u(X,z;x,y)|
=|(t-u)b_v(x)|\le K|t-u|.
$$
With $h=K|t-u|/\sigma$, this places $T_t(X,z)$ between $T_u(X,z-h)$ and $T_u(X,z+h)$. The implication just proved gives both selected-set inclusions in the statement, and integrating $1$ and $\ell$ gives both rank and true-mass sandwiches. They hold for all real $t,u,z$ on the same line. The proof uses neither a sign condition on $b_v$ nor a common tag or common loading direction. It therefore includes mixed-label populations with several loading directions. The common private mark is a representation of the integrated population measure, not a coupling assertion about noises in a finite test sample.

**4. The global whole-payoff Lipschitz bound.** On the open portion $r>a$ of the triangle $0\le n\le r\le1$, direct differentiation gives
$$
|\partial_n g_a|=\chi_a(r)/r\le1/a,\qquad
|\partial_r g_a|=|\chi_a'(r)n/r-\chi_a(r)n/r^2|
\le\|\chi_a'\|_\infty+1/a=W_a.
$$
On $r<a$ both derivatives vanish. The zero extension is continuous at $r=a$ because $\chi_a(a)=0$. Integrate along the segment joining any two points of the convex triangle, splitting at its possible crossing of $r=a$; segments lying on the boundary follow by continuity. This proves
$$
|g_a(r,n)-g_a(r',n')|\le a^{-1}|n-n'|+W_a|r-r'|.
$$
If $R(z)$ is any nondecreasing function valued in $[0,1]$, choose its right-continuous version and let $dR$ be its Lebesgue--Stieltjes measure, of total mass at most one. Changes at its at most countably many discontinuities do not affect Gaussian expectations, including after a fixed translation. Tonelli now gives, for $h\ge0$,
$$
\mathbb E[R(Z+h)-R(Z-h)]
=\int\left(\int_{x-h}^{x+h}\phi(z)\,dz\right)dR(x)
\le2h\|\phi\|_\infty=\frac{2h}{\sqrt{2\pi}}.
$$
Both $R_t(X,z)$ and $R_u(X,z)$ lie between $R_u(X,z-h)$ and $R_u(X,z+h)$. Both numerators likewise lie between the corresponding $\nu_u$ values, whose increment is at most the same rank increment by step 3. Hence each of $|R_t-R_u|$ and $|\nu_t-\nu_u|$ is bounded by $R_u(X,z+h)-R_u(X,z-h)$. Since the conditional payoff is $\mathbb E_Z g_a(R_t,\nu_t)$, we obtain
$$
|\mathfrak f_\pi(X_t)-\mathfrak f_\pi(X_u)|
\le\frac{2K|t-u|}{\sigma\sqrt{2\pi}}(a^{-1}+W_a)
=C_{a,\sigma,\tau}\|v\|\,|t-u|.
$$
This holds simultaneously for every pair $t,u$ on each admissible line. In particular the line function is bounded between zero and one, globally Lipschitz, locally absolutely continuous, and ordinarily differentiable for Lebesgue-almost every line parameter.

**5. Direct conditional differentiation and endpoint calculus.** Write $b=b_v$ and define the translated densities by
$$
k_{t,x}(z)=c(w)^{-1}\phi((z-A_0(x)-t b(x))/c(w)),\qquad
h_t(z)=\int k_{t,x}(z)d\pi(x),\qquad
h_{0,t}(z)=\int\ell k_{t,x}(z)d\pi(x).
$$
Gaussian differentiation, using $|b|\le K$ and $c\ge s$, gives uniformly bounded first and second derivatives of the individual kernels in $(t,z)$ at fixed $s,K$. For example $k_{t,x}(z)\le L_s$ and $|\partial_z k_{t,x}(z)|\le s^{-2}\sup_{u}|u\phi(u)|$; translation derivatives insert factors $b$. Dominated differentiation and dominated convergence therefore give joint continuous differentiability and
$$
\partial_t H_t(z)=\int b k_{t,x}(z)d\pi(x),\quad
\partial_t V_t(z)=\int\ell b k_{t,x}(z)d\pi(x),\quad
\partial_z H_t=-h_t<0,\quad \partial_z V_t=-h_{0,t}.
$$
At $t=0$ these are the $h_b,h_{0b}$ and densities in the statement. Bounded score shifts give the ordered-tail inequalities and inverse bound
$$
H_u(z+K|t-u|)\le H_t(z)\le H_u(z-K|t-u|),
\qquad |Q_t(r)-Q_u(r)|\le K|t-u|.
$$
On a compact rank interval inside $(0,1)$, these bounds place all nearby quantiles in a compact threshold interval. There $h_t$ has a strictly positive minimum, by continuity and positivity. Differentiating $H_t(Q_t(r))=r$, or applying the mean value theorem to that equation and passing to the limit, yields continuous derivatives locally uniformly in rank:
$$
\partial_t Q_t(r)=\frac{\int b k_{t,x}(Q_t(r))d\pi(x)}{h_t(Q_t(r))}.
$$
Uniformity follows from uniform continuity of the displayed continuous functions on the compact set and the uniform positive denominator. In particular $|\partial_tQ_t(r)|\le K$. Differentiating $V_t(Q_t(r))/r$ then proves precisely
$$
\dot Q(r)=\frac{h_b(Q(r))}{h(Q(r))},\qquad
\dot f(r)=\frac{h_{0b}(Q(r))-[h_0/h](Q(r))h_b(Q(r))}{r}.
$$
These derivatives are two-sided for the conditional kernels, although only their right values are required.

For any $t,u,r$, splitting a true-tail difference first in its center shift and then in its threshold gives
$$
|V_t(Q_t(r))-V_u(Q_u(r))|
\le K L_s|t-u|+L_s|Q_t(r)-Q_u(r)|
\le2K L_s|t-u|.
$$
Consequently $|\dot f(r)|\le2K L_s/r$. Differentiation in rank uses $Q'(r)=-1/h(Q(r))$ and gives
$$
\frac{d}{dr}V(Q(r))=\frac{h_0(Q(r))}{h(Q(r))}\in[0,1],\qquad
f'(r)=\frac{h_0(Q(r))/h(Q(r))-f(r)}r,
\quad |f'(r)|\le1/r.
$$
Here $0\le f\le1$ since $0\le V\le H$. As $r\uparrow1$, $Q_t(r)\to-\infty$, and dominated convergence gives $V_t(Q_t(r))\to\int\ell d\pi$. Thus $f_t$ extends continuously to the specified value at one, which is independent of $t$ and has derivative zero. At ranks at most $a$ the product involving $\dot f$ is defined as zero. None of these conditional differentiations changes tags or treats $b$ as a lawful mean velocity.

**6. Actual survival and the full active-minimum derivative.** For $0<\rho<1$, strict monotonicity of $H_t$ gives the exact equivalence
$$
H_t(u_q(\rho)-\sigma z)\ge\rho
\quad\Longleftrightarrow\quad z\ge B_t(\rho).
$$
The quantile endpoints and continuity imply $B_0(\rho)\to+\infty$ as $\rho\uparrow1$, since $u_q(\rho)\to u_q(1)$ is finite. Moreover the global inverse bound proves
$$
|B_t(\rho)-B_u(\rho)|\le K|t-u|/\sigma\quad(0<\rho<1).
$$
For every fixed $r<1$, continuity on $[r,1)$ and divergence at one give a finite suffix minimum attained away from one. The same compact set contains every suffix minimizer for all sufficiently small $|t|$: the bound above prevents a point with very large baseline barrier from beating the finite competitor $r$. More explicitly, for $|t|\le\delta$ choose $b_r<1$ so that $B_0(\rho)>B_0(r)+2K\delta/\sigma+1$ whenever $\rho>b_r$. Such points cannot minimize $B_t$ on $[r,1)$. For lower endpoints $r$ in a compact $[d,c]\subset(0,1)$, the fixed competitor $c$ is available for all of them, so the identical argument with $B_0(c)$ and $b>c$ gives one common compact $[d,b]$. This proves the stated local compact localization of all minimizers.

Attainment of the largest rank and of the suffix minimum now proves, including non-strict contacts,
$$
\{R_t(X,z)\ge r\}=\{z\ge M_t(r)\},\qquad
\mathbb P_Z(R_t\ge r\mid X)=S(M_t(r)).
$$
At rank one both survival sides are zero by $R_t<1$ and the convention $M_t(1)=+\infty$. Measurability of $M_t(r)$ follows without choosing a minimizer: write $\rho=r+(1-r)d$ with $d$ in a countable dense subset of $[0,1)$ and take the infimum of $B_t(\rho)$. Continuity makes this the actual minimum value. This argument gives joint measurability in background, translation and lower endpoint.

Here is the envelope argument in full. On the compact just obtained, step 5 gives the uniform expansion
$$
B_t(\rho)=B_0(\rho)+t d(\rho)+o(t),\qquad
d(\rho)=-\dot Q(\rho)/\sigma,
$$
where $d$ is continuous and the remainder is uniform in $\rho$. For any $\rho\in\mathcal A_0(r)$, comparison with that fixed point gives
$$
\limsup_{t\downarrow0}\frac{M_t(r)-M_0(r)}t\le d(\rho).
$$
Taking the minimum over the compact active set bounds this limsup by $\min_{\mathcal A_0(r)}d$. Conversely, choose any sequence $t_j\downarrow0$ realizing the liminf and minimizers $\rho_j$ of $B_{t_j}$; after passage to a subsequence, $\rho_j\to\rho_*$. Uniform convergence of $B_{t_j}$ and continuity show $B_0(\rho_*)=M_0(r)$, so $\rho_*$ is baseline active. Since $B_0(\rho_j)\ge M_0(r)$,
$$
\frac{M_{t_j}(r)-M_0(r)}{t_j}
\ge d(\rho_j)+o(1)\longrightarrow d(\rho_*)
\ge\min_{\mathcal A_0(r)}d.
$$
The quotient is bounded by $K/\sigma$, so the liminf and subsequence used here are finite. The upper and lower inequalities prove
$$
\dot M(r)=\frac1\sigma\min_{\rho\in\mathcal A_0(r)}[-\dot Q(\rho)].
$$
No active point was discarded, and no uniform convergence in the lower endpoint $r$ of these derivative quotients has been used or asserted.

**7. Survival differentiation, rank convergence and domination.** Taking infima in the global barrier bound gives $|M_t(r)-M_0(r)|\le K|t|/\sigma$ for every $r<1$. Thus
$$
\frac{S(M_t(r))-S(M_0(r))}{t}
\longrightarrow-\phi(M_0(r))\dot M(r)\quad(t\downarrow0),
\qquad
\left|\frac{S(M_t(r))-S(M_0(r))}{t}\right|
\le\frac{K}{\sigma\sqrt{2\pi}}.
$$
At one define the survival quotient and its derivative to be zero. Dominated convergence proves convergence in $L^1([a,1],dr)$, and against every fixed bounded rank weight; also $|\dot M(r)|\le K/\sigma$. All these quotients are measurable, so their limits give a measurable version of $\dot M$ for $r<1$, without a measurable choice among active minima.

For fixed baseline, $z\mapsto R_0(X,z)$ is nondecreasing and bounded. Such a function has at most countably many discontinuities: each jump interval of size at least $1/n$ is disjoint from the others, hence there are at most $n$ of them, and every discontinuity has a positive jump. At every continuity point its two translates at $z\pm K|t|/\sigma$ converge to $R_0(X,z)$. The rank sandwiches therefore give $R_t(X,z)\to R_0(X,z)$. The excluded countable set is Gaussian-null. This establishes the needed almost-everywhere convergence directly for the actual ranks. It imposes no regularity on selectors as functions of the Gaussian background.

**8. Complete conditional signed response and fixed-$s$ bounds.** Put $P_t(r)=\chi_a(r)f_t(r)$ for $r>a$ and zero for $r\le a$. The function $P_0$ is continuously differentiable locally on $(a,1)$, has continuous values at $a$ and one, and its derivative $w$ satisfies
$$
|w(r)|=|\chi_a'(r)f_0(r)+\chi_a(r)f_0'(r)|
\le\chi_a'(r)+\chi_a(r)/r,\qquad
\int_a^1|w(r)|dr\le1+\log(1/a).
$$
The first term integrates to one because $\chi_a(a)=0$ and $\chi_a(1)=1$. The bound on $f'$ gives the second. The fundamental theorem of calculus on $[a+\epsilon,1-\delta]$, followed by the continuity at $a,1$ and integrability of $w$, shows $P_0(r)=\int_a^r w(u)du$ on $[a,1]$. Extending by zero below $a$ proves absolute continuity on $[0,1]$. We may also use the pointwise bound $|w|\le\|\chi_a'\|_\infty+1/a$ on $(a,1)$.

The exact difference of conditional payoffs is
$$
\mathbb E_Z[P_t(R_t)-P_0(R_t)]
+\mathbb E_Z[P_0(R_t)-P_0(R_0)].
$$
For the first term divided by $t$, the fixed-rank bound of step 5 gives, for every $z$ and nonzero $t$,
$$
\left|\frac{P_t(R_t)-P_0(R_t)}t\right|\le\frac{2K L_s}{a}.
$$
Indeed the quotient vanishes for $R_t\le a$, and for $R_t>a$ it is $\chi_a(R_t)$ times the true-tail difference divided by $t R_t$. At each continuity point of the baseline rank with $a<R_0<1$, local compact-uniform quantile differentiation from step 5 and $R_t\to R_0$ identify its limit as $\chi_a(R_0)\dot f(R_0)$. If $R_0<a$ it is eventually zero. If $R_0=a$, the same true-tail bound multiplied by $\chi_a(R_t)\to0$ proves a zero limit. Rank one never occurs at finite $z$; its fixed-rank convention has zero variation. Dominated convergence in $z$ proves that the derivative of the first term is
$$
\mathbb E_Z[\chi_a(R_0)\dot f(R_0)],
\qquad\left|\mathbb E_Z[\chi_a(R_0)\dot f(R_0)]\right|
\le\frac{2K}{a s\sqrt{2\pi}}.
$$
For the second term, the absolutely continuous representation of $P_0$ gives the signed layer-cake identity
$$
\mathbb E_Z[P_0(R_t)-P_0(R_0)]
=\int_a^1 w(r)\,[S(M_t(r))-S(M_0(r))]\,dr.
$$
To justify it, write $P_0(R_t)=\int_a^1 w(r)\mathbf1_{\{R_t\ge r\}}dr$; the possible equality endpoint has zero Lebesgue measure and $\int|w|<\infty$, so Fubini applies even though $w$ is signed. The survival identity then gives the display. Step 7 permits differentiation under this integral, either by its bounded quotients times $|w|$, or by its $L^1$ convergence and the boundedness of $w$. Its derivative is
$$
-\int_a^1 (\chi_a f_0)'(r)\phi(M_0(r))\dot M(r)\,dr,
$$
and its absolute value is at most $K[1+\log(1/a)]/(\sigma\sqrt{2\pi})$. The integral is over $a<r<1$; it never evaluates a product at $M(1)=+\infty$.

Adding the two derivatives proves the full stated right response at every admissible conditional baseline. Both signed terms are retained, including the conditional true-mass composition response and every active suffix minimum. All quantities in the formula are jointly measurable: this follows from the integrated kernels, measurable quantile inversion, countable compact infima, their derivative limits, and parameter integration. The explicit bounds just proved are deterministic at fixed $s>0$, so each term is absolutely integrable also over the Gaussian backgrounds. Every interchange used above is covered by these bounds or by the stated compact-uniform differentiation and domination. No separate-term bound uniform in vanishing $s$ is needed.

**9. Ordinary derivative at Gaussian baselines.** On each admissible residual line let $F(y)=\mathfrak f_\pi(X^{U,y})$. By step 4, its Lipschitz constant in $y$ is $C_{a,\sigma,\tau}$, since $t$ in direction $v$ moves $y$ by $t\|v\|$. The elementary one-dimensional differentiability theorem for Lipschitz functions gives ordinary differentiability for Lebesgue-almost every $y$, and the derivative has absolute value at most this constant. The set on which the ordinary derivative exists is measurable: existence and equality of the one-sided limits can be tested through countable rational difference quotients; the Lipschitz bound extends those tests to all increments. Define the directional derivative by this ordinary limit on that set and by zero elsewhere.

The scalar $\eta$ is independent of $U$ and has a strictly positive Lebesgue density. Fubini therefore makes the exceptional set Gaussian-null at the random baseline $y=\eta$. At every ordinary differentiability point the right response of step 8 must equal the ordinary derivative. The same conditional proof applies at each baseline along each admissible line, so it identifies the formula at almost every point on almost every line. Multiplying the derivative in $y$ by $\|v\|$ gives
$$
D_v\mathfrak f_\pi(X)
=\mathbb E_Z[\chi_a(R)\dot f_X(R)]
-\int_a^1(\chi_a f_X)'(r)\phi(M_X(r))\dot M_X(r)\,dr,
\qquad |D_v\mathfrak f_\pi(X)|\le C_{a,\sigma,\tau}\|v\|.
$$
The constant on this complete expression is the stronger one from the marked-space Lipschitz argument, not a sum of the separate fixed-$s$ bounds. Absolute continuity on all bounded intervals is already supplied by that Lipschitz argument.

**10. Weighted scalar Gaussian integration by parts.** Let $v\ne0$ and take the coherent version of the specified test weight on the same scalar lines, writing $J(y)=\zeta(X^{U,y})$. For almost every residual background, $J$ is $C^1$ and bounded, and $\|v\|J'(y)=D_v\zeta(X^{U,y})$. If the given bounds hold initially almost surely, conditional Fubini gives them for almost every $y$ on almost every line. Continuity of $J,J'$ and strict positivity of the scalar Gaussian density extend the bounds to every $y$ on those lines. Thus $FJ$ is locally absolutely continuous and
$$
(FJ)'=F'J+FJ'\quad\hbox{for Lebesgue-almost every }y.
$$
The factors $F,J$ are bounded and $F',J'$ are bounded almost everywhere. All these products are integrable against $\phi(y)dy$, and so is $yF(y)J(y)$. Ordinary integration by parts for absolutely continuous functions on $[-L,L]$, using $\phi'=-y\phi$, gives
$$
\int_{-L}^{L}yF(y)J(y)\phi(y)dy
=-[F(y)J(y)\phi(y)]_{-L}^{L}
+\int_{-L}^{L}\bigl(F'(y)J(y)+F(y)J'(y)\bigr)\phi(y)dy.
$$
Boundedness of $FJ$ makes the boundary term tend to zero as $L\to\infty$. The bounds just stated justify dominated convergence for both integrals. Now multiply by $\|v\|$, use $X(v)=\|v\|\eta$, $D_v\mathfrak f_\pi=\|v\|F'$ and $D_v\zeta=\|v\|J'$, and average over the independent residual background. Outer Fubini is justified by $0\le F\le1$, bounded $\zeta,D_v\zeta$, the bound of step 9, and $\mathbb E|X(v)|<\infty$. This yields exactly
$$
\mathbb E[X(v)\zeta(X)\mathfrak f_\pi(X)]
=\mathbb E[\mathfrak f_\pi(X)D_v\zeta(X)+\zeta(X)D_v\mathfrak f_\pi(X)].
$$
Taking $\zeta=1$ gives the unweighted formula. For $v=0$ the score line and the payoff line are constant, $b_v=0$, all conditional response derivatives vanish, $D_0\zeta=0$ and $X(0)=0$ almost surely. Both sides of both identities are consequently zero.

This proves all five clauses with direction-dependent coherent versions. It proves regularity of the complete payoff and the fixed-regularizer signed response and integration-by-parts identity asserted here; it introduces no selector Sobolev assumption, matching-pair identification, or limit uniform as $a,\sigma,s$ vanish. $\square$
