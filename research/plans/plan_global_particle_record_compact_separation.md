---
id: plan_global_particle_record_compact_separation
title: >-
  Record-weight compactness and finite-coordinate separation for global particle
  potentials
type: plan
status: succeeded
target_asset: gaussian_bh_global_particle_potential_certificate
inspired_by:
  - idea_4be6ed0aaaec
adapts: []
proof_digest: ea01af150eac8565eb0ef51118075cf08ecade81d0700310ce89333755f4a025
statement_digest: 5c18aaddd67e681c31bff48ee957bb54c0681a855d0bfd853d043ea65e593f90
dependency_digests:
  gaussian_bh_private_cutoff_particle_mass_variation: 8345cf59553f81f078aa75b8209e82e7b444527650ffec26a456254734403e01
  gaussian_bh_averaged_signed_mean_level_complementarity: e3dcfc508ee344fb52d4454b0676313187354eefcb69339fb28a33f503d7f350
  gaussian_bh_private_noise_cutoff_signed_transport_variation: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
  gaussian_bh_exchangeable_array_variational_compactification: 82e91305e89e8c5f50be87b28d54dc08a251a8adf76f9407859ccdd4f3536aee
  gaussian_bh_hybrid_particle_potential_convention: 44bb848d3c12d87628ebdcb7a237000a1acd371405766aa91e48b52b80e6abec
  gaussian_bh_private_smoothed_directing_population: 0fbae7cf085365821031dfb661f7b64a292089719262bcc88d2b940ede32bad0
  gaussian_bh_signed_near_active_gradient_cones: daef18b4707d34b07e148fff17d26c059ab590109aab8317dc11d00224f3a9e0
  gaussian_bh_marked_exchangeable_parameter_array: 92f2b0b67ee27711461bffe8724ed1bc06dd5ba6251b57e671d1584b0754c805
verified_proof_digest: ea01af150eac8565eb0ef51118075cf08ecade81d0700310ce89333755f4a025
---

## Goal

Target: [Global averaged particle-potential certificate at regularized Gaussian BH maxima](../assets/gaussian_bh_global_particle_potential_certificate.md).

Prove every clause for the given actual canonical deterministic maximum and its fixed positive regularizers. Use a conditional record-weight estimate, compactness of continuously extended averaged potentials, and direct finite-coordinate separation. Obtain mean normal conditions from the same global potential's contact points rather than independently selecting a mean-gradient pair.

## Source and method check

The stage pack supplies no existing pending plan or failed plan for this target. Native library searches for particle-potential compactness/separation and finite-coordinate cone separation found no matching global-potential theorem. The closest envelope result, lib_bernhard_rapaport1995_compact_danskin, has no Proof section available to adapt. Its statement is not a declared prerequisite and is not used. The target's approved mass-variation prerequisite already supplies the all-active derivative. The scalar L1 library results do not establish compactness in the present evaluation topology and are not additional black boxes. This plan claims no new general quasidifferential principle: Step 9 proves the particular compact-set/cone argument directly.

## Plan

1. [x] **Fix the lawful setting and versions.** Fix the deterministic law, level, regularizers and common separable Hilbert space before Gaussian innovations. Use the approved mass-variation and signed-variation statements for the actual largest rank, suffix-minimum survival law, positive smooth conditional density, endpoint conventions, local quantile regularity and exact extremal inequalities. Obtain conditional assertions on one event for the population and the countable deterministic particle/rank families used. For any additional fixed particle or finite competitor use its own Fubini event. Use the jointly measurable series version; do not assume a samplewise continuous isonormal field on the entire Hilbert ball or an optimum conditional on that field.

2. [x] **Prove record geometry and hybrid selection.** Differentiate to obtain \(Q_X'(t)=-1/h_X(Q_X(t))\), \(u_q'(t)=-m(u_q(t))/t\), and the target formula for \(B_X'\). Interior active points are ordinary local minima, so \(B_X'=0\). Prove locally that the suffix minimum is locally Lipschitz and nondecreasing, is locally constant where \(B_X>M_X\), and satisfies \(M_X'=B_X'\ge0\) at almost every contact point \(B_X=M_X\). The chain rule, compact-rank exhaustion and the approved survival absolute continuity yield
   $$
   \int_a^1\phi(M_X(r))M_X'(r)\,dr\le1.
   $$
   On the measurable contact set include the exact boundary candidate. Elsewhere enumerate rationals strictly above \(r\) satisfying both hybrid inequalities. Continuity of \(B_X,B_X'\) near an interior minimum supplies qualifying rationals converging to it. Prove nonemptiness almost everywhere and approximation of every active point, including the boundary and tied minima. First qualifying and first nearly maximizing members of this countable list give jointly measurable selectors without an additional measurable-selection black box.

3. [x] **Bound the entire conditional inverse-density weight.** Define
   $$
   A_{\pm,j}^t(X)=\frac1\sigma\int_a^1
   w_{X,\pm}(r)\phi(M_X(r))
   \frac{dr}{h_X(Q_X(t(X,r)))}.
   $$
   Rational candidates satisfy \(1/h_X(Q_X(t))\le m(1)/a+\sigma/j\). Boundary candidates satisfy \(1/h_X(Q_X(r))=m(u_q(r))/r+\sigma M_X'(r)\) almost everywhere. Using \(\int|w_X|\le T_a\), \(|w_X|\le W_a\) and Step 2 prove, simultaneously for every hybrid selector and \(j\ge1\), the conditional estimate
   $$
   0\le A_{\pm,j}^t(X)\le
   \frac{T_a}{\sigma\sqrt{2\pi}}
   \left(\frac{m(1)}a+\sigma\right)+W_a=K_0.
   $$
   This bound is independent of \(X,\pi\) and the selector. Deduce \(0\le G_\pm^t(x)\le K_0\) at every fixed particle and \(0\le c_\pm^t\le T_am(1)/(\sigma\sqrt{2\pi})\). Retain this integrated record estimate instead of assuming a global bound on \(1/h_X\).

4. [x] **Construct smooth continuous averaged versions.** Bound \(K\), its first two real \(\theta\) derivatives, and the changes of \(K,\partial_\theta K\) under center/variance changes by explicit Gaussian derivative suprema and \(c_s\ge s\). Use
   $$
   |c_s(v)-c_s(v')|\le(\tau_s^2/s)\|v-v'\|,
   \qquad \mathbb E|X(v)-X(v')|\le\|v-v'\|.
   $$
   These kernel estimates are uniform in the quantile argument. Multiply them by the conditional total weight of Step 3 before taking the background expectation. Establish common bounds \(|\partial_\theta G|\le C_sK_0\), \(|\partial_\theta^2G|\le C'_sK_0\), and a common strong-parameter modulus for \(G,\partial_\theta G\). Justify derivatives by dominated difference quotients. Begin on a countable strong dense parameter set, extend the averaged functions continuously, and prove agreement with the expectation at each fixed particle by the same Gaussian L1 estimates. Establish representative invariance this way, without a common continuity event for \(X(v)\). For analyticity, derive complex Gaussian-tail and derivative bounds on every strip \(|\operatorname{Im}\theta|\le b\), uniformly in real center and \(c\ge s\). Step 3 then bounds each averaged analytic extension on that strip. Use its local power series and these bounds to prove preservation under the convex limits below, on either tag.

5. [x] **Prove compactness in exactly the declared topology.** Diagonalize the bounded coordinates \((G(x),\partial_\theta G(x),c)\) on a countable strong dense set \(\mathscr D\). The common moduli uniquely extend every coordinate limit to the whole strong domain. Use the fundamental theorem in \(\theta\) and bounded convergence to identify the limiting derivative, retaining the derivative bounds and analytic strip estimates. On this common bounded family prove that convergence on \(\mathscr D\) is equivalent to all prescribed evaluations. A metric formed from bounded weighted sums of the countable coordinates and the diagonal construction prove compactness of the ambient family closure. This argument does not require a compact strong Hilbert ball. Convex combinations retain every estimate, so each closed convex hull \(\mathscr C_j^\pm\) is nonempty compact convex. Nestedness and compactness give nonempty compact intersections \(\mathscr C^\pm\). Pointwise convergence and the uniform bounds give continuity of \(\int G\,d\pi\) and \(\int\partial_\theta G\,d\pi\) on these metrizable compact families. Therefore centering is continuous there, as are all required finitely supported mass pairings. The quadratic penalty is a fixed coordinate function and need not belong to the compact bounded family.

6. [x] **Prove exact all-active supports.** For a fixed finitely supported lawful \(\nu\), \(\rho\ge0\) and finite \(\lambda\), Fubini rewrites a generator's pairing as the integral of
   $$
   \frac1\sigma w_{X,\pm}(r)\phi(M_X(r))
   \left[
   \rho\frac{H_{\nu,X}(Q_X(t))-H_X(Q_X(t))}{h_X(Q_X(t))}
   +\lambda m(u_q(t))
   \right].
   $$
   Prove that its supremum over measurable hybrid selectors is the integral of the pointwise supremum using first nearly maximizing candidates from Step 2. Candidate suprema converge pointwise to the maximum over the full active set: near-minimizers cannot escape to \(t=1\), where \(B_X\to+\infty\); all their cluster points are active, and every active point is approximable. For domination use \(|H_\nu-H|\le1\), \(m_t\le m(1)\), and the pointwise majorant consisting of a constant times \(|w_X|\phi(M_X)\) plus \(W_a\phi(M_X)M_X'\) on the boundary record set. Step 3 bounds its conditional integral independently of \(X\). This justifies the rank and Gaussian interchanges. Closure and convexification leave the support unchanged by Step 5. Finally, maximizing elements of nested compact hulls have convergent subsequences, proving
   $$
   h_{\mathscr C^\pm}(\rho(\nu-\pi),\lambda)
   =\lim_j h_{\mathscr C_j^\pm}(\rho(\nu-\pi),\lambda)
   $$
   and the exact all-active maximum integral in the target. Include every tied minimum and every finite \(\lambda\), even when only one level sign is lawful. Do not identify the positive and negative optimizing selectors or infer a linear derivative.

7. [x] **Construct the bulk potential and full mass derivative.** The coefficient multiplying its kernel has absolute value at most \(1/a\). Apply the fixed-particle Gaussian L1 and derivative estimates of Step 4 to prove boundedness, strong continuity, \(C^1\) regularity and analytic extension of \(P_0\), with the prescribed zero exceptional-rank convention. Differentiate only the particle kernel, keeping the base law and actual rank fixed, to obtain \(\partial_\theta P_0=\mathfrak b\) from the approved averaged complementarity statement. The approved fixed-rank mass derivative integrates to \(\rho\int P_0\,d(\nu-\pi)\). Combine it with Step 6 and the approved all-active envelope derivative to get exactly
   $$
   \dot{\mathcal F}^a
   =\rho\int P_0\,d(\nu-\pi)
   +h_{\mathscr C^+}(\rho(\nu-\pi),\lambda)
   -h_{\mathscr C^-}(\rho(\nu-\pi),\lambda).
   $$
   Retain its signed terms and full FDP.

8. [x] **Center before separating.** Write \(L=\beta F^a-\delta qU\). The approved normalized mass extremal inequality becomes
   $$
   \rho\int\overline P_0\,d\nu
   -\eta qU\rho\int(\theta^2-M_2(\pi))\,d\nu
   +h_{\mathscr C^+}(\rho(\nu-\pi),\lambda)
   -h_{\mathscr C^-}(\rho(\nu-\pi),\lambda)-\lambda L\le0.
   $$
   Verify the centered moment shift and the restriction \(\lambda\le0\) only at the upper level endpoint. Use continuity of centering on the established compact families. Do not extend \(\pi\)-integration as a continuous functional on an unrestricted product space.

9. [x] **Prove finite-coordinate cone separation directly.** Fix any \((G_+,c_+)\in\mathscr C^+\). Map the compact convex set \(\mathscr C^-\) into real coordinates indexed by lawful particles and one level coordinate by
   $$
   z_-(x)=\overline P_0(x)+\overline G_+(x)-\overline G_-(x)
   -\eta qU(\theta(x)^2-M_2(\pi)),\qquad
   z_-^{\rm lev}=c_+-c_--L.
   $$
   The image is compact by Step 5. The desired closed cone requires all particle coordinates to be nonpositive, and the level coordinate to be zero in the interior or nonnegative at \(q=q_{\max}\). If the image misses the cone, compactness and the finite-intersection property produce finitely many particle constraints, together with the level constraint, already infeasible. In that finite-dimensional projection prove strict separation by the closest-point argument for a compact convex set and a disjoint closed convex cone. Its coefficients are \(\alpha_i\ge0\) on particle coordinates, and \(\lambda\in\mathbb R\) in the interior or \(\lambda\le0\) at the endpoint. Set \(\rho=\sum_i\alpha_i\), \(\nu=\sum_i(\alpha_i/\rho)\delta_{x_i}\) when \(\rho>0\); otherwise use the pure level direction. Strict separation says the fixed positive pair's pairing exceeds the negative support with exactly the scalar terms of Step 8. This contradicts Step 8 because the positive support is at least that fixed pairing. Obtain a matching negative pair satisfying all coordinates simultaneously. No derivative coordinates, general quasidifferential theorem, finitely additive gradient or infinite-support separating functional is used.

10. [x] **Recover contact and coherent mean normals for this pair.** Define \(\mathcal P,P,\kappa\) as in the target. Step 9 gives \(P(x)\le\kappa\) at every lawful particle. Its integral is equality by centering and the finite second moment; hence \(P=\kappa\) \(\pi\)-almost everywhere. The level coordinate gives \(\Lambda=L\) in the interior and \(\Lambda\ge L\) at the endpoint. At each contact point with \(\theta<0,\ell=1\) or \(\theta>0,\ell=0\), the differentiable function \(P\) has a local maximum on a lawful open mean interval and derivative zero. At a true zero contact point its restriction to \(\theta\le0\) gives a nonnegative derivative at zero. Canonicality eliminates false-tagged zero points from the almost-everywhere assertion. Thus this same pair has \(\Psi=2\eta qU\theta\) off \(E_0\) and \(\Psi\ge0\) on \(E_0\). This uses deterministic particle comparisons and does not select an unrelated mean-gradient certificate.

11. [x] **Identify the same pair's exact total flux.** For every generator, \(\partial_\theta K=k\) and posterior mass normalization give
   $$
   \int\partial_\theta G_\pm^t\,d\pi
   =\frac1\sigma\mathbb E_X\int_a^1w_{X,\pm}(r)\phi(M_X(r))\,dr.
   $$
   Justify differentiation and Fubini by Steps 3--4, and pass to convex limits using the derivative-integral continuity in Step 5. The bulk derivative has integral zero because conditionally
   \(\int(\ell-h_{0,X}/h_X)k_{X,x}\,d\pi=0\).
   Subtract to obtain \(\int\Psi\,d\pi=\Gamma_a\). For the survival identity write
   \(g_X(R)=\int_a^1w_X(r)\mathbf1_{\{R\ge r\}}\,dr\)
   and use the actual-rank event \(\{R\ge r\}=\{Z\ge M_X(r)\}\) with
   \(\mathbb E_Z[Z\mathbf1_{\{Z\ge M\}}]=\phi(M)\).
   Signed Fubini follows from \(\int|w_X|\le T_a\) and Gaussian integrability. This yields exactly the target's second expression for \(\Gamma_a\), without an unlawful upward mean velocity at a retained true zero.

12. [x] **Prove the tag price and finite comparison.** Each generating \(G_\pm^t\) is tag independent, and evaluation limits preserve this. Subtract the bulk formulas at the two tags to obtain the target's nonnegative \(T(\theta,v)\); the quadratic penalty cancels. This holds for the analytic extensions on either tag, while global comparisons stay lawful. At each true-zero contact point compare with the lawful particle \((h,v,0)\) for any fixed \(h>0\), and substitute the tag identity at zero to get
   $$
   \mathcal P(h,v,0)-\mathcal P(0,v,0)
   \le T(0,v)+\eta qUh^2.
   $$
   Since
   \(\int_{E_0}K_{X,0,v}(Q_X(R))\,d\pi\le V_X(Q_X(R))\),
   multiplying by the nonnegative cutoff/rank factor and taking expectations gives \(\int_{E_0}T\,d\pi\le F^a\). Integrate the finite comparison to obtain its final bound, keeping the factor \(\pi(E_0)\). All inserted particles and the fixed \(h\) are parameter-level choices before noise.

## Verification

Steps 1--2 prove actual-record geometry, measurable hybrid nonemptiness, and approximation of boundary and tied minima. Steps 3--5 prove the explicit bound, uniform \(C^1\) and second-derivative bounds, strong equicontinuity, analytic preservation, compact potential sets and continuous centering. Step 6 proves the all-active support representation and nested-hull limits with all interchanges. Steps 7--9 give the exact mass derivative and finite-coordinate separation with the centered penalty and correct level signs. Steps 10--11 give the global certificate, contact, mean normals and total flux for one matching pair. Step 12 gives the tag identity and both finite comparison bounds. Explicitly check the signs at \(q=q_{\max}\) and at a true zero mean.

The execution gates are the conditional bound of Step 3, preservation of analytic/derivative coordinates in Step 5, both directions of the support limit in Step 6, and the finite-projection contradiction in Step 9. Failure is an obstruction to this plan, not permission to weaken the statement or assume a missing theorem. No derivative is passed through finite-model, private-noise or cutoff limits.

## Assumed definitions

Use exactly the four definitions in the target's uses_definitions. The pack identifies all four as approved, including the hybrid convention despite the target's older descriptive word “draft.” Assume exactly the target's four theorem prerequisites, all approved in this pack: particle-mass variation, averaged signed complementarity, complete signed transport variation, and marked-array compactification. No unproved draft theorem or additional library conclusion is assumed. The risk idea [Global particle certificates need continuous averaged versions, not a pathwise continuous isonormal field](../ideas/idea_4be6ed0aaaec.md) motivates Steps 1, 4 and 5; its proposed estimates are proved here rather than treated as established facts.

## Difference from failed plans

No failed plan for this target is supplied in the current stage pack. The search summaries leave global compactness and matching unresolved. This plan supplies a concrete conditional record-weight estimate, dense-coordinate compactness and finite-coordinate separation to address those obligations; excluded search candidates are not treated as proofs.

## Outcome

Complete proof is in [Global averaged particle-potential certificate at regularized Gaussian BH maxima](../assets/gaussian_bh_global_particle_potential_certificate.md), under `## Proof`; its frontmatter, statement, and prior scope text are unchanged, and the asset remains draft. The proof establishes all twelve checklist steps: its Sections 1--2 establish versions, record geometry, hybrid selection and the conditional weight bound; Sections 3--5 establish smooth analytic averaged potentials, compactness, continuous centering and all-active supports; Sections 6--7 establish the exact mass derivative and direct finite-coordinate separation; Sections 8--10 establish contact, coherent same-pair mean normals and total flux, and the explicit tag price and finite comparisons.

The proof assumes precisely the four declared approved prerequisites and the target's four approved definitions. No draft theorem, new hypothesis, library black box, finitely additive gradient, or samplewise continuous isonormal process is assumed. In particular, at the upper level endpoint the level cone is nonnegative and its separating coefficient is nonpositive; at a true zero mean the contact derivative is nonnegative. Regularizers are fixed throughout. Independent verification, the separate uniform zero-null flux bound and all regularizer-removal/main-bound obligations remain outstanding.


## Verdict

confirmed

Independently checked the complete ten-step proof against every clause of the statement and the four approved prerequisite statements in the verification context pack; the producing plan reasoning was not read. The contact/suffix-minimum argument proves the boundary derivative identity and the integrable record term, giving the conditional reciprocal-density weight bound uniformly in the background. The hybrid candidate lists are measurable, nonempty almost everywhere, and approximate every active minimum, including contact points and ties.

The averaged Gaussian increment estimates establish strong continuity and continuous mean derivatives without a samplewise continuous isonormal field. Uniform complex-strip bounds preserve analyticity under convex evaluation limits. Countable dense evaluations, the common moduli, and derivative coherence prove compactness in the specified topology; bounded domination makes the fixed-law integral pairings and centering continuous. The candidate majorant and compact active-set approximation justify both signed support formulas and their nested-intersection limits.

The finite-coordinate compactness/separation argument has the correct particle and level polar signs, includes pure-level directions, and retains the centered moment shift. Integrating the global comparison gives contact almost everywhere; lawful mean comparisons then give the normal conditions for the same selected pair. Posterior normalization and derivative-integral continuity preserve its exact flux through the convex limits, and actual-rank survival integration gives the stated Gaussian flux identity. Tag cancellation, the lawful finite false-particle comparison, and the integrated tag budget all follow with the stated endpoint and null-set conventions. No additional hypothesis or substantive gap was found.
