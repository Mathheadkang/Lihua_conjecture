---
type: plan
title: >-
  Prove isotropic population BH by signed feasibility and squared-excess
  transport
status: succeeded
target_asset: spherical_isotropic_population_bh_bound
inspired_by:
  - idea_512caaf7c8bd
  - idea_6b241a577263
  - idea_e189af0f66e7
adapts: []
proof_digest: 91e5d61962d34de1c15cfffb33864ed8b21af6311ab10bf3251e9d49b1b0b355
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
dependency_digests:
  spherical_isotropic_directional_population: 2cf09d24200523b06e3ec5c57ddc0f185068f8e5df130b2cae9229e6062e3b39
  spherical_population_bh_false_discovery_rate: 57e21b1b6e612abe8b86885379a7c0b3e90cfce5d585209335bd4dbb6cda82a9
verified_proof_digest: 91e5d61962d34de1c15cfffb33864ed8b21af6311ab10bf3251e9d49b1b0b355
---

## Goal

Target: [Uniform dimension bound for isotropic spherical population BH](../assets/spherical_isotropic_population_bh_bound.md).

Prove the target's frozen Statement, without changing it or either approved definition. In particular, for the actual isotropic, nonnegative-absolute-mean, two-sided population with arbitrary Borel probability law $W$ on $[0,\infty)$, $d\ge4$, $q\in(0,1)$ and $u=Q^{-1}(q/2)\ge104$, prove
$$
\operatorname{FDR}_{\mathrm{pop}}(q;W,d)
\le q\pi_0\{2+4M_d(1+u^{-2})\log(3u)\}+e^{-2u^2}.
$$
The proof below is allowed to establish a stronger intermediate estimate, but its deliverable remains this exact target and its stated uniform $O(q\log u)=o(qu)$ consequence. The draft ideas suggest calculations only: none of their claims, candidate audits, or search outcomes is a premise. No nonisotropic, one-sided, or finite-array extension is part of this plan.

## Plan

1. [x] **Freeze notation, scope, and elementary cases.** Use exactly the approved $W$, $\pi_0=W(\{0\})$, $H_r$, $F_r$, and smallest finite contact $x_r$, with $x_r=\infty$ for no contact. Fix $d,q,W$ throughout the derivation; uniform constants will subsequently allow $d,W$ to vary with $q$. Put
   $$
   c_d=\frac{\Gamma(d/2)}{\sqrt\pi\,\Gamma((d-1)/2)},\quad
   a=\max\{u,52\sqrt d/u\},\quad b=\sqrt d+2u,
   \quad \ell(r)=r/(2\sqrt d).
   $$
   Reserve $D$ for $r\partial_rF_r(x)$, $B$ for $-\partial_xF_r(x)$, and $\Lambda(r)$ for the gradient coefficient; do not use $F_r$ ambiguously for a radial derivative. If $\pi_0=0$, FDP and FDR are zero. Otherwise verify from the contact identity that finite-contact FDP equals $q\pi_0H_r(x_r)/Q(x_r)$ and lies in $[0,1]$, with value zero at no contact. At $x=u$, $F_r(u)<1$ for $\pi_0>0$ and finite $r$, because $2H_r(u)<1$, so no positive-null-mass endpoint contact is missed.

2. [x] **Reprove the isotropic density and all numerical sphere inputs.** Derive
   $$
   g_r(t)=\frac{c_d}{r}\left(1-\frac{t^2}{r^2}\right)^{(d-3)/2}\mathbf1_{\{|t|<r\}},
   \qquad H_r(t)=\int_t^\infty g_r(z)\,dz,
   $$
   using a latitude integral and its beta normalization. The zero-extended $g_r$ is continuous at both endpoints for $d\ge4$. Maximize $|t|g_r(t)$ explicitly to obtain the target's exact $M_d$; the maximum occurs at $|t|/r=(d-2)^{-1/2}$. Derive the gamma Cauchy--Schwarz inequality
   $$
   \Gamma(d/2)^2\le\Gamma((d-1)/2)\Gamma((d+1)/2)
   $$
   from its defining integral, giving $c_d\le\sqrt{(d-1)/(2\pi)}\le\sqrt d$ and $M_d\le\sqrt{(d-1)/(2\pi(d-2))}<1$. For a uniform sphere coordinate $U_1$, derive $\mathbb EU_1^2=1/d$ and $\mathbb EU_1^4=3/[d(d+2)]$ from rotational invariance and $\sum U_i^2=1$. Apply Cauchy--Schwarz to $Y=dU_1^2$, with $\mathbb EY=1$, $\mathbb EY^2\le3$, to prove $\mathbb P(Y\ge1/4)\ge3/16$; symmetry gives
   $$
   H_r(\ell(r))\ge3/32.
   $$
   **Stop gate:** if any sphere constant or endpoint assertion fails, fail the plan rather than insert an additional lemma assumption.

3. [x] **Prove regularity and measurable selection for arbitrary $W$.** Write the component rejection tail as
   $$
   f_\mu(r,x)=H_r(x-\mu)+H_r(x+\mu).
   $$
   Derive the actual folded derivatives
   $$
   b_\mu=g_r(x-\mu)+g_r(x+\mu),\qquad
   d_\mu=(x-\mu)g_r(x-\mu)+(x+\mu)g_r(x+\mu),
   $$
   and $B=\int b_\mu\,dW=-\partial_xF$, $D=\int d_\mu\,dW=r\partial_rF$. On compact positive-$r$ rectangles, bound $b_\mu\le2c_d/r$ and $|d_\mu|\le2M_d$, independently of $\mu$. Justify differentiation and continuous derivatives after $W$ integration by these uniform bounds and the zero-extended density, without any support or moment assumption. For every finite $t\ge u$, prove
   $$
   \{r:x_r\le t\}=\left\{r:\max_{u\le x\le t}[F_r(x)-2Q(x)/q]\ge0\right\}.
   $$
   The compact maximum is continuous in $r$, so this proves extended Borel measurability of $x_r$ and then of FDP. Reprove minimum attainment and the contact identity by continuity; no finite contact has positive FDP when $x_r\ge r$.

4. [x] **Reprove the all-signed gradient budget in the folded isotropic model.** Define
   $$
   I_- =\int(d_\mu)_-\,dW,\qquad I_+=\int(d_\mu)_+\,dW,
   \qquad D=I_+-I_-.
   $$
   If $d_\mu<0$, then $\mu>x$, its rejection tail is at least $1/2$, and $(d_\mu)_-\le M_d$ because only the $(x-\mu)$ term can be negative. Consequently $I_-\le2M_dF$ and $D\ge-2M_dF$ for every sign of $D$. For $x\ge\ell>0$, split at $\mu\le x-\ell$. On this lower set both coefficients in $d_\mu$ are at least $\ell$, whence its $B$ contribution is at most $I_+/\ell$. On the complementary set $f_\mu\ge H_r(\ell)$ and $b_\mu\le2g_r(0)$. Combine these pointwise facts, retaining both folded boundaries, to prove
   $$
   B\le D/\ell+\Lambda(r)F,\qquad
   \Lambda(r)=2M_d/\ell+2g_r(0)/H_r(\ell).
   $$
   With $\ell=\ell(r)$, step 2 gives $\Lambda(r)\le26\sqrt d/r$. Check $a<b$, $\ell(r)\le u$ on $[a,b]$, and $\Lambda(r)\le u/2$ there, including both cases in the maximum defining $a$. **Stop gate:** this inequality must hold for all $D$; a proof restricted to $D\le0$ does not support the next step.

5. [x] **Construct a global feasible comparison, without differentiating a selected root.** Establish the Mills inequalities directly by integrating the Gaussian density by parts:
   $$
   x<h(x):=\phi(x)/Q(x)\le x+1/x\quad(x>0).
   $$
   For any $a\le r_1\le r_2\le b$ and any finite feasible $x_1\ge u$ at $r_1$, take the explicit finite path
   $$
   X(r)=\{x_1^2+8M_d\log(r/r_1)\}^{1/2},\quad
   X'=4M_d/(rX),\quad
   \beta=(r/\ell)X'=8M_d\sqrt d/(rX)\le2M_d/13<1.
   $$
   While $F_r(X(r))>0$, differentiate $J(r)=\log[qF_r(X(r))/(2Q(X(r)))]$ and use the all-signed budget to obtain
   $$
   J'\ge\frac{D}{rF}(1-\beta)+(h(X)-\Lambda)X'
      \ge-\frac{2M_d}{r}(1-\beta)+\frac X2\frac{4M_d}{rX}
      =\frac{2M_d\beta}{r}>0.
   $$
   Since $F_{r_1}(x_1)>0$, exclude a first zero of $F_r(X(r))$ on the compact path: increasing $J$ and strictly positive finite $Q(X)$ give a positive lower bound up to such a zero, contradicting continuity. Therefore $J\ge J(r_1)\ge0$ throughout. Apply this to $x_1=x_{r_1}$ to prove persistence of finite contacts and the all-pairs estimate
   $$
   x_{r_2}^2-x_{r_1}^2\le8M_d\log(r_2/r_1)
   \qquad(x_{r_1}<\infty).
   $$
   **Stop gate:** feasibility persistence, not merely an almost-everywhere root derivative, must be proved. It covers contact birth, tangency, branch switches, and any disappearance that would otherwise be possible.

6. [x] **Make jump and positive-variation control explicit.** Choose any finite $T>b$ with $T>u$ and set $y(r)=\min\{x_r,T\}$, including $y=T$ at no contact. Check separately $x_{r_1}=\infty$, $x_{r_1}\ge T$, and $x_{r_1}<T$ to prove the same all-pairs inequality for $y^2$. Thus
   $$
   y(r)^2-8M_d\log r\quad\hbox{is nonincreasing on }[a,b].
   $$
   Deduce bounded variation and regulatedness from this exact monotonicity. In particular every upward increment is bounded by $8M_d\Delta\log r$, positive jumps are impossible, and the increment measure of a standard one-sided representative satisfies $d(y^2)\le8M_d\,dr/r$; justify the measure statement from interval increments, rather than an a.e. derivative. Point values at its at most countably many discontinuities do not affect radial integration. The following transport will use the all-pairs inequality directly and remains valid for the actual Borel representative, so no choice at a birth or jump is silently assumed.

7. [x] **Derive the squared-excess radial kernel, including its exact normalization.** Let $Z_1\sim N(0,1)$ and $V=\sum_{j=2}^d Z_j^2\sim\chi^2_{d-1}$ be independent. From polar disintegration prove
   $$
   k(r,x):=f_{\chi_d}(r)H_r(x)/Q(x)
   $$
   is the conditional density of $R$ given $Z_1\ge x$. For $x\ge u$, compute the density of $E_x=Z_1^2-x^2$ conditional on $Z_1\ge x$:
   $$
   p_x(t)=\frac{h(x)e^{-t/2}}{2\sqrt{x^2+t}}\mathbf1_{\{t\ge0\}}
      \le(1+u^{-2})\frac{e^{-t/2}}2\mathbf1_{\{t\ge0\}}.
   $$
   Reprove the gamma-density convolution by a beta integral, so convolution with $V$ turns the right side into $(1+u^{-2})f_{\chi^2_{d+1}}$. The change of variables $r^2=x^2+E_x+V$ then gives
   $$
   k(r,x)\le(1+u^{-2})\,2r\,f_{\chi^2_{d+1}}(r^2-x^2).
   $$
   Extend this chi-square density by zero to nonpositive arguments; check $k=0$ for $r\le x$. No mode bound or unproved conditional-transport lemma is used here.

8. [x] **Prove transport as domination of a Borel pushforward measure.** Since $T>b$, $k(r,x_r)=k(r,y(r))$ on the core, using value zero at $x_r=\infty$. Put $s=r^2$ and
   $$
   \zeta(s)=s-y(\sqrt s)^2,\qquad c=1-4M_d/a^2>0.
   $$
   Step 6 and $\log(s_2/s_1)\le(s_2-s_1)/a^2$ imply
   $$
   \zeta(s_2)-\zeta(s_1)\ge c(s_2-s_1)
   \quad(a^2\le s_1\le s_2\le b^2).
   $$
   Prove directly that for every target interval $I$, its preimage is an interval up to endpoints, of Lebesgue length at most $|I|/c$. Extend through countable disjoint open intervals and outer regularity to every Borel set. Thus the pushforward of $ds$ by $\zeta$ is dominated by $c^{-1}$ times Lebesgue measure, even at jumps or skipped intervals. Integrate the nonnegative, unit-integral density $f_{\chi^2_{d+1}}$ and use step 7 to obtain
   $$
   \int_a^b k(r,x_r)\,dr\le\frac{1+u^{-2}}{1-4M_d/a^2}.
   $$
   **Stop gate:** establish this measure domination with its exact constant. An a.e. change-of-variables calculation without the interval argument is insufficient.

9. [x] **Reprove the lower-radius envelope from the exact Gaussian decomposition.** Let $\nu=d-1$ and $L=a^2-u^2$. Check $0\le L\le d-3=\nu-2$: this is immediate if $a=u$; otherwise $a^2=2704d/u^2\le d/4$ and $d/4\le d-3$ for $d\ge4$. The $\chi^2_\nu$ density increases on $[0,\nu-2]$. For $u<r\le a$ and $u\le x<r$, derive the identity
   $$
   k(r,x)=\frac{2r}{Q(x)}\int_x^r\phi(z)f_{\chi^2_\nu}(r^2-z^2)\,dz
      \le2r f_{\chi^2_\nu}(r^2-u^2).
   $$
   Check the zero cases $r\le u$ and $x\ge r$. It follows that the integrated envelope over all cutoffs, not just smooth selected roots, obeys
   $$
   \int_0^a f_{\chi_d}(r)\sup_{x\ge u}\frac{H_r(x)}{Q(x)}\,dr
      \le\mathbb P(V\le L).
   $$
   If $a=u$, this contribution is zero. If $a>u$, prove $d>u^4/2704\ge4u^2$ and $L\le d/4\le(d-1)/3$. Derive $\mathbb Ee^{-V}=3^{-\nu/2}$ from Gaussian integration; Chernoff then gives
   $$
   \mathbb P(V\le L)\le e^{-\nu(\log3-2/3)/2}
      \le e^{-\nu/5}\le e^{-3u^2/4}.
   $$
   Verify the elementary numerical inequality $\log3-2/3>2/5$ and $\nu\ge15u^2/4$ under the displayed conditions. No density monotonicity is used past its mode.

10. [x] **Bound the upper-radius probability with the exact chi-square Chernoff calculation.** Derive the Gaussian product moment-generating function for $R^2\sim\chi^2_d$ and optimize at $\lambda=(1-d/b^2)/2$. This yields
    $$
    \mathbb P(R>b)\le\exp\{-[b^2-d-d\log(b^2/d)]/2\}\le e^{-2u^2}.
    $$
    For the second inequality write $b=\sqrt d(1+z)$ with $z=2u/\sqrt d$ and use $\log(1+z)\le z$. Multiply only the upper-region probability by the pointwise bound FDP$\le1$; do not assume any threshold regularity beyond the core.

11. [x] **Assemble with the correct null factor and verify every constant.** Lower radii use step 9 times $q\pi_0$, core radii use step 8 times $q\pi_0$, and upper radii use step 10. Thus prove, with no averaging over population indices left outside the actual $F$,
    $$
    \operatorname{FDR}_{\mathrm{pop}}
    \le q\pi_0\left\{e^{-3u^2/4}
       +\frac{1+u^{-2}}{1-4M_d/a^2}\right\}+e^{-2u^2}.
    $$
    For $t=u^{-2}\le104^{-2}$, show $4M_d/a^2\le4t$, $(1+t)/(1-4t)\le1+6t$ (it suffices that $t\le1/24$), and $e^{-3u^2/4}\le u^{-2}$. Consequently the braces are at most $1+7/u^2<2$. Since $M_d>0$ and $\log(3u)>0$, this implies the exact frozen bound with coefficient $2+4M_d(1+u^{-2})\log(3u)$. Preserve this comparison explicitly instead of replacing the asset's Statement by the stronger intermediate estimate. **Stop gate:** if any intermediate constant fails, report the obstruction in this plan; do not weaken or amend the target.

12. [x] **Verify uniform asymptotics and audit the proof's dependency closure.** Use $M_d\le1$, $\pi_0\le1$, and the already proved Mills lower bound for $Q(u)$ to show $e^{-2u^2}=o(q)$ as $q=2Q(u)\downarrow0$. Then the frozen right side is uniformly $O(q\log u)$ and its ratio to $qu$ tends to zero. Check that all derivations apply for every fixed $d\ge4$ and every Borel $W$, with constants independent of $d,W$, so choices $d=d(q)$ and $W=W_q$ are allowed. Recheck factors of two in the folded component, contact identity, null numerator, and conditional kernel. Record explicitly that ten unsuccessful search rounds supply no proof step, and that no assertion about finite Gaussian arrays or nonuniform directions has been made.

## Verification

The proof has three quantitative obligations and one global-selection obligation. The global obligation is the all-signed feasible-path argument in steps 4--6, not a regular-branch derivative assertion. It supplies finite-contact persistence and all-pairs control, including contact births, switches, and the full positive-variation measure. The quantitative obligations are the lower envelope in step 9, core pushforward transport in steps 7--8, and upper chi-square tail in step 10. Steps 1 and 3 make the actual FDP measurable, include no-contact samples, and justify all integrals for arbitrary $W$. Step 11 gives the exact frozen inequality; step 12 gives its exact uniform asymptotic consequence. The execution succeeds only if every stop gate and all twelve checklist items are proved from the approved definitions and elementary calculations spelled out here.

Library checks at plan construction: native searches for spherical/radial/BH first-contact analogues, and for spherical density negative-radial/conditional-chi-square-excess lemmas, returned no matching library results. Accordingly no library result is cited as an undeclared black box and `adapts` is empty. The draft approach nodes are inspirations only; every used calculation is explicitly scheduled for proof.

## Assumed definitions

- [Definition (isotropic spherical directional population)](../definitions/spherical_isotropic_directional_population.md), approved: the product $W\otimes\sigma_{d-1}$ population, exact two-sided folded tail, arbitrary finite nonnegative absolute means, and zero residual variance.
- [Definition (largest spherical population BH threshold and false discovery rate)](../definitions/spherical_population_bh_false_discovery_rate.md), approved: the smallest finite Gaussian cutoff, contact identity, and zero FDP at no contact.

No draft definition, draft theorem, unproved dependency, external transport lemma, or candidate audit verdict is assumed. Standard Gaussian/gamma identities, density estimates, selection regularity, interval-to-Borel measure domination, and every specialized analytic inequality required by the argument are to be derived in the checklist. No dependency change, approval record, target edit, or loop-state transition is authorized by this plan.

## Outcome

All twelve checklist items, in order, are established in the correspondingly numbered parts of the complete proof under `## Proof` of [Uniform dimension bound for isotropic spherical population BH](../assets/spherical_isotropic_population_bh_bound.md). The proof gives the stronger intermediate estimate
$$
\operatorname{FDR}_{\mathrm{pop}}(q;W,d)
\le q\pi_0\left\{e^{-3u^2/4}+\frac{1+u^{-2}}{1-4M_d/a^2}\right\}+e^{-2u^2}
\le q\pi_0(1+7u^{-2})+e^{-2u^2},
$$
and explicitly derives the exact frozen target inequality and its uniform asymptotic consequence from it. The target's Statement, hypotheses and frontmatter are unchanged; neither an approved definition nor any unrelated asset was changed. The target remains draft and awaits independent native verification.

Only the two approved definitions listed above are assumed. The sphere estimates, arbitrary-law regularity and Borel selection, all-signed gradient budget, finite-contact persistence, jump and positive-variation control, normalized squared-excess kernel, interval-to-Borel pushforward domination, lower envelope, and upper Chernoff bound are fully derived in the proof. No draft definition, unproved theorem, search result, or candidate audit is a premise. The original arbitrary finite one-sided and two-sided Gaussian BH conjectures remain unresolved.

Notation review against both approved definitions and the configured `macros.tex` and `notations.tex` found no missing definition relation, undefined symbol, or conflicting notation; both configured TeX files contain only their placeholder comments. Maintenance `validate` reported zero problems. Asset-scoped links preview and application each reported zero files and zero review items, and the final preview was clean. No approval or loop-state transition was performed.

## Verdict

confirmed

Independently checked the frozen statement and all twelve proof parts using only the native verification context pack, the two approved definition statements in that pack, and the proof's displayed calculations. The quantifiers cover every integer d >= 4 and every Borel probability law W on [0,infinity), including atomic and unbounded-support laws; no moment condition is used. The zero-null-mass case, zero-radius null event, infinite/no-contact cutoff, and finite contacts with zero null rejection mass are covered. Attainment, the contact identity, Borel measurability of the actual smallest finite BH contact, and FDP <= 1 are justified.

The signed component bounds give B <= D/ell + Lambda F and D >= -2 M_d F with the correct signs for both positive and negative radial derivatives. The feasible-path derivative estimate is valid with beta < 1 and Lambda <= u/2 on the entire core interval. The first-zero argument establishes persistence of a feasible path before minimality is used, so the resulting all-pairs comparison controls the actual selected smallest contact globally, including births, switches, tangencies, and downward jumps. Truncation at T > b preserves the kernel. The all-pairs comparison gives both the stated signed variation measure bound and the strictly increasing Borel transport zeta; the interval-preimage argument establishes pushforward domination for the actual representative without assuming absolute continuity or relying only on an almost-everywhere derivative.

Differentiation under arbitrary W is justified by uniform component first-derivative bounds on compact positive-radius rectangles; the sphere density has a continuous zero extension for d >= 4. The spherical normalization, M_d bound, lower cap estimate, Gaussian conditional squared-excess density, convolution shape d+1, single-tail normalization Q(x), and Jacobian 2r all check. The lower-radius envelope stays below the chi-square density mode and its Markov bound is uniform in dimension. The upper-radius Chernoff calculation gives precisely exp(-2 u^2). The assembly multiplies the two kernel integrals by exactly q pi_0 and uses FDP <= 1 only for the upper tail.

The numerical inequalities at u >= 104 yield the stronger bound q pi_0 (1 + 7/u^2) + exp(-2 u^2), which implies the exact frozen coefficient 2 + 4 M_d (1+u^-2) log(3u). The final Mills estimate makes the exponential remainder negligible uniformly and establishes both claimed uniform asymptotics while allowing d and W to depend on q. No substantive gap or proof repair was needed. No theorem dependency beyond the two approved definitions is used; the unrestricted finite Gaussian conjectures remain outside the checked statement.

Audited asset SHA-256: `6ab050275fdd8f5743d249c8b3820a6784d1739ff72dd91213f301fa77588b10`. Audited native context SHA-256: `1664978a1dc9a9da0fe4e0b06a989532b50b8ed8ac306a63c1b44e586345c66d`.
