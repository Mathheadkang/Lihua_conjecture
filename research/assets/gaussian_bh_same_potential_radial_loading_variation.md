---
type: lemma
title: >-
  Same-potential radial loading variation and fixed-rank Gaussian integration by
  parts
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_global_particle_potential_certificate
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
  - gaussian_bh_exchangeable_array_variational_compactification
uses_definitions:
  - gaussian_bh_private_smoothed_directing_population
  - gaussian_bh_hybrid_particle_potential_convention
  - gaussian_bh_signed_near_active_gradient_cones
  - gaussian_bh_marked_exchangeable_parameter_array
tags:
  - gaussian_bh
  - radial_loading
  - particle_potential
  - fixed_regularizers
  - gaussian_integration_by_parts
---

## Statement

Use the approved [private-smoothed directing population](../definitions/gaussian_bh_private_smoothed_directing_population.md), [hybrid particle-potential convention](../definitions/gaussian_bh_hybrid_particle_potential_convention.md), [signed near-active conventions](../definitions/gaussian_bh_signed_near_active_gradient_cones.md), and [marked-array conventions](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md). The approved [global particle-potential certificate](gaussian_bh_global_particle_potential_certificate.md), [complete private signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md), and [marked-array compactification](gaussian_bh_exchangeable_array_variational_compactification.md) are declared prerequisites before any search. Standard one-dimensional Gaussian calculus and the elementary one-dimensional compactness argument required below are to be proved directly here; no additional known-result black box is assumed.

Fix $\sigma,s>0$ with $\sigma^2+s^2<1$, $0<a<1/4$, the specified cutoff $\chi_a$, and $\eta,\delta>0$. All tests here are one-sided; $s$ denotes private smoothing. Write $S=\overline\Phi$, $\phi(u)=(2\pi)^{-1/2}e^{-u^2/2}$, $\tau_s=\sqrt{1-\sigma^2-s^2}$, and $q_{\max}=S(1)$. Fix a genuine deterministic canonical normalized global maximum $(\pi,q)$ from the global certificate, with $0<q\le q_{\max}$ and $U=S^{-1}(q)$. Thus $\pi$ is a lawful pre-noise Borel probability on $E_{\rm ball}$, $M_2(\pi)<\infty$, and $\pi\{\theta=0,\ell=0\}=0$.

Retain its actual largest BH rank $R$, full FDP $D$, conditional tails $H_X,V_X$, positive densities $h_X,h_{0,X}$, quantile $Q_X$, suffix minimum $M_X$, signed weights $w_X,w_{X,\pm}$, and hybrid selector classes $\mathcal S_j$. Retain the bulk potential $P_0$ and one fixed matching pair
$$
(G_+,c_+)\in\mathscr C^+,
\qquad (G_-,c_-)\in\mathscr C^-,
\qquad \mathcal P=P_0+G_+-G_-,
\qquad P=\mathcal P-\eta qU\theta^2.
$$
The fixed pair is the pair satisfying all global, mean and level conditions of the approved certificate; it is not selected again for the conclusions below. All parameters, trial particles and physical perturbations are chosen before Gaussian innovations. No conditional-on-noise optimization of the baseline is permitted.

1. **Radial kernel generator and prelimit bounds.** For a fixed trial particle $x=(\theta,v,\ell)$ with $\|v\|\le1$, vary only its loading to $rv$, $0\le r\le1$, and define
$$
c_r^2=s^2+\tau_s^2(1-r^2\|v\|^2),
\qquad K_r(z)=S\!\left(\frac{z-\theta-\tau_s rX(v)}{c_r}\right),
\qquad k_r(z)=\partial_\theta K_r(z).
$$
Every baseline threshold $z$, selector, coefficient and weight is held fixed while differentiating in $r$. At $\|v\|<1$ use a small physical extension past $r=1$ with $\|rv\|\le1$; at $\|v\|=1$ derivatives at one are left derivatives. At zero use right derivatives. For $v=0$ the radial functions are constant. Prove the exact identity
$$
\partial_rK_r(z)=\tau_sX(v)k_r(z)
-\tau_s^2r\|v\|^2\partial_\theta^2K_r(z).
$$
For $m=0,1,2,3$, prove conditional bounds, uniform in $\theta,z,v$ and physical $r$ on the stated fixed interval,
$$
|\partial_r^mK_r(z)|\le C_m(s,\tau_s)[1+|X(v)|^m],
$$
with explicit finite choices of $C_m$. Use $c_r\ge s$, Gaussian moments, the approved conditional total-selector-weight bound
$$
K_0=\frac{T_a}{\sigma\sqrt{2\pi}}
\left(\frac{m(1)}a+\sigma\right)+W_a,
\qquad m(u)=S(u)/\phi(u),\quad
T_a=1+\log(1/a),\quad W_a=\|\chi_a'\|_\infty+1/a,
$$
and the bulk coefficient bound $1/a$ to deduce uniform radial derivative bounds through order three for generating selector potentials, their finite convex combinations, and $P_0$. These bounds are independent of the baseline $\pi$, $\theta,v$, Hilbert dimension, $q$, selector and convex approximation index. They may depend on the fixed $\sigma,s,a,\chi_a$; no regularizer-uniform assertion is made.

2. **Radial regularity of the same limiting potentials.** Every fixed convex-limit potential $G$ in the approved compact potential classes, $P_0$, and $\mathcal P$ is $C^2$ along each stated radial curve, with the one-sided endpoint interpretation above. For every sequence of finite convex selector combinations $(G_n,c_n)$ converging to a fixed $(G,c)$ in the approved evaluation topology, prove on the fixed loading interval
$$
\max_{0\le m\le2}\sup_r
\left|\frac{d^m}{dr^m}G_n(\theta,rv,\ell)
-\frac{d^m}{dr^m}G(\theta,rv,\ell)\right|\longrightarrow0.
$$
The same statement applies on any chosen physical extension when $\|v\|<1$. Justify the needed one-dimensional compactness and identification from the uniform third-order prelimit bounds and evaluation convergence. The radial generator formula for a closed convex limit means the justified limit of its generating averaged expressions. No norm convergence of gradients on the whole Hilbert ball, pathwise continuous isonormal field, exact selector realizing a limit, or replacement of the fixed matching pair is asserted.

3. **Contact loading-normal condition.** At $\pi$-almost every contact particle $x=(\theta,v,\ell)$, prove
$$
J(x):=\left.\partial_r\mathcal P(\theta,rv,\ell)\right|_{r=1}\ge0,
\qquad J(x)=0\quad\text{if }\|v\|<1.
$$
Prove Borel measurability and $\pi$-integrability of $J$, including representative invariance in the averaged potentials. Consequently
$$
\int J\,d\pi
=\int_{\{\|v\|=1\}}J\,d\pi\ge0.
$$
The mean penalty is unchanged under loading motion. These are necessary conditions of the same dual potential certificate, obtained from its lawful global contact comparisons.

4. **Fixed-rank Cameron-Martin quantile derivative.** Fix deterministic $0<t<1$ and $v\in\mathcal H$ with $\|v\|\le1$. For functions of the isonormal field define the Cameron-Martin directional derivative $D_v$ by translating $X(w)$ to $X(w)+\epsilon\langle w,v\rangle$ and differentiating at $\epsilon=0$; in particular $D_vX(w)=\langle w,v\rangle$. Prove directly from the conditional tails that
$$
D_vQ_X(t)=\tau_s\int
\langle w,v\rangle
\frac{k_{X,(\theta',w,\ell')}(Q_X(t))}{h_X(Q_X(t))}
\,d\pi(\theta',w,\ell'),
\qquad |D_vQ_X(t)|\le\tau_s\|v\|.
$$
Justify differentiability and all differentiations under the fixed directing-law integral in finite or separable Hilbert dimension.

5. **Gaussian integration by parts retaining the baseline derivatives.** Let $A(X)$ be a bounded test weight, $C^1$ along the Cameron-Martin direction $v$, with bounded directional derivative $D_vA$. Independent extra randomness may be conditioned on, with the stated bounds applying to the conditioned test weight. Hold $A$ independent of the radial parameter $r$; it is an integration-by-parts test function, not a noise-selected model competitor. For the fixed trial $(\theta,v,\ell)$ above put $K=K_1(Q_X(t))$ and $k=k_1(Q_X(t))$. Prove the exact identity
$$
\mathbb E\!\left[A\left.\partial_rK_r(Q_X(t))\right|_{r=1}\right]
=\tau_s\mathbb E\!\left[
kD_vA-A\bigl(\partial_\theta^2K_1(Q_X(t))\bigr)D_vQ_X(t)
\right].
$$
On the left the radial derivative holds the baseline threshold $Q_X(t)$ fixed; the Cameron-Martin differentiation on the right differentiates that baseline threshold. For $v\ne0$, conditioning on the orthogonal Gaussian field and integrating in $X(v)/\|v\|$ is allowed. Prove the differentiability, vanishing Gaussian boundary terms and absolute integrability required for that one-dimensional argument. For $v=0$ both sides are zero. Both the test-weight derivative and the quantile derivative are retained.

## Scope and provenance

Draft original supporting checkpoint extracted from the leading block beginning “The researcher-requested independent replanning of 9 November 2026” in `research/project.md`, Intended Contribution, before its historical tenth-reassessment block. The library was searched before drafting for reusable Gaussian integration-by-parts, radial derivative and compactness results; none matched this checkpoint, so its elementary calculus and compactness obligations remain internal to this statement. No new definition node is needed: all additional symbols above are local notation, not assumed conclusions.

This checkpoint keeps the two unrestricted main goals, all sixteen preceding required entries, their complete quantifiers, approved statements and historical research unchanged. It asserts no uniform $q$ payment, covariance monotonicity of ordinary FDR, derivative of the full FDR under loading changes, or exchange of any derivative with regularizer limits. Actual hybrid selector and rank-switch weights are generally only measurable: no Gaussian Sobolev or bounded-variation regularity for them is granted here, and no record or switch term is discarded. A full signed loading integration-by-parts balance for those weights, followed by a $q$-scaled estimate independent of every regularizer, remains a separate unresolved gap. This statement is a target for native falsification, proof planning, execution and independent verification; no proof is claimed in this scaffold.

## Proof

All laws, particles and physical perturbations are fixed before the innovations. Write $\tau=\tau_s$ throughout this proof. We use only the three approved prerequisites in the statement. In particular the [global particle-potential certificate](gaussian_bh_global_particle_potential_certificate.md) supplies the already fixed matching pair, its conditional selector bound, its compact potential classes and its global contact comparison. The version and differentiation arguments below adapt, and explicitly reprove in the changed directions, the corresponding arguments in that certificate and the [complete private signed variation](gaussian_bh_private_noise_cutoff_signed_transport_variation.md). No actual hybrid selector is differentiated in a Gaussian direction.

### 1. Versions, physical intervals and the kernel generator

Use the jointly measurable series of the approved population definition. Each deterministic loading has a probability-one convergence event, and Fubini gives convergence for almost every particle of each fixed directing law, simultaneously for any specified countable family. For a fixed $v$, convergence of its series gives $X(rv)=rX(v)$ for every real $r$ on that single event, since every partial sum has this identity. This gives a coherent version on each fixed radial curve without a samplewise continuous field on the ball. In the averaged expressions every baseline threshold, coefficient, rank and selector stays fixed under radial differentiation.

Let $I=[0,1]$. When $0<\|v\|<1$, the same proof works on any fixed $I=[0,1+\epsilon]$ with $(1+\epsilon)\|v\|\le1$. For $v=0$ all radial kernels and potentials are constant. On every other such physical interval put
$$
b=\tau X(v),\qquad d=\tau^2\|v\|^2,\qquad e_r=rd,\qquad \partial=\partial_\theta.
$$
Then $c_r\ge s$, $d\le\tau^2$ and $0\le e_r\le\tau^2$: indeed $r\|v\|^2\le\|v\|\le1$, also on extensions. For a tail $F(\mu,u)=S((z-\mu)/\sqrt u)$, writing $y=(z-\mu)/\sqrt u$ gives by direct differentiation
$$
\partial_\mu F=\frac{\phi(y)}{\sqrt u},\qquad
\partial_\mu^2F=\frac{y\phi(y)}u,\qquad
\partial_uF=\frac{y\phi(y)}{2u}=\frac12\partial_\mu^2F.
$$
Here $\mu=\theta+rb$ and $u=s^2+\tau^2-r^2d$, so
$$
K_r'=(b\partial-e_r\partial^2)K_r
=\tau X(v)k_r-\tau^2r\|v\|^2\partial_\theta^2K_r.
$$
This proves the requested identity with its negative variance term. The operators in this formula commute with $\partial$ and with one another; their radial derivative is $-d\partial^2$. Differentiating once and twice more therefore gives, explicitly,
$$
K_r''=(b^2-d)\partial^2K_r-2be_r\partial^3K_r+e_r^2\partial^4K_r,
$$
$$
K_r'''=(b^3-3bd)\partial^3K_r
+(-3b^2e_r+3e_rd)\partial^4K_r
+3be_r^2\partial^5K_r-e_r^3\partial^6K_r.
$$
For example the third derivative is the cube of $b\partial-e_r\partial^2$ applied to $K_r$, plus $3(-d\partial^2)(b\partial-e_r\partial^2)K_r$, which verifies every coefficient. These formulas are valid to the physical endpoints with the indicated one-sided interpretation, including $r=0$ where $e_r=0$.

### 2. Explicit bounds and averaging

For $p\ge0$ let $M_0=1$ and $M_p=(p/\exp(1))^{p/2}$ for $p\ge1$. Maximizing $y^p e^{-y^2/2}$ for $y\ge0$ by differentiation gives
$$
\sup_y |y|^p\phi(y)=M_p/\sqrt{2\pi}.
$$
Define for $1\le j\le6$
$$
B_j=\frac{(j-1)!}{\sqrt{2\pi}\,s^j}
\sum_{k=0}^{\lfloor(j-1)/2\rfloor}
\frac{M_{j-1-2k}}{2^k k!(j-1-2k)!}.
$$
To verify the derivative bound directly, put
$$
H_n(y)=n!\sum_{k=0}^{\lfloor n/2\rfloor}
\frac{(-1)^k y^{n-2k}}{2^k k!(n-2k)!}.
$$
Differentiating this finite sum verifies $H_0=1$ and $H_{n+1}=yH_n-H_n'$. Since $\phi'=-y\phi$, repeated center differentiation starting from $\partial K_r=c_r^{-1}\phi(y)$ consequently gives
$$
\partial^jK_r=c_r^{-j}H_{j-1}(y)\phi(y),\qquad
|\partial^jK_r|\le B_j.
$$
Thus all $B_j$ are explicit finite constants depending only on $s$. With
$$
C_0=1,\qquad C_1=\tau B_1+\tau^2B_2,
$$
$$
C_2=\tau^2B_2+2\tau^3B_3+\tau^4B_4,
$$
$$
C_3=4\tau^3B_3+6\tau^4B_4+3\tau^5B_5+\tau^6B_6,
$$
the formulas in part 1 prove
$$
|K_r^{(m)}(z)|\le C_m(1+|X(v)|^m),\qquad 0\le m\le3,
$$
and also the sharper $0\le K_r\le1$. Indeed for $x=|X(v)|$, the second-order terms are bounded by $\tau^2(x^2+1)B_2$, $2\tau^3xB_3$, and $\tau^4B_4$. At order three they are bounded by $\tau^3(x^3+3x)B_3$, $3\tau^4(x^2+1)B_4$, $3\tau^5xB_5$, and $\tau^6B_6$. The inequalities $x\le1+x^2$, $x^3+3x\le4(1+x^3)$ and $x^2+1\le2(1+x^3)$ prove the displayed choices. They hold uniformly in $\theta,z,v,r$ on the physical intervals, including their endpoints.

For a generating selector $t$ and either sign, use the nonnegative conditional coefficient measure
$$
d\Lambda_{X,\pm}^t(u)=\frac1\sigma
\frac{w_{X,\pm}(u)\phi(M_X(u))}
{h_X(Q_X(t(X,u)))}\,du,\qquad a<u<1.
$$
The approved certificate supplies, conditionally on the background,
$$
\Lambda_{X,\pm}^t((a,1))\le K_0
=\frac{T_a}{\sigma\sqrt{2\pi}}
\left(\frac{m(1)}a+\sigma\right)+W_a.
$$
In particular this is a bound on the entire conditional coefficient, before any expectation involving $X(v)$ is taken. Multiplying the preceding kernel envelopes by this nonnegative measure and integrating first in $u$ yields the integrable domination
$$
\int |K_r^{(m)}(Q_X(t(X,u)))|d\Lambda_{X,\pm}^t(u)
\le K_0 C_m(1+|X(v)|^m).
$$
There is no independence assumption on the selector and $X(v)$. If $N$ is standard normal, direct integration using $\phi'=-y\phi$ gives
$$
\mathbb E|N|=\sqrt{2/\pi},\qquad \mathbb E N^2=1,
\qquad \mathbb E|N|^3=2\sqrt{2/\pi}.
$$
Since $X(v)$ has the law of $\|v\|N$, its absolute moments through order three are at most $\mu_1=\sqrt{2/\pi}$, $\mu_2=1$ and $\mu_3=2\sqrt{2/\pi}$, respectively. Therefore every generating potential, and every finite convex combination, has radial derivative bounds
$$
|G^t|\le K_0,\qquad
\left|\frac{d^m}{dr^m}G^t(\theta,rv,\ell)\right|
\le K_0C_m(1+\mu_m),\qquad 1\le m\le3.
$$
Each differentiation is justified as follows. Pathwise kernel derivatives are continuous on $I$. Difference quotients of each order below three are bounded by the supremum of the next derivative, which has the integrable bound just displayed before averaging. Dominated convergence therefore gives successive derivatives under both integrations, and applying it to the third derivative proves its continuity. At endpoints the same reasoning uses one-sided quotients.

For the bulk potential, its frozen coefficient
$$
\mathbf1_{\{R>a\}}\frac{\chi_a(R)}R
\left(\ell-\frac{h_{0,X}(Q_X(R))}{h_X(Q_X(R))}\right)
$$
has absolute value at most $1/a$. The stipulated zero values handle $R\le a$ and the exceptional rank-one event. Repeating the same domination with this absolute bound gives
$$
|P_0|\le1/a,\qquad
\left|\frac{d^m}{dr^m}P_0(\theta,rv,\ell)\right|
\le a^{-1}C_m(1+\mu_m),\qquad 1\le m\le3,
$$
and $C^3$ regularity along each physical interval. The tag is fixed during this differentiation. These constants are independent of the baseline law, means, trial loadings, Hilbert dimension, level, selector, selector tolerance and convex approximation index. Their allowed dependence is exactly on the fixed $\sigma,s,a,\chi_a$. In particular no claim here is uniform as regularizers vanish.

### 3. Every fixed convex limit on its radial curve

Let $(G_n,c_n)\to(G,c)$ be any sequence of finite convex selector combinations in the approved evaluation topology, and put $f_n(r)=G_n(\theta,rv,\ell)$ on the fixed compact interval $I$. Part 2 bounds $f_n,f_n',f_n'',f_n'''$ uniformly. For $j=0,1,2$ the mean value formula consequently makes $f_n^{(j)}$ uniformly Lipschitz, with a common constant for each $j$.

Here is the required compactness argument in one real variable. On a countable dense subset of $I$ containing the endpoints, successively extract convergent real-coordinate subsequences for each of the three functions and diagonalize. The real-coordinate extraction uses only boundedness: repeated subdivision of a bounded interval supplies nested intervals of lengths tending to zero, each containing infinitely many terms. For any tolerance, a finite mesh from the dense subset has every point of $I$ within a prescribed distance of a mesh point. The common Lipschitz constants then show that the diagonal subsequence is uniformly Cauchy in all three functions. Its uniform limits $f,g,h$ are continuous. Passing to the limit in
$$
f_n(r)-f_n(r_0)=\int_{r_0}^r f_n'(u)\,du,\qquad
f_n'(r)-f_n'(r_0)=\int_{r_0}^r f_n''(u)\,du
$$
gives $f'=g$, $g'=h$, with one-sided derivatives at the endpoints. Evaluation convergence at every fixed particle $(\theta,rv,\ell)$ identifies $f(r)=G(\theta,rv,\ell)$. Thus all three limits are uniquely determined by this fixed function.

To obtain the entire sequence, suppose one of the three asserted sup-norm convergences fails. A subsequence then has error bounded below by a positive number. Applying the extraction just proved to that subsequence gives a further subsequence with all three uniform limits, and evaluation convergence identifies them with the same $f,f',f''$. This contradicts the lower bound. Hence
$$
\max_{0\le j\le2}\sup_{r\in I}
|f_n^{(j)}(r)-f^{(j)}(r)|\longrightarrow0.
$$
For existence of these derivatives at every closure point, use the established metrizability and compactness of the approved potential families: each point of a closed convex hull has a sequence of finite convex combinations converging to it in the declared evaluation topology. For a point in the nested intersection one may use its membership in the first hull. The uniform bounds of part 2 hold for that sequence, so the preceding argument applies. This proves regularity of every such fixed potential and the assertion for every approximating sequence. The same proof on any chosen physical extension gives the extension assertion. No compactness of the strong Hilbert ball is used.

Apply this separately to the fixed $G_+$ and $G_-$. Together with part 2 it gives $C^2$ radial regularity of $\mathcal P=P_0+G_+-G_-$. Each generating derivative is precisely its averaged frozen-threshold generator in part 1. The derivative of a closed convex limit is the justified uniform limit of these averaged expressions; it does not assert an exact selector or a norm-convergent Hilbert-ball gradient. No extraction has replaced either member of the original matching pair.

### 4. The contact radial normal

The same fixed certificate gives $P(y)\le\kappa$ for every lawful $y$ and $P(x)=\kappa$ on one full-$\pi$-measure contact set. Fix such an $x=(\theta,v,\ell)$. Every physical $x_r=(\theta,rv,\ell)$ is lawful, has the same mean penalty and obeys
$$
\mathcal P(x_r)\le\mathcal P(x).
$$
For $r<1$ this makes $[\mathcal P(x)-\mathcal P(x_r)]/(1-r)\ge0$. Letting $r\uparrow1$ proves $J(x)\ge0$. If $0<\|v\|<1$, a physical extension past one is available, so the same comparison on both sides and differentiability give $J(x)=0$. At $v=0$ this follows from constancy. There is no mean-tag change in any of these comparisons, so true-zero and all other lawful tags are included.

For measurability define $r_n=1-1/n$, $n\ge2$, and write globally
$$
J(x)=\lim_{n\to\infty}
n[\mathcal P(\theta,v,\ell)-\mathcal P(\theta,r_nv,\ell)].
$$
Part 3 guarantees existence of this limit at every particle. Every term is Borel, since the approved averaged potentials are strongly continuous and radial scaling is continuous. Bounds from parts 2 and 3 imply
$$
|J(x)|\le(1/a+2K_0)C_1(1+\mu_1).
$$
Consequently $J$ is integrable and the Borel set $\{\|v\|=1\}$ gives
$$
\int J\,d\pi=\int_{\{\|v\|=1\}}J\,d\pi\ge0.
$$
Representative invariance is an averaged assertion. For every fixed law and fixed trial particle, Fubini and equality of the isonormal representatives give equality almost surely of the integrated kernels and population objects, including selectors interpreted as the same field functions modulo null sets. Hence every generating averaged potential is unchanged at each fixed particle. The common strong continuity moduli from the approved certificate extend equality from any countable strong dense set to the entire parameter space. The compact closures and their fixed evaluation coordinates therefore give the same limiting potentials. The displayed deterministic difference quotients then give the same $J$. This proves the required invariance without a common pathwise continuous field on the whole ball.

### 5. A coherent conditional Gaussian line and the quantile

Fix deterministic $0<t<1$ and $v\ne0$ and put $\alpha=\|v\|$, $e_v=v/\alpha$, $\xi=X(e_v)$. To make the conditioning precise even for the specified original series, write its basis as $(f_i)$ and set
$$
Y_i=X(f_i)-\xi\langle f_i,e_v\rangle.
$$
The countable Gaussian family $(Y_i)$ is independent of $\xi$: every finite subfamily is jointly Gaussian with $\xi$ and has zero cross covariances, so its joint normal density or characteristic function factors; the countable sigma field follows by finite-cylinder approximation. It represents the orthogonal field. For fixed $w$, the residual series
$$
\sum_i\langle w,f_i\rangle Y_i
$$
converges almost surely, because the original isonormal series converges and the subtracted series converges to $\xi\langle w,e_v\rangle$ by the Hilbert inner product. Its convergence is an event of the residual family alone. Define its jointly measurable sum as $Y(w)$ on convergence, zero otherwise. Fubini with the fixed $\pi$ shows that for almost every residual realization the series converges for $\pi$-almost every loading $w$. Intersect this with the event for the fixed trial loading $v$. On this single residual event put
$$
X_\xi(w)=Y(w)+\xi\langle w,e_v\rangle,\qquad \xi\in\mathbb R.
$$
For those loadings this is coherent for every real $\xi$, not merely almost every scalar value. Indeed substituting $X(f_i)=Y_i+\xi\langle f_i,e_v\rangle$ into the original partial sums proves convergence and the displayed value for every $\xi$. Moreover $Y(v)=0$, so $X_\xi(v)=\alpha\xi$. At the random original $\xi$ these fixed-law integrals equal those of the original representative. Replacing the field by its Cameron-Martin shift in direction $v$ translates this scalar to $\xi+\epsilon\alpha$, since $\epsilon\alpha\langle w,e_v\rangle=\epsilon\langle w,v\rangle$. This proves the connection to the actual shift derivative in the statement. In finite dimension the same construction has finite sums; in dimension one the residual field is zero.

Condition on a good residual realization and abbreviate the translated tail and density by $H_\xi(z)$ and $h_\xi(z)$. The fixed directing-law kernels are
$$
S\left(\frac{z-\theta'-\tau Y(w)-\tau\xi\langle w,e_v\rangle}{c_s(w)}\right).
$$
They are continuously differentiable in $(\xi,z)$. Their first derivatives are bounded in absolute value by $B_1\max(1,\tau)$, since $|\langle w,e_v\rangle|\le1$. Their higher first-derivative increments can also be dominated by $B_2$ times the bounded center velocities. Dominated difference quotients and dominated convergence give, directly under $\pi$,
$$
\partial_zH_\xi(z)=-h_\xi(z)<0,\qquad
\partial_\xi H_\xi(z)=\tau\int\langle w,e_v\rangle k_{X_\xi,(\theta',w,\ell')}(z)\,d\pi.
$$
The integrated positive density is finite, positive and jointly continuous. For each finite $\xi$ all centers are finite almost everywhere; bounded convergence as $z\to\pm\infty$ gives tail limits zero and one. Thus there is a unique finite $Q_\xi(t)$.

The center displacement from $\xi$ to $\xi+u$ has absolute value at most $\tau|u|$ for every particle. Monotonicity of each scalar tail therefore gives
$$
H_\xi(z+\tau|u|)\le H_{\xi+u}(z)\le H_\xi(z-\tau|u|),
\qquad |Q_{\xi+u}(t)-Q_\xi(t)|\le\tau|u|.
$$
Set $\Delta Q=Q_{\xi+u}(t)-Q_\xi(t)$. The jointly $C^1$ expansion of the identity $H_{\xi+u}(Q_\xi(t)+\Delta Q)=t$ at $(\xi,Q_\xi(t))$ reads
$$
0=u\partial_\xi H_\xi(Q_\xi(t))-h_\xi(Q_\xi(t))\Delta Q
+o(|u|+|\Delta Q|).
$$
The displacement bound makes the remainder $o(|u|)$. Since the fixed positive denominator has a positive lower bound on a small neighborhood, division gives the derivative for every real $\xi$:
$$
\frac{d}{d\xi}Q_\xi(t)=\tau\int\langle w,e_v\rangle
\frac{k_{X_\xi,(\theta',w,\ell')}(Q_\xi(t))}{h_\xi(Q_\xi(t))}\,d\pi.
$$
The quotient is continuous along the line by the same dominated arguments and positivity of the denominator, so $Q_\xi(t)$ is $C^1$. Its absolute derivative is at most $\tau$, because the nonnegative posterior density in the integral integrates to one. Multiplication by $\alpha$ proves, for the actual Cameron-Martin version,
$$
D_vQ_X(t)=\tau\int\langle w,v\rangle
\frac{k_{X,(\theta',w,\ell')}(Q_X(t))}{h_X(Q_X(t))}\,d\pi,
\qquad |D_vQ_X(t)|\le\tau\|v\|.
$$
The ratio here is used only with its integrated posterior normalization; no uniform reciprocal-density bound is assumed. This derivation proves every differentiation under the fixed directing law in separable as well as finite dimension. For $v=0$ the translated field and quantile are unchanged, and the same formula has both sides zero.

### 6. Scalar Gaussian integration by parts and cancellation

Retain the line and notation of part 5 and condition also on any permitted independent extra randomness. The weight $A$ is held independent of the physical parameter $r$. By its hypotheses it is $C^1$ on this Gaussian line, bounded together with $D_vA$ under the stated conditioned bounds. Set
$$
k=k_1(Q_X(t)),\qquad L=\partial_\theta^2K_1(Q_X(t)).
$$
Since the score derivative of $k_1$ is $-L$, whereas the center shift of the trial kernel under the Cameron-Martin translation is $\tau\|v\|^2$, the ordinary scalar chain rule gives exactly
$$
D_vk=L\{\tau\|v\|^2-D_vQ_X(t)\},
$$
$$
D_v(Ak)=kD_vA+AL\{\tau\|v\|^2-D_vQ_X(t)\}.
$$
Here $|k|\le B_1$, $|L|\le B_2$ and
$$
|D_vk|\le B_2\tau(\|v\|^2+\|v\|).
$$
For the fixed $\alpha=\|v\|>0$, the scalar line function $F(\xi)=(Ak)(X_\xi)$ is bounded and continuously differentiable, and $F'(\xi)=D_v(Ak)/\alpha$ is bounded. These facts follow from part 5 and the assumed directional regularity of $A$. If a stated bound is initially an essential bound along the scalar Gaussian law, continuity makes it a bound everywhere on that good line. Integrating $\phi'=-\xi\phi$ on the finite interval $[-N,N]$ gives
$$
\int_{-N}^N\xi F(\xi)\phi(\xi)d\xi
=\int_{-N}^NF'(\xi)\phi(\xi)d\xi
-[F(\xi)\phi(\xi)]_{-N}^N.
$$
Both boundary terms tend to zero by boundedness of $F$ and $\phi(\pm N)\to0$. Both absolute integrals converge, since $F,F'$ are bounded and $\int |\xi|\phi(\xi)d\xi<\infty$. Multiplication by $\alpha$ and removal of the conditioning therefore prove
$$
\mathbb E[X(v)Ak]=\mathbb E[D_v(Ak)].
$$
The original bounded test and derivative bounds justify this last averaging and absolute integrability; if extra randomness is kept conditioned, the same argument holds for its stated conditioned bounds. No regularity of the baseline actual selector is needed for this analytic test identity.

At $r=1$, part 1 with the baseline quantile held fixed gives
$$
\mathbb E\left[A\left.\partial_rK_r(Q_X(t))\right|_{r=1}\right]
=\tau\mathbb E[X(v)Ak]-\tau^2\|v\|^2\mathbb E[AL].
$$
Substitute the proved integration-by-parts identity and the product rule. The explicit $\tau^2\|v\|^2\mathbb E[AL]$ terms cancel, leaving
$$
\mathbb E\left[A\left.\partial_rK_r(Q_X(t))\right|_{r=1}\right]
=\tau\mathbb E[kD_vA-ALD_vQ_X(t)],
$$
which is the asserted formula. The original left side is absolutely integrable by $\|A\|_\infty C_1(1+|X(v)|)$. The final right side is absolutely integrable by $\tau[B_1\|D_vA\|_\infty+\|A\|_\infty B_2\tau\|v\|]$. For $v=0$ the radial curve, field translation and all derivatives occurring in this identity are zero.

Parts 1–2 prove clause 1, part 3 proves clause 2, part 4 proves clause 3, and parts 5–6 prove clauses 4–5. Radial endpoints are one-sided where specified; an interior loading has every chosen physical extension, and the zero loading was included separately. All global, mean and level conditions remain those of the original fixed pair. This proof establishes neither Gaussian Sobolev regularity for the actual measurable hybrid weights nor any loading derivative of full FDR, exchange with regularizer limits, or uniform $q$-scaled budget.
