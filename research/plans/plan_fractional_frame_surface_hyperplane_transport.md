---
id: plan_fractional_frame_surface_hyperplane_transport
title: Complete-frame hyperplane transport proof of the fractional surface kernel
type: plan
status: succeeded
target_asset: gaussian_bh_fractional_frame_surface_kernel
inspired_by:
  - idea_ac8371a287d5
  - idea_3bf8068cc80a
  - idea_44667528e0be
proof_digest: 8d89a54b99659532df526664eea452e20a4b23c794c5df6d73be8970ea2a8114
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
dependency_digests: {}
verified_proof_digest: 8d89a54b99659532df526664eea452e20a4b23c794c5df6d73be8970ea2a8114
---

## Goal

Target: [Fractional-frame Gaussian surface kernel with arbitrary exposure](../assets/gaussian_bh_fractional_frame_surface_kernel.md).

Prove the exact stated bound, with constant sqrt(e), for every canonical exposure value y, including singular covariances, zero weights, and thresholds a_i >= u >= 1. Reconstruct the observation in idea_ac8371a287d5 inside the proof; it is not an approved black-box theorem. The library search returned no applicable fractional-frame surface result. The closest listed OU reverse-isoperimetry analogue has no Proof section and is not adapted or cited.

## Plan

1. [x] Reduce every original threshold to u and discard only zero-weight constraints, enlarging the conditional event without changing beta. Keep the original beta throughout. If no positive original weights remain, still use the construction below, or verify directly that K(y) <= phi(0) <= sqrt(e) h(u). Verify h(u) >= u >= 1 from u S(u) <= integral_u^infinity x phi(x) dx = phi(u).

2. [x] Diagonalize the positive-semidefinite slack I - sum_original c_i v_i v_i^T and append its positive-eigenvalue unit eigenvectors with those eigenvalues as weights. Check the completed identities sum_all c_i v_i v_i^T = I, sum_all c_i = d, and sum_all c_i (v_i dot w)^2 = 1. Define f_i(s) = phi(s) 1_{s >= u}/S(u) for retained original indices and f_i(s) = phi(s) for added indices. Each integrates to one, and its supremum M_i is at most h(u). For every x, including threshold boundaries, verify product_all f_i(v_i dot x)^{c_i} = S(u)^{-beta} phi_d(x) times the retained conjunction indicator.

3. [x] Establish the precise geometric integral inequality needed later without an external dependency: for unit e_i in R^r with positive p_i and sum_i p_i e_i e_i^T = I_r, and integrable scalar functions g_i that are positive smooth functions on an open interval and zero outside its closure, prove integral product_i g_i(e_i dot z)^{p_i} dz <= product_i (integral g_i)^{p_i}. Our functions are powers of translated/scaled Gaussian densities, possibly truncated to a half-line. Normalize each scalar integral to one, take the increasing transport T_i to standard Gaussian on the open support interval, and check g_i(s) = phi(T_i(s)) T_i'(s). On the open convex intersection D of support slabs, set Theta(z) = sum_i p_i T_i(e_i dot z) e_i. Show DTheta is positive definite, and show injectivity by integrating the strictly positive directional quadratic form along any nonconstant segment in D. Prove the synthesis contraction ||sum_i p_i a_i e_i||^2 <= sum_i p_i a_i^2 from the exact frame identity.

4. [x] Complete the geometric inequality: with V having columns sqrt(p_i) e_i, use Cauchy-Binet to write det(sum_i p_i q_i e_i e_i^T) = sum_{|J|=r} alpha_J product_{i in J} q_i, where alpha_J = det(V_J)^2, sum_J alpha_J = 1, and sum_{J containing i} alpha_J = p_i, the last identity obtained by differentiating at q = 1. Weighted arithmetic-geometric mean gives the determinant lower bound product_i q_i^{p_i}. Taking q_i = T_i' and using sum_i p_i = r bounds the normalized integrand by phi_r(Theta(z)) det DTheta(z). Apply injective change of variables on D, obtaining mass at most one; exhaust D by compact interior sets to justify the integration. If D is empty, the intersection of the closed support slabs has empty interior and hence Lebesgue measure zero; the integral is zero. Otherwise omitted support boundaries lie in finitely many hyperplanes and have measure zero. These facts also handle support intersections with no full-dimensional interior. Treat r = 0 separately by the empty-product convention, rather than invoking positive-dimensional transport.

5. [x] For H = w^perp, write b_i = v_i dot w, ell_i = sqrt(1-b_i^2), and, when ell_i > 0, e_i = P_H v_i/ell_i and p_i = c_i ell_i^2. Verify sum_{ell_i>0} p_i e_i e_i^T = I_H. On x = yw + z with z in H, use g_i(s) = f_i(ell_i s + b_i y)^{1/ell_i^2}. Apply steps 3-4 to these exact Gaussian or truncated Gaussian functions. Establish the scalar bound integral g_i <= ell_i^{-1} M_i^{1/ell_i^2-1} from integral f_i = 1 and f_i^{1/ell_i^2} <= M_i^{1/ell_i^2-1} f_i. Retain indices ell_i = 0 as constant factors f_i(b_i y)^{c_i} <= M_i^{c_i}; zero constant factors make the integral zero. Handle d = 1 directly as a zero-dimensional slice, including a threshold equality where the event probability can equal one.

6. [x] Combine the scalar factors to bound the hyperplane integral by product_{ell_i>0} ell_i^{-c_i ell_i^2} times product_all M_i^{c_i b_i^2}. The second product is at most h(u), since sum_all c_i b_i^2 = 1. Set z_i = b_i^2 and prove -(1-z_i) log(1-z_i) <= z_i on [0,1], using the limit zero at z_i = 1. Therefore the logarithm of the first product is at most (1/2) sum_all c_i b_i^2 = 1/2. This yields the uniform bound sqrt(e) h(u), with no dimension or inverse-variance term.

7. [x] Integrate the pointwise identity from step 2 on H using its Euclidean Lebesgue measure, and verify exactly that integral_H phi_d(yw+z) 1_A(yw+z) dz = phi(y) P(A | w dot G = y) for the canonical conditional law. In dimension zero use its unit point mass. Multiply the bound of step 6 by S(u)^beta, then reverse the event enlargements of step 1. This proves the original inequality at every real y, including the threshold boundary values, arbitrary a_i >= u, and a_i = u-theta_i with theta_i <= 0.

## Verification

The proof's only auxiliary analytic inequality is proved in steps 3-4 for exactly the functions needed in step 5. Check independently its Cauchy-Binet marginal-exponent identity and the direction of its determinant and synthesis inequalities. Then check the completed-frame Gaussian normalization, the projected frame weights c_i ell_i^2, the scalar exponent c_i b_i^2, and the entropy penalty exp(1/2). Their product gives precisely sqrt(e) h(u) S(u)^beta. Canonical disintegration is pointwise in y; no almost-everywhere choice or nonsingular joint-covariance assumption enters. Verify separately all-zero original weights, d = 1, zero projected directions, empty support interiors, and deterministic threshold equalities. The result remains a surface-kernel lemma and makes no BH aggregation claim.

## Assumed definitions

Only the definitions in the target statement are used: the canonical conditional law, standard Gaussian densities, S, h, and the positive-semidefinite frame order. There are no assumed draft definitions and no assumed unproved dependencies. The resolved observation idea_ac8371a287d5 supplies a route that is reproved here, not an assumed conclusion. Standard finite-dimensional linear algebra and multivariable change of variables are used explicitly as above.

## Outcome

The complete proof is in the target asset's `## Proof`. All seven checklist steps are established there. The geometric integral inequality is reconstructed using one-dimensional Gaussian transports, injectivity on the open convex support intersection, the Cauchy--Binet marginal identity, and an injective change of variables with compact exhaustion. The projected scalar powers give exactly the factors \(\prod_i M_i^{c_i b_i^2}\le h(u)\) and \(\prod_{\ell_i>0}\ell_i^{-c_i\ell_i^2}\le\sqrt e\).

No draft definitions, unproved dependencies, or external geometric integral theorem are assumed. Only the target hypotheses and standard finite-dimensional linear algebra and multivariable calculus are used. The proof covers all-zero original weights, dimension one, zero projected directions, empty support interiors, support-boundary slices, and deterministic threshold equalities. The target statement and `status: draft` remain unchanged; this is an executed proof awaiting independent verification and researcher approval, and it establishes no BH FDR bound.

## Verdict

confirmed

Independently checked the statement and proof in the verify_proof context pack, without reading this plan's reasoning. Threshold reduction and zero-weight removal preserve pointwise event containment; spectral frame completion gives the exact Gaussian product identity. The transport is smooth on each open support interval, its Jacobian is positive definite, and strict monotonicity on the convex domain gives injectivity. The inverse function theorem therefore yields a global C1 diffeomorphism onto its open image; change of variables and compact exhaustion are valid. Cauchy--Binet coefficients sum to one and have inclusion marginals p_i, which establishes the claimed determinant inequality with the correct exponents.

Checked the projected frame, density-power integral bound, and all parallel directions. Nonconstant endpoint hyperplanes have zero slice measure; constraints constant on a slice retain their actual endpoint values. The separate zero-dimensional calculation covers d=1 and threshold equality. The identity sum_i c_i b_i^2=1 pays both the density supremum and logarithmic projection loss, giving h(u) and at most sqrt(e), independently of d and n. The final Gaussian disintegration is valid for every specified y under the canonical law, including degenerate joint constraints. No unresolved gap found. This verdict confirms only the stated surface-kernel lemma, not any BH FDR conclusion or researcher approval.
