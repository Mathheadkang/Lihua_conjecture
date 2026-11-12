---
type: lemma
title: >-
  Complete signed mean-and-level variation at private-noise Gaussian BH cutoff
  extrema
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_common_loading_uniform_submodel_compression
  - gaussian_bh_exchangeable_array_variational_compactification
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
uses_definitions:
  - gaussian_bh_private_smoothed_directing_population
  - gaussian_bh_marked_exchangeable_parameter_array
  - gaussian_bh_common_loading_tagged_population
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - private_noise
  - rank_cutoff
  - signed_variation
  - suffix_minimum
  - finite_competitors
---

## Statement

Fix $0<q<1/2$, $0<\sigma<1$, $s>0$ with $\sigma^2+s^2<1$, $0<a<1/4$, and the nondecreasing $C^1$ cutoff $\chi_a$ of the [private-noise-smoothed unit-ball directing population](../definitions/gaussian_bh_private_smoothed_directing_population.md). All notation in that definition is used with the same $q,\sigma,s,a$, except where a level is explicitly varied or optimized: a deterministic directing law $\pi$, $M_2(\pi)<\infty$, $\tau_s=\sqrt{1-\sigma^2-s^2}$, lawful marks, isonormal background $X$, common $Z$, Gaussian centers $A_X$, private variances $c_s(v)^2=s^2+\tau_s^2(1-\|v\|^2)$, upper tails $H_X,V_X$, upper quantile $Q_X$, top-r true mass $v_X(r)$, full fractional payoff $f_X(r)$, and actual largest non-strict rank $R$. Write $S=\overline\Phi$, $\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}$, $m(t)=S(t)/\phi(t)$ and $q_{\max}=S(1)$. The private-noise symbol $s$ in this lemma is not the test-type index in other definitions; all tests here are one-sided.

1. **Kernel, actual ranks, and finite identification.** Prove joint measurability and representative invariance of these kernels, including simultaneous validity for each stated countable endpoint family. Every finite conditional-on-parameters model has variance exactly one and private noises independent across tests. For almost every residual background, $H_X$ is strictly decreasing from one to zero, is smooth, and has everywhere positive density. For $0<r<1$, $Q_X(r)$ is its unique upper quantile; $Q_X(1)=-\infty$ and $Q_X(0)=+\infty$. Prove that the population rank is attained when positive, that it uses the globally largest crossing, and that its full FDP is $f_X(R)$, with zero payoff at rank zero and $f_X(1)=\int\ell d\pi$ as endpoint convention.

For $u_q(r)=S^{-1}(qr)$ put
$$
B_X(r)=\frac{u_q(r)-Q_X(r)}{\sigma}\quad(0<r<1),\qquad B_X(1)=+\infty,
$$
$$
M_X(r)=\min_{t\in[r,1]}B_X(t),\qquad
\mathcal A_X(r)=\operatorname*{argmin}_{t\in[r,1]}B_X(t)\quad(0<r<1).
$$
Prove that each minimum is finite and attained on a compact subset of $[r,1)$, that all necessary objects are measurable, and the actual-rank identity
$$
\{R(X,Z)\ge r\}=\{Z\ge M_X(r)\},\qquad
\mathbb P_Z\{R(X,Z)\ge r\mid X\}=S(M_X(r))
$$
for $0<r<1$, with any exceptional boundary convention justified rather than assumed. At $r=1$, use $M_X(1)=+\infty$ and $\mathbb P_Z(R=1\mid X)=0$. This is a derived description of the actual largest rank, not an independent rank optimization.

Prove that ordinary finite Gaussian competitors with independent private noise converge to these population values, including the full FDP and cutoff-weighted FDP. In doing so extend, rather than silently reuse outside its stated class, the microscopic bound of the approved [common-loading continuity theorem](gaussian_bh_common_loading_wasserstein_fdr_continuity.md). For each fixed parameter, the residual marginal variance after integrating both $X$ and private noise is exactly $1-\sigma^2$. Hence derive, or rigorously pass through finite competitors,
$$
\mathbb E[D\mathbf1_{\{0<R\le t\}}]\le B_{q,\sigma}(t),\qquad
B_{q,\sigma}(t)=\mathbb E_Z\min\left\{1,q\int_{(0,qt]}u^{-1}dF_Z(u)\right\}\longrightarrow0,
$$
where $F_z(u)=S((S^{-1}(u)-\sigma z)/\sqrt{1-\sigma^2})$. The bound is uniform in directing dimension, law and private smoothing, and its locally uniform-in-$q$ version must be established when used.

2. **Exact regularized extrema.** Apply the private smoothing $C\mapsto C^{(s)}$ to the [marked-array completion](gaussian_bh_exchangeable_array_variational_compactification.md). Prove continuity of this map, closedness of its image on moment-bounded compact sets, and uniform convergence of its finite expectations $\mathcal F_n^a$ to a jointly continuous $\mathcal F^a(P;q,\sigma,s)$, locally uniformly in $q$. The proof must compare normalized ranks as well as FDPs before multiplying by $\chi_a$. Use the outer expectation convention for general array mixtures.

For each $\eta>0$ and fixed $0<q<1/2$, the supremum
$$
A_{\eta,\sigma,s,a}(q)=\sup_{P\in\mathfrak P_2}
\{\mathcal F^a(P;q,\sigma,s)-\eta M_2(P)\}
$$
is attained. For each $\eta,\delta>0$, the analogous supremum
$$
L_{\eta,\delta,\sigma,s,a}=\sup_{P\in\mathfrak P_2,\ 0<q\le q_{\max}}
\left\{\frac{\mathcal F^a(P;q,\sigma,s)}{qS^{-1}(q)}-\eta M_2(P)-\delta\log(1/q)\right\}
$$
is finite and attained. Prove the needed moment bounds, coercivity and upper semicontinuity; do not assume a sphere optimizer or finite support. Only after the known representation source gate, its marked adaptation, kernel identification and affinity are proved, show that a deterministic directing maximum can be selected. Show it may be chosen with canonical zero-mean tags by numerator domination. These maxima are within the completed privately smoothed class; no equality with the supremum over every finite model having a fixed private-noise lower bound is assumed.

3. **Fixed-rank quantile derivatives.** Let $b$ be any bounded lawful deterministic mean velocity, $|b|\le K$, chosen before all observations, and let $\pi_\epsilon$ be its mean-shift pushforward. Conditional on $X$, suppress its subscript and define
$$
k_x(t)=\frac1{c_s(v)}\phi\!\left(\frac{t-A_X(x)}{c_s(v)}\right),\qquad
h(t)=\int k_x(t)d\pi(x),\quad h_b(t)=\int b(x)k_x(t)d\pi(x),
$$
$$
h_0(t)=\int\ell k_x(t)d\pi(x),\qquad
h_{0b}(t)=\int\ell b(x)k_x(t)d\pi(x).
$$
For $0<r<1$ prove the right derivatives, locally uniformly on compact subintervals in $r$,
$$
\dot Q(r)=\frac{h_b(Q(r))}{h(Q(r))},\qquad
\dot f(r)=\frac{h_{0b}(Q(r))-h_0(Q(r))h_b(Q(r))/h(Q(r))}{r}.
$$
Dots mean $d/d\epsilon|_{0+}$ for this fixed perturbation, not a variation in $r$. Set $\dot f(1)=0$ since the total true mass is unchanged, and use $\chi_a(R)\dot f(R)=0$ when $R\le a$. Prove the uniform score-coupling bound $|Q_\epsilon(r)-Q(r)|\le\epsilon K$, a corresponding true-tail bound $|v_\epsilon(r)-v(r)|\le2\epsilon K/(s\sqrt{2\pi})$, and $|f'(r)|\le1/r$. Here primes denote ordinary derivatives in $r$.

4. **All-minima envelope and full signed response.** Allow also $q_\epsilon=q(1+\epsilon\lambda)$ for fixed finite $\lambda$, staying in the allowed level interval. For $0<r<1$ prove the right envelope derivative
$$
\dot M(r)=\min_{t\in\mathcal A(r)}
\frac{-\lambda m(u_q(t))-\dot Q(t)}{\sigma}.
$$
The minimum includes every active suffix minimizer. Prove local uniform implicit differentiation needed for this envelope and rule out escapes to the $r=1$ endpoint. No unique minimum, isolated fold, nondegenerate critical point, or linear response under $b\mapsto-b$ is assumed.

The complete right derivative of the cutoff functional is
$$
\dot{\mathcal F}^{a}
=\mathbb E_X\left[
\mathbb E_Z\{\chi_a(R)\dot f(R)\}
-\int_a^1(\chi_a f)'(r)\phi(M(r))\dot M(r)\,dr
\right].
$$
The first expectation uses the unperturbed actual rank. The integral is over $a<r<1$, so no undefined endpoint product is required. Prove the derivative by separating the change of payoff at the perturbed rank from the change in its distribution, using the actual-rank suffix-minimum identity. Justify conditional rank convergence outside Gaussian-null jump levels and domination in the integral and in $X$. This expression includes ordinary smooth branches and births, switches and tied minima; no signed term may be dropped or replaced by a positive part.

For mean transport alone ($\lambda=0$), establish a uniform difference-quotient domination with bound
$$
\frac{2K}{a s\sqrt{2\pi}}+
\frac{K[1+\log(1/a)]}{\sigma\sqrt{2\pi}},
$$
or a larger explicitly justified constant. For finite $\lambda$, also justify domination of the level term, for example using $\sup_{0<r\le1}m(u_q(r))=m(S^{-1}(q))$ and the resulting bound $(K+|\lambda|m(S^{-1}(q)))/\sigma$ on $|\dot M|$.

5. **Exact extremal inequalities.** At a deterministic directing fixed-level maximum, every lawful mean direction satisfies
$$
\dot{\mathcal F}^{a}-2\eta\int\theta b\,d\pi\le0.
$$
At a true normalized maximum $(\pi,q)$, write $U=S^{-1}(q)$. For every allowed mean/level right perturbation, including only $\lambda\le0$ if $q=q_{\max}$, prove
$$
\frac{\dot{\mathcal F}^{a}}{qU}
-\lambda\frac{\mathcal F^a}{qU}\left(1-\frac{m(U)}U\right)
-2\eta\int\theta b\,d\pi+\delta\lambda\le0.
$$
This retains the signed moment derivative, normalization derivative, and derivative of $-\delta\log(1/q)$. Derive it from the exact lawful comparison at an attained maximum; do not infer linear complementarity from the nonlinear active-minimum response.

6. **Finite endpoint recovery and value limits.** For each fixed deterministic directing law and each fixed lawful perturbation endpoint, construct canonical ordinary finite Gaussian models whose full FDR, cutoff-weighted FDR and empirical second mean moment approximate the corresponding endpoint quantities arbitrarily closely. Every false-tagged zero must be shifted to a strictly positive mean with moment control. When the endpoint depends on $\epsilon>0$, choose approximants after fixing it so that all three errors are $o(\epsilon)$, at its actual level $q_\epsilon$. This is a conclusion requiring proof beyond equality of penalized suprema; it is not asserted for arbitrary outer mixtures.

At fixed $q,\sigma,\eta>0$, recover the original completed fixed-$\sigma$ penalized value of the array lemma through
$$
\lim_{\substack{s\downarrow0,\ a\downarrow0\\\sigma^2+s^2<1}}
A_{\eta,\sigma,s,a}(q)=A_{\eta,\sigma}(q).
$$
Likewise, for fixed $\sigma,\eta,\delta>0$, prove $L_{\eta,\delta,\sigma,s,a}\to L_{\eta,\delta,\sigma}$ as $s,a\downarrow0$. Use finite-model covariance continuity, array topology, the microscopic bound and the coercive level interval. These are value limits only. They do not pass a derivative through private smoothing, cutoffs, atomization or covariance limits.

## Scope and provenance

Extracted as a new draft goal from the seventh resumed reassessment and its complete smoothed-cutoff variation proposal. The Dovbysh--Sudakov input is the known source theorem to be verified and approved in the sources stage, then adapted in the prerequisite array lemma; no unverified representation theorem is assumed or reproved here. This target does not construct the paired inverse-Mills transport, make tied-minimum response linear, or pay the $q$-scaled extremal zero-null flux. A main bound would still require estimates uniform in the regularizers before taking these value limits.

## Proof

We use the approved [continuity theorem](gaussian_bh_common_loading_wasserstein_fdr_continuity.md), [compression theorem](gaussian_bh_common_loading_uniform_submodel_compression.md), and [array compactification](gaussian_bh_exchangeable_array_variational_compactification.md) only within their stated classes. Write $\tau=\sqrt{1-\sigma^2}$. All expectations involving an array law first condition on its parameters. A deterministic directing law always generates an admissible base marked-array law by iid parameter draws, off-diagonal entries $\langle v_i,v_j\rangle$, and diagonal entries one: each finite residual matrix is its Gram matrix plus the nonnegative diagonal $1-\|v_i\|^2$.

### 1. Kernels and actual ranks

For a fixed $v$, the defining series for $X(v)$ converges almost surely, since its independent centered summands have summable variances $\sum_k\langle v,e_k\rangle^2=\|v\|^2$. Partial sums are jointly measurable in $(v,X)$. Their convergence set is measurable, and taking the limit there and zero elsewhere gives a jointly measurable representative. Fubini shows that, for each specified parameter law, almost every $X$ is valid at almost every parameter. Intersect these probability-one events for any stated countable endpoint family. Two representatives equal almost surely at each deterministic parameter are equal for parameter-almost every point for almost every $X$, again by Fubini. Consequently their integrated kernels, quantiles, ranks, and expectations agree. Mean pushforwards keep $v$ unchanged, so the same parameter-almost-everywhere validity event also works throughout a fixed mean perturbation.

Fix such a valid $X$. The centers $A_X(x)$ are finite for $\pi$-almost every $x$, and $s\le c_s(v)\le\tau$. For every nonnegative integer $j$, the $j$th derivative of a centered Gaussian density of standard deviation $c\ge s$ has supremum bounded by a finite constant depending only on $j,s$. This follows by writing it as $c^{-j-1}$ times a polynomial times the standard Gaussian density. Differentiation under the parameter integral is therefore valid to every finite order, uniformly on compact score intervals. It gives $H_X'=-h_X$, with $h_X(t)>0$ for every finite $t$, and analogous derivatives for $V_X$. Bounded convergence gives $H_X(-\infty)=1$, $H_X(+\infty)=0$, and $V_X(-\infty)=\int\ell\,d\pi$. Hence the asserted unique quantiles exist, depend continuously and smoothly on $r\in(0,1)$, and have the stated infinite endpoints. For example $\{Q_X(r)>t\}=\{H_X(t)>r\}$ proves their joint measurability. Parameter integration also proves joint measurability of all displayed densities and tails.

For a finite parameter list, generate independent $\zeta_i$ as specified in the definition. The centered scores are jointly Gaussian and
$$
\operatorname{Var}(T_i)=\tau_s^2\|v_i\|^2+c_s(v_i)^2+\sigma^2=1,
\qquad
\operatorname{Cov}(T_i,T_j)=\tau_s^2\langle v_i,v_j\rangle+\sigma^2\quad(i\ne j).
$$
Thus each conditional-on-parameters observation is exactly a lawful finite Gaussian model, with independent private noises. Parameter mixing is kept outside that model.

For $0<r<1$, strict decrease of $H_X$ gives
$$
H_X(u_q(r)-\sigma z)\ge r
\quad\Longleftrightarrow\quad
u_q(r)-\sigma z\le Q_X(r)
\quad\Longleftrightarrow\quad z\ge B_X(r).
$$
The function $B_X$ is continuous on $(0,1)$ and tends to $+\infty$ at one, since $u_q(r)\to S^{-1}(q)$ and $Q_X(r)\to-\infty$. On each suffix $[r,1)$ it consequently has a finite minimum, attained in a compact subset bounded away from one. The active set is nonempty and compact. The infimum may be computed over rational $t\in(r,1)$ together with $t=r$; this proves measurability of $M_X(r)$ jointly in $X,r$. The graph of the active set is the measurable set $r\le t<1$, $B_X(t)=M_X(r)$, with compact sections. This supplies the needed measurable active-set objects; no choice of a minimizer is required below.

For finite $z$ no rank sufficiently close to one qualifies: $H_X(u_q(r)-\sigma z)$ tends to the number $H_X(S^{-1}(q)-\sigma z)<1$. If the supremum of qualifying ranks is positive, take a sequence tending to it. Continuity then proves that the supremum $R$ qualifies and is below one. If its total tail were strictly greater than $R$, the same strict inequality would hold at a slightly larger rank, a contradiction. Thus
$$
H_X(u_q(R)-\sigma z)=R,\qquad
u_q(R)-\sigma z=Q_X(R),\qquad
D=V_X(Q_X(R))/R=f_X(R).
$$
This argument starts with all qualifying ranks and proves the identity for their globally largest member. Attainment of both the suffix minimum and every positive largest crossing proves, including equality at the minimum,
$$
R(X,z)\ge r\quad\Longleftrightarrow\quad
\text{some }t\in[r,1)\text{ qualifies}
\quad\Longleftrightarrow\quad z\ge M_X(r).
$$
Rational $r$ in this identity prove measurability of $R$, and then of $D$. Conditioning on $X$ gives $S(M_X(r))$. In fact $R<1$ for every finite $z$ on the valid event, so rank one has conditional probability zero. The value $f_X(1)=\int\ell\,d\pi$ is its continuous endpoint convention, obtained by bounded convergence, and is not an assertion of positive mass at rank one.

### 2. Microscopic ranks and finite identification

It is useful to integrate one auxiliary private normal in the population as well. Let $\gamma$ denote standard normal probability measure and set
$$
p(x,w)=S(A_X(x)+c_s(v)w+\sigma z),\qquad w\sim N(0,1).
$$
At a positive actual rank $R\le t$, every rejected pair $(x,w)$ has $p(x,w)\le qR\le qt$ and $1/R\le q/p(x,w)$. Hence, pointwise in $X,z$,
$$
D\mathbf1_{\{0<R\le t\}}
\le q\int\!\int \ell\,p(x,w)^{-1}\mathbf1_{\{p(x,w)\le qt\}}\,d\gamma(w)d\pi(x).
$$
The left side is also at most one. Conditional on $Z=z$, integrating $X,w$ gives residual variance
$$
\tau_s^2\|v\|^2+c_s(v)^2=\tau^2
$$
for every fixed parameter. If $\ell=1$, its mean is at most zero, so its conditional p-value distribution function is at most $F_z$. The function $p\mapsto p^{-1}\mathbf1_{\{p\le qt\}}$ is nonnegative and decreasing. Apply this stochastic comparison first to its bounded truncations and then use monotone convergence. Taking conditional expectation and the bound by one proves the requested $B_{q,\sigma}(t)$ estimate. The same argument with a finite empirical average proves it for each finite model, including terminal rank one when $t=1$. Finite BH has exact self-consistency: at its positive largest rank $k/n$, the count below $qk/n$ is exactly $k$, since a greater count would make that greater grid rank qualify.

The scalar assertion $\int_{(0,b]}u^{-1}dF_z(u)<\infty$ for every $b<1,z\in\mathbb R$ is available from the approved continuity dependency. Its use here concerns precisely the same scalar $F_z$, after the enlarged class's marginal variance and mean comparison have just been checked. Its shrinking-interval integral tends to zero. Bounded convergence after taking the minimum with one proves $B_{q,\sigma}(t)\to0$. If $q$ lies in a compact interval with upper endpoint $q_1<1/2$, then
$$
B_{q,\sigma}(t)\le
\mathbb E_Z\min\left\{1,q_1\int_{(0,q_1t]}u^{-1}dF_Z(u)\right\}\longrightarrow0.
$$
This establishes the required local uniformity, independent of law, dimension, and private smoothing.

Now draw iid $x_i\sim\pi$ and independent $\zeta_i$, independently of $X,Z$. Conditional on a valid $X$, the residual scores $Y_i=A_X(x_i)+c_s(v_i)\zeta_i$ are iid with continuous upper tail $H_X$, and their tagged tails have mean $V_X$. Their total and true empirical upper tails converge uniformly almost surely. To see this directly, choose finitely many score endpoints for which consecutive $H_X$ tail masses, including the two exterior tails, are at most a prescribed $\varepsilon$. The strong law applies at these endpoints to both total and tagged counts. Monotonicity brackets every other threshold between consecutive endpoints, with tagged increments bounded by the corresponding total increments. The eventual supremum errors are at most $2\varepsilon$; a sequence $\varepsilon\downarrow0$ proves the assertion. The empirical conditional tail errors do not depend on $Z$.

Here is the rank transfer used to handle competing crossings. For two total residual tails with supremum distance at most $\gamma$, a qualifying rank $r\ge d>0$ of either law at $z$ gives count at least $r-\gamma$ for the other at the same score threshold. Put
$$
L_{q,d}=\sup_{d/2\le r\le1}|u_q'(r)|,\qquad
h_\gamma=L_{q,d}\gamma/\sigma,\qquad 0<\gamma<d/2.
$$
Since $u_q(r-\gamma)-\sigma(z+h_\gamma)\le u_q(r)-\sigma z$, the other law qualifies at $r-\gamma,z+h_\gamma$. This applies in both directions. For empirical tails the continuous-rank supremum equals the grid BH rank: a qualifying $r$ with count $k/n\ge r$ makes $k/n$ qualify, and the reverse inclusion is immediate. Thus the transfer includes finite grid endpoints and ties.

The population rank is nondecreasing in $z$, and therefore has at most countably many discontinuities. At its continuity points, the two transfers, first with fixed $d$ and then $d\downarrow0$, show $\rho_n(X,z)\to R(X,z)$. For example $\rho_n\ge d$ implies $\rho_n\le R(X,z+h_\gamma)+\gamma$; the reverse transfer gives the lower bound wherever $R(X,z-h_\gamma)\ge d$. When $R=0$ the upper bound followed by $d\downarrow0$ suffices. Conditional Gaussian $Z$ avoids every discontinuity. If $R>0$, it is below one, and empirical self-consistency and uniform tagged-tail convergence give
$$
D_n=\frac{V_{n,X}(u_q(\rho_n)-\sigma Z)}{\rho_n}
\longrightarrow \frac{V_X(u_q(R)-\sigma Z)}R=f_X(R).
$$
Finite terminal rank one is allowed in this display; for large $n$ convergence to $R<1$ places the ranks away from that endpoint. The cutoff payoff converges even when $R=0$, because eventually $\rho_n\le a$ there. Bounded convergence proves convergence of expected normalized ranks and cutoff payoffs, with parameter sampling included in the expectation.

For the full FDP, on $\{R>d\}$ use the preceding bounded convergence. On $\{R\le d\}$, the part of $D_n$ with $\rho_n\le2d$ has expectation at most $B_{q,\sigma}(2d)$, and $\mathbb P\{\rho_n>2d,R\le d\}\to0$ by rank convergence. The population contribution with $0<R\le d$ is at most $B_{q,\sigma}(d)$. Letting $d\downarrow0$ proves convergence in $L^1$ of the full FDP under this sampling construction. These statements average over the iid parameters; deterministic finite recovery with moment control is proved separately below.

### 3. The cutoff array completion and its maxima

Let $\mathsf S_s$ denote private smoothing of an array law. On each finite matrix it is $C\mapsto\alpha C+(1-\alpha)I$, where $\alpha=1-s^2/\tau^2\in(0,1)$. It preserves positive semidefiniteness, diagonal one, exchangeability, and marked means and moments. It is a continuous map on the product array space, so its pushforward on laws is continuous for finite-subarray weak convergence. The approved array compactification makes each moment cap $\mathcal K_C=\{P:M_2(P)\le C\}$ compact. Thus $\mathsf S_s\mathcal K_C$ is compact and closed in the Hausdorff law space. These statements also hold jointly in $s$ on a compact admissible interval, with $s=0$ allowed for value comparisons.

We establish the cutoff completion rather than applying the uncut completion to a changed payoff without justification. Apply the approved simultaneous rank/FDP compression to every smoothed finite covariance, realized by a finite Gram matrix if necessary. Set $c_a=\max\{1,\|\chi_a'\|_\infty\}$. The elementary inequality
$$
|\chi_a(r)d-\chi_a(r')d'|
\le |d-d'|+\|\chi_a'\|_\infty|r-r'|
$$
gives cutoff compression error at most $c_a e_m(q,\sigma)$. For an exchangeable $n$-array sample $m$ indices with replacement. On the event they are distinct, their conditional Gaussian submodel has exactly the smoothed $m$-array law. Couple to a uniform sample without replacement; the failure probability is at most $m(m-1)/(2n)$. For repeated indices the sampled original score copies its private normal, whereas an independently generated smoothed $m$-array need not do so; the coupling uses equality only on the distinct-index event. Consequently, for $n\ge m$,
$$
|\mathcal F_n^a(P;q,\sigma,s)-\mathcal F_m^a(P;q,\sigma,s)|
\le c_a e_m(q,\sigma)+\frac{m(m-1)}{2n}.
$$
Comparing two large indices through a fixed $m$ proves a uniform Cauchy property over $P$, locally uniformly in $q$. Passing $n\to\infty$ also bounds the error of the $m$th expectation by $c_a e_m$. Without the cutoff the same proof gives uniform error $e_m$ for the full expectation.

For completeness these limits are jointly continuous in all admissible arguments $P,q,\sigma,s$. At finite size use the continuous positive semidefinite square root of the observation covariance and the same standard Gaussian vector for a convergent sequence of parameters. Outside the finite union of sets
$$
S(T_i)=qk/n\quad(1\le i,k\le n),
$$
all threshold comparisons, and hence rank and tagged FDP, are eventually unchanged. Each set is null because the corresponding score marginal has variance one, even when the joint covariance is singular. Tags are eventually unchanged in the product topology. Bounded convergence proves continuity of the finite conditional Gaussian kernels. It also proves joint continuity of their integrals under weakly convergent array laws: restrict to a compact set carrying arbitrarily large mass, use uniform continuity there, and bound the complement by the uniform kernel bound. To obtain locally uniform completion when $\sigma$ varies, choose a fixed $\sigma_0>0$ smaller than every $\sigma$ in a neighborhood. A covariance with common loading $\sigma$ can be written with common loading $\sigma_0$ and residual matrix
$$
\widetilde C=\frac{(1-\sigma^2)C^{(s)}+(\sigma^2-\sigma_0^2)\mathbf1\mathbf1^{\mathsf T}}{1-\sigma_0^2}.
$$
This is positive semidefinite with diagonal one. The compression bound at the fixed $\sigma_0$ is therefore uniform in that neighborhood, and locally uniform in $q$ by its stated conclusion. Uniform limits of the finite continuous expectations give the desired joint continuity, for both full and cutoff payoffs. All integrations are outer expectations of conditional Gaussian values.

For fixed level, $0\le\mathcal F^a\le1$. The law with all means zero and all tags false has payoff and moment zero, so the objective supremum is at least zero. A maximizing sequence has $\eta M_2\le1+o(1)$ and lies eventually in a fixed compact moment cap. The functional $\mathcal F^a-\eta M_2$ is upper semicontinuous there by continuity of the first term and lower semicontinuity of $M_2$. It attains its supremum. Any maximizer has $M_2\le1/\eta$.

For normalized levels, apply the approved array logarithmic bound to $\mathsf S_sP$ and dominate the cutoff payoff by the full payoff:
$$
\frac{\mathcal F^a(P;q,\sigma,s)}{qS^{-1}(q)}
\le C_\sigma\frac{1+\log(1/q)}{S^{-1}(q)}.
$$
As $q\downarrow0$ the right side is $O_\sigma(\sqrt{\log(1/q)})$, so subtracting $\delta\log(1/q)$ tends uniformly to $-\infty$, even before subtracting the moment penalty. The zero-moment all-false competitor at $q_{\max}$ supplies the finite baseline $-\delta\log(1/q_{\max})$. Hence all maximizing levels can be restricted to $[q_0,q_{\max}]$ for some $q_0>0$. On this interval $1/(qS^{-1}(q))$ is bounded, so the same baseline confines moments to a fixed cap. Joint upper semicontinuity on that compact set proves finiteness and attainment. These moment and level restrictions depend only on $\sigma,\eta,\delta$ and a fixed level interval, and can be chosen independently of $s,a$.

We now use the marked directing representation of the approved array dependency, with its verified source gate; we do not invoke a new representation theorem. Conditional on its directing probability $\mu$, parameters are iid, off-diagonal correlations are $\langle v_i,v_j\rangle$, diagonal entries are one, and $M_2(P)=\mathbb E\int\theta^2d\mu$. Smoothing gives residual off-diagonal covariance $\tau_s^2\langle v_i,v_j\rangle$ and diagonal residual variance $\tau^2$, exactly the conditional kernel representation in part 1. Part 2 identifies the component limit with $\mathcal F^a(\mu;q,\sigma,s)$. At finite size, disintegration is literal conditioning; bounded convergence then gives
$$
\mathcal F^a(P;q,\sigma,s)=\mathbb E_\mu\mathcal F^a(\mu;q,\sigma,s).
$$
At a finite-moment maximizing array law the moment identity gives finite $M_2(\mu)$ almost surely. Every such deterministic $\mu$ itself generates a lawful array competitor. Thus its fixed-level objective, or its normalized objective at the maximizing level, is at most the global maximum. Their average equals that maximum, by the displayed affinity and the moment identity, so almost every component has the maximum value. Select one such deterministic component. Retagging every false-tagged zero as true preserves its total score distribution, actual ranks, and moment, and increases the cutoff true numerator. The resulting lawful canonical directing law is also a maximum. No support restriction, finite-support assertion, or equality with a separately fixed finite private-noise class has been used.

### 4. Fixed-rank differentiation

Fix a bounded lawful velocity $b$ and suppress $X$. On the parameter-private-noise probability space the residual score changes from $Y$ to $Y+\epsilon b(x)$. Thus
$$
H(t+\epsilon K)\le H_\epsilon(t)\le H(t-\epsilon K),\qquad
|Q_\epsilon(r)-Q(r)|\le\epsilon K
$$
for all $0<r<1$. At fixed $t$, differentiating the Gaussian tails gives $\dot H(t)=h_b(t)$ and $\dot V(t)=h_{0b}(t)$. The Gaussian density derivative has a uniform supremum bound at standard deviations at least $s$; bounded $b$ therefore makes these first-order expansions uniform on compact score intervals. On each compact rank interval the quantiles lie in a compact score interval and $h$ has a positive minimum. The preceding displacement bound and the quantile equation imply, uniformly there,
$$
0=H_\epsilon(Q_\epsilon(r))-H(Q(r))
=-h(Q(r))(Q_\epsilon(r)-Q(r))+\epsilon h_b(Q(r))+o(\epsilon).
$$
This proves $\dot Q=h_b/h$. Applying the same expansion to $V_\epsilon(Q_\epsilon(r))$ gives
$$
\dot v(r)=h_{0b}(Q(r))-h_0(Q(r))\frac{h_b(Q(r))}{h(Q(r))},\qquad
\dot f(r)=\dot v(r)/r.
$$
The formulas do not require $b$ to be a function recoverable from its perturbed image; they follow by integrating against the original law and its fixed velocity.

The original and perturbed true tails have score Lipschitz constants at most $1/(s\sqrt{2\pi})$. Their difference at any fixed score is at most $\epsilon K/(s\sqrt{2\pi})$. Applying these two facts at $Q_\epsilon,Q$ gives
$$
|v_\epsilon(r)-v(r)|\le\frac{2\epsilon K}{s\sqrt{2\pi}},\qquad
|f_\epsilon(r)-f(r)|\le\frac{2\epsilon K}{r s\sqrt{2\pi}}.
$$
Ordinary rank differentiation uses $Q'=-1/h(Q)$ and yields
$$
v'(r)=h_0(Q(r))/h(Q(r))\in[0,1],\qquad
f'(r)=\frac{h_0(Q(r))/h(Q(r))-f(r)}r,
$$
so $|f'(r)|\le1/r$. All these functions and parameter derivatives are continuous at interior ranks. Since $|h_b|\le Kh$ and $|h_{0b}|\le Kh_0$, one has $|\dot v|\le2K h_0(Q)\le2K h(Q)$. Dominated convergence gives $h(t)\to0$ as $t\to-\infty$. Consequently $\dot f(r)\to0$ at rank one; this agrees with the unchanged total true mass and justifies $\dot f(1)=0$. Below the cutoff we define the weighted derivative to be zero, so no rank-zero ratio is evaluated.

### 5. All-minima envelopes and the signed derivative

For $q_\epsilon=q(1+\epsilon\lambda)$, inverse differentiation gives
$$
\left.\frac{d}{d\epsilon}u_{q_\epsilon}(t)\right|_{0+}
=-\lambda\frac{qt}{\phi(u_q(t))}=-\lambda m(u_q(t)).
$$
The representation $m(u)=\int_0^\infty e^{-uy-y^2/2}dy$ shows that $m$ is positive and decreasing. Choose $q_1<1/2$ above all levels in a sufficiently small perturbation interval, also with $|1+\epsilon\lambda|\ge1/2$. Throughout that interval,
$$
\left|\frac{d}{d\epsilon}u_{q_\epsilon}(t)\right|
\le2|\lambda|m(S^{-1}(q_1))\quad(0<t\le1).
$$
Combining with the quantile displacement bound gives, with the explicit finite constant
$$
C=\frac{K+2|\lambda|m(S^{-1}(q_1))}{\sigma},\qquad
\sup_{0<t<1}|B_\epsilon(t)-B(t)|\le\epsilon C,
\qquad |M_\epsilon(r)-M(r)|\le\epsilon C.
$$
For a fixed $r$, every perturbed suffix minimizer satisfies $B(t)\le M(r)+2\epsilon C$. Divergence of $B$ at one confines all such minimizers, for small $\epsilon$, to one compact subset of $[r,1)$. On that set part 4 and inverse level differentiation give a uniform first-order expansion of $B_\epsilon$. Its derivative is the continuous function
$$
d(t)=\frac{-\lambda m(u_q(t))-\dot Q(t)}{\sigma}.
$$
Testing at each unperturbed minimizer gives $\limsup (M_\epsilon-M)/\epsilon\le\min_{\mathcal A(r)}d$. For any sequence of perturbed minimizers, compactness supplies a subsequential limit $t_*$. Uniform convergence of $B_\epsilon$ shows $B(t_*)=M(r)$; also
$$
\frac{M_\epsilon(r)-M(r)}\epsilon
=\frac{B(t_\epsilon)-M(r)}\epsilon+d(t_\epsilon)+o(1)
\ge d(t_\epsilon)+o(1).
$$
Taking the lower limit proves the reverse inequality. Thus $\dot M(r)=\min_{t\in\mathcal A(r)}d(t)$ with all active points retained. Its measurability follows from the measurable difference quotients. In particular
$$
|\dot M(r)|\le\frac{K+|\lambda|m(S^{-1}(q))}{\sigma}.
$$
Neither uniqueness nor nondegeneracy of a minimum was used.

Put $g=\chi_a f$, extend it by zero on $[0,a]$, and put $g_\epsilon=\chi_a f_\epsilon$ with the same extension. Since $0\le f\le1$, $\chi_a'\ge0$, and $|f'|\le1/r$,
$$
\int_a^1|g'(r)|dr\le\int_a^1\chi_a'(r)dr+\int_a^1\frac{dr}{r}
\le1+\log(1/a).
$$
The continuous endpoint limit of $f$ at one makes $g$ absolutely continuous on $[0,1]$: apply the fundamental theorem on compact interior intervals and pass to the endpoint using this integrable derivative bound. Therefore, by Fubini and the actual-rank survival identity,
$$
\mathbb E_Zg(R)=\int_a^1g'(r)\mathbb P_Z(R\ge r\mid X)dr
=\int_a^1g'(r)S(M(r))dr.
$$
The same identity holds for any perturbed rank on the left with $g$ kept fixed and $M_\epsilon$ on the right. The distinction between $R\ge r$ and $R>r$ does not affect the Lebesgue integral: for each fixed rank it changes one integration point. This also justifies boundary conventions without assuming ranks have atomless laws.

Separate the two payoff changes exactly:
$$
g_\epsilon(R_\epsilon)-g(R)
=(g_\epsilon-g)(R_\epsilon)+g(R_\epsilon)-g(R).
$$
The uniform $B$ bound implies the pointwise rank sandwich
$$
R(X,z-\epsilon C)\le R_\epsilon(X,z)\le R(X,z+\epsilon C).
$$
Thus $R_\epsilon\to R$ outside the countable discontinuity set of the monotone rank map. For almost every $z$ with $a<R<1$, the locally uniform fixed-rank expansion gives
$$
\frac{(g_\epsilon-g)(R_\epsilon)}\epsilon\longrightarrow\chi_a(R)\dot f(R).
$$
If $R<a$ the term eventually vanishes. If $R=a$, its absolute value is bounded by $\chi_a(R_\epsilon)2K/(a s\sqrt{2\pi})$ when $R_\epsilon>a$, and this tends to zero. Rank one is absent for finite $z$. The uniform bound for this whole term is $2K/(a s\sqrt{2\pi})$, so conditional dominated convergence applies.

For the second change the survival identity gives
$$
\frac{\mathbb E_Z[g(R_\epsilon)-g(R)]}{\epsilon}
=\int_a^1g'(r)\frac{S(M_\epsilon(r))-S(M(r))}{\epsilon}dr.
$$
The integrand quotient is bounded by $C/\sqrt{2\pi}$, uniformly in $X,r,\epsilon$. The envelope derivative and dominated convergence give its limit $-\phi(M(r))\dot M(r)$. Combining the two limits proves exactly
$$
\dot{\mathcal F}^{a}
=\mathbb E_X\left[
\mathbb E_Z\{\chi_a(R)\dot f(R)\}
-\int_a^1(\chi_a f)'(r)\phi(M(r))\dot M(r)dr
\right].
$$
Before taking $X$ expectation, the conditional difference quotient is bounded in absolute value by
$$
\frac{2K}{a s\sqrt{2\pi}}+\frac{C[1+\log(1/a)]}{\sqrt{2\pi}}.
$$
For mean transport alone $C=K/\sigma$, giving the stated constant. For finite $\lambda$ the displayed compact-level $C$ is an explicit difference-quotient bound, while the sharper bound on $|\dot M|$ above applies to the limiting derivative. These deterministic bounds justify all averaging over $X$. The integral uses only $a<r<1$ and no undefined endpoint product. Its signed integrand has not been replaced by its absolute value; absolute values above serve only to justify convergence.

The degenerate cases provide useful direct checks. With zero true mass $f=\dot f=0$, so every term vanishes. With all mass true, $f=1$, $\dot f=0$, and the expression is exactly the derivative of $\mathbb E\chi_a(R)$. For a constant lawful mean translation $b=k$, one has $h_b=kh$, $h_{0b}=kh_0$, $\dot f=0$, and, at fixed level, $\dot M=-k/\sigma$; the formula equals the survival derivative for the exact common shift $z\mapsto z+\epsilon k/\sigma$.

For the specified antipodal check, take true center $a_0=\tau_s x$, false center $a_1=A-\tau_s x$, and $x>A/(2\tau_s)$, so $a_0>a_1$ and both private standard deviations are $s$. The ratio of the two positive score densities at score $y$ is
$$
\frac{\phi((y-a_0)/s)}{\phi((y-a_1)/s)}
=\exp\left\{\frac{(a_0-a_1)y}{s^2}+\frac{a_1^2-a_0^2}{2s^2}\right\},
$$
which is strictly increasing. The true posterior density fraction $p_0(y)$, with the equal prior weights included, is therefore strictly increasing. At any finite threshold $t$, the upper-tail true fraction is the conditional average of $p_0(Y)$ over $Y\ge t$, strictly greater than $p_0(t)$ since both densities are positive. Thus $f(r)>h_0(Q(r))/h(Q(r))$ and $f'(r)<0$ for every $0<r<1$ on this event. For $r>2a$ the derivative $(\chi_af)'$ is strictly negative. The event has positive Gaussian probability. The preceding deterministic domination bounds already guarantee integrability, for either lawful false-mean direction $+1$ or $-1$ (with $\epsilon<A$), and for finite level velocities. At a tied active set the two opposite mean directions give their respective minima of $-\dot Q/\sigma$; these generally need not be negatives of each other. All arguments used integrated kernels and the variance lower bound, so they cover non-atomic laws and unequal private variances as well.

### 6. Exact extremal inequalities

At a selected deterministic fixed-level maximum, the pushed-forward law $\pi_\epsilon$ is a lawful competitor for every sufficiently small positive $\epsilon$. Its moment change is exactly
$$
M_2(\pi_\epsilon)-M_2(\pi)
=2\epsilon\int\theta b\,d\pi+\epsilon^2\int b^2d\pi.
$$
Both integrals are finite because $b$ is bounded and $\theta$ has finite second moment. Subtract the two objective values, divide their nonpositive difference by $\epsilon$, and apply part 5. This gives $\dot{\mathcal F}^a-2\eta\int\theta b\,d\pi\le0$.

At a normalized maximum $(\pi,q)$ the same exact comparison is made at its actual perturbed level $q_\epsilon$. With $U=S^{-1}(q)$,
$$
\left.\frac{d}{d\epsilon}(q_\epsilon S^{-1}(q_\epsilon))\right|_{0+}
=\lambda qU\left(1-\frac{m(U)}U\right),\qquad
\left.\frac{d}{d\epsilon}[-\delta\log(1/q_\epsilon)]\right|_{0+}=\delta\lambda.
$$
The quotient rule, part 5, and the exact moment identity yield the claimed normalized inequality with every displayed sign. At $q=q_{\max}$ only $\lambda\le0$ stays in the allowed interval. Lawfulness of the mean direction is required for the whole small positive interval, as stipulated. These are one-sided inequalities for each exact competitor; the active-minimum derivative has not been treated as a linear functional of $b$.

### 7. Deterministic finite endpoint recovery

Fix a deterministic law $\pi$ and its level, noise, and cutoff parameters. Let $K_m(x_1,\ldots,x_m)$ and $K_m^a(x_1,\ldots,x_m)$ be the conditional Gaussian expected full and cutoff payoffs for these $m$ parameters, with fresh independent private noises even at repeated parameter values. They are bounded continuous functions on the strong marked parameter product space: their means and covariance entries depend continuously on $\theta_i,v_i$, and the finite Gaussian threshold-null argument in part 3 applies. Discrete tags make their numerator continuous under the same convergence.

Choose one infinite iid parameter sample $(x_i)$. Almost surely its empirical measures $\nu_N$ converge weakly to $\pi$ and their second moments converge to $M_2(\pi)$. Here is an elementary way to ensure the simultaneous weak convergence being used. The parameter space is a closed subset of a separable complete metric product, hence admits tight probability laws and countable dense sets. Choose compact sets with $\pi$ mass tending to one. Apply the strong law to their indicators, to $\theta^2$, and to a countable family of bounded Lipschitz functions formed from rational values and distances to a countable dense set. On each compact set finite nets make this family uniformly approximate every bounded Lipschitz function there. The strong law and the small complement masses then give convergence of integrals of every bounded Lipschitz function, hence weak convergence. Intersect these countably many probability-one events. Product weak convergence now implies, for each fixed $m$,
$$
\int K_m\,d\nu_N^{\otimes m}\to\int K_m\,d\pi^{\otimes m},\qquad
\int K_m^a\,d\nu_N^{\otimes m}\to\int K_m^a\,d\pi^{\otimes m}.
$$

Let $F_N(x_{1:N})$ and $F_N^a(x_{1:N})$ be the conditional expected whole-$N$ payoffs with independent private noises. Compression compares this whole model to a sampled-with-replacement submodel of its original scores. Such sampled scores copy the original private normal when indices repeat. On the other hand, the kernel integral against $\nu_N^{\otimes m}$ uses fresh private normals at every occurrence. Couple them on the no-collision event; their expected payoffs differ by at most $m(m-1)/(2N)$. Thus, deterministically for every parameter list,
$$
\left|F_N-\int K_m\,d\nu_N^{\otimes m}\right|
\le e_m(q,\sigma)+\frac{m(m-1)}{2N},
$$
and the cutoff version has $c_a e_m$ in place of $e_m$. On the chosen sample path let $N\to\infty$ at fixed $m$. Part 2 identifies $\int K_m\,d\pi^{\otimes m}\to\mathcal F(\pi;q,\sigma,s)$ and its cutoff analogue as $m\to\infty$. Sending $m\to\infty$ proves that $F_N,F_N^a$ converge to the two population endpoint values on this same deterministic parameter sample path, together with the empirical second mean moment. This proves simultaneous recovery rather than extracting it from a penalized supremum identity.

At any fixed finite $N$, move every false-tagged zero mean to the same sufficiently small $d>0$, leaving all other means and tags fixed. Every resulting label is canonical. Finite Gaussian continuity makes both expected payoffs converge to the unshifted tagged ones as $d\downarrow0$. The empirical second-moment increment is at most $d^2$, since only zeros were moved. Choose first $N$ and then $d$ so that all three endpoint errors are below any specified tolerance. Every covariance still has diagonal one and the same independent private noise. Apply this construction after fixing each lawful perturbed endpoint and its actual level $q_\epsilon$. Choosing each of its three errors at most $\epsilon^2$ makes them $o(\epsilon)$. No exchange of this choice with differentiation is asserted; the argument concerns deterministic directing endpoints, not arbitrary outer mixtures.

### 8. Removing regularizers in value

Write $\mathcal F(P;q,\sigma,0)$ for the original full array completion. On a compact moment cap and compact level interval, approximate both $\mathcal F(P;q,\sigma,s)$ and $\mathcal F(P;q,\sigma,0)$ uniformly by their fixed-size full expectations. The error is at most the same $e_m$ from part 3, uniformly in $s$. For that fixed size the expectation is jointly continuous on the compact set of $P$, levels, and a compact interval $0\le s\le s_0<\tau$; at $s=0$ finite Gaussian covariance continuity still holds, including singular matrices. Uniform continuity on this compact set therefore gives
$$
\sup_{P\in\mathcal K_C,\ q\in K}
|\mathcal F(P;q,\sigma,s)-\mathcal F(P;q,\sigma,0)|\longrightarrow0.
$$
For each finite array, $1-\chi_a(\rho_n)$ vanishes at ranks above $2a$, so the microscopic bound yields
$$
0\le\mathcal F_n(P;q,\sigma,s)-\mathcal F_n^a(P;q,\sigma,s)
\le B_{q,\sigma}(2a).
$$
Pass to the two finite-size limits to obtain the same inequality for the completed values. Part 2 makes the right side vanish locally uniformly in $q$, independently of $P,s$. Thus $\mathcal F^a(P;q,\sigma,s)$ converges to the original full completion uniformly on each compact moment cap and compact level interval as $s,a\downarrow0$, with no relation required between the rates. This argument avoids any dependence on $\|\chi_a'\|_\infty$ when removing the cutoff.

The moment restriction $M_2\le1/\eta$ at fixed level and the moment/level restrictions for normalized objectives in part 3 hold uniformly in both regularizers, using the same zero-moment baseline and the same smoothed-array logarithmic bound. They also hold for the original unregularized objectives by the approved array dependency. Restrict all the corresponding maxima to these common compact sets. The just-proved uniform convergence of the payoffs, and boundedness of $1/(qS^{-1}(q))$ on the coercive level interval, imply uniform convergence of the respective penalized objectives there. The difference of their maxima is bounded by their uniform difference. This proves both asserted limits to $A_{\eta,\sigma}(q)$ and $L_{\eta,\delta,\sigma}$.

All derivative calculations above kept $s,a>0$ fixed. This last argument and the deterministic finite recovery concern values only, and do not move any derivative through private smoothing, a cutoff limit, atomization, or covariance limits.
