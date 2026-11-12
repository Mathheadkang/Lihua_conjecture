---
id: plan_a6d0e7b4c891
type: plan
title: >-
  Conditional-energy domination, compact support limits, and averaged cone
  separation
status: succeeded
target_asset: gaussian_bh_averaged_signed_mean_level_complementarity
inspired_by:
  - idea_1fa28e9136fb
  - idea_fd90b2fd8168
adapts: []
proof_digest: 264942256c2e4c06f3f8e296a8196a2b43c6f32f6062d17820f6492f83793b74
statement_digest: e3dcfc508ee344fb52d4454b0676313187354eefcb69339fb28a33f503d7f350
dependency_digests:
  gaussian_bh_private_noise_cutoff_signed_transport_variation: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
  gaussian_bh_exchangeable_array_variational_compactification: 82e91305e89e8c5f50be87b28d54dc08a251a8adf76f9407859ccdd4f3536aee
  lib_diestel1991_ui_absolute_continuity: ae93f80d7b9c249101693a5fae93818f1dbcbf1ad6e2ad19bb22d06384642d40
  lib_diestel1991_dunford_pettis_compactness: b4b6733969904bcb01274f19299863595945d7369e6d9c98ae31c5eb69800eb9
  gaussian_bh_signed_near_active_gradient_cones: daef18b4707d34b07e148fff17d26c059ab590109aab8317dc11d00224f3a9e0
  gaussian_bh_private_smoothed_directing_population: 0fbae7cf085365821031dfb661f7b64a292089719262bcc88d2b940ede32bad0
  gaussian_bh_marked_exchangeable_parameter_array: 92f2b0b67ee27711461bffe8724ed1bc06dd5ba6251b57e671d1584b0754c805
  lib_diestel1991_scalar_l1_ui_weak_topology: 0d793693ef75bb1ab6a14fdbb6bf2bbe74b8b51323ff90e5077ff80f9d2cd44d
verified_proof_digest: 264942256c2e4c06f3f8e296a8196a2b43c6f32f6062d17820f6492f83793b74
---

## Goal

Target: [Averaged signed mean-level complementarity at regularized Gaussian BH maxima](../assets/gaussian_bh_averaged_signed_mean_level_complementarity.md).

Prove all five clauses with their exact quantifiers and endpoint signs. Clauses 1--3 hold for each fixed lawful finite-second-moment deterministic law and fixed positive regularizers; cone matching and nonnegative normal density require an actual canonical normalized global maximum. Keep the signed moment term, actual largest non-strict rank and complete signed response. No estimate of the total flux on a universal scale is part of this plan.

## Plan

1. [x] **Measurable selectors and their elementary bounds.** Use the approved complete signed variation for joint measurable kernels, continuous positive-density quantiles, measurable suffix minimum, compact nonempty active sets and the actual-rank law. Enumerate rational points in $(0,1)$, and select the first satisfying $t\ge r$ and $B_X(t)\le M_X(r)+1/j$. Continuity at every active point, including approximation from the right if it equals $r$, proves existence; the countable construction proves measurability. Establish joint measurability of $p_{X,t}(x)$ by measurable composition and its normalization $\int p_{X,t}d\pi=1$. Changes of the isonormal representative affect only a background-null set after Fubini, so all these objects and integrated vectors are invariant in the required almost-everywhere senses. From $0\le f_X\le1$, $|f_X'|\le1/r$ and nondecreasing $\chi_a$, prove $\int_a^1|g_X'|dr\le C_a:=1+\log(1/a)$. Since $u_q(t)\ge U\ge1$ and $m$ is decreasing, $0\le m_t\le m(U)$. Tonelli then proves that both mean coordinates are nonnegative $L^1(\pi)$ functions of mass at most $C_a/(\sigma\sqrt{2\pi})$, and the scalar coordinates lie in $[0,m(U)C_a/(\sigma\sqrt{2\pi})]$.

2. [x] **Uniform absolute continuity for all near-active selectors.** Put $E_X=\int A_X^2d\pi$ and verify $\mathbb E E_X\le2M_2(\pi)+2\tau_s^2<\infty$. Fix truncations $L,T>0$ and retain backgrounds with $E_X\le L$ and ranks with $|M_X(r)|\le T$. For every admissible selector, every $j\ge1$ and retained pair, prove
   $$
   U-\sigma(T+1)\le Q_X(t)\le\sqrt{(L+1)/a}.
   $$
   The first inequality follows from $B_X(t)\le M_X(r)+1$; for the second use $t\ge a$ and the conditional second moment $\int(A_X^2+c_s^2)d\pi\le L+1$ if the quantile is positive. At least half the centre mass lies in $|A_X|\le\sqrt{2L+2}$. On these bounded centre and quantile intervals and $s\le c_s\le\sqrt{1-\sigma^2}$ the Gaussian kernel has a deterministic positive minimum $\kappa_{L,T}$, so $h_X(Q_X(t))\ge\kappa_{L,T}/2$ and $p_{X,t}(x)\le2/(s\sqrt{2\pi}\kappa_{L,T})$. For any measurable particle set $A$, integrate $p_{X,t}$ over $A$ and bound the discarded contribution using only its normalization. Obtain, uniformly over both signs, $j$ and selectors,
   $$
   \int_A V_{\pm,\mathrm{mean}}(t)d\pi
   \le D_{L,T}\pi(A)+\frac{C_a}{\sigma\sqrt{2\pi}}\mathbb P(E_X>L)
   +\frac{C_a}{\sigma}\sup_{|z|>T}\phi(z),
   $$
   with finite explicit $D_{L,T}$. Choose $L,T$ before making $\pi(A)$ small. This proves uniform absolute continuity with respect to this fixed $\pi$, hence UI by the registered approved absolute-continuity criterion. The finite-support idea is used only for its normalization/weight principle; this argument replaces its atomwise bound and covers diffuse laws.

3. [x] **Direct countably additive compactness.** Uniform absolute continuity, positivity and the mass bounds persist under convex combinations and weak closure, because $\int_A g\,d\pi$ is a weakly continuous test for every measurable $A$. Give a direct compactness argument for these hulls: clip a sequence of nonnegative densities at integer heights, extract diagonal weak $L^2(\pi)$ subsequences (using separability of $L^2$ for the standard Borel parameter space), and use the uniform clipping-error bound to show the clipped weak limits are Cauchy in $L^1$. Their $L^1$ limit represents every bounded test limit; extract the bounded scalar coordinate as well. A countable generating algebra of the parameter space metrizes the weak topology on this bounded uniformly absolutely continuous family: approximate each bounded measurable test in measure by uniformly bounded algebra-simple functions, and use uniform absolute continuity to make the pairing approximation uniform over the family. Consequently sequential compactness here implies compactness. This proves weak compactness directly without finitely additive substitutes; the registered approved Dunford--Pettis criterion is an independent available check, not an adapted sketch. Nonemptiness follows from step 1, nesting from $\mathcal T_{j+1}\subset\mathcal T_j$, and the compact finite-intersection property gives nonempty weakly compact convex $C^\pm$.

4. [x] **Bulk and exact support representation.** Bound the absolute bulk integrand by $1/(as\sqrt{2\pi})$, use Fubini for measurability and integrability, and integrate its braces times the kernel over $\pi$ to obtain $h_0-(h_0/h)h=0$. This proves $\int\mathfrak b\,d\pi=0$. For a fixed bounded $b$ and finite $\lambda$ set $L_{X,t}=\int p_{X,t}b\,d\pi+\lambda m_t$. It is continuous in $t\in(0,1)$, jointly measurable, and bounded by $\|b\|_\infty+|\lambda|m(U)$. A first near-maximizing rational choice proves that the support of $C_j^\pm$ is the integral of the pointwise supremum of $L_{X,t}$ over the rational $1/j$-near-active points. For each fixed $(X,r)$, compactness of bounded barrier sublevels away from $1$ and continuity imply that these decreasing suprema converge to $\max_{t\in\mathcal A_X(r)}L_{X,t}$; rational approximation recovers every active minimizer, not only a chosen one. Apply domination using $C_a$ before averaging in $X$. Prove separately that supports decrease to the support of $C^\pm$: choose maximizers in nested compact $C_j^\pm$ and use a cluster point, or the nested compact maximizer-level sets. Substitute the approved all-minima envelope response, $\dot M=-\max_{\mathcal A}L/\sigma$, into its full signed variation, and use the bulk identity for the fixed-rank term. Obtain exactly $\dot{\mathcal F}^{a}=\int\mathfrak b b\,d\pi+h_{C^+}(b,\lambda)-h_{C^-}(b,\lambda)$ for every lawful direction. The two signs can have different maximizing selectors.

5. [x] **Mass and survival flux without an unlawful direction.** The continuous test $(b,\lambda)=(1,0)$ and posterior normalization show that every element of each convex hull and its weak closure has the same mean mass $\sigma^{-1}\mathbb E_X\int_a^1w_{X,\pm}\phi(M_X)dr$. Thus subtracting the masses and adding the zero bulk mass gives the stated first expression for $\Gamma_a$, independent of the selected pair. Prove $g_X(R)=\int_a^1g_X'(r)\mathbf1_{\{R\ge r\}}dr$ almost surely, with $g_X(a)=0$ and the approved $\mathbb P_Z(R=1\mid X)=0$ convention; $g_X$ extends absolutely continuously to $1$ since its derivative has the displayed integrable bound. Multiply by $Z$, apply Fubini using $\mathbb E|Z|C_a<\infty$, and use the actual-rank survival identity and $\mathbb E_Z[Z\mathbf1_{\{Z\ge M\}}]=\phi(M)$. This yields exactly $\Gamma_a=\sigma^{-1}\mathbb E[Z\chi_a(R)D]$, including all boundary terms.

6. [x] **Extend the exact extremal inequality to the testing cone.** At an actual canonical normalized maximum, take arbitrary $(b,\lambda)\in K$ and define $b_\zeta=b\mathbf1_{E_0}+b\mathbf1_{\{|\theta|\ge\zeta\}}$. Canonicality excludes false-tagged zero mass; $b\le0$ on $E_0$, and $\epsilon\|b\|_\infty<\zeta$ protects the remaining signs. Thus $b_\zeta$ is a lawful deterministic velocity. Apply the approved normalized inequality and step 4 to $(b_\zeta,\lambda)$. Since the omitted sets $\{0<|\theta|<\zeta\}$ decrease to the empty set, uniform absolute continuity gives convergence of both support functions, while bounded bulk density and $\theta\in L^1$ give convergence of their pairings. Obtain for every $(b,\lambda)\in K$, with $d=(\mathfrak b-2\eta qU\theta,-\beta F^a+\delta qU)$,
   $$
   \langle d,(b,\lambda)\rangle+h_{C^+}(b,\lambda)\le h_{C^-}(b,\lambda).
   $$
   Keep the factor $qU$ and the level constraint $\lambda\le0$ at $q=q_{\max}$. This is convergence of pairings, not a norm-density assertion about lawful velocities.

7. [x] **Direct weak separation and matching with exact signs.** Compute the polar using indicator tests: $K^\circ$ consists of $L^1$ mean densities vanishing off $E_0$ and nonnegative on $E_0$, with scalar zero at interior levels and nonnegative at the upper level endpoint. This also proves it is weakly closed. Prove $C^-+K^\circ$ is weakly closed: from a convergent net of sums, take a subnet of the $C^-$ components converging in their compact set; the differences converge into the closed polar. For a point outside this closed convex sum, a finite-coordinate weak neighborhood disjoint from it gives separation in a finite-dimensional projection; separate its projected closed convex closure by the nearest-point Euclidean argument. The separating continuous functional is therefore a pair $(b,\lambda)\in L^\infty\times\mathbb R$. Its finite support on the polar forces $(b,\lambda)\in K$, and then $h_{C^-+K^\circ}=h_{C^-}$ at this test, contradicting step 6 for any outside point in $d+C^+$. This proves $d+C^+\subseteq C^-+K^\circ$. Read the polar coordinates to obtain a matching negative element for every positive one: $\Psi=2\eta qU\theta$ off $E_0$, $\Psi\ge0$ on $E_0$, and $\Lambda=\beta F^a-\delta qU$ in the interior or $\Lambda\ge\beta F^a-\delta qU$ at $q_{\max}$. All separation occurs after Gaussian averaging and in the declared countably additive dual pairing.

8. [x] **Normal mass and the fixed-regularizer value/penalty limit.** Steps 5 and 7 give the nonnegative $L^1$ density $\Psi-2\eta qU\theta$ supported on $E_0$, of exact mass $\Gamma_a-2\eta qU\int\theta d\pi$. Cauchy--Schwarz gives the target bound $|2\eta qU\int\theta d\pi|\le2qU\sqrt\eta\sqrt{\eta M_2(\pi)}$. Establish the fixed-threshold domination suggested by the cutoff idea directly in the approved population model: when $R>0$, its true discovery mass is $V_X(u_q(R)-\sigma Z)$; since $u_q(R)\ge U$ it is at most $V_q:=V_X(U-\sigma Z)$. Thus $\chi_a(R)D\le V_q/a$. Each true-tag score has mean $\theta\le0$ and unconditional variance one, so $\mathbb E V_q\le q$, and $F^a\le q/a$ uniformly in the directing law. For $J=F^a/(qU)-\delta\log(1/q)$ this gives $J\le1/(aU)-\delta\log(1/q)\to-\infty$ uniformly as $q\downarrow0$, and $J\le1/a$. A fixed lawful zero-mean true-tag finite-moment comparison at a fixed positive level gives a common finite lower bound for the maximizing objectives, hence a common coercive level interval for $0<\eta\le\eta_*$. In particular $L_0^a$ is finite and has a finite lower bound. Choose a finite-moment comparison pair with $J\ge L_0^a-\varepsilon$ to obtain $L_0^a-\varepsilon-\eta M_2(\pi_\varepsilon)\le L_\eta^a\le L_0^a$. Therefore $L_\eta^a\to L_0^a$ and, for every maximizing family, $0\le\eta M_2(\pi_\eta)\le L_0^a-L_\eta^a\to0$. Finally $qU$ is bounded on $0<q\le q_{\max}$ (or on the common coercive interval), so the signed moment error vanishes. No derivative limit or limit as $\delta\downarrow0$ is involved.

## Verification

Steps 1--3 prove precisely the fixed-law measurability, uniform integrability and countably additive compactness in clause 1. Step 4 proves all bulk and support equalities in clause 2, retaining all active minima and both signs. Step 5 proves clause 3, including its selector-independent survival flux. Steps 6--7 prove the exact cone inclusion and matching in clause 4 with the upper-level and true-zero signs checked explicitly. Step 8 proves clause 5 with its signed mass, error bound, and fixed-private/cutoff value and penalty assertions for every choice of actual maxima. An execution succeeds only if each of these gates is proved; a finite-support argument alone, bounded total selector mass alone, or a mere existence theorem for maxima cannot substitute for them.

## Assumed definitions

All definitions used are approved: [Signed near-active posterior gradients and lawful mean-level cones](../definitions/gaussian_bh_signed_near_active_gradient_cones.md), [Private-noise-smoothed unit-ball population](../definitions/gaussian_bh_private_smoothed_directing_population.md), [Marked exchangeable parameter arrays](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md), and the registered scalar $L^1$ conventions. The two approved original theorem dependencies and two approved Diestel criteria are used only within their registered statements; no unproved draft lemma or observation is assumed. The two inspired ideas are proposals whose needed claims are proved in steps 1--2 and 8. The later particle-mass redistribution/potential proposal supplies no premise or step here.

## Adapted from

No external proof adaptation is claimed; `adapts` is empty. The two listed library analogues, the positive-Gaussian Simes result and the Dovbysh--Sudakov mixture representation, have no recorded Proof section and supply neither this fixed-law posterior domination nor this product-cone separation. The registered Dunford--Pettis node records a source sketch rather than a complete proof, so that sketch is not labeled adapted. The already registered approved scalar criteria are legitimate black boxes; step 3 additionally supplies the requested direct compactness construction, and step 7 proves the required separation instead of invoking an undeclared quasidifferential theorem. Library searches for posterior/near-active gradients, uniform integrability/compactness, and compact-convex cone separation supplied no further usable proof analogue.

## Difference from failed plans

The stage context lists no failed or pending plan for this target. This plan therefore retries no recorded failed plan. Its substantive general-law gate is the explicit conditional-energy and Gaussian-weight estimate in step 2; its fixed-regularizer coercivity uses the elementary cutoff-to-fixed-threshold comparison, with constants allowed to depend on $a$. Neither is a universal extremal flux estimate.

## Outcome

All eight checklist items are established in parts 1--8 of `## Proof` in [Averaged signed mean-level complementarity at regularized Gaussian BH maxima](../assets/gaussian_bh_averaged_signed_mean_level_complementarity.md). The original target statement, frontmatter and draft status are unchanged. Parts 1--5 prove fixed-law measurability, uniform absolute continuity, direct countably additive weak compactness, all-active support limits, and selector-independent survival flux. Parts 6--7 use lawful truncations and direct weak separation to give the averaged polar inclusion with both endpoint signs and the mean-penalty factor $qU$. Part 8 proves the normal-density mass formula, its signed-moment bound, and the fixed-private/cutoff value and penalty limits for every maximizing family, using the separately proved $F^a\le q/a$.

Only the registered approved definitions and approved dependency statements are assumed. In particular the complete signed variation supplies lawful derivatives, actual-largest-rank identities, and canonical deterministic global maxima; the registered scalar absolute-continuity criterion is applied after uniform absolute continuity is proved. The requested compactness and separation arguments are written directly. No unproved flux-scale estimate, global mass potential, background-dependent stationarity, or derivative-through-regularization limit is used. This success is execution of a draft proof, not independent verification or researcher approval.

Checks: research-maintenance validate reports 0 problems (with its pre-existing older-schema advisory); target-scoped links preview and apply report 0 changes and 0 review items. Manual check-notation against the approved definition context and configured macros.tex/notations.tex found no undefined or conflicting symbols or missing direct relationships. The two configured notation files contain only their header comments. All eight proof sections and standalone display delimiters were checked; the original pre-proof content is preserved byte-for-byte.


## Verdict
confirmed

Independently checked the unchanged statement against the complete proof and the approved dependency statements and definitions. The conditional-energy and barrier truncations establish uniform absolute continuity for the fixed law; the clipping/L2 and countable-algebra argument proves weak compactness directly with countably additive L1 limits. Rational near-minimizers recover every active minimum, and compact nesting justifies both support limits before Gaussian averaging.

The actual-largest-rank survival representation justifies the signed total-flux identity with integrable boundary terms. Lawful mean truncation extends the averaged normalized extremal inequality to K; weak closedness of the compact-set-plus-polar sum and the finite-coordinate separation argument prove the stated inclusion. The mean penalty retains qU, and the level polar gives equality in the interior and the asserted greater-than-or-equal sign at qmax.

The residual normal density and its signed moment correction follow from this inclusion and selector-independent mass. The elementary cutoff bound F^a <= q/a gives a common coercive level interval; finite-moment comparison then proves L_eta^a -> L_0^a and eta M2 -> 0 for every maximizing family. All five clauses are established without assuming conditional-background optimality, unique active minima, or a uniform flux-scale estimate.
