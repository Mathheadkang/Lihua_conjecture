---
title: Prove the deterministic Gaussian conditional tail-density replica bound
type: plan
status: succeeded
target_asset: gaussian_conditional_tail_density_replica_bound
inspired_by: []
adapts: []
proof_digest: 06ce399fd7f751b106e868c8c5a85e91c5d3796379f4da71a081806393ba2c9f
statement_digest: d962a0c4c2ebebb96a5dc8b28cb1e9b4f8c265c0b7f73aedb2d43016b25043f7
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
verified_proof_digest: 06ce399fd7f751b106e868c8c5a85e91c5d3796379f4da71a081806393ba2c9f
---

## Goal

Target: [Gaussian conditional tail-density replica bound at deterministic levels](../assets/gaussian_conditional_tail_density_replica_bound.md).

Prove its exact statement for arbitrary finite positive integer $N$, arbitrary unit-diagonal positive-semidefinite $\Sigma$ including singular matrices, every $0<\nu\le1$, all true-null means $\theta_i\le0$, and the stated deterministic levels. Include coincident indices, the weighted cross-product bound, the exact interpolation integral, and its bound by $2$. Write a self-contained canonical proof; the extracted proof is a candidate argument to reconstruct, not an assumed theorem.

## Plan

1. [x] **Failure gate and scope lock.** Read the current target statement and confirm that every level used below is deterministic and that the only variance relation is $r^2=1-\nu$, $0<\nu\le1$. At the first scalar step below that cannot be proved with its displayed constant and full quantifiers, stop and record that exact obstruction in this plan's failure outcome. Do not replace the target by a restricted correlation case, random-level claim, different range of $\nu$, or matrix aggregation claim. No conclusion about the main FDR target or a matrix completion charge follows from this plan.
2. [x] **Derive both Mills inequalities directly.** For $b>0$, use $\phi'(x)=-x\phi(x)$ and integration by parts, with the vanishing boundary term justified, to obtain
   $$
   S(b)\le\frac{\phi(b)}b,\qquad
   S(b)=\frac{\phi(b)}b-\int_b^\infty\frac{\phi(x)}{x^2}\,dx
   \ge\frac{\phi(b)}b-\frac{S(b)}{b^2}.
   $$
   Conclude $\phi(b)\le(b+b^{-1})S(b)$. At $U\ge1$, check explicitly that $\sqrt{2/\pi}\phi(U)\le(1+U)S(U)$. Neither the source plan's Step 4(a) nor any unapproved node supplies this inequality as a black box.
3. [x] **Construct three genuinely independent residual copies.** For fixed $i,j$ take independent standard normals $\varepsilon^0,\varepsilon^1,\varepsilon^2$, independent of $X$, and set
   $$
   Y_i=\theta_i+rX_i+\sqrt\nu\varepsilon^0,\quad
   Y_j^1=\theta_j+rX_j+\sqrt\nu\varepsilon^1,\quad
   Y_j^2=\theta_j+rX_j+\sqrt\nu\varepsilon^2.
   $$
   Keep all three copies distinct when $i=j$. Show by conditioning on $X$ that $\mathbb E[p_i(v\mid X)d_j(u_1\mid X)d_j(u_2\mid X)]$ is the continuous joint density in $(u_1,u_2)$ of the finite measure $\Pr\{Y_i\ge v,(Y_j^1,Y_j^2)\in\cdot\}$. Justify pointwise evaluation at $(w,w)$ using the independent residual smoothing; no density for the possibly singular original vector $X$ is required.
4. [x] **Compute the replica transformation and its constants.** Set $A=(Y_j^1+Y_j^2)/2$, $D=(Y_j^1-Y_j^2)/2$, and $\sigma_A^2=1-\nu/2$. Show $\operatorname{Var}(D)=\nu/2$, $D$ is independent of $(A,Y_i)$ by joint Gaussianity and zero covariances, and the map $(A,D)\mapsto(Y_j^1,Y_j^2)$ has absolute Jacobian $2$. With $b=v-\theta_i\ge U$, $t=(w-\theta_j)/\sigma_A$, $Z_i=Y_i-\theta_i$, and $Z_A=(A-\theta_j)/\sigma_A$, derive the exact identity
   $$
   \mathbb E[p_i(v\mid X)d_j(w\mid X)^2]
   =\frac{\phi(t)}{2\sqrt{\pi\nu}\,\sigma_A}
      \Pr\{Z_i\ge b\mid Z_A=t\}.
   $$
   Check that $Z_i,Z_A$ are standard normals and their correlation is $\rho=(1-\nu)\Sigma_{ij}/\sigma_A$, including $i=j$. From $|\Sigma_{ij}|\le1$ and $1-\nu/2-(1-\nu)^2=\nu(3/2-\nu)>0$, verify $|\rho|<1$ for every allowed $\nu$, including $\nu=1$.
5. [x] **Prove the uniform bivariate estimate without a missing scalar lemma.** For any $b\ge1$, $t\in\mathbb R$, $|\rho|<1$, and $s=\sqrt{1-\rho^2}$, derive
   $$
   \phi(t)\Pr\{Z_i\ge b\mid Z_A=t\}
   =\int_b^\infty\phi(x)s^{-1}\phi((t-\rho x)/s)\,dx.
   $$
   If $|\rho|\ge1/2$, bound $\phi(x)\le\phi(b)$ on $x\ge b$ and compute the integral of the kernel over all real $x$ as $1/|\rho|$, obtaining at most $2\phi(b)$. Treat negative $\rho$ through the absolute Jacobian. If $|\rho|<1/2$, use $s>\sqrt3/2$, the kernel supremum $1/(s\sqrt{2\pi})$, and Step 2 to obtain at most $\phi(b)/(bs\sqrt{2\pi})\le\phi(b)$. Verify the numerical constant analytically via $s\sqrt{2\pi}>\sqrt{3\pi/2}>1$. This branch includes $\rho=0$.
6. [x] **Assemble the exact squared-density bound.** Substitute Step 5 into Step 4 and use $\sigma_A\ge1/\sqrt2$, $b\ge U\ge1$, and monotonicity of $\phi$ on $[1,\infty)$ to derive
   $$
   \mathbb E[p_i(v\mid X)d_j(w\mid X)^2]
   \le\frac{\phi(b)}{\sqrt{\pi\nu}\,\sigma_A}
   \le\sqrt{\frac2\pi}\frac{\phi(U)}{\sqrt\nu}
   \le\frac{S(U)(1+U)}{\sqrt\nu}.
   $$
   List why no bound on $N$, the other means, the deterministic $w$, or a nonsingular $\Sigma$ entered. Check the allowed endpoint $\nu=1$ directly against the same construction.
7. [x] **Derive the mixed-density bound with the same weight.** Since $p_i(v\mid X)\ge0$, apply ordinary Cauchy--Schwarz to $\sqrt{p_i(v\mid X)}d_j(w\mid X)$ and $\sqrt{p_i(v\mid X)}d_k(z\mid X)$. Their finite squared moments follow from Step 6. Obtain both inequalities in the target, allowing any coincidences among $i,j,k$ and arbitrary deterministic $w,z$.
8. [x] **Verify the interpolation endpoint exactly.** For every $\eta>0$ and $a\in[0,1]$, compute $\nu_a+r_a^2=1$ and $0<\nu_a\le1$, so the preceding bound applies to $T_{a,\eta}=\theta+r_aX+\sqrt{\nu_a}\varepsilon$ with residual coordinates independent of $X$ and one another. Integrate directly to obtain
   $$
   \int_0^1\nu_a^{-1/2}\,da
   =2\sqrt{1+\eta^2}(\sqrt{1+\eta^2}-\eta)
   =\frac{2\sqrt{1+\eta^2}}{\sqrt{1+\eta^2}+\eta}\le2.
   $$
   State this as a uniform integrable scalar bound without claiming that the endpoint $\nu=0$ belongs to the pointwise lemma.
9. [x] **Write and audit the canonical proof.** Put the reconstructed argument in the asset's canonical proof section, retaining the immutable statement and the provenance that the extracted candidate came from a failed main plan's partial scalar result. The canonical proof must include Step 2 in full and may not refer to the failed main plan as an unproved premise. Check every coefficient, the Jacobian, both correlation branches, all repeated-index cases, and every displayed conclusion of the target. Keep the asset draft for independent native verification and researcher approval.

## Verification

Steps 3--6 prove the first scalar inequality for every allowed model and deterministic level, and Step 2 proves its displayed comparison with $q=S(U)$. Step 7 proves the exact two-part cross-product assertion. Step 8 proves the interpolation representation and all equalities and inequalities in the endpoint integral. Verification must reconstruct these deductions independently and specifically check the density interpretation, the factor $1/2$ from the replica Jacobian, the strict correlation bound despite original singularity, and the lower Mills inequality. Numerical searches are not proof of any uniform claim. Passing this plan proves only this supporting lemma, with no random-level extension, matrix aggregation budget, or main FDR conclusion.

## Assumed definitions

The approved [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) and [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md) are the only research definitions used. No draft definitions or unproved research dependencies are assumed. Elementary Gaussian density, linear-transform and independence facts, integration by parts, and Cauchy--Schwarz are used explicitly; both Mills estimates and the bivariate scalar estimate are proved inside the canonical proof.

The supplied context pack listed no library analogues. Native library searches for `Gaussian conditional tail density replica Mills`, `Gaussian`, `Mills`, and `conditional density` returned no matching results. No external citation or library conclusion is imported.

## Difference from failed plans

- [Gaussian interpolation SDP source plan](plan_one_sided_order_gaussian_interpolation_sdp_20261106.md): its separate matrix-aggregation gate failed. This plan addresses only the extracted deterministic scalar lemma, reconstructs its replica argument and Mills estimate self-containedly, and neither assumes nor repairs that failed aggregation. No failed plan for this supporting asset was listed in the current context pack.

## Outcome

The complete self-contained proof is under `## Proof` in [Gaussian conditional tail-density replica bound at deterministic levels](../assets/gaussian_conditional_tail_density_replica_bound.md). All nine checklist items succeeded. The exact statement is unchanged (SHA256 `dafe2018de21c829c53ade021b8d898b2af5e0c2efa6580ad3039033cbcbd4c2` for its body before `## Provenance and scope`); all pre-existing provenance and extracted-candidate text is retained. The asset remains `draft` for independent native verification and researcher approval.

Both Mills inequalities, the replica density and continuity argument, the absolute Jacobian, the strict correlation bound, both bivariate branches, the exact scalar constant, weighted Cauchy--Schwarz and the interpolation integral are proved in the canonical argument. Singular covariance, coincident indices, $\nu=1$ and arbitrarily small positive $\nu$ are included. The only research definitions used are the two approved definitions already listed above; no draft definitions, unproved research dependencies or failed-plan premises are assumed. The scope remains deterministic scalar levels, with no pointwise $\nu=0$ claim, random-level extension or matrix-aggregation conclusion.

Validation completed with `0 problem(s)`. Links preview and application found `0` proposed/updated files and `0` review items. The notation audit read both approved definition files and their definition dependency, `macros.tex` and `notations.tex`; the two TeX files contain only their placeholder comments. The local proof symbols are defined in context, the existing `uses_definitions` links are complete, and no missing or conflicting notation was found. This execution audit does not replace independent native proof verification or researcher approval.

## Verdict

confirmed

Independently checked the canonical Statement and Proof only, against the two named approved definitions. The proof covers arbitrary finite N, every positive-semidefinite unit-diagonal covariance including singular laws, negative true-null means, all index coincidences, and every allowed deterministic level. The three independent residuals, continuous pointwise event density, inverse Jacobian factor 1/2, strict correlation for every positive residual variance, both correlation branches, both Mills bounds, the constant sqrt(2/pi), and weighted Cauchy--Schwarz are valid. The endpoint nu=1 and arbitrarily small positive nu are covered; nu=0 is excluded. The exact interpolation integral is at most 2 uniformly in eta>0. No random-level or matrix-aggregation conclusion is verified or asserted. No mathematical gap needed closure.

Version binding (unchanged before and after this Verdict append): full asset SHA256 9a7b957b343f8303e9a93395a01997796c057d3737840eb210393dc8a302e466; canonical Statement followed by Proof SHA256 1fe7b43fabff298fb2a3f89c34ccdae3030e3393b77be46efd2b9de6e836ce15.
