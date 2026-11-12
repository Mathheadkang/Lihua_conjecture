---
type: lemma
title: >-
  Complete signed actual-rank response to inward radial Gaussian loading
  transport
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_same_potential_radial_loading_variation
  - gaussian_bh_private_cutoff_particle_mass_variation
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
  - gaussian_bh_exchangeable_array_variational_compactification
uses_definitions:
  - gaussian_bh_private_smoothed_directing_population
  - gaussian_bh_signed_near_active_gradient_cones
  - gaussian_bh_marked_exchangeable_parameter_array
tags:
  - gaussian_bh
  - radial_loading
  - signed_variation
  - actual_rank
---

## Statement

Use the approved [private-smoothed directing population](../definitions/gaussian_bh_private_smoothed_directing_population.md), [signed near-active conventions](../definitions/gaussian_bh_signed_near_active_gradient_cones.md), and [marked-array conventions](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md). The approved [same-potential radial loading variation](gaussian_bh_same_potential_radial_loading_variation.md), [particle-mass signed variation](gaussian_bh_private_cutoff_particle_mass_variation.md), [private signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md), and [marked-array compactification](gaussian_bh_exchangeable_array_variational_compactification.md) are declared prerequisites before search. Kernel calculus and the additional conditional domination required below are to be proved directly, rather than assumed from continuity of values.

Fix $\sigma,s>0$ with $\sigma^2+s^2<1$, $0<a<1/4$, its specified nondecreasing $C^1$ cutoff $\chi_a$, and $0<q\le q_{\max}=S(1)$. Here $S=\overline\Phi$, $\phi(u)=(2\pi)^{-1/2}e^{-u^2/2}$, $s$ denotes private smoothing, and all tests are one-sided. Put $\tau_s=\sqrt{1-\sigma^2-s^2}$. Let $\pi$ be any lawful deterministic Borel directing law on $E_{\rm ball}$ in a separable real Hilbert space $\mathcal H$, with $M_2(\pi)<\infty$. No extremality or canonical-tag assumption is made until clause 5. All laws and perturbations are chosen before Gaussian innovations.

For $0\le\epsilon<1/2$, let $\pi_\epsilon$ be the pushforward of $\pi$ by
$$
(\theta,v,\ell)\longmapsto(\theta,(1-\epsilon)v,\ell).
$$
Keep $q,\sigma,s,a,\chi_a$, means and tags fixed. Couple the background by the same isonormal series representative $X$ and independent common $Z$ from the approved population definition, and use the private variance
$$
c_\epsilon(v)^2=s^2+\tau_s^2\{1-(1-\epsilon)^2\|v\|^2\}.
$$
Thus each finite conditional Gaussian score has total variance one. Subscripts $\epsilon$ refer to these transported populations, with $\epsilon=0$ omitted. A dot means the right derivative $d/d\epsilon|_{0+}$ along this inward physical transport; it has the opposite sign to the outward trial-particle radial derivative in the preceding result. Retain the actual globally largest non-strict rank $R_\epsilon(X,Z)$ and full fractional FDP $D_\epsilon$ throughout.

1. **Conditional kernels and integrable tail envelope.** For a baseline particle $x=(\theta,v,\ell)$ and a fixed real threshold $z$, set
$$
K_{\epsilon,X,x}(z)=S\!\left(\frac{z-\theta-\tau_s(1-\epsilon)X(v)}{c_\epsilon(v)}\right),
\qquad K_{X,x}=K_{0,X,x},\qquad k_{X,x}=\partial_\theta K_{X,x},
$$
$$
L_{X,x}(z)=-\tau_sX(v)k_{X,x}(z)
+\tau_s^2\|v\|^2\partial_\theta^2K_{X,x}(z).
$$
Prove $\dot K_{X,x}(z)=L_{X,x}(z)$ and, for the conditional total and true tails,
$$
\dot H_X(z)=\int L_{X,x}(z)d\pi(x),\qquad
\dot V_X(z)=\int\ell L_{X,x}(z)d\pi(x).
$$
Prove joint measurability, almost-everywhere validity and representative invariance for the transported family and every stated countable family of finite endpoints, including all required differentiation under $\pi$. Establish, simultaneously for $0\le\epsilon<1/2$,
$$
\max\{\|H_{\epsilon,X}-H_X\|_\infty,
\|V_{\epsilon,X}-V_X\|_\infty\}\le\epsilon C_X,
\qquad
C_X=C_{s,\tau_s}\left(1+\int|X(v)|d\pi(x)\right),
$$
with an explicit finite $C_{s,\tau_s}$ independent of $\pi$, means and Hilbert dimension, and prove $\mathbb E_X C_X<\infty$. The envelope uses an integrated Gaussian moment, never a samplewise supremum over the Hilbert ball.

2. **Fixed-rank differentiation and true-tail error.** With the approved density fields $h_X=-H_X'>0$ and $h_{0,X}=-V_X'\ge0$, prove, locally uniformly on every compact rank interval in $(0,1)$,
$$
\dot Q_X(r)=\frac{\dot H_X(Q_X(r))}{h_X(Q_X(r))},
$$
$$
\dot f_X(r)=\frac{\dot V_X(Q_X(r))-
[h_{0,X}/h_X](Q_X(r))\dot H_X(Q_X(r))}{r}.
$$
For every $a\le r<1$, prove
$$
|V_{\epsilon,X}(Q_{\epsilon,X}(r))-V_X(Q_X(r))|
\le2\epsilon C_X.
$$
At rank one use the unchanged true-mass endpoint $f_{\epsilon,X}(1)=\int\ell d\pi$, with $\dot f_X(1)=0$ and zero true-tail change. Rank zero has zero cutoff payoff; set $\chi_a(R)\dot f_X(R)=0$ on $R\le a$.

3. **All-minima envelope and complete actual response.** For $u_q(r)=S^{-1}(qr)$ retain the approved barrier, suffix minimum and full active set
$$
B_X(r)=\frac{u_q(r)-Q_X(r)}\sigma,\quad B_X(1)=+\infty,\qquad
M_X(r)=\min_{t\in[r,1]}B_X(t),\qquad
\mathcal A_X(r)=\operatorname*{argmin}_{t\in[r,1]}B_X(t)
$$
for $0<r<1$, with $M_X(1)=+\infty$. Define their transported versions in the same way. Prove the right envelope derivative
$$
\dot M_X(r)=\frac1\sigma\min_{t\in\mathcal A_X(r)}[-\dot Q_X(t)].
$$
With $w_X(r)=(\chi_a f_X)'(r)$ and $\mathcal F^a(\pi_\epsilon;q,\sigma,s)=\mathbb E[\chi_a(R_\epsilon)D_\epsilon]$, prove existence and finiteness of the complete right derivative and the identity
$$
\dot{\mathcal F}^{a}
=\mathbb E_{X,Z}[\chi_a(R)\dot f_X(R)]
-\mathbb E_X\int_a^1 w_X(r)\phi(M_X(r))\dot M_X(r)\,dr.
$$
The first term uses the unperturbed actual rank $R=R_0$. The integral is over $a<r<1$, with no undefined rank-one product. Justify all envelope, measurability, endpoint, absolute-integrability and limit-interchange steps, retaining every active suffix minimum and both signed bulk and rank contributions. No unique old fold, finite or generic critical set, positive-part replacement or deletion of a signed dilution contribution is allowed.

4. **Actual-rank qualifier transfer and conditional domination.** Put
$$
L_{q,a}=\sup_{a/2\le r\le1}\frac q{\phi(S^{-1}(qr))},\qquad
d_X=\epsilon C_X,\qquad \Delta_X=\frac{d_XL_{q,a}}\sigma.
$$
For almost every $X$, whenever $d_X<a/2$, prove for every $a\le r<1$ the brackets for the actual globally largest ranks
$$
\mathbf1\{R_0(X,Z-\Delta_X)\ge r+d_X\}
\le\mathbf1\{R_\epsilon(X,Z)\ge r\}
\le\mathbf1\{R_0(X,Z+\Delta_X)\ge r-d_X\}.
$$
Extend survival by zero above rank one. Adapt the approved survival absolute-continuity and translation-uniform-integrability argument to this conditional random $d_X$: establish absolute continuity of $r\mapsto S(M_X(r))$ on $[a/2,1]$ with value zero at one, the all-active-minima pointwise survival derivative, and convergence of the survival difference quotients in $L^1(dr)$ before integrating against $w_X$.

Prove conditional compact uniformity of the quantile differentiation and the barrier envelope, absence of minimizing escapes to rank one, and convergence of the perturbed actual rank outside its Gaussian-null jump levels. Establish a finite constant $C(q,\sigma,s,a,\chi_a)$ independent of $X,\pi$ and Hilbert dimension such that
$$
\left|\frac{\mathbb E_Z[\chi_a(R_\epsilon)D_\epsilon\mid X]
-\mathbb E_Z[\chi_a(R)D\mid X]}\epsilon\right|
\le C(q,\sigma,s,a,\chi_a)C_X.
$$
For $d_X\ge a/2$ use bounded cutoff payoff and $1/\epsilon\le2C_X/a$; do not assume the small-perturbation regime is uniform in $X$. Use $\mathbb E C_X<\infty$ to justify the outer expectation. No reciprocal-density bound uniform over $X$ or $\pi$ is presumed.

5. **Genuine extremal comparison and finite endpoint recovery.** At a genuine deterministic global maximum of the approved fixed-level objective $\mathcal F^a-\eta M_2$, $\eta>0$, or of the approved normalized objective
$$
\frac{\mathcal F^a(\pi;q,\sigma,s)}{qS^{-1}(q)}
-\eta M_2(\pi)-\delta\log(1/q),\qquad \eta,\delta>0,
$$
derive
$$
\dot{\mathcal F}^{a}\le0
$$
along this inward transport, because the level and second mean moment are unchanged. Do not identify this nonlinear actual response with minus the integral of the radial contact derivative $J$ from one chosen dual matching pair without an additional theorem.

After fixing each positive $\epsilon$, use the approved endpoint approximation to recover lawful canonical ordinary finite Gaussian endpoint models whose full FDR, cutoff FDR and empirical second mean moment differ from the transported endpoint quantities by $o(\epsilon)$ as $\epsilon\downarrow0$. Retain the full fractional FDP, original tag rules and unit marginal variances; approximate any false-tagged zero by a strictly positive mean with moment control. Choose atomization only after fixing the endpoint. No finite-derivative limit is exchanged with $\epsilon$.

All constants in this checkpoint may depend on the fixed regularizers and $q$. The statement asserts neither covariance monotonicity for arbitrary models, Gaussian Sobolev or bounded-variation regularity of actual selectors, a Gaussian integration-by-parts formula for actual switching weights, nor a $q$-scaled estimate uniform as regularizers vanish. These remain later proof obligations.

## Proof

All parameter laws and all radial paths in this proof are deterministic and chosen before the Gaussian innovations. Write $\tau=\tau_s$. We use the actual-rank and finite-endpoint conclusions of the approved [private signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md), and its approved [marked-array comparison setting](gaussian_bh_exchangeable_array_variational_compactification.md). The elementary kernel calculation of the [same-potential radial variation](gaussian_bh_same_potential_radial_loading_variation.md) and the quantile, qualifier-transfer and translation arguments of the [particle-mass variation](gaussian_bh_private_cutoff_particle_mass_variation.md) are reproved below for this nonaffine radial family. No extremal hypothesis, potential certificate, or bound for a selector is used in §§1–8.

### 1. Coherent versions and an integrated kernel bound

The partial sums defining the isonormal series are jointly measurable in the loading and background; their convergence set is measurable, and setting their limit to zero off this set gives the specified jointly measurable representative. For each deterministic loading $v$, the series converges almost surely and $X(v)$ has law $\|v\|N$, where $N$ is standard normal. Fubini and Tonelli therefore give one background event of probability one on which the series converges for $\pi$-almost every particle and
$$
I_X:=\int|X(v)|d\pi(x)<\infty,\qquad
\mathbb E I_X=\sqrt{2/\pi}\int\|v\|d\pi(x)\le\sqrt{2/\pi}.
$$
On the convergence event at each such $v$, partial-sum linearity gives
$$
X((1-\epsilon)v)=(1-\epsilon)X(v)
$$
simultaneously for every $0\le\epsilon<1/2$. Thus this single event supplies the entire transported family, rather than one exceptional set for each perturbation. Intersect it with the Fubini events for each member of any specified countable deterministic endpoint or recovery family. All statements below are made on this common good event.

For a baseline particle put $b=\tau X(v)$ and $d_v=\tau^2\|v\|^2$. For
$$
F(\mu,u)=S((z-\mu)/\sqrt u),\qquad y=(z-\mu)/\sqrt u,
$$
direct differentiation gives
$$
\partial_\mu F=\phi(y)/\sqrt u,\qquad
\partial_\mu^2F=y\phi(y)/u,\qquad
\partial_uF=\tfrac12\partial_\mu^2F.
$$
Here $\mu_\epsilon=\theta+(1-\epsilon)b$ and $u_\epsilon=c_\epsilon^2=s^2+\tau^2-(1-\epsilon)^2d_v$. Its center velocity is $-b$ and its variance velocity is $2(1-\epsilon)d_v$. Consequently
$$
\partial_\epsilon K_{\epsilon,X,x}(z)
=-\tau X(v)\partial_\theta K_{\epsilon,X,x}(z)
+\tau^2(1-\epsilon)\|v\|^2\partial_\theta^2K_{\epsilon,X,x}(z).
$$
At zero this is exactly $L_{X,x}(z)$, with the inward sign in the statement. Since $c_\epsilon\ge s$ and $\|v\|\le1$, maximizing $\phi$ and $|y|\phi(y)$ gives, uniformly in score, particle and perturbation,
$$
|\partial_\epsilon K_{\epsilon,X,x}(z)|\le A|X(v)|+B,\qquad
A=\frac{\tau}{s\sqrt{2\pi}},\qquad
B=\frac{\tau^2}{s^2\sqrt{2\pi e}}.
$$
Indeed the maxima are $1/\sqrt{2\pi}$ and $1/\sqrt{2\pi e}$, respectively. Define
$$
C_{s,\tau}=A+B,\qquad C_X=(A+B)(1+I_X).
$$
The fundamental theorem along each particle path, followed by integration, proves simultaneously for every $0\le\epsilon<1/2$
$$
\|H_{\epsilon,X}-H_X\|_\infty\le\epsilon C_X,\qquad
\|V_{\epsilon,X}-V_X\|_\infty\le\epsilon C_X,
$$
and
$$
\mathbb E C_X\le(A+B)(1+\sqrt{2/\pi})<\infty.
$$
These constants are independent of means, the directing law, and the Hilbert dimension. The bound is an integrated first Gaussian moment, not a supremum of a field over the ball.

The same bound dominates perturbation difference quotients under $\pi$, so dominated convergence gives
$$
\dot H_X(z)=\int L_{X,x}(z)d\pi(x),\qquad
\dot V_X(z)=\int\ell L_{X,x}(z)d\pi(x).
$$
For completeness, every finite score derivative of a Gaussian kernel with variance at least $s^2$ is a polynomial times $\phi$ divided by a power of $c_\epsilon$, hence has a finite bound depending only on $s$ and the derivative order. Applying score derivatives to the displayed generator bounds each corresponding first perturbation derivative by $C_j(1+|X(v)|)$. Dominated convergence thus proves joint continuity in $(\epsilon,z)$ of the integrated score derivatives and their first perturbation derivatives on compact parameter/score sets, including the right endpoint at zero. In particular $(H_\epsilon-H)/\epsilon\to\dot H$ and $(V_\epsilon-V)/\epsilon\to\dot V$ uniformly on every compact score interval: write each quotient as the average of its continuous perturbation derivative between zero and $\epsilon$.

The series, kernels and their integrals are jointly measurable in background, perturbation and score. Two coherently coupled isonormal-series representatives of the same process agree almost surely at every deterministic loading. Fubini gives their agreement for almost every baseline particle, and radial partial-sum linearity extends it to all its transported loadings simultaneously. Kernel equality holds at every score, either directly or first at rational scores and then by continuity. Intersecting the identical events for the stated countable endpoint family proves representative invariance there as well. Isometric presentations can be coupled by the corresponding isonormal evaluations. This establishes the required version assertions without asserting samplewise continuity of an infinite-dimensional field.

### 2. Quantiles, the signed marked-tail derivative, and cutoff bounds

The radial map preserves the closed ball, means and tags. Hence every $\pi_\epsilon$ is lawful and $M_2(\pi_\epsilon)=M_2(\pi)<\infty$. Its finite scores have covariance
$$
\operatorname{Cov}(T_i,T_j\mid x_1,\ldots,x_n)
=\tau^2(1-\epsilon)^2\langle v_i,v_j\rangle+\sigma^2\quad(i\ne j),
$$
and diagonal variance
$$
\tau^2(1-\epsilon)^2\|v_i\|^2+c_\epsilon(v_i)^2+\sigma^2=1.
$$
The private noises remain independent of one another and of $X,Z$.

On the good background event, dominated convergence at scores tending to either infinity shows that every $H_\epsilon$ decreases from one to zero. Its density $h_\epsilon$ is everywhere positive, and $0\le h_{0,\epsilon}\le h_\epsilon$. All these functions are smooth in score by §1. Their inverses are jointly measurable; for example
$$
\{Q_\epsilon(r)<z\}=\{H_\epsilon(z)<r\}.
$$
Fix a compact rank interval $I\subset(0,1)$. Uniform tail convergence traps $Q_\epsilon(I)$ in a common compact score interval for sufficiently small $\epsilon$ and gives $Q_\epsilon\to Q$ uniformly on $I$. The positive minimum of $h$ on that conditional score interval is all that is needed here. The continuity established in §1, or the implicit equation differentiated at a nearby perturbation parameter $\gamma$, gives
$$
\partial_\gamma Q_\gamma(r)
=\frac{(\partial_\gamma H_\gamma)(Q_\gamma(r))}{h_\gamma(Q_\gamma(r))}.
$$
This derivative is jointly continuous for small $\gamma$ and $r\in I$. Integrating it over $[0,\epsilon]$ proves locally uniform convergence of quantile difference quotients, with
$$
\dot Q_X(r)=\frac{\dot H_X(Q_X(r))}{h_X(Q_X(r))}.
$$
Chain differentiation of $v_\epsilon(r)=V_\epsilon(Q_\epsilon(r))$, whose score derivative is $-h_{0,\epsilon}$, now gives, locally uniformly on $I$,
$$
\dot f_X(r)=\frac{\dot V_X(Q_X(r))-[h_{0,X}/h_X](Q_X(r))\dot H_X(Q_X(r))}{r}.
$$
No lower density bound uniform in background or law has been used.

A different argument gives the bound needed up to the terminal rank. Put $z_\epsilon=Q_\epsilon(r)$, $z=Q(r)$ and $d=\epsilon C_X$. The inverse equations imply $|H(z_\epsilon)-H(z)|\le d$. Integrating $h_0\le h$ between these scores gives
$$
|V(z_\epsilon)-V(z)|\le d,\qquad
|V_\epsilon(Q_\epsilon(r))-V(Q(r))|\le2d\quad(0<r<1).
$$
At rank one the true mass is unchanged, so this error is zero and $\dot f_X(1)=0$.

Ordinary rank differentiation gives $v'(r)=h_0(Q(r))/h(Q(r))\in[0,1]$, while $0\le v(r)\le r$. Thus
$$
0\le f\le1,\qquad |f'(r)|=|v'(r)-f(r)|/r\le1/r.
$$
The limit of $v(r)$ at one is the total true mass. Define $g(r)=\chi_a(r)f(r)$ for positive ranks and $g(0)=0$. It is zero through $a$, continuous at one, and absolutely continuous on $[a,1]$: apply the fundamental theorem below one and then the integrable derivative bound and endpoint limit. With $w=g'$,
$$
|w|\le W_a:=\|\chi_a'\|_\infty+1/a,\qquad
\int_a^1|w(r)|dr\le T_a:=1+\log(1/a).
$$
The same assertions hold for every $g_\epsilon$. The true-tail error gives the refined estimate
$$
\left|\frac{g_\epsilon(r)-g(r)}\epsilon\right|
\le\frac{2C_X\chi_a(r)}r\quad(a<r<1),
$$
with value zero on $r\le a$ and also at $r=1$. In particular this quotient is bounded by $2C_X/a$ everywhere, and $|\chi_a(r)\dot f_X(r)|\le2C_X/a$ with the endpoint assignments in the statement.

### 3. Uniform endpoint exclusion and the full active-minimum envelope

Fix the background and $0\le\epsilon\le\epsilon_0<1/2$. For each finite $K>0$, §1 gives continuity of $\epsilon\mapsto H_\epsilon(-K)$. Every such tail value is strictly less than one because each almost-everywhere finite-center Gaussian kernel is strictly less than one. Compactness therefore gives
$$
\max_{0\le\epsilon\le\epsilon_0}H_\epsilon(-K)<1.
$$
For ranks above this maximum, $Q_\epsilon(t)<-K$. Thus $Q_\epsilon(t)\to-\infty$ uniformly in this perturbation interval as $t\uparrow1$. Since $u_q(t)\ge1$, $B_\epsilon(t)\to+\infty$ uniformly there as well.

For suffix endpoints in any fixed $[c,b]\subset(0,1)$ choose $t_0\in(b,1)$. Continuity of $Q_\epsilon(t_0)$ gives a common upper bound for the trial values $B_\epsilon(t_0)$. The preceding divergence excludes all sufficiently large ranks from every corresponding minimizing set. Thus all minima are attained in a common $[c,k]$, $k<1$, after reducing the perturbation interval if necessary. On this compact §2 gives the uniform expansion
$$
B_\epsilon(t)=B(t)+\epsilon b_*(t)+o(\epsilon),\qquad
b_*(t)=-\dot Q(t)/\sigma,
$$
where $b_*$ is continuous. The remainder is uniform on the common minimizing compact. In particular $M_\epsilon\to M$ uniformly for suffix endpoints in $[c,b]$, since the difference between two minima over the same suffix subset of this compact is bounded by the sup norm of $B_\epsilon-B$.

Fix an interior rank $r$ and let $A=\mathcal A(r)$, a nonempty compact set. Evaluation at a point of $A$ minimizing $b_*$ gives
$$
\limsup_{\epsilon\downarrow0}\frac{M_\epsilon(r)-M(r)}\epsilon\le\min_{t\in A}b_*(t).
$$
For any perturbed minimizer $t_\epsilon$ in the common compact, uniform value convergence gives $B(t_\epsilon)\to M(r)$, so every convergent subsequence has limit in $A$. Also
$$
\frac{M_\epsilon(r)-M(r)}\epsilon
=\frac{B(t_\epsilon)-M(r)}\epsilon+b_*(t_\epsilon)+o(1)
\ge b_*(t_\epsilon)+o(1).
$$
If the lower limit were smaller than $\min_A b_*$, a sequence realizing that strict inequality followed by a convergent subsequence of minimizers would contradict continuity of $b_*$. Hence
$$
\dot M_X(r)=\min_{t\in\mathcal A_X(r)}b_*(t)
=\frac1\sigma\min_{t\in\mathcal A_X(r)}[-\dot Q_X(t)].
$$
This argument retains every tie. The compact uniformity used for the barrier envelope is the uniform first-order expansion of $B_\epsilon$ on common minimizing compacts and uniform convergence of the minimum values there. The displayed right derivative of the minimum is pointwise in $r$; uniform convergence of its difference quotients across tied minimizers is neither needed nor asserted. The survival quotients will instead converge in $L^1$ in §6.

The suffix infimum equals the infimum of $B_\epsilon(t)$ over rational $r<t<1$, by continuity, so it is jointly measurable in $(X,\epsilon,r)$. This also proves measurability of the envelope derivative through its difference-quotient limit, without any measurable choice of one active fold.

### 4. Identification of actual ranks and conditional qualifier transfer

For each perturbation, a positive rank $t<1$ qualifies exactly when $B_\epsilon(t)\le Z$. The qualifier set is closed on intervals away from zero and is empty near one for every finite $Z$ by §3. Consequently its supremum is attained whenever positive, and for every interior rank
$$
\{R_\epsilon(X,Z)\ge r\}=\{Z\ge M_{\epsilon,X}(r)\},\qquad
P_{\epsilon,X}(r):=\mathbb P_Z(R_\epsilon\ge r\mid X)=S(M_{\epsilon,X}(r)).
$$
No finite $Z$ gives rank one: the total tail at $u_q(1)-\sigma Z$ is strictly below one, and the same endpoint argument excludes nearby qualifiers. Set $P_{\epsilon,X}(1)=0$. These identities give measurable actual largest ranks, for example by their survival events at rational ranks. The approved private signed-variation prerequisite identifies their full fractional FDP with $f_{\epsilon,X}(R_\epsilon)$, zero at rank zero; it is not replaced by a success indicator. The identities just proved hold simultaneously for the entire coherent family, all finite $Z$ and every interior rank on the good event.

Fix $X$ and abbreviate $d=\epsilon C_X<a/2$, $L=L_{q,a}$ and $\Delta=dL/\sigma$. The finite constant $L$ is the maximum of $|u_q'|=q/\phi(u_q)$ on $[a/2,1]$. Suppose first $r+d<1$ and $R_0(Z-\Delta)\ge r+d$. Its attained largest qualifier $t$ lies in $[r+d,1)$. Put $y=t-d\ge r$. The mean value bound gives
$$
u_q(y)-\sigma Z\le u_q(t)+dL-\sigma Z=u_q(t)-\sigma(Z-\Delta).
$$
The tails decrease, and $H_\epsilon\ge H-d$, so $H_\epsilon(u_q(y)-\sigma Z)\ge t-d=y$. Thus $R_\epsilon(Z)\ge r$. If $r+d\ge1$, the left event is empty, using rank-one exclusion at equality and the zero extension above one.

Conversely, if $R_\epsilon(Z)\ge r$, its attained qualifier $t=R_\epsilon(Z)<1$ gives $y=t-d\ge r-d>a/2$. Now
$$
u_q(y)-\sigma(Z+\Delta)\le u_q(t)-\sigma Z.
$$
Since $H\ge H_\epsilon-d$, $y$ is a baseline qualifier at $Z+\Delta$. Therefore $R_0(Z+\Delta)\ge r-d$. These two transfers prove precisely both indicator brackets, with non-strict inequalities, for every $a\le r<1$ and finite $Z$. The quantity $C_X$ has been fixed only inside this conditional argument. No deterministic bound for it has been assumed.

### 5. Absolute continuity of baseline survival through rank one

Fix $[a/2,b]$ with $b<1$. The minimizing compact from §3 places all its baseline minimizers in $[a/2,k]$, $k<1$, where the $C^1$ barrier has a finite Lipschitz constant $L_B$. For $r_1<r_2\le b$, $M(r_1)\le M(r_2)$. If a minimizer at $r_1$ lies at least at $r_2$, equality holds. Otherwise such a minimizer $t$ lies in $[r_1,r_2)$ and
$$
0\le M(r_2)-M(r_1)\le B(r_2)-B(t)\le L_B(r_2-r_1).
$$
Thus $M$ and $P=S(M)$ are locally Lipschitz below one. Moreover $M(r)\to+\infty$ and $P(r)\to0$ at one. Because $P$ is nonincreasing, its compact-interval fundamental-theorem identities yield
$$
\int_{a/2}^1|P'(r)|dr
=\lim_{b\uparrow1}[P(a/2)-P(b)]=P(a/2)\le1.
$$
Passing to the endpoint in those identities gives $P(r)=\int_r^1(-P'(t))dt$ for $r\in[a/2,1]$. This proves absolute continuity on the closed interval with value zero at one, including absence of a singular terminal remainder. Extend $P$ constantly below $a/2$ and by zero above one. The extension is locally absolutely continuous on the real line and $F:=|P'|\in L^1(\mathbb R)$ with $\|F\|_1\le1$.

### 6. Direct conditional translation uniform integrability

Integrate the two qualifier brackets in $Z$. The survival function of a standard normal is $1/\sqrt{2\pi}$-Lipschitz. Thus, with the extension just specified,
$$
P_\epsilon(r)\le P(r-d)+\frac{dL}{\sigma\sqrt{2\pi}},\qquad
P_\epsilon(r)\ge P(r+d)-\frac{dL}{\sigma\sqrt{2\pi}}.
$$
The second bound remains true when $r+d\ge1$. For $J_\epsilon(r)=(P_\epsilon(r)-P(r))/\epsilon$ this gives
$$
|J_\epsilon(r)|\le
\frac{P(r-d)-P(r)}\epsilon+
\frac{P(r)-P(r+d)}\epsilon+
\frac{2C_XL}{\sigma\sqrt{2\pi}}\quad(a\le r<1).
$$
The two horizontal terms are respectively
$$
\frac{C_X}{d}\int_0^d F(r-v)dv,\qquad
\frac{C_X}{d}\int_0^d F(r+v)dv.
$$
For fixed $X$, let $F_N=\min(F,N)$. Its translation averages are bounded by $N$, while Tonelli bounds the integral over any measurable rank set $E$ of each average of $F-F_N$ by $\|F-F_N\|_1$. Each horizontal term therefore has integral over $E$ at most
$$
C_XN|E|+C_X\|F-F_N\|_1.
$$
First take $N$ large and then $|E|$ small. This proves uniform absolute continuity of the horizontal integrals for all sufficiently small positive perturbations at this background. Their total integrals are at most $C_X$ each. The constant term in the preceding bound has the same uniform absolute-continuity property on $[a,1]$. Hence the family $J_\epsilon$ is uniformly integrable there, conditionally on $X$.

By §3 and ordinary scalar differentiation, at every $a<r<1$
$$
J_\epsilon(r)\longrightarrow J(r):=-\phi(M(r))\dot M(r).
$$
Fatou gives $J\in L^1(a,1)$. Here is the limit interchange explicitly. The uniform $L^1$ bound makes the measures of the sets $\{|J_\epsilon|>K\}$ uniformly small as $K\to\infty$. Uniform absolute continuity of their integrals therefore makes $\int_{|J_\epsilon|>K}|J_\epsilon|$ uniformly small. The same tail property holds for the integrable limit $J$. Clipping each function to $[-K,K]$ gives pointwise convergence and, by bounded convergence, $L^1$ convergence of the clipped functions. Letting $K\to\infty$ proves
$$
\|J_\epsilon+\phi(M)\dot M\|_{L^1(a,1)}\longrightarrow0.
$$
Only now multiply by the bounded signed $w$. In particular the conditional rank-law derivative is $-\int_a^1w\phi(M)\dot M\,dr$, with an absolutely integrable integrand. Tied active minima require no separate exceptional-rank convention.

### 7. Moving payoff and convergence of actual ranks

The map $Z\mapsto R_0(X,Z)$ is bounded and nondecreasing, and therefore has at most countably many discontinuities. To prove full rank convergence at each continuity point, the qualifier-transfer proof of §4 can be repeated with any fixed positive rational lower cutoff $c$ in place of $a$, taking $d<c/2$ and $\Delta_c=dL_{q,c}/\sigma$. This repetition uses only the uniform tail error, not the cutoff payoff.

If $R_0(Z)>0$, choose any $0<r<R_0(Z)$ and a rational $c\le r$. At a continuity point, $R_0(Z-\Delta_c)>r+d$ eventually, so the left bracket gives $R_\epsilon(Z)\ge r$. Conversely, for any $r>R_0(Z)$ below one, choose rational $c\le r$. If $R_\epsilon(Z)\ge r$ along a sequence, the right bracket would give $R_0(Z+\Delta_c)\ge r-d$, contrary to continuity. These statements also yield $\limsup R_\epsilon\le0$ when $R_0(Z)=0$. Thus $R_\epsilon(Z)\to R_0(Z)$ at every continuity point, including zero ranks. Rank one is absent for finite $Z$. The countable excluded set is Gaussian-null for each fixed $X$; the convergence event itself is measurable by the rank measurability already proved.

Absolute continuity of $g$ and $g(a)=0$ give the signed survival representation
$$
g(t)=\int_a^1w(r)\mathbf1_{\{t\ge r\}}dr\quad(0\le t\le1).
$$
Since $\int|w|\le T_a$, signed Fubini gives the exact decomposition
$$
\mathbb E_Z[g_\epsilon(R_\epsilon)-g(R)]
=\mathbb E_Z[(g_\epsilon-g)(R_\epsilon)]
+\int_a^1w(r)[P_\epsilon(r)-P(r)]dr.
$$
At a continuity point with $a<R_0(Z)<1$, the compact-uniform fixed-rank differentiation of §2 and convergence of $R_\epsilon$ give
$$
\frac{(g_\epsilon-g)(R_\epsilon)}\epsilon
\longrightarrow\chi_a(R_0)\dot f_X(R_0).
$$
If $R_0<a$, then $R_\epsilon<a$ eventually and the quotient is zero. At $R_0=a$, either it is zero or its absolute value is at most $2C_X\chi_a(R_\epsilon)/R_\epsilon$, which tends to zero by continuity of $\chi_a$ and its zero value at $a$. The global bound $2C_X/a$ justifies conditional dominated convergence in $Z$. Combining it with the $L^1$ survival convergence in §6 proves the full conditional derivative, with both its signed bulk and signed rank contributions.

### 8. Domination across all backgrounds and the complete formula

In the regime $d<a/2$, each horizontal term of §6 has integral at most $C_X$ on $[a,1]$. Consequently
$$
\int_a^1|w(r)|\,|J_\epsilon(r)|dr
\le\left(2W_a+\frac{2T_aL_{q,a}}{\sigma\sqrt{2\pi}}\right)C_X.
$$
The bulk estimate and exact decomposition in §7 imply
$$
\left|\frac{\mathbb E_Z[g_\epsilon(R_\epsilon)-g(R)]}{\epsilon}\right|
\le C_*C_X,\qquad
C_*:=\frac2a+2W_a+\frac{2T_aL_{q,a}}{\sigma\sqrt{2\pi}}.
$$
If $d\ge a/2$, use the bounded full cutoff payoffs $0\le g_\epsilon(R_\epsilon),g(R)\le1$ to obtain instead
$$
\left|\frac{\mathbb E_Z[g_\epsilon(R_\epsilon)-g(R)]}{\epsilon}\right|
\le1/\epsilon\le2C_X/a\le C_*C_X.
$$
Thus the required conditional domination holds for every $0<\epsilon<1/2$, with a finite constant independent of $X,\pi$ and dimension. There is no assumption that the small-displacement regime is uniform in background.

Fatou, or the conditional $L^1$ limit, also gives
$$
\int_a^1|w(r)\phi(M(r))\dot M(r)|dr
\le\left(2W_a+\frac{2T_aL_{q,a}}{\sigma\sqrt{2\pi}}\right)C_X.
$$
The absolute bulk contribution is at most $2C_X/a$. Their sum is at most $C_*C_X$, and §1 gives its finite expectation. All derivative terms are jointly measurable by the kernel, inverse and difference-quotient constructions. Dominated convergence of the whole conditional quotient in $X$ therefore proves existence and finiteness of the right derivative, while the separate absolute bounds permit Fubini for its signed terms. Restoring subscripts gives precisely
$$
\dot{\mathcal F}^{a}
=\mathbb E_{X,Z}[\chi_a(R)\dot f_X(R)]
-\mathbb E_X\int_a^1w_X(r)\phi(M_X(r))\dot M_X(r)dr.
$$
The bulk is assigned zero on $R\le a$; at rank one its assigned derivative is zero and the event itself is null. The integral is over the open terminal rank interval, with no undefined rank-one product. Neither a signed dilution term nor any member of an active minimizing set has been dropped.

### 9. Genuine maxima and finite endpoint recovery

Only in this paragraph assume a genuine deterministic global maximum of one of the stated objectives. The inward pushforward is a lawful deterministic competitor fixed before the innovations, and it leaves the level, tags, means and second mean moment unchanged. The exact maximum comparison therefore gives $\mathcal F^a(\pi_\epsilon)\le\mathcal F^a(\pi)$ at fixed level. It gives the same inequality at a normalized maximum because $qS^{-1}(q)>0$ and both penalties are unchanged. Divide by $\epsilon>0$ and use §8 to conclude $\dot{\mathcal F}^a\le0$. This reasoning does not identify the nonlinear all-minima response with an integral of the contact derivative from one dual matching pair.

For each fixed positive $\epsilon$, $\pi_\epsilon$ is a deterministic lawful finite-second-moment endpoint at the original level $q$. Apply the finite-endpoint conclusion in clause 6 of the approved [private signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md) to this endpoint, choosing simultaneous full-FDR, cutoff-FDR and empirical-second-moment errors smaller than $\epsilon^2$.

The canonicalization can be made explicit with a split tolerance. First choose the finite tagged endpoint approximation with all three errors below $\epsilon^2/2$. Change only its false-tagged zero means to a common sufficiently small strictly positive mean $\kappa$. All other means, every tag and the covariance remain fixed. Each score has variance one, so every finite BH threshold equality has probability zero, even if the joint covariance is singular. Coupling the finite Gaussian noise before shifting means, the rejection set is thus eventually constant at almost every sample as $\kappa\downarrow0$. Its full tagged FDP and its cutoff payoff converge, and bounded convergence makes both expectations continuous. The added empirical second moment is at most $\kappa^2$. Choose $\kappa$ sufficiently small to make all three additional errors below $\epsilon^2/2$. The labels are now canonical: true-tagged means were already nonpositive, all false-tagged means are strictly positive. This retains the original tag rules and the full denominator $R_n\vee1$.

The covariance has the Gram component $\tau^2(1-\epsilon)^2\langle v_i,v_j\rangle$, the positive private diagonal $c_\epsilon(v_i)^2$, and the common component $\sigma^2$; hence it is positive semidefinite and has diagonal one. All finite parameters are chosen before their independent Gaussian innovations. Sizes, atomization and canonicalization shifts are selected only after fixing the endpoint. The three errors $\epsilon^2=o(\epsilon)$ do not pass any finite derivative through the perturbation limit.

### 10. Boundary and sign checks

At a particle with $v=0$, both terms of $L$ vanish, as does its inward loading change. If the entire law has zero loadings, all tails and ranks are unchanged and the complete derivative is zero. If all tags are true, $V_\epsilon=H_\epsilon$ and $f_\epsilon=1$, so the two terms in the numerator of $\dot f$ cancel and only the cutoff rank-law response remains. If the true sector is empty, $V_\epsilon=0$ throughout this radial family, so $g_\epsilon=w=0$ and both contributions vanish. Equal active minima enter through their minimum velocity in §3, not through a choice of a preferred fold. The cases $R=a$, $r\uparrow1$, and $\epsilon C_X\ge a/2$ were handled respectively by the refined cutoff bound, uniform endpoint exclusion and closed-interval survival representation, and the bounded-payoff estimate.

Every constant here is for the fixed level and regularizers. The proof establishes no covariance monotonicity, selector Sobolev or BV regularity, Gaussian integration by parts for switching weights, contact-pair identification, or estimate uniform as the regularizers vanish. $\square$
