---
type: lemma
title: Averaged signed mean-level complementarity at regularized Gaussian BH maxima
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
  - gaussian_bh_exchangeable_array_variational_compactification
  - lib_diestel1991_ui_absolute_continuity
  - lib_diestel1991_dunford_pettis_compactness
uses_definitions:
  - gaussian_bh_signed_near_active_gradient_cones
  - gaussian_bh_private_smoothed_directing_population
  - gaussian_bh_marked_exchangeable_parameter_array
  - lib_diestel1991_scalar_l1_ui_weak_topology
tags:
  - gaussian_bh
  - signed_variation
  - near_active_selectors
  - weak_compactness
  - complementarity
---

## Statement

Fix $0<\sigma<1$, $s>0$ with $\sigma^2+s^2<1$, $0<a<1/4$, and the specified nondecreasing $C^1$ cutoff $\chi_a$. Use the [private-smoothed directing population](../definitions/gaussian_bh_private_smoothed_directing_population.md) and the [signed near-active gradient and cone conventions](../definitions/gaussian_bh_signed_near_active_gradient_cones.md), with all symbols and endpoint conventions as defined there. In particular $s$ is private smoothing, all tests are one-sided, $S=\overline\Phi$, $m=S/\phi$, $q_{\max}=S(1)$ and $U=S^{-1}(q)$.

The first three conclusions and the total-flux identity below concern any fixed lawful deterministic directing law $\pi$ with $M_2(\pi)<\infty$ and $0<q\le q_{\max}$. Complementarity and positivity of the normal density concern an actual canonical normalized global maximizer, not an arbitrary directing law. All choices of laws and perturbation velocities precede Gaussian innovations. The approved [complete signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md) supplies its actual largest non-strict rank, full FDP, suffix-minimum identities and exact extremal inequalities; the approved [marked-array compactification](gaussian_bh_exchangeable_array_variational_compactification.md) supplies the lawful completion and its comparison framework. No conditional-background maximizing property is assumed.

1. **Measurable near-active gradients and countably additive compactness.** Prove that $\mathcal T_j$ is nonempty for every $j\ge1$, that the posterior densities and integrated selector vectors are jointly measurable and representative invariant, and that $V_\pm(t)$ belongs to $L^1(\pi)\times\mathbb R$. For this fixed $\pi$ and these fixed regularizers, prove uniform integrability of the mean-density coordinates of all $V_\pm(t)$, over all $j\ge1$ and $t\in\mathcal T_j$, and boundedness of their scalar coordinates. Prove that the weakly closed convex hulls $C_j^\pm$ are nonempty, nested and weakly compact in the topology paired with $L^\infty(\pi)\times\mathbb R$, and hence that $C^\pm$ are nonempty weakly compact convex sets.

The compactness proof must establish uniform absolute continuity with respect to $\pi$. A permitted route truncates the conditional centre energy $\int A_X(x)^2d\pi(x)$ and $|M_X(r)|$, obtains a deterministic compact interval for $Q_X(t)$ on the retained near-active part, and uses $c_s\ge s$ and positive bounded-centre mass to bound $h_X(Q_X(t))$ below. Control the discarded part using finite mean energy, the Gaussian $\phi(M_X(r))$ factor, and $\int_a^1|g_X'(r)|dr\le1+\log(1/a)$. Any alternative must prove the same uniform absolute continuity. Prove the weak compactness and required separation facts directly, for example by clipping densities, extracting weak $L^2$ subsequences and using a countable generating algebra; do not invoke an undeclared finite-dimensional quasidifferential theorem or replace $L^1$ densities by finitely additive dual functionals. No uniform integrability over varying $\pi$ or vanishing regularizers is claimed.

2. **Bulk density and exact support representation.** Define the Gaussian-averaged bulk density by
$$
\mathfrak b(x)=\mathbb E_{X,Z}\left[
\mathbf1_{\{R>a\}}\frac{\chi_a(R)}R
\left\{\ell(x)-\frac{h_{0,X}(Q_X(R))}{h_X(Q_X(R))}\right\}
 k_{X,x}(Q_X(R))\right].
$$
The integrand is set to zero on $R\le a$; any remaining rank-one exceptional set uses the approved zero-probability endpoint convention. Prove that $\mathfrak b$ is measurable and bounded, belongs to $L^1(\pi)$, and satisfies
$$
\int\mathfrak b\,d\pi=0.
$$
For every bounded lawful deterministic mean velocity $b$, and allowed constant level velocity $\lambda$ with $q_\epsilon=q(1+\epsilon\lambda)$, prove
$$
\dot{\mathcal F}^{a}
=\int\mathfrak b\,b\,d\pi
+h_{C^+}(b,\lambda)-h_{C^-}(b,\lambda).
$$
Here the dot is the right derivative along the fixed lawful mean/level perturbation, as in the approved variation lemma. More explicitly, prove for each sign
$$
h_{C^\pm}(b,\lambda)
=\lim_{j\to\infty}h_{C_j^\pm}(b,\lambda)
=\frac1\sigma\mathbb E_X\int_a^1w_{X,\pm}(r)\phi(M_X(r))
\max_{t\in\mathcal A_X(r)}
\left\{\int p_{X,t}(x)b(x)d\pi(x)+\lambda m_t\right\}dr.
$$
Justify the nested-intersection support limit, rational approximation, all active minima, conditional maximization and passage through Gaussian averaging. This is a difference of two support functions; it does not assert a linear directional derivative or a single exact selector realizing every gradient.

3. **Selector-independent total mass and survival flux.** Every $(g_\pm,c_\pm)\in C^\pm$ satisfies
$$
\int g_\pm\,d\pi
=\frac1\sigma\mathbb E_X\int_a^1w_{X,\pm}(r)\phi(M_X(r))dr.
$$
Consequently every pair from $C^+\times C^-$, with $\Psi=\mathfrak b+g_+-g_-$, has the same exact total signed mass
$$
\Gamma_a:=\int\Psi\,d\pi
=\frac1\sigma\mathbb E_X\int_a^1g_X'(r)\phi(M_X(r))dr
=\frac1\sigma\mathbb E_{X,Z}[Z\chi_a(R)D].
$$
Prove the last identity by survival integration using the actual largest-rank law $\mathbb P_Z(R\ge r\mid X)=S(M_X(r))$, with all integrability and boundary terms justified. An upward shift of a retained zero-mean true tag is not a permissible argument for this identity.

4. **Averaged cone inclusion at an actual canonical normalized maximum.** Fix $\eta,\delta>0$. Let $(\pi,q)$ be an actual deterministic directing global maximizer supplied by the approved variation lemma for
$$
\frac{\mathcal F^a(\pi;q,\sigma,s)}{qU}-\eta M_2(\pi)-\delta\log(1/q),
\qquad 0<q\le q_{\max},
$$
and select a canonical maximum, so $\pi\{\theta=0,\ell=0\}=0$. Write $F^a=\mathcal F^a(\pi;q,\sigma,s)$ and $\beta=1-m(U)/U$, and use $E_0,K,K^\circ$ from the cone convention.

First extend the exact normalized extremal inequality from lawful velocities to every $(b,\lambda)\in K$. Use legal truncations away from $E_0$ at $|\theta|\ge\zeta$, then let $\zeta\downarrow0$, justifying convergence by the established uniform integrability and $\theta\in L^1(\pi)$. Do not identify $K$ with a norm closure of uniformly lawful velocities. Prove the exact polar inclusion
$$
\bigl(\mathfrak b-2\eta qU\theta,\ -\beta F^a+\delta qU\bigr)+C^+
\ \subseteq\ C^-+K^\circ.
$$
Prove the needed weak closedness of $C^-+K^\circ$ and the relevant separation statement in the stated dual pairing. All gradients are averaged in $X$ before separation; the velocities remain independent of $X,Z$ and private noises.

In particular, for every selected $(g_+,c_+)\in C^+$ there exists a matching $(g_-,c_-)\in C^-$ such that, on setting $\Psi=\mathfrak b+g_+-g_-$ and $\Lambda=c_+-c_-$,
$$
\Psi=2\eta qU\theta\quad\pi\text{-almost everywhere off }E_0,\qquad
\Psi\ge0\quad\pi\text{-almost everywhere on }E_0,
$$
$$
\Lambda=\beta F^a-\delta qU\quad(q<q_{\max}),\qquad
\Lambda\ge\beta F^a-\delta qU\quad(q=q_{\max}).
$$
These are countably additive, Gaussian-averaged mean and level gradients in the convexified weak-limit sets. No exact active selector realizing a matching pair, pointwise-in-$X$ stationarity, unique active minimum, opposite-sign linearity, or conditional-background optimality is asserted. The $qU$ factor in the mean penalty and both endpoint signs are part of the conclusion.

5. **Normal mass and vanishing mean penalty at fixed private regularizers.** For every matching pair at the canonical normalized maximum, prove that
$$
\Psi-2\eta qU\theta
$$
is a nonnegative $L^1(\pi)$ density supported on $E_0$, with exact total mass
$$
\Gamma_a-2\eta qU\int\theta\,d\pi.
$$
Retain the signed moment term and prove the error bound
$$
\left|2\eta qU\int\theta\,d\pi\right|
\le2qU\sqrt\eta\sqrt{\eta M_2(\pi)}.
$$
For clarity, establish the fixed-private/cutoff vanishing-penalty assertion needed here: with $\sigma,s,a,\chi_a,\delta$ fixed, let $L_\eta^a$ be the normalized maximum in clause 4 and define
$$
L_0^a=\sup_{\substack{\pi\text{ lawful deterministic},\ M_2(\pi)<\infty\\0<q\le q_{\max}}}
\left\{\frac{\mathcal F^a(\pi;q,\sigma,s)}{qS^{-1}(q)}-\delta\log(1/q)\right\}.
$$
Prove $L_0^a<\infty$, $L_\eta^a\to L_0^a$ and $\eta M_2(\pi_\eta)\to0$ for any choices of these maxima as $\eta\downarrow0$. Justify any common coercive level interval used. Thus the displayed signed moment error vanishes along such maximizing families. This is a value/penalty assertion at fixed private regularizers, not a derivative limit or a claim that $L_0^a$ is bounded as $\delta\downarrow0$.

## Scope and provenance

New original draft extracted from the ninth resumed autonomous reassessment in the approved project, Intended Contribution. Both approved theorem dependencies are registered before this target's first counterexample search. The structural posterior-gradient, support and flux statements above are formulated for each fixed finite-moment lawful law; complementarity and normal positivity use an actual canonical normalized maximum. The selector/cone definition records notation only: compactness, uniform integrability, support limits and separation remain obligations of this lemma.

This is an averaged structural target. It does not estimate $\Gamma_a$ or the total normal mass by a universal multiple of $qU^2$, construct paired inverse-Mills transport, pass derivatives through smoothing or cutoff limits, or prove either unrestricted Gaussian BH main bound. A uniform extremal flux estimate remains a separate missing step.

## Proof

We use the approved [complete signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md) for its kernel and actual-rank conclusions, all-minima right derivative, lawful extremal inequality and existence of canonical deterministic maxima. Its [marked-array completion prerequisite](gaussian_bh_exchangeable_array_variational_compactification.md) is used only through those registered conclusions. Throughout parts 1--5 the law $\pi$ and all positive regularizers are fixed. Background assertions are understood on the probability-one set supplied by the variation lemma. We prove compactness and separation in the declared countably additive pairing, rather than assuming either as a differentiability principle.

### 1. Measurability, selection and elementary bounds

The kernels and quantiles supplied by the variation lemma make $(X,t,x)\mapsto k_{X,x}(Q_X(t))$ jointly measurable for $0<t<1$. The denominator $h_X(Q_X(t))$ is measurable and strictly positive, so $p_{X,t}(x)$ is jointly measurable and nonnegative, with
$$
\int p_{X,t}(x)d\pi(x)=1.
$$
For a fixed $X$, the quantile is continuous, and dominated convergence using $k_{X,x}(z)\le1/(s\sqrt{2\pi})$ shows that its numerator and denominator integrals against any bounded Borel function are continuous in $t$. The same holds for $m_t$.

Enumerate $\mathbb Q\cap(0,1)$ as $(d_n)_{n\ge1}$. For each $(X,r)$ and $j$, choose the first $d_n$ with $d_n\ge r$ and $B_X(d_n)\le M_X(r)+1/j$. Such a rational exists: a minimizer $t_*\in[r,1)$ exists by the variation lemma, and continuity of $B_X$ permits rationals approaching $t_*$, from the right when $t_*=r$. Each eligibility condition is measurable, so the first-index choice is measurable. Assign a fixed rational on the background-null exceptional set. This constructs an element of $\mathcal T_j$ for every $j$.

For representative invariance, two valid isonormal representatives agree for almost every background at every fixed parameter $v$. Fubini therefore gives agreement for $\pi$-almost every $x$ on one background event of probability one. On that event all kernels integrated against $\pi$, their quantiles, barriers and active sets agree; their unintegrated kernels agree for $\pi$-almost every $x$ at every real argument. Thus the admissible selector classes agree modulo product null sets, and the resulting integrated densities agree $\pi$-almost everywhere. This also proves invariance for any specified selector and its transported counterpart. Joint measurability and Tonelli below show that these densities have measurable representatives. Equivalently the integrands define measurable $L^1(\pi)$-valued maps: $L^1(\pi)$ is separable on this standard Borel probability space, and simple-function approximation of the jointly measurable kernels gives this assertion.

Write $C_a=1+\log(1/a)$. Since $0\le f_X\le1$, $|f_X'(r)|\le1/r$, and $\chi_a$ is nondecreasing,
$$
\int_a^1|g_X'(r)|dr
\le\int_a^1\chi_a'(r)dr+\int_a^1\frac{dr}{r}
=C_a.
$$
Here and below integrals at the open endpoint are improper integrals; the bound makes them absolutely convergent. Also $u_q(t)\ge U\ge1$ and
$$
m(z)=\int_0^\infty e^{-zy-y^2/2}dy
$$
is decreasing for $z\ge1$. Hence $0<m_t\le m(U)$. Tonelli, posterior normalization and $\phi\le1/\sqrt{2\pi}$ give, for either sign and every admissible selector,
$$
V_{\pm,\mathrm{mean}}(t)\ge0,\qquad
\|V_{\pm,\mathrm{mean}}(t)\|_1\le A_a:=\frac{C_a}{\sigma\sqrt{2\pi}},\qquad
0\le V_{\pm,\mathrm{scalar}}(t)\le m(U)A_a.
$$
In particular these vectors belong to $L^1(\pi)\times\mathbb R$.

### 2. Uniform absolute continuity for the fixed directing law

Let $E_X=\int A_X(x)^2d\pi(x)$. The isonormal variance bound $\mathbb E X(v)^2=\|v\|^2\le1$ implies
$$
\mathbb E E_X\le2M_2(\pi)+2\tau_s^2<\infty.
$$
Fix $L,T>0$ and retain $E_X\le L$, $|M_X(r)|\le T$. For any $t=t(X,r)$ from any $\mathcal T_j$, the inequalities $t\ge r>a$ and $B_X(t)\le M_X(r)+1$ imply
$$
Q_X(t)=u_q(t)-\sigma B_X(t)\ge U-\sigma(T+1).
$$
Conditionally on $X$, let $Y=A_X(x)+c_s(v)\zeta$ with $x\sim\pi$ and an independent standard normal $\zeta$. Then $\mathbb E[Y^2\mid X]\le L+1$. If $Q_X(t)>0$, Markov's inequality and $\mathbb P(Y\ge Q_X(t)\mid X)=t\ge a$ give $Q_X(t)^2\le(L+1)/a$. The same upper bound holds if the quantile is nonpositive. Put
$$
J_{L,T}=\left[\min\{U-\sigma(T+1),0\},\sqrt{(L+1)/a}\right],
\qquad H_L=\sqrt{2L+2}.
$$
At least half the $\pi$ mass has $|A_X(x)|\le H_L$, since its complement has mass at most $L/(2L+2)<1/2$. The positive continuous function $c^{-1}\phi((z-A)/c)$ has a positive minimum $\kappa_{L,T}$ on
$$
z\in J_{L,T},\quad |A|\le H_L,\quad s\le c\le\sqrt{1-\sigma^2}.
$$
Thus, on the retained part,
$$
h_X(Q_X(t))\ge\kappa_{L,T}/2,\qquad
p_{X,t}(x)\le P_{L,T}:=\frac{2}{s\sqrt{2\pi}\kappa_{L,T}}
$$
for $\pi$-almost every $x$. For every measurable particle set $A$, split the defining integral for $V_\pm$ into the retained part, $\{E_X>L\}$, and $\{|M_X(r)|>T\}$ not already discarded. On the latter parts use only $\int_Ap_{X,t}d\pi\le1$. This yields uniformly in $j,t$ and the sign
$$
\int_A V_{\pm,\mathrm{mean}}(t)d\pi
\le D_{L,T}\pi(A)+A_a\mathbb P(E_X>L)
+\frac{C_a}{\sigma}\sup_{|z|>T}\phi(z),
\qquad D_{L,T}=A_aP_{L,T}.
$$
First choose $L$ and $T$ large, using integrability of $E_X$ and Gaussian decay, and then make $\pi(A)$ small. This proves uniform absolute continuity with respect to the fixed $\pi$. Together with the uniform mass bound it proves uniform integrability by the approved [absolute-continuity criterion](../library/diestel1991_uniform_integrability/assets/lib_diestel1991_ui_absolute_continuity.md). No uniformity in $\pi$ or in a vanishing regularizer has been used.

### 3. Direct weak compactness and nested intersections

Positivity, the scalar bounds, and every displayed bound on $\int_A g\,d\pi$ persist under convex combinations and weak closure: the relevant tests are $(\mathbf1_A,0)$ and $(0,1)$. Consequently the union of all $C_j^\pm$ still has uniformly absolutely continuous nonnegative mean densities of mass at most $A_a$, and uniformly bounded scalar coordinates. These facts alone suffice for the following direct compactness argument.

Take any sequence $(g_n,c_n)$ in one such weakly closed hull. Uniform absolute continuity and the mass bound imply
$$
e_k:=\sup_n\|g_n-(g_n\wedge k)\|_1\longrightarrow0:
\quad \pi\{g_n>k\}\le A_a/k,
$$
so the tail integral is uniformly small. For each integer $k$, $g_n\wedge k$ lies in the radius-$k$ ball of $L^2(\pi)$. This space is separable: a countable generating algebra of the standard Borel parameter space gives a dense set of algebra-simple functions. Diagonal extraction of its orthonormal-basis coefficients, followed by the $L^2$ norm bound and approximation of a general $L^2$ test by finitely many basis vectors, gives a weakly convergent $L^2$ subsequence. Extract diagonally for every $k$ and also for the bounded scalar sequence. Denote the clipped weak limits by $u_k$ and the scalar limit by $c$.

For $l\ge k$, the clipping difference has $L^1$ norm at most $e_k$. Testing its weak $L^2$ limit against every bounded function of norm at most one gives
$$
\|u_l-u_k\|_1\le e_k.
$$
Thus $u_k\to g$ in $L^1(\pi)$ for some nonnegative $g$, and $\|g-u_k\|_1\le e_k$. For any $b\in L^\infty(\pi)\subset L^2(\pi)$, along the diagonal subsequence,
$$
\limsup_n\left|\int b(g_n-g)d\pi\right|
\le2\|b\|_\infty e_k.
$$
Letting $k\to\infty$ proves weak $L^1$ convergence to $g$. Weak closedness puts $(g,c)$ in the hull. In particular every limit obtained here is an $L^1$ density.

To turn this sequential argument into compactness, enumerate a countable generating algebra as $(A_i)$. On the family at issue, the scalar coordinate and the countably many coordinates $\int_{A_i}g\,d\pi$ induce the full weak topology. Indeed every measurable set can be approximated in $\pi$ measure by algebra sets: the class of sets with this property contains the algebra and is closed under complements and countable unions, the latter by truncation of a union and the finite measure property. Quantization then approximates any bounded measurable test in measure by uniformly bounded algebra-simple functions. If $b_n\to b$ in measure and $|b_n|,|b|\le B$, for every $\epsilon>0$,
$$
\sup_g\int|b_n-b|g\,d\pi
\le\epsilon A_a+2B\sup_g\int_{\{|b_n-b|>\epsilon\}}g\,d\pi\longrightarrow\epsilon A_a.
$$
Uniform absolute continuity and then $\epsilon\downarrow0$ give uniform pairing approximation. Therefore every weak test is continuous in the countable coordinate topology on this family. These coordinates separate densities, and the usual bounded weighted sum of coordinate distances is a metric for that topology. Sequential compactness in this metric implies compactness: failure of total boundedness supplies a separated sequence, while a countable ball refinement of an open cover of a totally bounded metric space with no finite subcover supplies a sequence with no convergent subsequence. This proves weak compactness directly. It also agrees with the registered [Dunford--Pettis criterion](../library/diestel1991_uniform_integrability/assets/lib_diestel1991_dunford_pettis_compactness.md), without using its source sketch as an adapted proof.

Each $C_j^\pm$ is nonempty by part 1 and convex and weakly closed by definition. Since $\mathcal T_{j+1}\subset\mathcal T_j$, these sets are nested. The compact finite-intersection property inside $C_1^\pm$ proves that $C^\pm$ is nonempty, weakly compact and convex.

### 4. Bulk density and supports of all active minima

Since $0\le h_{0,X}/h_X\le1$, the absolute value of the bulk integrand is at most $1/(as\sqrt{2\pi})$. Joint measurability, Fubini and the rank-one null convention thus give a bounded measurable $\mathfrak b\in L^1(\pi)$. For each retained $(X,Z)$, its integral in $x$ is a scalar multiple of
$$
h_{0,X}(Q_X(R))-
\frac{h_{0,X}(Q_X(R))}{h_X(Q_X(R))}h_X(Q_X(R))=0.
$$
Consequently $\int\mathfrak b\,d\pi=0$. The fixed-rank derivative formula of the variation lemma and Fubini also give
$$
\mathbb E_{X,Z}[\chi_a(R)\dot f_X(R)]
=\int\mathfrak b(x)b(x)d\pi(x)
$$
for each bounded lawful mean velocity.

For the support calculation take any bounded Borel $b$ and finite $\lambda$; lawfulness is unnecessary for this calculation alone. Set
$$
L_X(t)=\int p_{X,t}(x)b(x)d\pi(x)+\lambda m_t,
\qquad B_* =\|b\|_\infty+|\lambda|m(U).
$$
Part 1 gives joint measurability, continuity in $t\in(0,1)$, and $|L_X(t)|\le B_*$. Let $S_j(X,r)$ be the nonempty set of eligible rationals in the definition of $\mathcal T_j$, and put $s_j(X,r)=\sup_{d\in S_j(X,r)}L_X(d)$. This supremum is measurable because it is countable. For every $\varepsilon>0$, choosing the first eligible rational with $L_X(d)>s_j(X,r)-\varepsilon$ is a measurable admissible selector. With the nonnegative weight $w_{X,\pm}(r)\phi(M_X(r))/\sigma$, the upper bound by $s_j$ and this choice show
$$
h_{C_j^\pm}(b,\lambda)
=\frac1\sigma\mathbb E_X\int_a^1
w_{X,\pm}(r)\phi(M_X(r))s_j(X,r)dr.
$$
The error of this choice is at most $\varepsilon A_a$. Closing and convexifying do not change a continuous linear functional's supremum.

For fixed $(X,r)$, $s_j$ decreases. The set
$$
\{t\in[r,1):B_X(t)\le M_X(r)+1\}
$$
is compact: $B_X$ is continuous away from $1$ and tends to $+\infty$ there, since $Q_X(t)\to-\infty$ and $u_q(t)\to U$. If $d_j\in S_j(X,r)$ has $L_X(d_j)>s_j(X,r)-1/j$, a convergent subsequence has limit $t_*\in[r,1)$ with $B_X(t_*)=M_X(r)$. Thus $\lim_js_j\le\max_{\mathcal A_X(r)}L_X$. Conversely, for each active point $t_0$, continuity permits, for every $j$, an eligible rational arbitrarily near $t_0$ with $L_X(d)$ arbitrarily near $L_X(t_0)$. This remains true when $t_0=r$, by approximation from the right. Hence $s_j\ge L_X(t_0)$ for every active point. We have proved
$$
s_j(X,r)\downarrow\max_{t\in\mathcal A_X(r)}L_X(t).
$$
This proves attainment and measurability of the displayed active maximum as well. Domination by $B_*|g_X'|/(\sigma\sqrt{2\pi})$ and part 1 justify integration and Gaussian averaging.

Independently, the nested compact sets give
$$
h_{C^\pm}(b,\lambda)=\lim_jh_{C_j^\pm}(b,\lambda).
$$
For completeness, choose a maximizing element in each $C_j^\pm$. A convergent subsequence in the compact metrizable $C_1^\pm$ has limit in every $C_j^\pm$, and its pairing is the decreasing limit of these supports. The reverse inequality follows from $C^\pm\subset C_j^\pm$. Combining the last three displays proves the claimed support representation, with every active minimum included.

For a lawful direction the approved envelope formula now reads
$$
\dot M_X(r)=-\frac1\sigma\max_{t\in\mathcal A_X(r)}L_X(t).
$$
Insert this into the complete signed variation and write $g_X'=w_{X,+}-w_{X,-}$. Together with the fixed-rank bulk identity it yields precisely
$$
\dot{\mathcal F}^{a}=\int\mathfrak b b\,d\pi
+h_{C^+}(b,\lambda)-h_{C^-}(b,\lambda).
$$
The two support suprema are taken separately. The argument uses conditional selection only for this support calculation, not conditional-background optimality or observation-dependent lawful velocities.

### 5. Selector masses and survival integration

Posterior normalization shows that every original selector of a given sign has mean mass
$$
\mu_\pm=\frac1\sigma\mathbb E_X\int_a^1
w_{X,\pm}(r)\phi(M_X(r))dr.
$$
The test $(1,0)$ is a continuous test in the declared pairing, regardless of whether it is a lawful perturbation. Thus this equality persists in the convex hull, its weak closure and its intersection. Subtracting and using $\int\mathfrak b\,d\pi=0$ gives $\int\Psi\,d\pi=\mu_+-\mu_-=\sigma^{-1}\mathbb E_X\int_a^1g_X'\phi(M_X)dr$ for every pair.

The function $f_X$ tends to $\int\ell d\pi$ at $1$, because $Q_X(r)\to-\infty$ and dominated convergence gives $V_X(Q_X(r))\to\int\ell d\pi$. Thus $g_X$ is continuous at $1$, is zero at $a$, and, by its integrable derivative bound and local smoothness, is absolutely continuous on $[a,1]$. Extending it by zero below $a$, the actual-rank payoff obeys
$$
\chi_a(R)D=\int_a^1g_X'(r)\mathbf1_{\{R\ge r\}}dr
$$
almost surely. Rank zero and $R\le a$ give zero on both sides; rank one is conditionally null by the variation lemma, and the continuous endpoint convention would also give the formula there. Multiplication by $Z$ is integrable under Fubini since $\int_a^1|g_X'|dr\le C_a$ and $\mathbb E|Z|<\infty$. Using the actual event identity $\{R\ge r\}=\{Z\ge M_X(r)\}$ from the approved variation lemma,
$$
\mathbb E_Z[Z\mathbf1_{\{R\ge r\}}\mid X]
=\int_{M_X(r)}^\infty z\phi(z)dz=\phi(M_X(r)).
$$
It follows that
$$
\Gamma_a=\frac1\sigma\mathbb E_{X,Z}[Z\chi_a(R)D].
$$
The lower boundary contributes zero because $g_X(a)=0$; the representation already includes the upper boundary through the survival indicator. No upward motion of a zero-mean true tag is used.

### 6. Extending the extremal inequality by lawful truncation

Now let $(\pi,q)$ be the canonical normalized maximum in the statement and let $(b,\lambda)\in K$. Define
$$
b_\zeta=b\mathbf1_{E_0}+b\mathbf1_{\{|\theta|\ge\zeta\}},\qquad\zeta>0.
$$
On $E_0$, $b_\zeta=b\le0$. Off $E_0$ there is no zero-mean mass by canonicality; at $|\theta|\ge\zeta$, $0<\epsilon\|b\|_\infty<\zeta$ preserves the mean sign required by its tag. The other means are unchanged. Hence $b_\zeta$ is lawful. The same fixed $\lambda$ is allowed for small $\epsilon$, with $\lambda\le0$ at $q=q_{\max}$. The approved normalized extremal inequality, multiplied by $qU$, and part 4 give
$$
\int(\mathfrak b-2\eta qU\theta)b_\zeta d\pi
+(-\beta F^a+\delta qU)\lambda
+h_{C^+}(b_\zeta,\lambda)-h_{C^-}(b_\zeta,\lambda)\le0.
$$
Put $A_\zeta=\{0<|\theta|<\zeta\}$. These sets decrease to the empty set, and $|b-b_\zeta|\le\|b\|_\infty\mathbf1_{A_\zeta}$ almost everywhere. For either sign,
$$
|h_{C^\pm}(b_\zeta,\lambda)-h_{C^\pm}(b,\lambda)|
\le\|b\|_\infty\sup_{(g,c)\in C^\pm}\int_{A_\zeta}g\,d\pi\longrightarrow0
$$
by part 3's inherited uniform absolute continuity. The bulk pairing converges since $\mathfrak b$ is bounded, and the moment pairing converges by $\theta\in L^1(\pi)$. With
$$
d=(\mathfrak b-2\eta qU\theta,-\beta F^a+\delta qU),
$$
we therefore obtain, for every $(b,\lambda)\in K$,
$$
\langle d,(b,\lambda)\rangle+h_{C^+}(b,\lambda)
\le h_{C^-}(b,\lambda).
$$
This uses convergence of pairings and supports, not norm density of uniformly lawful velocities in $K$.

### 7. Polar, weak closedness and direct separation

Indicator tests supported off $E_0$, with both signs, show that $(g,c)\in K^\circ$ must have $g=0$ off $E_0$. Negative indicator tests on $E_0$ show $g\ge0$ there. Conversely those mean conditions suffice for the mean pairing to be nonpositive. Independent scalar tests give $c=0$ if $q<q_{\max}$ and $c\ge0$ if $q=q_{\max}$. This completely characterizes $K^\circ$ as the claimed product cone and also proves it is weakly closed, being an intersection of closed half-spaces.

Let $\mathcal D=C^-+K^\circ$. This set is convex and weakly closed. To prove the latter for the full weak topology, take a convergent net $y_i=u_i+v_i$ in it with $u_i\in C^-$ and $v_i\in K^\circ$. Compactness of $C^-$ gives a subnet $u_i\to u\in C^-$. On that subnet $v_i\to y-u$, and the polar's closedness gives $y-u\in K^\circ$. Thus $y\in\mathcal D$.

Here is the separation argument in this specific pairing. If $y\notin\mathcal D$, a basic weak neighborhood of $y$ disjoint from $\mathcal D$ has finitely many coordinate tests $z_i=(b_i,\lambda_i)\in L^\infty(\pi)\times\mathbb R$ and positive coordinate radii. Let $T$ map a vector to its pairings with these tests. The neighborhood implies $T(y)\notin\overline{T(\mathcal D)}$, with positive Euclidean distance. This closure is a nonempty closed convex subset of a finite-dimensional space. Its nearest point $p$ to $T(y)$ exists by restriction of a minimizing sequence to a bounded ball. Put $v=T(y)-p\ne0$. Differentiating squared distance along line segments from $p$ to any other point of the convex set gives
$$
v\mathbin{\cdot}w\le v\mathbin{\cdot}p<v\mathbin{\cdot}T(y)
\quad(w\in\overline{T(\mathcal D)}).
$$
Thus $z=\sum_i v_i z_i$ is an actual bounded-mean/scalar test satisfying
$$
\langle y,z\rangle>h_{\mathcal D}(z),\qquad h_{\mathcal D}(z)<\infty.
$$
Since $K^\circ$ is a cone containing zero, finiteness forces $\langle v_0,z\rangle\le0$ for every $v_0\in K^\circ$. The explicit polar description then forces $b\le0$ on $E_0$, and at $q=q_{\max}$ forces $\lambda\le0$; there are no other restrictions. Hence $z\in K$ and $h_{\mathcal D}(z)=h_{C^-}(z)$.

If now $y=d+u_+$ for $u_+\in C^+$ were outside $\mathcal D$, the preceding separation and part 6 would give
$$
h_{C^-}(z)<\langle d+u_+,z\rangle
\le\langle d,z\rangle+h_{C^+}(z)\le h_{C^-}(z),
$$
a contradiction. Therefore $d+C^+\subseteq C^-+K^\circ$.

For each chosen $(g_+,c_+)\in C^+$ choose its matching $(g_-,c_-)\in C^-$ in this inclusion. The mean coordinate of the residual polar vector is $\Psi-2\eta qU\theta$; its scalar coordinate is $\Lambda-\beta F^a+\delta qU$. The polar description gives exactly the mean identities off $E_0$, positivity on $E_0$ (where $\theta=0$), and the asserted interior equality or upper-endpoint inequality for $\Lambda$. All objects being separated are already Gaussian-averaged elements of $L^1(\pi)\times\mathbb R$.

### 8. Normal mass and the fixed-regularizer penalty limit

The same residual polar vector has a nonnegative $L^1$ mean density supported on $E_0$. Parts 5 and 7 give its exact mass
$$
\int(\Psi-2\eta qU\theta)d\pi
=\Gamma_a-2\eta qU\int\theta d\pi.
$$
By Cauchy--Schwarz,
$$
\left|2\eta qU\int\theta d\pi\right|
\le2\eta qU\sqrt{M_2(\pi)}
=2qU\sqrt\eta\sqrt{\eta M_2(\pi)}.
$$
The sign of $\int\theta d\pi$ has not been constrained or discarded.

It remains to justify the value/penalty limit for this fixed private smoothing and cutoff. We first prove a uniform elementary domination. At any realized positive rank $R<1$, continuity and the globally largest crossing imply
$$
H_X(u_q(R)-\sigma Z)=R.
$$
Indeed a strict inequality would persist for a slightly larger rank, contradicting maximality. It follows that $Q_X(R)=u_q(R)-\sigma Z$, and the true discovery mass equals $V_X(u_q(R)-\sigma Z)$. Since $u_q(R)\ge U$ and $V_X$ is nonincreasing,
$$
0\le\chi_a(R)D\le\frac1a V_X(U-\sigma Z).
$$
For $R\le a$ the left side is zero, and the rank-one exceptional set is null. Each true-tag parameter has $\theta\le0$ and unconditional score variance
$$
\tau_s^2\|v\|^2+c_s(v)^2+\sigma^2=1.
$$
Integration of both Gaussian backgrounds and private noise therefore gives, by Tonelli,
$$
\mathbb E_{X,Z}V_X(U-\sigma Z)
=\int\ell(x)S(U-\theta(x))d\pi(x)\le q.
$$
Consequently $F^a\le q/a$ for every lawful deterministic law, without a moment-dependent constant.

Write $J(\pi,q)=F^a/(qU)-\delta\log(1/q)$. Uniformly in $\pi$,
$$
J(\pi,q)\le\frac1{aU}-\delta\log(1/q)\le\frac1a,
\qquad \sup_\pi J(\pi,q)\longrightarrow-\infty\quad(q\downarrow0).
$$
The latter follows already from $U\ge1$ and $\log(1/q)\to\infty$. A comparison law concentrated at $(\theta,v,\ell)=(0,0,1)$ is lawful, canonical, and has moment zero. At the fixed level $q_{\max}$ its objective is at least $B_0=-\delta\log(1/q_{\max})$, since $F^a\ge0$. This is a common finite lower bound for every penalized maximum. Choose $q_*>0$ so small that the uniform upper bound for $J$ is below $B_0-1$ at every $q<q_*$. Every maximizing level, for any $\eta>0$, must then belong to $[q_*,q_{\max}]$, since subtracting the nonnegative moment penalty cannot improve that upper bound. This supplies a common coercive level interval whenever one is needed. The fixed comparison and upper bound also show $-\infty<L_0^a<\infty$.

By definition of this supremum, for each $\varepsilon>0$ there is a lawful deterministic comparison $(\pi_\varepsilon,q_\varepsilon)$ with finite $M_2(\pi_\varepsilon)$ and $J(\pi_\varepsilon,q_\varepsilon)\ge L_0^a-\varepsilon$. The existence and deterministic-global comparison for $L_\eta^a$ are supplied by the approved variation lemma. Thus
$$
L_0^a-\varepsilon-\eta M_2(\pi_\varepsilon)
\le L_\eta^a\le L_0^a.
$$
First $\eta\downarrow0$ and then $\varepsilon\downarrow0$ give $L_\eta^a\to L_0^a$. For every choice of maximizing pair $(\pi_\eta,q_\eta)$,
$$
0\le\eta M_2(\pi_\eta)
=J(\pi_\eta,q_\eta)-L_\eta^a
\le L_0^a-L_\eta^a\longrightarrow0.
$$
Finally $qU=S(U)U\le\phi(U)\le1/\sqrt{2\pi}$, using the elementary Mills inequality $S(U)\le\phi(U)/U$ for $U\ge1$. Hence the signed moment error tends to zero by the earlier Cauchy--Schwarz estimate. This proves the fixed-regularizer assertion for every maximizing family and completes all five clauses. No flux-scale estimate, global mass potential, conditional-background stationarity, or passage of derivatives through regularization limits is assumed.
