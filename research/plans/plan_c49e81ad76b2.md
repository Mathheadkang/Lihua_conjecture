---
id: plan_c49e81ad76b2
type: plan
status: succeeded
title: >-
  Collision completion, penalized compactness, and measurable marked Gram
  directing laws
target_asset: gaussian_bh_exchangeable_array_variational_compactification
inspired_by:
  - idea_80e457272a8f
  - idea_aec904d88a42
  - idea_190cde547cc5
  - idea_96f9a60e7015
  - idea_d091353e2434
  - idea_e6bd6ec5faf8
tags:
  - gaussian-bh
  - exchangeable-arrays
  - compactification
  - measurable-lifting
proof_digest: 572befa3daccdecb168b51ba3dc7e7164fbda41314ed92b09197f2f9c3fe0271
statement_digest: 82e91305e89e8c5f50be87b28d54dc08a251a8adf76f9407859ccdd4f3536aee
dependency_digests:
  gaussian_bh_common_loading_uniform_submodel_compression: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
  gaussian_bh_common_loading_wasserstein_fdr_continuity: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
  lib_panchenko2009_dovbysh_sudakov_mixture: 6452f258fe31d1e81fbd37918f2b2d8124b945ed91b96fcdc2f343cd6ecfa120
  gaussian_bh_marked_exchangeable_parameter_array: 92f2b0b67ee27711461bffe8724ed1bc06dd5ba6251b57e671d1584b0754c805
  gaussian_bh_common_loading_tagged_population: 231a8f229542b6b2293185c00d427dab12fe7b375e48f8d675f3b6828db09437
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
  gaussian_worst_case_bh_fdr: 5c3438b5ed0ad228d4c497cb1bba3bc00df045464de3732cd69e217ebf9b28a1
verified_proof_digest: 572befa3daccdecb168b51ba3dc7e7164fbda41314ed92b09197f2f9c3fe0271
---

# Collision completion, penalized compactness, and measurable marked Gram directing laws

## Goal

Target: [Cross-dimension marked-array compactification and penalized Gaussian BH extrema](../assets/gaussian_bh_exchangeable_array_variational_compactification.md).

Prove all six clauses at the fixed common loading in the statement. Use the three registered approved dependencies as black boxes. In particular, use the general diagonal-correction conclusion of [Dovbysh-Sudakov mixture representation of Gram-de Finetti laws](../library/panchenko2009_dovbysh_sudakov/assets/lib_panchenko2009_dovbysh_sudakov_mixture.md), without claiming to adapt its unprovided proof. Construct the marked extension and measurable lifting below within this proof.

## Plan

1. [x] **Finite Gaussian kernels and the parameter space.** Write \(f_n(\omega,q)\) for conditional tagged FDR. Prove it is a bounded jointly continuous function of finite parameters and \(q\in(0,1/2)\). Couple convergent finite Gaussian models by the continuous PSD square root and the same standard normal vector. Every discontinuity of the actual largest BH rank and tagged FDP is contained in the finite union of sets \(T_i=S^{-1}(qk/n)\), each having probability zero because its marginal variance is one, even for singular joint covariance. Tags are discrete. Verify that lawful arrays form a closed Polish subspace of the countable parameter product, that exchangeability is closed under weak limits, and that weak convergence of laws there is equivalent to finite-subarray weak convergence. For the latter implication prove countable-product tightness from tightness of individual coordinates before using cylinder identification.

2. [x] **Collision coupling gives uniform completion.** For \(n\ge m\), condition on the first \(n\) parameter coordinates and realize their residual PSD matrix by unit vectors. Apply approved uniform submodel compression to iid uniform indices from \([n]\), retaining exact duplicate observations on collisions. Given no collision, joint exchangeability identifies the ordered induced parameter array with the first \(m\) coordinates; its conditional Gaussian law agrees with the distinct sampled observations. Thus prove, uniformly in \(P\),
   \[
   |\mathcal F_n(P;q,\sigma)-\mathcal F_m(P;q,\sigma)|
   \le e_m(q,\sigma)+\frac{m(m-1)}{2n}.
   \]
   First keep \(m\) fixed and send both large indices to infinity to establish the uniform Cauchy property; then send \(n\to\infty\) in the displayed inequality to obtain \(|\mathcal F-\mathcal F_m|\le e_m\). Use the dependency's locally uniform errors and Step 1 to prove joint continuity in \(P,q\). Do not identify repeated-index observations with fresh private noise.

3. [x] **Moment compactness.** On \(M_2\le C\), exchangeability and Markov's inequality give \(P(|\theta_i|>R_i)\le C/R_i^2\). Choose \(R_i\) with summable error as small as desired. The corresponding product of compact mean intervals, finite tag sets, and compact covariance intervals gives tightness. Apply the standard probability compactness theorem on the Polish parameter space and the closed constraints from Step 1. Prove lower semicontinuity of \(M_2\) by bounded continuous truncations of \(\theta_1^2\). Conclude compactness of every moment sublevel, including \(C=0\).

4. [x] **Both finite/completed supremum comparisons, with penalty.** For each deterministic finite lawful tagged model, replace alternative-tagged zeros by positive means tending to zero. Step 1 gives FDR convergence and empirical second-moment convergence, so its FDR minus its moment penalty is bounded by the corresponding canonical finite supremum. Condition on an arbitrary \(P\), integrate this inequality for each finite prefix, and use \(\mathbb E n^{-1}\sum_i\theta_i^2=M_2(P)\) and Step 2. For the reverse inequalities, fix a deterministic finite canonical model and generate an infinite array by iid sampling its coordinate indices; use the original residual covariance between sampled indices, including covariance one between duplicate copies. This is a lawful exchangeable parameter law, with the finite model's empirical moment. Compression applied to iid sampled coordinates shows its completed FDR equals that finite model's FDR. This proves both supremum identities and the equality after restricting the unpenalized supremum to \(\mathfrak P_2\). No deterministic finite approximation of a general outer mixture is selected.

5. [x] **Fixed-level attainment and zero-penalty limit.** A zero-mean, all-true, perfectly correlated model has FDR \(q\) and moment zero, hence \(A_{\eta,\sigma}\ge q\). A maximizing sequence can be restricted to a finite moment cap because \(\mathcal F\le1\) and \(\eta>0\). Steps 2--3 imply upper semicontinuity of \(\mathcal F-\eta M_2\) and attainment. Every maximizer satisfies \(\eta M_2\le1\). The finite models in Step 4 show \(A_{\eta,\sigma}\uparrow W_\sigma\) as \(\eta\downarrow0\). Prove \(\eta M_2(P_\eta)\to0\) either by comparing the optima at \(\eta/2\) and \(\eta\), or directly from \(0\le\eta M_2(P_\eta)=\mathcal F(P_\eta)-A_{\eta,\sigma}\le W_\sigma-A_{\eta,\sigma}\). Deduce \(\mathcal F(P_\eta)\to W_\sigma\). Retag every alternative zero as true, coupling the same observations: ranks and moments are unchanged and each finite FDP only increases. Step 2 transfers this to \(\mathcal F\); maximality makes the retagged law another maximizer. This selects a canonical maximizer without characterizing every maximizer.

6. [x] **A direct logarithmic bound including terminal rank one.** Put \(\tau=\sqrt{1-\sigma^2}\), \(U=S^{-1}(q)\ge1\), and condition on the common \(Z=z\) and parameters. For a rejected true coordinate with \(p_i\le qR_n/n\), use \(1/R_n\le q/(np_i)\), valid also when \(R_n=1\). Summing and using \(D_n\le1\), conditional marginal stochastic domination at true means \(\theta_i\le0\), and the decreasing function \(t^{-1}\mathbf1_{\{t\le q\}}\), proves the bound in clause 3 with
   \[
   J(z)=\int_U^\infty\frac{\phi((u-\sigma z)/\tau)}{\tau S(u)}\,du.
   \]
   Prove \(J(z)<\infty\) for fixed \(z\) by completing the square. To integrate its truncated contribution, split \(Z>U\), which costs exactly \(q\), and use the elementary bivariate normal conditioning identity
   \[
   \mathbb E[J(Z)\mathbf1_{\{Z\le U\}}]
   =\int_U^\infty\frac{\phi(u)}{S(u)}
       \Phi\!\left(\frac{U-\sigma u}{\tau}\right)\,du.
   \]
   On \([U,2U/\sigma]\), Mills' inequality \(\phi(u)/S(u)\le u+u^{-1}\) bounds this by \(C_\sigma(1+U^2)\). On \([2U/\sigma,\infty)\), use \(\Phi((U-\sigma u)/\tau)\le\Phi(-\sigma u/(2\tau))\) and its Gaussian tail to get another finite \(C_\sigma\). Therefore \(\mathbb E D_n\le C_\sigma q(1+U^2)\), uniformly in parameters and dimension. Derive the needed elementary Mills bounds by integration by parts, including \(U^2\le C(1+\log(1/q))\), and pass to \(\mathcal F\) by Step 2. No microscopic-rank lemma is used here.

7. [x] **Normalized attainment and vanishing moment cost.** From Step 6 and the two-sided Mills comparison \(U\asymp\sqrt{\log(1/q)}\), prove uniformly in \(P\)
   \[
   \mathcal L_{\eta,\delta}(P,q;\sigma)
   \le C_\sigma\sqrt{\log(1/q)}-\delta\log(1/q),
   \]
   after enlarging the constant on the allowed level interval. The right side tends to minus infinity. The zero-moment model at \(q_{\max}\) gives a fixed finite lower comparison value. Exclude all sufficiently small levels, then bound moments on maximizing sequences using \(\eta>0\) and the remaining compact level interval. Steps 2--3 prove finite attained maximum. The same coercivity without the moment term proves \(L_{0,\delta,\sigma}<\infty\). At any fixed level, Step 4 supplies finite-moment laws approaching its unpenalized supremum, so monotone convergence of suprema gives \(L_{\eta,\delta,\sigma}\uparrow L_{0,\delta,\sigma}\). For any maximizing pair, compare penalties \(\eta/2\) and \(\eta\) at that same pair to obtain
   \[
   \eta M_2(P_{\eta,\delta})\le
   2(L_{\eta/2,\delta,\sigma}-L_{\eta,\delta,\sigma})\to0.
   \]
   Do not send \(\delta\) to zero or assert a uniform value bound in that limit.

8. [x] **Exact competitor inequalities and removal of loading.** Subtract the maximizing objective from any lawful competitor objective to obtain both inequalities in clause 4, retaining the normalized level factors exactly. For bounded pre-observation lawful mean velocities, expand \((\theta_1+\epsilon b_1)^2\) and integrate; finite second moment makes the linear term integrable. State the sign restriction at a retained true zero explicitly. Means and marks fixed under a lawful direction/covariance change give zero moment difference. For clause 5, every fixed-loading finite covariance is admissible for the unrestricted supremum, hence \(W_\sigma(q)\le F_1(q)\). Conversely, for each fixed unrestricted finite model, smooth its covariance to \((1-\sigma^2)\Sigma+\sigma^2\mathbf1\mathbf1^{\mathsf T}\); Step 1 yields its FDR limit as \(\sigma\downarrow0\). Take the lower limit before taking the finite-model supremum. No uniform compression as \(\sigma\downarrow0\), rate, or independent-block closure is required.

9. [x] **Encode marks and invoke only the registered unmarked theorem.** Use the explicit injective Borel code
   \[
   c(\theta,1)=\frac{-\theta}{3(1-\theta)}\quad(\theta\le0),\qquad
   c(\theta,0)=\frac{2+\theta/(1+\theta)}3\quad(\theta\ge0).
   \]
   Its image is \([0,1/3)\cup[2/3,1)\) and its inverse is Borel. Set \(D_{ij}=C_{ij}\) off the diagonal and \(D_{ii}=1+c(\theta_i,\ell_i)\). This remains a jointly exchangeable PSD array. Apply the approved general diagonal-correction theorem to \(D\), obtaining a measurable mixture of component array laws, each generated by iid \((h_i,a_i)\) with diagonal \(\|h_i\|^2+a_i\). Original support properties transfer to almost every component law by integrating the probabilities of their complements. Decode the lawful mark from \(D_{ii}-1\) there; the decoding is a Borel map of full arrays, defined arbitrarily outside its lawful Borel domain. This yields a measurable kernel of marked component laws. At this point do not assert a jointly measurable choice of iid generators.

10. [x] **Prove unit-ball support component by component.** For any one of the preceding good components, the iid Hilbert marginal satisfies \(|\langle h,h'\rangle|\le1\) almost surely under its product measure. If positive mass lay outside the closed unit ball, a countable cover by sufficiently small open balls would give one positive-mass ball on which every pair has inner product greater than one: at a center \(h_0\) of norm greater than one, choose \(r>0\) with \(\|h_0\|^2-2r\|h_0\|-r^2>1\). This contradicts the product bound. Thus \(\|h\|\le1\) almost surely. Push the iid pair law through the decoded diagonal mark and \(v=h\) to obtain, for this component, some law \(\mu\) on the lawful closed space \(E\subset\mathbb R\times B_{\ell^2}\times\{0,1\}\). Its marked Gram law has off-diagonal \(\langle v_i,v_j\rangle\) and unit diagonal. The diagonal correction has been absorbed into the private variance, rather than discarded.

11. [x] **A continuous generating map and the exact lifting problem.** Give \(E\) its strong Polish topology. Let \(\Psi:\operatorname{Prob}(E)\to\operatorname{Prob}(\Omega_{\rm array})\) send \(\mu\) to its iid-generated marked Gram law with unit diagonal. Prove continuity using weak continuity of iid countable product laws, continuity of every finite Gram map, and countable-product tightness. The relation \(R=\{(Q,\mu):\Psi(\mu)=Q\}\) is closed between Polish spaces. The preceding component argument shows that the probability law \(\lambda\) of component marked-array laws is supported on its projection, in the completed sense justified in Step 12. Do not use a general Borel-section assertion for a continuous surjection.

12. [x] **Prove probability-completed projection measurability inline.** For a finite Borel probability \(\lambda\) on a Polish space \(X\), set \(c(A)=\inf\{\lambda(B):A\subset B,\ B\text{ Borel}\}\). A countable intersection of approximating envelopes attains this infimum. A Borel subset of such a minimal envelope disjoint from \(A\) has measure zero. Consequently, for increasing \(A_n\), minimal envelopes are increasing modulo null sets and \(c(\bigcup A_n)=\lim c(A_n)\); give both inequalities. For a nonempty closed relation in \(X\times Y\), use complete compatible metrics and construct a continuous surjection from \(\mathbb N^{\mathbb N}\) onto that relation: recursively cover each nonempty closed cell by countably many nonempty closed subcells of diameter at most \(2^{-n}\), repeating children if necessary; nested cells determine a unique point and every point has a branch. Project to obtain a continuous \(F:\mathbb N^{\mathbb N}\to X\) whose depth-\(n\) cylinder images have diameter at most \(2^{-n}\). At each depth retain only finitely many children of each retained node. Continuity from below of \(c\) permits choosing these children so that outer content falls by at most \(\epsilon2^{-n-1}\). The finite unions of closures of retained cylinder images form decreasing closed sets with measure at least \(c(F(\mathbb N^{\mathbb N}))-\epsilon\). Their intersection is compact: it is closed in a complete metric and totally bounded by the shrinking finite covers. A finite-branching tree argument supplies, for each point of the intersection, one compatible branch; continuity and shrinking diameters put the point in the actual image of \(F\). Let \(\epsilon\downarrow0\). A countable union of these compact inner approximations differs from a minimal Borel envelope by a null Borel set. Hence every projection of a closed Polish relation is \(\lambda\)-completion measurable. Handle the empty relation separately. This is a proved subargument, not an imported selection theorem.

13. [x] **Construct the completion-measurable section.** In a complete compatible metric on \(\operatorname{Prob}(E)\), fix countable dense centers. For \(Q\) in the projection of \(R\), recursively choose the first closed ball of radius at most \(2^{-n}\) whose intersection with all previous chosen balls and the fiber \(R_Q\) is nonempty. The closed balls cover the space. For each fixed finite history, its hit set is a projection of a closed relation, and hence measurable in the completion of \(\lambda\) by Step 12. Thus the countably valued choices are completion measurable. The nested nonempty closed fiber cells have diameters tending to zero, and their centers converge to their unique fiber point. Prove this limit is a completion-measurable \(\mu(Q)\) with \(\Psi(\mu(Q))=Q\); define it arbitrarily on the completed null complement. Push forward completed \(\lambda\) to get an actual random directing probability. This supplies the target's mixture representation without silently strengthening the source theorem's component-law formulation.

14. [x] **Observation representative and moment identity.** On \(\ell^2\) use the Gaussian series \(X(v)=\sum_k v_k\xi_k\) where it converges, and zero elsewhere. The convergence set and representative are jointly measurable. For fixed \(v\), square summability gives almost sure and mean-square convergence; Fubini against the directing law gives almost sure validity for almost every parameter and for the countable iid parameter sequence. Take all innovations independent of the directing law and parameter sampling. With independent \(\zeta_i,Z\), compute the conditional covariance of the displayed observation in the target: its diagonal is one and its off-diagonal is \((1-\sigma^2)\langle v_i,v_j\rangle+\sigma^2\). Finite linear combinations are Gaussian, including singular cases. This proves conditional Gaussian equivalence. Tonelli gives \(M_2(P)=\mathbb E\int\theta^2\,d\mu\), allowing infinity.

15. [x] **Affinity, integrability, and maximum-component selection.** At each finite \(n\), FDR is affine under parameter-law mixtures. Step 2's uniform convergence or bounded convergence passes this to \(\mathcal F(P)=\mathbb E\mathcal F(P_\mu)\). Combine with Step 14's moment identity. At any attained finite-moment maximum, component moments are finite almost surely; every such component is a lawful competitor, so its nonnegative objective gap from the global maximum has expectation zero. Pick a component of zero gap. Apply the same argument to a normalized maximum with its optimizing level held fixed. This selects a deterministic directing law at each maximum. Finally push that directing law through zero-mean canonical retagging as in Step 5, yielding a canonical deterministic maximizing component. Do not infer finite support, positive definiteness, or simultaneous deterministic finite value/moment recovery of arbitrary mixtures.

## Verification

Steps 1--3 establish clause 1. Steps 4--5 establish clause 2, including both directions of the penalized equality, existence, all stated limits, and the existential canonical-tag conclusion. Steps 6--7 prove clause 3 with an independent bound that includes actual terminal rank one and with no \(\delta\downarrow0\) assertion. Step 8 proves clauses 4--5. Steps 9--15 prove the full measurable marked representation, Gaussian observation equivalence, moment disintegration and deterministic maximum-component selection in clause 6.

The delicate checks are the exact-copy sampling interpretation in Step 2, the order of finite-model supremum comparisons in Step 4, the truncation of the common Gaussian in Step 6, and all three parts of measurable lifting (projection measurability, closed generating relation, and fiber selection). Each has a concrete argument above and must be independently verified during execution. Failure of any one is a failure of this plan, not permission to omit a clause or alter the statement.

## Assumed definitions

All definitions in the supplied target context are approved; no draft definition or unproved dependency is assumed. Use the approved compression and Wasserstein-continuity dependencies only within their fixed-\(\sigma\) scope. Use the registered approved Panchenko theorem only for its stated unmarked, general-diagonal-correction component-law mixture conclusion. No proof was provided in that source node, so the plan does not list it under `adapts`.

Standard measure/probability foundations used are weak convergence and tightness on Polish spaces, probability compactness, finite-dimensional Gaussian square-root coupling, product probability measures, Tonelli, and almost sure convergence of square-summable independent Gaussian series. The specialized analytic-projection and measurable-lifting facts needed here are proved in Steps 12--13 rather than assumed as unnamed source results. All parameter randomness is independent of Gaussian innovations; observations retain their lawful dependence on parameters.

## Library analogue check

Native library searches for exchangeable compactification, measurable projection/selection, and Gaussian BH logarithmic/Mills bounds found no additional applicable proof. The listed positive-dependence Simes analogue has no Proof section and its positive-dependence hypotheses do not cover the present arbitrary covariance models. The registered Panchenko node likewise has no Proof section; its approved statement is a permitted dependency, and the marked extension is proved here. No unregistered library conclusion is used and no absent or sketched proof is labeled adapted.

## Outcome

The complete proof of all six clauses is under `## Proof` in [Cross-dimension marked-array compactification and penalized Gaussian BH extrema](../assets/gaussian_bh_exchangeable_array_variational_compactification.md). Proof part 1 establishes checklist items 1--2; part 2 establishes 3--5; part 3 establishes 6--7; part 4 establishes 8; parts 5--6 establish 9--13; part 7 establishes 14--15. The target statement and frontmatter are unchanged, with status still `draft`.

The proof uses the approved fixed-loading uniform-compression theorem and the registered approved general diagonal-correction Dovbysh--Sudakov mixture theorem as external dependencies. The marked extension, unit-ball support, probability-completed projection argument, measurable section, Gaussian representative, moment disintegration and maximum-component selection are written out in the proof. No draft definition, finite-support assertion, positive-definiteness assertion, FDR derivative, main order bound or limit uniform in the loading or logarithmic penalty is assumed.

Scoped research-maintenance validation reported 0 problems (with the existing older-schema advisory); the asset links preview reported 0 proposed files and 0 review items. The notation audit used all seven approved definitions in the supplied context and the configured macros/notation files (both contain comments only); local auxiliary symbols are defined, and no conflicting or missing relationship was found. Independent native proof verification remains the next research-loop gate.


## Verdict

confirmed

Independent review of the statement, complete proof, approved dependency statements and source definitions confirms all six clauses. The producing plan's reasoning and author ideas were not used.

The finite Gaussian square-root coupling is valid at singular covariances: every possible BH decision change lies on one of finitely many marginal threshold-null events. This covers the actual largest non-strict rank, ties, zero rejection and terminal rank one. The compression application uses unit-vector realizations and exact copies at repeated indices; exchangeability on distinct samples gives (P1), uniform completion and local-in-level continuity. Coordinate tightness, lower semicontinuity of the second moment, canonical approximation with moment convergence, iid replication and upper semicontinuity justify the faithful suprema and attained penalized maxima.

The decreasing conditional marginal bound (P4) includes every positive rank. Its density transformation, Mills inequalities and truncated joint-normal identity (P6) yield the stated logarithmic bound. The resulting uniform level coercivity and moment compactness establish normalized attainment; the half-penalty comparison proves vanishing moment cost for arbitrary maximizing choices. The exact lawful comparisons and loading-removal limit follow with their stated finite-moment and fixed-level restrictions.

For the marked representation, the nonnegative diagonal code preserves all source-theorem hypotheses; decoding is Borel, and the off-diagonal product bound forces unit-ball support. The projection proof is valid: Borel envelopes give continuity from below of outer content, finite-tree pruning gives compact subsets of the projection with arbitrarily close content, and finite-measure continuity from above completes the measurability argument. Successive closed-ball hit tests therefore give a section on the completed component-law probability space without assuming a Borel generator selection. The measurable Gaussian series, Fubini validity at sampled vectors, retained private variance, Tonelli moment identity and affine bounded FDR limit establish conditional Gaussian equivalence and integrable zero-gap component selection, including canonical retagging. No essential gap or additional hypothesis was found; no repair was made.
