---
type: lemma
title: >-
  Wasserstein continuity of full population Gaussian BH FDR with a fixed common
  loading
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_bh_common_loading_tagged_population
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - common_loading
  - population_bh
  - wasserstein
---

## Statement

Fix $q\in(0,1/2)$, $\sigma\in(0,1)$ and a nonzero separable real Hilbert space $\mathcal H$. Use exactly the unit-sphere directions, closed tagged parameter space $\mathcal E$, deterministic laws $\mathcal P_1(\mathcal E)$, metric $c$, Wasserstein distance $W_1$, isonormal process $X$, independent common standard Gaussian $Z$, scores $T$, functions $H_\pi,V_\pi$, actual largest non-strict crossing $\rho_\pi$, full fractional FDP $D_\pi$ and expectation $F_\pi$ of the [common-loading tagged population definition](../definitions/gaussian_bh_common_loading_tagged_population.md). In particular $T(\theta,v,\ell)=\theta+\sqrt{1-\sigma^2}X(v)+\sigma Z$, every $\|v\|=1$, true tags have $\theta\le0$, and alternative tags have $\theta\ge0$. The alternative-tagged zero points belong only to the analytic completion.

1. **Well-defined population functional.** The series construction provides a jointly measurable isonormal evaluation representative. For any countable family of parameter laws, a common probability-one event makes the evaluations valid for almost every parameter under every law in that family. The functions $H_\pi,V_\pi$ and the random variables $\rho_\pi,D_\pi$ are measurable, $0\le D_\pi\le1$, and $F_\pi$ is well defined. Changing the representative on a set null for the product of a given parameter law and Gaussian probability does not change its $F_\pi$. Every positive $\rho_\pi$ is an attained qualifying largest crossing and satisfies
$$
H_\pi(\rho_\pi)=\rho_\pi.
$$
The event $\rho_\pi=1$ and the possibility $\rho_\pi=0$ are both included. The definition and conclusions retain all competing crossings, without uniqueness or a strict-root hypothesis.

2. **Uniform control of microscopic ranks.** Put $\tau=\sqrt{1-\sigma^2}$ and use the scalar distribution $F_z$ and measure $dF_z$ in the definition. For every true-tagged parameter, the conditional marginal comparison is
$$
\mathbb P\{S(\theta+\tau X(v)+\sigma Z)\le t\mid Z=z\}
=S\!\left(\frac{S^{-1}(t)-\theta-\sigma z}{\tau}\right)\le F_z(t)
\quad(0<t<1).
$$
This is a marginal comparison and requires no independence among the residual evaluations. For every $z\in\mathbb R$ and $b\in(0,1)$,
$$
\int_{(0,b]}\frac{dF_z(t)}t<\infty.
$$
For every $a\in(0,1)$ one has the dimension- and law-uniform estimate
$$
\sup_{\pi\in\mathcal P_1(\mathcal E)}
\mathbb E\!\left[D_\pi\mathbf1_{\{0<\rho_\pi\le a\}}\right]
\le
\mathbb E_Z\min\!\left\{1,\ q\int_{(0,qa]}\frac{dF_Z(t)}t\right\}
\longrightarrow0\qquad(a\downarrow0).
$$
Here $\mathbb E_Z$ integrates only the standard normal $Z$. The ratio defining $D_\pi$ is used only at positive ranks. Finiteness, the displayed comparison and the limiting assertion are conclusions to establish at the fixed $q,\sigma$.

3. **Wasserstein continuity of the full FDR.** For arbitrary $\pi,\pi_n\in\mathcal P_1(\mathcal E)$, indexed by positive integers $n$, one has
$$
W_1(\pi_n,\pi)\longrightarrow0
\quad\Longrightarrow\quad
F_{\pi_n}\longrightarrow F_\pi.
$$
This assertion covers atomic and non-atomic laws, arbitrary means in the tagged domain, changes among competing largest crossings, vanishing positive ranks and the endpoint rank one. It concerns the original common-cutoff numerator $V_\pi(\rho_\pi)$ and the full mixed-label FDP, not a separately optimized rank or null-only functional. Any common-shift monotonicity used to prove it must be applied to the rank; monotonicity of the mixed FDP is not a hypothesis or conclusion.

4. **Approximation by ordinary finite Gaussian BH.** For every $\pi\in\mathcal P_1(\mathcal E)$ there are finite rational parameter laws
$$
\pi_n=\sum_{j=1}^{m_n}\frac{k_{nj}}{N_n}\,
\delta_{(\theta_{nj},v_{nj},\ell_{nj})},\qquad
N_n=\sum_{j=1}^{m_n}k_{nj},\quad
m_n,k_{nj}\in\{1,2,\ldots\},
$$
where $\delta_x$ denotes unit point mass at $x$, with $\|v_{nj}\|=1$ and canonical labels
$$
\ell_{nj}=\mathbf1_{\{\theta_{nj}\le0\}},\qquad
\ell_{nj}=0\Longrightarrow\theta_{nj}>0,
$$
such that $W_1(\pi_n,\pi)\to0$. In particular, any alternative-tagged zero means in $\pi$ are approached by strictly positive means with the alternative tag unchanged. Realize $\pi_n$ by exactly $k_{nj}$ identical copies of the score
$$
T_{nj}=\theta_{nj}+\tau X(v_{nj})+\sigma Z.
$$
Every resulting $N_n$-coordinate observation is an admissible [finite Gaussian testing model](../definitions/gaussian_multiple_testing_model.md), including possible singular covariance, with all marginal variances one. Its [one-sided p-values and actual true-null labels](../definitions/gaussian_test_pvalues.md) are canonical. Its [ordinary largest-rank BH](../definitions/benjamini_hochberg_step_up.md) [false discovery rate](../definitions/false_discovery_rate.md) at the same $q$ is exactly $F_{\pi_n}$, and
$$
F_{\pi_n}\longrightarrow F_\pi.
$$
Exact uniform replication of any such finite array preserves its FDR. Thus every completed tagged value is a limit of actual finite-model FDR values at the same fixed common loading, and the completion does not enlarge the supremum beyond the original finite admissible Gaussian models.

## Scope

This is an original draft supporting continuity target, with no proof asserted. Its four conclusions require native falsification, proof execution and fresh independent proof verification before use. Any constants or continuity moduli may depend on the fixed $q$ and $\sigma$. No uniform limit as $\sigma\downarrow0$, extension of a first-variation identity to this space, attained finite positive-definite optimizer, Ekeland application, $q$-scaled boundary payment or unrestricted Gaussian BH order bound is asserted.

## Proof

Write $\phi(u)=(2\pi)^{-1/2}e^{-u^2/2}$ and $\tau=\sqrt{1-\sigma^2}$. All parameter laws and couplings below are deterministic. We use the five approved definitions in `uses_definitions`; there are no asset prerequisites or draft-definition assumptions.

**1. Jointly measurable Gaussian evaluations.** In infinite dimension let $X_m(v)=\sum_{k=1}^m\langle v,e_k\rangle\xi_k$. Its convergence set is the measurable set
$$
C=\bigcap_{j\ge1}\bigcup_{N\ge1}\bigcap_{m,n\ge N}
\{|X_m(v)-X_n(v)|<1/j\}.
$$
Each partial sum is jointly measurable, so its limit on $C$, extended by zero on $C^c$, is jointly measurable. The finite-dimensional case is immediate.

For completeness fix $v$. The independent centered summands have total variance $\sum_k\langle v,e_k\rangle^2=\|v\|^2<\infty$. For independent centered square-integrable summands, the maximal inequality
$$
\mathbb P\left\{\max_{N<m\le M}\left|\sum_{k=N+1}^mY_k\right|>t\right\}
\le t^{-2}\sum_{k=N+1}^M\mathbb EY_k^2
$$
follows by partitioning according to the first index where the partial sum exceeds $t$: subsequent centered increments have zero cross expectation with that stopped partial sum, and the final second moment is at least $t^2$ times the crossing probability. Choose $N_j$ so that the variance tail after $N_j$ is at most $2^{-4j}$. Letting $M\to\infty$ in this inequality gives probability at most $2^{-2j}$ that a tail partial sum from $N_j$ exceeds $2^{-j}$. Borel--Cantelli implies the Cauchy property and almost-sure convergence. The same series converges in $L^2$. Thus the finite partial-sum covariance identity passes to the limit, giving $\mathbb EX(v)X(w)=\langle v,w\rangle$. For any finite list of directions, every linear combination of the partial sums is centered normal and converges in $L^2$; convergence of characteristic functions gives a normal limit with the limiting variance. This identifies all joint Gaussian finite-dimensional distributions. The same argument applies to arbitrary vectors of $\mathcal H$ if the process is extended off the sphere.

For any fixed parameter law, Fubini applied to $C^c$ gives a probability-one event on which the series is valid for parameter-almost every point. Intersect these events for a countable list of laws. In particular we may include $\pi,\pi_1,\pi_2,\ldots$ below; each coupling of two of these laws then gives full mass to pairs of valid evaluations. No assertion of a bounded linear functional on the whole Hilbert space for a fixed Gaussian sample is involved.

**2. Exact largest crossings and measurability.** First fix any probability law of finite scalar scores, with their tags. Its p-values lie in $(0,1)$. The function $H(r)=\int\mathbf1_{\{p\le qr\}}$ is increasing and right-continuous on $(0,1]$. At any interior $r$, monotonicity and right-continuity give $\limsup_{s\to r}H(s)\le H(r)$; the analogous one-sided assertion holds at $1$. Consequently $H(r)-r$ is upper semicontinuous on every $[a,1]$, $a>0$.

If the supremum $\rho$ of qualifying ranks is positive, take positive qualifying $r_j\to\rho$. Upper semicontinuity gives $H(\rho)\ge\rho$. If $\rho<1$ and $H(\rho)>\rho$, choose $s$ strictly between $\rho$ and $\min\{H(\rho),1\}$; monotonicity gives $H(s)\ge H(\rho)>s$, contradicting maximality. If $\rho=1$, $H(1)\le1$ already gives equality. Thus
$$
\rho>0\quad\Longrightarrow\quad H(\rho)=\rho,\qquad 0\le V(\rho)\le\rho.
$$
There need be neither a unique crossing nor an interval of qualifying ranks.

For fixed $a\in(0,1]$, compactness and upper semicontinuity show
$$
\{\rho\ge a\}=\left\{\max_{r\in[a,1]}(H(r)-r)\ge0\right\}.
$$
The maximum's value equals the supremum of $H(r)-r$ over $r\in\mathbb Q\cap(a,1)$ together with the two endpoints $a,1$: for any $r<1$ approach $r$ from the right by such rationals and use right-continuity. For $a=1$ just use the endpoint. This computes a value by a countable supremum; it does not claim that a rational qualifying rank exists whenever an irrational one does. Therefore $\rho$ is measurable. This argument also proves joint measurability in the residual Gaussian sequence and a freely varying real common shift $z$.

The score field is measurable; integration of its measurable indicators shows that $H,V$ are jointly measurable in rank and Gaussian inputs, with their stipulated value zero at rank zero. Composition with $\rho$ makes $V(\rho)$ and $D$ measurable. The preceding inequality gives $0\le D\le1$, including $D=0$ at $\rho=0$, so $F$ exists. Finally, a product-null change of representative leaves the evaluations equal for parameter-almost every point outside a single Gaussian-null set, by Fubini. On that event the two integrals $H(r),V(r)$ agree simultaneously for every $r$, because the integrands differ only on the same parameter-null set. Their largest crossings and FDPs agree. This proves all representative-invariance assertions.

**3. Uniformly negligible microscopic ranks.** Conditional on $Z=z$, each fixed $X(v)$ is standard normal. For $\theta\le0$ this gives, for every $0<t<1$,
$$
\mathbb P\{S(\theta+\tau X(v)+\sigma Z)\le t\mid Z=z\}
=S\left(\frac{S^{-1}(t)-\theta-\sigma z}{\tau}\right)
\le S\left(\frac{S^{-1}(t)-\sigma z}{\tau}\right)=F_z(t).
$$
These formulas specify conditional versions for every real $z$. They make no joint independence claim about residual evaluations.

Put $I_z(b)=\int_{(0,b]}t^{-1}\,dF_z(t)$. Writing the zero-mean conditional score as $U=\tau Y+\sigma z$, $Y$ standard normal, change variables $t=S(u)$ in its expectation to get
$$
I_z(b)=\int_{S^{-1}(b)}^\infty
\frac{\phi((u-\sigma z)/\tau)}{\tau S(u)}\,du.
$$
For $u\ge1$, integrating the normal density only over $[u,u+(u+1)^{-1}]$ yields
$$
S(u)\ge\frac{e^{-3/2}}{u+1}\phi(u).
$$
Indeed the density ratio across that interval is at least $e^{-3/2}$. The integrand in the last display for $I_z$ is consequently bounded, on this tail, by
$$
C_{z,\sigma}(u+1)
\exp\left\{-\frac{\sigma^2u^2}{2\tau^2}+\frac{\sigma z u}{\tau^2}\right\}.
$$
This is integrable since $\sigma>0$. On the remaining bounded interval the integrand is continuous and finite. Thus $I_z(b)<\infty$ for every $z$ and $b<1$. As $b\downarrow0$, the integrals decrease to zero by integrability on any fixed $(0,b_0]$; $F_z$ has no atom at zero.

The conditional CDF comparison also controls the reciprocal-tail expectation. One can see this without a discontinuous-test-function issue: couple the two scalar conditional p-values by the same standard normal $Y$. For $\theta\le0$,
$S(\theta+\tau Y+\sigma z)\ge S(\tau Y+\sigma z)$. The nonnegative function $f_b(t)=t^{-1}\mathbf1_{\{0<t\le b\}}$ is decreasing on $(0,1)$, so $f_b$ of the first p-value is at most $f_b$ of the second. Truncation, then monotone convergence if needed, gives its conditional expectation at most $I_z(b)$.

On $0<\rho\le a$, a selected p-value satisfies $p\le q\rho\le qa$ and $1/\rho\le q/p$. Hence pathwise
$$
D\mathbf1_{\{0<\rho\le a\}}
\le q\int\ell\,p(x)^{-1}\mathbf1_{\{p(x)\le qa\}}\,\pi(dx).
$$
Conditional Tonelli and the scalar comparison bound its conditional expectation by $qI_z(qa)\int\ell\,d\pi\le qI_z(qa)$. The conditional expectation is also at most one. Define
$$
B(a)=\mathbb E_Z\min\{1,qI_Z(qa)\}.
$$
Then $\mathbb E[D_\pi\mathbf1_{\{0<\rho_\pi\le a\}}]\le B(a)$ for every admissible law, independently of dimension or residual dependence. Bounded convergence in $Z$ gives $B(a)\to0$. This is precisely clause 2.

**4. Parameter couplings and residual score costs.** Suppose $W_1(\pi_n,\pi)\to0$. Choose couplings $\lambda_n\in\Gamma(\pi,\pi_n)$ with costs
$$
\delta_n:=\int c(x,x')\,\lambda_n(dx,dx')\le W_1(\pi,\pi_n)+1/n\longrightarrow0.
$$
Use the same residual series and the same independent $Z$ for all laws. Write $x=(\theta,v,\ell)$, $x'=(\theta',v',\ell')$ and
$$
A(x)=\theta+\tau X(v),\qquad A'(x')=\theta'+\tau X(v').
$$
The covariance identity in step 1 implies that $X(v)-X(v')$ is centered normal with variance $\|v-v'\|^2$. Fubini, the triangle inequality and the mean absolute value of a standard normal give
$$
\mathbb E_X\int|A-A'|\,d\lambda_n
\le\int\left(|\theta-\theta'|+\tau\sqrt{2/\pi}\|v-v'\|\right)d\lambda_n
\le C\delta_n,
\qquad \lambda_n\{\ell\ne\ell'\}\le\delta_n,
$$
where one may take $C=1$. Here $\mathbb E_X$ integrates the residual sequence alone. The estimate is integrated over the coupling, and asserts no supremum over directions. From now on the Gaussian samples where all required evaluations are valid are understood.

**5. A deterministic rank comparison after trimming.** Fix a residual realization and let $R(z),R_n(z)$ denote the two actual largest ranks when the common variable takes the value $z$. Set
$$
u(r)=S^{-1}(qr),\qquad
L_a=\sup_{a/2\le r\le1}|u'(r)|<\infty
\quad(0<a<1).
$$
Finiteness follows from $u'(r)=-q/\phi(u(r))$ on this compact interval. Fix $0<\gamma<a/2$, $e>0$, and put
$$
h=\frac{e+L_a\gamma}{\sigma},\qquad
\beta=\lambda_n\{|A-A'|>e\}.
$$
Assume $\beta\le\gamma$. If a rank $r\ge a$ qualifies for the primed law at $z$, it selects coupling mass at least $r$. After removing the pairs with $|A-A'|>e$, the remaining mass is at least $r-\gamma$. Put $s=r-\gamma\ge a/2$. On every remaining selected pair,
$$
A+\sigma(z+h)\ge A'+\sigma z-e+\sigma h
\ge u(r)+L_a\gamma\ge u(s),
$$
where $u(s)-u(r)\le L_a\gamma$. Thus $H_\pi(s;z+h)\ge s$: $s$ qualifies for the unprimed law at the shifted common value. Exchanging the two laws proves the identical transfer in the reverse direction. Both implications hold for every real $z$ on the same residual realization.

If $R_n(z)\ge a$, attainment from step 2 permits $r=R_n(z)$ and gives $R_n(z)\le R(z+h)+\gamma$. If $R_n(z)<a$, it is at most $R(z+h)+a+\gamma$ trivially. Apply the exchanged implication at $z-h$ to $R(z-h)$ when it is at least $a$; when it is smaller the lower bound is again trivial. We obtain simultaneously for all $z$,
$$
R(z-h)-a-\gamma\le R_n(z)\le R(z+h)+a+\gamma.
$$
This comparison applies to all competing crossings because each positive largest rank is attained; no branch has been chosen. In particular, a qualifying rank $r=1$ transfers only to $s=1-\gamma$, so the argument never asks for a rank beyond one. Zero ranks and ranks smaller than $a$ are covered by the additive $a$.

**6. Integrated convergence of the ranks.** Increasing $z$ increases every score and every $H(r;z)$. Thus $R(z)$ is increasing and takes values in $[0,1]$. For any such measurable increasing function and $h>0$,
$$
\mathbb E_Z[R(Z+h)-R(Z-h)]\le\frac{2h}{\sqrt{2\pi}}.
$$
To verify this directly, use $R(t)=\int_0^1\mathbf1_{\{R(t)>y\}}\,dy$. For each $y$, the set $\{t:R(t)>y\}$ is an upper interval, possibly empty or the whole line, with either endpoint convention. The difference of its indicators evaluated at $z+h$ and $z-h$ is supported on an interval of Lebesgue length at most $2h$. Its standard-normal integral is at most $2h/\sqrt{2\pi}$. Tonelli proves the display, including arbitrary jumps.

On $\beta\le\gamma$, the comparison in step 5 and $R(z-h)\le R(z)\le R(z+h)$ imply
$$
|R_n(z)-R(z)|\le a+\gamma+R(z+h)-R(z-h).
$$
Markov's inequality and step 4 give $\mathbb P_X\{\beta>\gamma\}\le C\delta_n/(e\gamma)$. On this exceptional event the rank difference is at most one. Independence of $Z$ from the residual sequence therefore gives
$$
\mathbb E|\rho_n-\rho|
\le a+\gamma+\frac{2(e+L_a\gamma)}{\sigma\sqrt{2\pi}}
+\frac{C\delta_n}{e\gamma}.
$$
First take $n\to\infty$ at fixed $a,e,\gamma$, then $e,\gamma\downarrow0$ at fixed $a$, and finally $a\downarrow0$. It follows that $\mathbb E|\rho_n-\rho|\to0$. Only ranks have been asserted to be monotone in the common shift.

**7. Bands at the dependent random cutoff.** Fix a residual realization and a parameter $x$ with finite evaluation. On $\{z:R(z)>0\}$ define
$$
g_x(z)=A(x)+\sigma z-u(R(z)).
$$
For $z_2>z_1$ in this set, rank monotonicity and the decreasing nature of $u$ give
$$
g_x(z_2)-g_x(z_1)
=\sigma(z_2-z_1)+u(R(z_1))-u(R(z_2))
\ge\sigma(z_2-z_1).
$$
If two points belong to $\{z:R(z)>0,|g_x(z)|\le b\}$, their distance is at most $2b/\sigma$. Hence this measurable set has Lebesgue measure at most $2b/\sigma$, even if it is disconnected or $R$ jumps. Integrating the standard normal density, then the parameter law and residual sequence, yields
$$
\mathbb E\int\mathbf1_{\{\rho>0,\ |T(x)-u(\rho)|\le b\}}\,\pi(dx)
\le\frac{2b}{\sigma\sqrt{2\pi}}.
$$
This bound concerns exactly the same $Z$ in the score and the cutoff. Atomic score laws cause no problem; neither an independent cutoff nor a continuous score distribution conditional on the residual sequence has been invoked.

**8. The original true-tag numerator on positive macroscopic ranks.** Abbreviate $V=V_\pi(\rho)$ and $V_n=V_{\pi_n}(\rho_n)$. Fix $a>0$, $d>0$, $e>0$, with $a<1$. On the event
$$
\rho,\rho_n\ge a,\qquad |\rho_n-\rho|\le d,
$$
we have $|u(\rho_n)-u(\rho)|\le L_a d$. A coupled pair with equal tags and $|A-A'|\le e$ can have different selection indicators only when
$$
|T(x)-u(\rho)|\le e+L_a d.
$$
Indeed, above this band the primed score remains strictly above its primed cutoff, and below it the primed score remains strictly below that cutoff. Non-strict selection at the band endpoints is included in the displayed band. Expressing both numerators as coupling integrals, their difference is bounded by the sum of the masses of unequal tags, pairs with $|A-A'|>e$, and this band, together with the indicator of $|\rho_n-\rho|>d$. Step 4, step 7 and Markov therefore give
$$
\mathbb E\left[|V_n-V|\mathbf1_{\{\rho_n,\rho\ge a\}}\right]
\le\delta_n+\frac{C\delta_n}{e}
+\frac{2(e+L_a d)}{\sigma\sqrt{2\pi}}
+\frac{\mathbb E|\rho_n-\rho|}{d}.
$$
Taking $n\to\infty$ and then $e,d\downarrow0$ proves convergence of this restricted numerator difference to zero. Since $V_n\le\rho_n$ and $V\le\rho$, direct subtraction of the two fractions on this event gives
$$
|D_n-D|\le\frac{|V_n-V|}{a}+\frac{|\rho_n-\rho|}{a}.
$$
Thus the expected FDP difference restricted to $\{\rho_n,\rho\ge a\}$ tends to zero. Both numerators here use their original common cutoffs and original mixed-label laws.

**9. Completion of full FDR continuity.** Take $0<2a<1$. Every rank pair belongs to at least one of the following sets: both ranks are at most $2a$; both ranks are at least $a$; or their minimum is smaller than $a$ and their maximum is greater than $2a$. On the first set, $|D_n-D|\le D_n+D$ costs at most $2B(2a)$ in expectation by step 3, including the stipulated zero FDP at zero rank. The middle set is controlled by step 8. The last set forces $|\rho_n-\rho|>a$, so its contribution is at most $\mathbb E|\rho_n-\rho|/a$. Consequently
$$
\limsup_{n\to\infty}\mathbb E|D_n-D|\le2B(2a).
$$
Letting $a\downarrow0$ proves $L^1$ convergence of the full FDPs and therefore $F_{\pi_n}\to F_\pi$. In particular this includes loss of a positive crossing at zero, competition among largest crossings and the terminal rank one.

**10. Canonical finite rational approximation.** The space $\mathcal E$ is a closed subset of the product of $\mathbb R$, the complete separable unit sphere and the two-point label space; hence it is Polish. Fix any unit direction $v_0$ and canonical anchor $x_0=(0,v_0,1)$. The distance $d_0(x)=c(x,x_0)$ is at most $|\theta|+3$, and is integrable for every law in question.

For $\varepsilon>0$ first push $\pi$ forward by the map which adds $\varepsilon$ to $\theta$ on alternative tags and leaves true tags unchanged. Call the resulting law $\mu$. This costs at most $\varepsilon$ in $W_1$, preserves unit directions, and gives full mass to the Borel canonical domain
$$
\mathcal E_{\mathrm{can}}=\{(\theta,v,1):\theta\le0\}\ \cup\ \{(\theta,v,0):\theta>0\}.
$$
Here all alternative means are at least $\varepsilon$. We give the finite approximation for $\mu$ explicitly, without a bounded-domain assumption. Given $\eta>0$, choose $R\ge1$ with $\int_{\{d_0>R\}}d_0\,d\mu<\eta$. Inner regularity of a Borel probability on a Polish space supplies a compact $K\subset\mathcal E_{\mathrm{can}}$ with $\mu(K^c)<\eta/R$. Thus
$$
\int_{K^c}d_0\,d\mu
\le\int_{\{d_0>R\}}d_0\,d\mu+R\mu(K^c)<2\eta.
$$
The compact set may also be chosen inside the full-mass subset where alternative means are at least $\varepsilon$. Cover $K$ by finitely many open $c$-balls of radius $\eta$ centered at points of $K$, and partition $K$ measurably according to the first such ball containing a point. Map each cell to its center and $K^c$ to $x_0$. The resulting finitely supported canonical law $\nu$ satisfies
$$
W_1(\mu,\nu)\le\eta+\int_{K^c}d_0\,d\mu<3\eta.
$$
Discard zero-weight atoms. If its remaining weights are $w_1,\ldots,w_m>0$, approximate them by positive rationals $k_j/N$ summing to one. For example, for large $N$ set $k_j=\lfloor Nw_j\rfloor$ for $j<m$ and $k_m=N-\sum_{j<m}k_j$; all counts are positive for sufficiently large $N$, and every weight converges to its prescribed value. Let $M=\max_j c(x_j,x_0)<\infty$. Couple the common mass at each atom identically and distribute the remaining masses arbitrarily. Since distances between atoms are at most $2M$, the transport cost is at most $M\sum_j|w_j-k_j/N|$, tending to zero (and identically zero if $M=0$). The atoms, their directions and their canonical labels are unchanged.

Choosing $\varepsilon\downarrow0$, $\eta\downarrow0$ and then sufficiently large denominators gives the claimed $\pi_n$ by the triangle inequality. At the first stage alternative-tagged zero points move to positive means with their tag fixed; every subsequent approximant still uses only strictly positive alternative means and the Wasserstein costs tend to zero. This also covers non-atomic direction laws and unbounded means.

**11. Finite Gaussian BH identification and replication.** For a rational law in step 10, list exactly $k_j$ identical copies of each atom's score. Step 1 identifies this vector as jointly Gaussian. Its covariance entries are
$$
\Sigma_{ii'}=\tau^2\langle v_i,v_{i'}\rangle+\sigma^2.
$$
This is the sum of a nonnegative multiple of a Gram matrix and $\sigma^2$ times the all-ones matrix, so is positive semidefinite, with diagonal $\tau^2+\sigma^2=1$. It is therefore an admissible finite Gaussian model even when singular. Its one-sided p-values and actual true-null labels are precisely the canonical ones of its atoms.

For its empirical law, a positive population largest rank satisfies $\rho=H(\rho)=k/N$ for an integer $1\le k\le N$ by step 2. Conversely,
$$
H(k/N)\ge k/N\quad\Longleftrightarrow\quad p_{(k)}\le qk/N.
$$
Hence the positive population largest rank equals $\widehat k_q/N$: every qualifying integer rank is a qualifying population rank, and the largest population rank is itself one of those integer ranks. If either list has no positive qualifying rank, both ranks are zero. Equality $H(\rho)=\rho$ says that there are exactly $\widehat k_q$ rejected coordinates, including all threshold ties. Moreover $V(\rho)$ is the rejected true count divided by $N$. Thus the population FDP equals the ordinary finite FDP pathwise, and its expectation is exactly $F_{\pi_n}$. Uniformly replicating every coordinate leaves the empirical law, $H,V,\rho$ and $D$ unchanged, so preserves FDR exactly.

By steps 4--9, $F_{\pi_n}\to F_\pi$. Every canonical finite empirical law is also a completed tagged law, so their two suprema at the fixed $q,\sigma,\mathcal H$ coincide. Each such empirical law is an admissible original finite Gaussian model; its supremum, and hence the completed supremum, is at most the supremum over the original unrestricted finite Gaussian class. No equality with that larger class is required. This proves all four clauses. The argument supplies continuity and approximation only, and makes none of the additional optimizer, first-variation or order-bound assertions excluded in the scope.
