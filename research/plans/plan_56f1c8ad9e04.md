---
id: plan_56f1c8ad9e04
type: plan
title: >-
  Direct radial envelopes, same-pair compactness, and conditional Gaussian
  calculus
status: succeeded
target_asset: gaussian_bh_same_potential_radial_loading_variation
inspired_by: []
adapts:
  - gaussian_bh_global_particle_potential_certificate
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
proof_digest: 6bb7cfdc1dbf8ae7eaef7d6f3fb6cd04b828616653b1529dc0e1192a77f962f1
statement_digest: 4fdd9f2e842b76290c660caf30ede224f0ee87a0eba3d74506e1fd2489a7ddf4
dependency_digests:
  gaussian_bh_global_particle_potential_certificate: 5c18aaddd67e681c31bff48ee957bb54c0681a855d0bfd853d043ea65e593f90
  gaussian_bh_private_noise_cutoff_signed_transport_variation: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
  gaussian_bh_exchangeable_array_variational_compactification: 82e91305e89e8c5f50be87b28d54dc08a251a8adf76f9407859ccdd4f3536aee
  gaussian_bh_private_smoothed_directing_population: 0fbae7cf085365821031dfb661f7b64a292089719262bcc88d2b940ede32bad0
  gaussian_bh_hybrid_particle_potential_convention: 44bb848d3c12d87628ebdcb7a237000a1acd371405766aa91e48b52b80e6abec
  gaussian_bh_signed_near_active_gradient_cones: daef18b4707d34b07e148fff17d26c059ab590109aab8317dc11d00224f3a9e0
  gaussian_bh_marked_exchangeable_parameter_array: 92f2b0b67ee27711461bffe8724ed1bc06dd5ba6251b57e671d1584b0754c805
verified_proof_digest: 6bb7cfdc1dbf8ae7eaef7d6f3fb6cd04b828616653b1529dc0e1192a77f962f1
---

## Goal

Target: [Same-potential radial loading variation and fixed-rank Gaussian integration by parts](../assets/gaussian_bh_same_potential_radial_loading_variation.md).

Prove all five clauses of the unchanged statement for its genuine pre-noise canonical normalized maximizer, fixed regularizers, and the one already matching pair $(G_+,c_+),(G_-,c_-)$. Keep the actual largest BH rank and full FDP of the prerequisites. Loading motion changes the trial particle only; it never changes the baseline threshold, selector, weight or directing law during a radial derivative. The Cameron-Martin calculation instead differentiates the baseline threshold at a fixed deterministic rank. These two derivatives must remain distinct.

## Plan

1. [x] **Fix the hypotheses and the versions before any derivative.** As in gaussian_bh_global_particle_potential_certificate Proof steps 1 and 8, retain the exact same pair and its lawful global comparison $P(x)\le\kappa$, with equality on one full-$\pi$-measure contact set. Use only the three approved prerequisites declared in the target. As in gaussian_bh_private_noise_cutoff_signed_transport_variation Proof section 1, start from jointly measurable isonormal series and apply Fubini for each fixed directing law, trial particle and stated countable endpoint family. For a fixed deterministic $v$, the series gives $X(rv)=rX(v)$ simultaneously for all $r$ on its convergence event. Work on $I=[0,1]$, or any fixed compact physical extension $I=[0,1+\epsilon]$ with $(1+\epsilon)\|v\|\le1$ when $0<\|v\|<1$. All $r$ on $I$ are nonnegative. At $v=0$ the radial functions are constant, so treat that case immediately. Endpoint derivatives mean one-sided derivatives. This step introduces no samplewise supremum over the Hilbert ball and no conditional-on-noise choice of a model.

2. [x] **Derive an explicit kernel envelope through radial order three (clause 1).** Replace the center-only differentiation in gaussian_bh_global_particle_potential_certificate Proof step 3 by center-plus-variance differentiation. Write $\tau=\tau_s$, $b=\tau X(v)$, $d=\tau^2\|v\|^2$, $e=rd$, and $\partial=\partial_\theta$. Along $I$, $c_r\ge s$, $d\le\tau^2$ and $0\le e\le\tau^2$; the last bound follows from $r\|v\|\le1$ and $\|v\|\le1$, including extensions. Prove directly for a Gaussian tail with center $\mu$ and variance $u$ that $\partial_uK=\tfrac12\partial_\mu^2K$. Therefore
   $$
   K_r'=(b\partial-e\partial^2)K_r,
   $$
   which is the exact requested generator. Differentiate the operator, whose derivative is $-d\partial^2$, to obtain and check
   $$
   K_r''=(b^2-d)\partial^2K_r-2be\partial^3K_r+e^2\partial^4K_r,
   $$
   $$
   K_r'''=(b^3-3bd)\partial^3K_r
       +(-3b^2e+3ed)\partial^4K_r
       +3be^2\partial^5K_r-e^3\partial^6K_r.
   $$
   Give finite numerical upper bounds for the Gaussian polynomial factors rather than leaving a missing regularity lemma. One explicit choice, for $1\le j\le6$, is
   $$
   B_j=\frac{(j-1)!}{\sqrt{2\pi}\,s^j}
      \sum_{k=0}^{\lfloor(j-1)/2\rfloor}
      \frac{M_{j-1-2k}}{2^k k!(j-1-2k)!},
   \qquad M_0=1,\quad M_p=(p/e_{\rm exp})^{p/2}\ (p\ge1),
   $$
   where $e_{\rm exp}=\exp(1)$. Prove $|\partial^jK_r|\le B_j$ by the directly differentiated probabilists' Hermite polynomial formula and $\sup_y|y|^p\phi(y)=M_p/\sqrt{2\pi}$. Verify that the following choices satisfy the requested bound $|K_r^{(m)}|\le C_m(1+|X(v)|^m)$:
   $$
   C_0=1,\qquad C_1=\tau B_1+\tau^2B_2,
   $$
   $$
   C_2=\tau^2B_2+2\tau^3B_3+\tau^4B_4,
   $$
   $$
   C_3=4\tau^3B_3+6\tau^4B_4+3\tau^5B_5+\tau^6B_6.
   $$
   For $m=0$ also retain the sharper $|K_r|\le1$. Check all signs in the generator, especially the negative variance contribution, at $r=0$ and at the physical endpoint.

3. [x] **Average only after applying the conditional total weight bound (rest of clause 1).** As in gaussian_bh_global_particle_potential_certificate Proof steps 2, 3 and 6, denote the nonnegative conditional rank-integrated selector coefficient by
   $$
   W^t_\pm(X)=\frac1\sigma\int_a^1
       \frac{w_{X,\pm}(u)\phi(M_X(u))}
       {h_X(Q_X(t(X,u)))}\,du\le K_0.
   $$
   Here $K_0$ is exactly the explicit constant in the target, including its near-stationarity tolerance term. Multiply each derivative envelope from step 2 by the nonnegative selector measure and integrate in $u$ first. This yields $K_0C_m(1+|X(v)|^m)$ before taking expectation in $X$. No independence between selector and $X(v)$ is needed. Since $X(v)$ is centered Gaussian with variance at most one, use
   $$
   \mu_0=1,\quad\mu_1=\sqrt{2/\pi},\quad
   \mu_2=1,\quad\mu_3=2\sqrt{2/\pi}
   $$
   to obtain the uniform bounds $K_0C_m(1+\mu_m)$ for $m=1,2,3$, and $K_0$ for order zero. For $P_0$, the absolute value of the baseline coefficient is at most $1/a$, so the same proof gives $a^{-1}C_m(1+\mu_m)$ and $1/a$. Dominate radial difference quotients and derivatives by these Gaussian envelopes to justify differentiating inside both integrations. Convex combinations retain all these bounds. They are independent of $\pi,\theta,v$, dimension, $q$, selector, $j$ and approximation index, but may depend on the fixed regularizers. The identity for generating potentials is the averaged generator at a frozen baseline threshold.

4. [x] **Prove one-dimensional $C^2$ compactness and identify every fixed limit (clause 2).** Adapt gaussian_bh_global_particle_potential_certificate Proof step 4 on the single compact interval $I$, now for radial derivatives. For a given sequence $(G_n,c_n)\to(G,c)$ in the declared evaluation topology put $f_n(r)=G_n(\theta,rv,\ell)$. Step 3 bounds $f_n,f_n',f_n'',f_n'''$ uniformly. On a countable dense subset of $I$, extract a diagonal subsequence of the first three functions. The bound on the next derivative makes each of $f_n,f_n',f_n''$ uniformly Lipschitz. A finite mesh on $I$ upgrades the extracted convergence to uniform convergence of all three, including the endpoint values. Pass to the limit in the two identities
   $$
   f_n(r)-f_n(r_0)=\int_{r_0}^r f_n'(u)\,du,
   \qquad
   f_n'(r)-f_n'(r_0)=\int_{r_0}^r f_n''(u)\,du.
   $$
   Evaluation convergence at every fixed $(\theta,rv,\ell)$ identifies the first limit with $f(r)=G(\theta,rv,\ell)$ and the other two uniquely with $f',f''$. Prove full-sequence convergence by contradiction: any subsequence violating one of the three sup-norm convergences has a further uniformly convergent subsequence with these same uniquely identified limits. The approved metrizable compact potential classes supply an approximating sequence for each fixed closure point, so this proves regularity of every such $G$, not merely selected limits. Apply it separately to each of the already fixed $G_+,G_-$; subsequence extraction identifies derivatives of those functions and never selects a different pair. $P_0$ is already $C^3$ along the curve by step 3, hence $\mathcal P$ is $C^2$. Repeat on each chosen physical extension. The generator for a closed convex limit is precisely the resulting limit of its averaged generating expressions; no realizing selector or Hilbert-ball gradient convergence is asserted.

5. [x] **Derive the contact radial normal, including measurable and integrable versions (clause 3).** Adapt gaussian_bh_global_particle_potential_certificate Proof step 8 by replacing lawful mean motion with lawful radial loading motion. At each point $x$ of its full-measure contact set, every $x_r=(\theta,rv,\ell)$ on the physical interval is lawful and has the same quadratic mean penalty. Consequently $\mathcal P(x_r)\le\mathcal P(x)$ near $r=1$. For $r<1$ the divided difference $[\mathcal P(x)-\mathcal P(x_r)]/(1-r)$ is nonnegative, giving $J(x)\ge0$ by step 4. When $\|v\|<1$ a physical interval past one is also available, so differentiability at this interior maximum gives $J(x)=0$; include $v=0$ directly. Define $J$ globally by the limit of these backward differences at $r_n=1-1/n$, $n\ge2$. Each difference is Borel because the averaged potentials are strongly continuous by the approved certificate. Step 4 makes its limit exist at every particle. Its uniform absolute bound is
   $$
   |J(x)|\le(1/a+2K_0)C_1(1+\mu_1).
   $$
   Thus $J$ is $\pi$-integrable and its integral equals its nonnegative integral on $\{\|v\|=1\}$. As in the adapted source's steps 1 and 3, Fubini establishes representative invariance for generators at each fixed particle; continuity extends agreement from a countable strong dense set. Evaluation limits are these intrinsic continuous functions, and $J$ is their difference-quotient limit, so it too is representative invariant. This requires no common probability-one continuous isonormal field on the entire ball.

6. [x] **Construct the conditional Gaussian line and differentiate the fixed-rank quantile (clause 4).** Adapt gaussian_bh_private_noise_cutoff_signed_transport_variation Proof sections 1 and 4 with the bounded center velocity $b_v(\theta',w,\ell')=\tau\langle w,v\rangle$ in place of a physical mean transport; this is an analytic translation of the background, so no mean-tag constraint on this velocity is required. For $v\ne0$ set $e_v=v/\|v\|$, $\xi=X(e_v)$ and construct the orthogonal isonormal representative $Y$ over $e_v^\perp$. Fubini gives, for almost every $Y$, finite $Y(w)$ for $\pi$-almost every $w$; on that same parameter event define
   $$
   X_\xi(w)=Y(w)+\xi\langle w,e_v\rangle\quad\text{for every }\xi\in\mathbb R.
   $$
   This directly provides a coherent line for all shifts, in finite or separable dimension, rather than taking an uncountable intersection of null sets. Identify it with the given jointly measurable isonormal representative for all fixed-law integrals almost surely. The translated kernels are $C^1$ in $(\xi,z)$, dominated by Gaussian density derivative bounds at $c_s(w)\ge s$. Their center velocities have magnitude at most $\tau$. Prove directly by integration that the translated tail has strictly negative score derivative $-h$, positive continuous $h$, and shift derivative $\tau\int\langle w,e_v\rangle k\,d\pi$. The bounded score shift gives the global quantile displacement bound $|Q_{\xi+u}(t)-Q_\xi(t)|\le\tau|u|$. Use it and a first-order expansion of $H_\xi(Q_\xi(t))=t$, with a positive local lower bound on $h$, to prove differentiability for each real $\xi$. Multiplying the line derivative by $\|v\|$ gives exactly
   $$
   D_vQ_X(t)=\tau\int\langle w,v\rangle
       \frac{k_{X,(\theta',w,\ell')}(Q_X(t))}{h_X(Q_X(t))}\,d\pi.
   $$
   The ratio is a nonnegative density integrating to one; since $\|w\|\le1$, deduce $|D_vQ_X(t)|\le\tau\|v\|$. The same dominated expansions give continuity of the line derivative. At $v=0$ both the translation and derivative vanish. The rank $t$ remains deterministic throughout; no derivative of an actual selector or switch weight is taken.

7. [x] **Prove the scalar integration by parts with both baseline derivatives present (clause 5).** On the Gaussian line from step 6, condition on $Y$ and any permitted independent extra randomness. For the bounded test $A$, which is independent of the physical radial parameter, use its assumed directional $C^1$ property and bounded $D_vA$. Put $L=\partial_\theta^2K_1(Q_X(t))$ and $k=k_1(Q_X(t))$. The ordinary chain rule must give
   $$
   D_vk=L\{\tau\|v\|^2-D_vQ_X(t)\},
   \qquad
   D_v(Ak)=kD_vA+AL\{\tau\|v\|^2-D_vQ_X(t)\}.
   $$
   In particular $|k|\le B_1$, $|L|\le B_2$, and $|D_vk|\le B_2\tau(\|v\|^2+\|v\|)$. The conditioned line function $Ak$ is bounded and continuously differentiable; for fixed $v\ne0$ its scalar derivative is $D_v(Ak)/\|v\|$, a bounded function under the stated conditioned bounds. Integrate $(Ak)(\xi)\phi(\xi)$ on $[-N,N]$ using $\phi'=-\xi\phi$, and show both boundary terms vanish as $N\to\infty$ because $Ak$ is bounded. The bounds above and $\mathbb E|\xi|<\infty$ justify every absolute integral and removal of the conditioning, with the original test bounds. This proves directly
   $$
   \mathbb E[X(v)Ak]=\mathbb E[D_v(Ak)].
   $$
   Insert the frozen-threshold radial generator from step 2 at $r=1$:
   $$
   \mathbb E[AK_r'(Q_X(t))|_{r=1}]
       =\tau\mathbb E[X(v)Ak]-\tau^2\|v\|^2\mathbb E[AL].
   $$
   Expand the first expectation with the preceding product rule and cancel only the explicit $\tau^2\|v\|^2\mathbb E[AL]$ term. The surviving identity is exactly
   $$
   \tau\mathbb E[kD_vA-ALD_vQ_X(t)].
   $$
   Check absolute integrability separately on the original left side using $|A|C_1(1+|X(v)|)$, and on the final right side using the bounds on $A,D_vA,k,L,D_vQ$. At $v=0$ both sides are zero. An analytic test weight may depend on $X$; it is never used to choose a physical competitor after observing noise.

8. [x] **Close the exact checkpoint and stop at its first unproved step.** Match steps 2–3 to clause 1, step 4 to clause 2, step 5 to clause 3, step 6 to clause 4, and step 7 to clause 5. Check the endpoint cases $r=0$, $\|v\|=1$, $\|v\|<1$, and $v=0$, all tag cases and representative claims, and uniformity of every constant over precisely the parameters stated. Preserve the fixed pair and all global/mean/level conditions already provided by the certificate. If any displayed derivative identity, conditional $K_0$ domination, full-sequence compactness identification, coherent Gaussian-line construction, implicit differentiation, contact comparison, or Gaussian boundary/interchange argument cannot be proved under the exact hypotheses, stop at that earliest obligation and record its precise obstruction when executing this plan. Do not substitute an additional black box, a new matching pair, an unjustified pathwise field supremum, or stronger selector regularity. This checkpoint makes no claim of actual-FDR loading differentiability, a signed loading identity for merely measurable hybrid selectors, a bound uniform in regularizers, or the unresolved uniform $q$-budget.

## Verification

Execution must reproduce the generator and its second and third radial derivatives by direct differentiation; the explicit $B_j,C_m$ bounds then supply dominated differentiation of all generating expressions. The one-dimensional diagonal-plus-finite-mesh argument and the two fundamental-theorem identities prove the full $C^2$ convergence for every specified approximating sequence, with the limit identified by the original evaluation coordinates. Lawful contact comparisons of that same function give the radial normal. Conditional scalar tail differentiation and one scalar Gaussian integration by parts prove the final two identities with both $D_vA$ and $D_vQ$ retained. No numerical diagnostic or absence of counterexamples substitutes for one of these analytic obligations.

## Assumed definitions

All four definitions explicitly used in the target are approved: [private-smoothed directing population](../definitions/gaussian_bh_private_smoothed_directing_population.md), [hybrid particle-potential convention](../definitions/gaussian_bh_hybrid_particle_potential_convention.md), [signed near-active conventions](../definitions/gaussian_bh_signed_near_active_gradient_cones.md), and [marked-array conventions](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md). The three declared prerequisites are approved. No draft definition or unproved dependency is assumed. Symbols $b,d,e,B_j,C_m,\mu_m,e_v,\xi,Y,L$ above are local proof notation. Elementary Gaussian polynomial bounds, compactness on one real interval, inverse differentiation on that interval, and scalar Gaussian integration by parts are obligations proved here, not new known-result black boxes.

## Adapted from

- [Global averaged particle-potential certificate](../assets/gaussian_bh_global_particle_potential_certificate.md), available Proof steps 1–4, 6 and 8. Its hypotheses transfer verbatim because the target fixes the same approved population, regularizers and matching pair. Step 2 supplies the already declared conditional $K_0$ bound; the averaging pattern in steps 3 and 6 is adapted with radial center-plus-variance derivatives in place of center-only derivatives. Step 4's diagonal and finite-net argument is reproved on a single compact radial interval with control through the third derivative; no global gradient topology is imported. Step 8's lawful-contact maximum argument becomes the loading boundary normal with unchanged mean penalty. We do not adapt the certificate's existence/separation or its cited mass-variation argument: their conclusions are supplied by this already declared prerequisite, not used as undeclared auxiliary statements.
- [Complete signed mean-and-level variation](../assets/gaussian_bh_private_noise_cutoff_signed_transport_variation.md), available Proof sections 1 and 4. Section 1's jointly measurable series/Fubini argument transfers to the same fixed-law kernels and is rebuilt on the orthogonal Gaussian line. Section 4's bounded center-shift coupling and implicit quantile differentiation are reproved for the bounded analytic velocity $\tau\langle w,v\rangle$. This velocity translates the background rather than transporting physical means, so no unlawful movement of a true-zero tag is introduced. We do not reuse its envelope, finite-model or value-limit arguments, nor any of their cited results. Both adapted source IDs are already in the target's declared prerequisites.

Library searches were performed first for Gaussian integration by parts, radial derivatives, compactness and fixed-rank Gaussian quantiles. No matching library proof was found. The returned compact Danskin and positive-Gaussian-Simes nodes have no Proof section and do not provide the argument needed here; neither is adapted or cited as a black box. The supplied related idea about a later actual-FDR loading variation is outside this checkpoint and is not an assumed result or an input to this plan.

## Difference from failed plans

The current plan-stage context pack contains no failed plan for this target and no existing pending plan. The earlier five searches supplied diagnostics, not proof plans or assumed lemmas. This plan follows the newly specified direct elementary route, with explicit envelopes, fixed-limit identification and a failure criterion at the first unproved analytic obligation.

## Outcome

Complete proof is in [Same-potential radial loading variation and fixed-rank Gaussian integration by parts](../assets/gaussian_bh_same_potential_radial_loading_variation.md), Proof sections 1–6. All five clauses and all eight checklist items are established there. Sections 1–2 prove the exact radial generator, explicit third-order envelopes and conditional-weight domination; section 3 proves full-sequence radial C² convergence to each fixed evaluation limit; section 4 proves the same-pair contact normal and its measurable integrable invariant version; sections 5–6 construct the actual coherent Gaussian-line quantile version and prove the integration-by-parts identity retaining both baseline derivatives.

The exact pre-execution target bytes, including its frontmatter, statement and provenance, were preserved by appending the Proof only. Target status remains draft; no approval is claimed and independent verification remains required. All four used definitions and three declared prerequisites are approved. No draft definition, extra assumption, new dependency, selector regularity, uniform regularizer estimate or unresolved uniform q-budget is assumed. No original plan history was removed. The workspace root is not a Git repository, so SHA256 guards and saved pre-execution bytes were used for write freshness and exact-scope verification.


## Verdict

confirmed

Independently checked the frozen Statement and Proof against the prerequisite statements and definitions supplied in the verify_proof context pack, without reading the producing plan reasoning, dependency proofs, remarks or earlier history.

The radial generator has the stated negative variance term; its second and third derivatives and the explicit Hermite envelopes give valid finite C_0 through C_3, also on every permitted physical extension. The conditional total-selector coefficient is bounded before Gaussian averaging, so the moment argument needs no independence between selectors and X(v). The constants have exactly the claimed fixed-regularizer scope.

The dense-mesh diagonal argument gives uniform limits of each function and its first two derivatives. Integral identification makes the limits C^2, evaluation convergence fixes the same potential, and the subsequence contradiction establishes convergence of the whole sequence. Approved metrizability supplies approximating sequences for every closure point. The chosen matching pair is never replaced.

The contact comparison has the correct inward derivative sign, gives zero at interior loadings, and leaves the mean penalty unchanged. Strong continuity of the approved averaged potentials makes the displayed radial difference quotients Borel; the uniform first-derivative bound proves integrability. Averaged representative invariance and countable dense evaluation identify the same limiting potentials and the same J.

The orthogonal-field construction supplies a single residual event on which the fixed-law Gaussian line is coherent for every scalar shift. Bounded kernel derivatives justify differentiation under the law; the quantile displacement estimate and positivity of the density justify its C^1 derivative without a uniform reciprocal-density assumption. Posterior normalization proves the stated Cameron-Martin bound.

On each conditioned scalar Gaussian line, the product derivative is bounded, Gaussian boundary terms vanish, and both integrals are absolutely convergent. The trial-center term cancels the explicit radial variance term, leaving both k D_v A and the baseline quantile derivative with the stated signs. The zero loading and one-sided endpoints are covered. This confirms only the five fixed-regularizer clauses: it establishes no regularity for actual measurable selector weights, no full-FDR loading derivative, and no regularizer-uniform q payment.
