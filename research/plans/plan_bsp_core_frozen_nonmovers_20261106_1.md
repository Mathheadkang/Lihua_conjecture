---
id: plan_bsp_core_frozen_nonmovers_20261106_1
title: Prove the baseline-subtracted core by frozen nonmover conditioning
type: plan
status: succeeded
target_asset: gaussian_bh_baseline_subtracted_pivotal_core
inspired_by:
  - idea_41e71c79a5f9
  - idea_c03006bb5bda
adapts: []
proof_digest: 85dd14e2b2ff2958330ba3e1a4f9d98fba33cbe269c4411a3ff01c3b8f47a30b
statement_digest: 182210875024e41e07afd86320271d77d4c3101bb674953cf99e16eee40678ba
dependency_digests:
  gaussian_bh_two_sided_exact_pivotal_identity: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 85dd14e2b2ff2958330ba3e1a4f9d98fba33cbe269c4411a3ff01c3b8f47a30b
---

## Goal

Target: [Baseline-subtracted pivotal identity for arbitrary Gaussian covariance](../assets/gaussian_bh_baseline_subtracted_pivotal_core.md).

Prove the frozen Statement exactly for every finite positive integer $N$, every $q\in(0,1)$, every admissible $(N,\theta,\Sigma)$ including singular $\Sigma$, and every two-sided true null $i$. Allow $N,\theta,\Sigma$ to depend arbitrarily on $q$. Establish the exact baseline subtraction, its stated upper bound, and the empty-movers consequence. The extracted source proof is an execution candidate, not a verified proof; its annotations do not discharge any checklist item.

## Plan

1. [x] Establish the deterministic BH prerequisites directly from the largest qualifying rank. For every $b\in[0,1]^N$, express each qualification event as a finite count of weak inequalities $b_j\le qk/N$, hence prove that $b\mapsto\widehat k_q(b)$ is Borel. Prove coordinate monotonicity: $b\le b'$ implies $\widehat k_q(b)\ge\widehat k_q(b')$. Apply it to $b^0\le b^\flat$, and use their common forced zero at $i$ to obtain $1\le R_i^\flat\le R_i\le N$ and $0<q/N\le\tau_i^\flat\le\tau_i\le q<1$. Explicitly include $N=1$, ties, and endpoint equality in the weak threshold inequalities. Check that all quantities in the frozen Statement are measurable and their normalized indicators are bounded by $N/q$ for the fixed model.

2. [x] Connect the deterministic notation with the approved dependency [Exact exogenous-pivotal identity for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_exact_pivotal_identity.md). Verify that the actual forced-zero vector equals the vector used in $\rho_i(T_i,Y_i)$, so $R_i=\rho_i(T_i,Y_i)$ and the target's $\tau_i$ is the dependency's threshold. Use only its explicitly all-$q$ parts A1(a), A1(c), and A1(d); its preliminary small-$q$ notation imposes no restriction on these clauses. If the deterministic forced-zero equality is expanded in execution, use maximal-rank counts with weak inequalities, including the case of no actual rejections, rather than an unverified source annotation.

3. [x] Verify the singular Gaussian conditioning step. Since $\theta_i=0$ and $\Sigma_{ii}=1$, the linear image $(T_i,Y_i)$ is jointly Gaussian, $\operatorname{Cov}(Y_i,T_i)=c_i-c_i=0$, and $\operatorname{Cov}(Y_i)=\Sigma_{-i,-i}-c_ic_i^{\mathsf T}\succeq0$. Use approved A1(a), or explicitly factor the joint Gaussian characteristic function to justify independence even when either residual block has zero variance. For each nonmover $j\ne i$, $c_{ij}=0$ gives $T_j=\theta_j+(Y_i)_j$. Thus $b^\flat$ is the Borel vector having entry $0$ at $i$, entry $1$ on movers, and entry $p(|\theta_j+(Y_i)_j|)$ on nonmovers. Conclude $\tau_i^\flat=g(Y_i)$ for a Borel $g$ taking values in $\{q/N,\ldots,q\}$ and independent of $T_i$. Treat an empty residual vector or empty nonmover set as constants.

4. [x] Establish the baseline expectation exactly. Because $T_i\sim N(0,1)$, the two-sided null p-value $P_i=p(|T_i|)$ is uniform on $[0,1]$. Apply approved A1(c) to the Borel $g$ just constructed, or condition on its finitely many threshold values, to obtain $\mathbb E[a(T_i;\tau_i^\flat)\mid Y_i]=1$ and hence $\mathbb E a(T_i;\tau_i^\flat)=1$. The positivity and bound in Step 1 justify every conditional expectation and subtraction for each finite $N,q$; no limit argument is needed.

5. [x] Derive both target assertions. Subtract the mean-one baseline to obtain $\Delta_i=\mathbb E[a(T_i;\tau_i)-a(T_i;\tau_i^\flat)]$. With $p=p(|T_i|)$, split pointwise into the exhaustive cases $p\le\tau_i^\flat$, $\tau_i^\flat<p\le\tau_i$, and $p>\tau_i$. Compute the differences as respectively $1/\tau_i-1/\tau_i^\flat\le0$, $1/\tau_i$, and $0$, retaining equality at both thresholds in the indicated cases. Taking expectations gives exactly the stated upper bound. The decomposition also covers $\tau_i^\flat=\tau_i$ without a separate continuity assumption.

6. [x] Prove the final consequence at its precise scope. If $\mathcal M_i=\emptyset$, no entries were changed, so $b^\flat=b^0$ and the exact subtraction yields $\Delta_i=0$. If $\Sigma=I$, this holds for every two-sided true null even with arbitrary alternative means. Use the approved A1(d) identity $\operatorname{FDR}=q\pi_0+(q/N)\sum_{i\in I_0}\Delta_i$ to conclude $\operatorname{FDR}=q\pi_0$ exactly, including an empty true-null set. No blockwise independence, all-$\varepsilon$ statement, or two-copy claim is part of this plan.

## Verification

The execution must independently fill every checklist item and compare its conclusions with all three displayed claims in the unchanged target Statement. Steps 1–3 supply positive, measurable ordered thresholds and the exogenous baseline for singular as well as nonsingular covariance. Step 4 proves its exact mean; Step 5 gives the identity and upper bound; Step 6 gives exactly the stated no-movers and independent-coordinate consequences. Verify all-$q$ coverage from the explicit quantifiers of the approved A1 clauses, and check that no bound on finite $N(q)$ or null proportion entered. Planning alone certifies none of these claims.

## Assumed definitions

The four definitions in the context pack—`gaussian_multiple_testing_model`, `gaussian_test_pvalues`, `benjamini_hochberg_step_up`, and `false_discovery_rate`—are approved. The sole black-box result is the target's approved dependency `gaussian_bh_two_sided_exact_pivotal_identity`, restricted to its explicitly all-$q$ clauses. No draft definition, unproved dependency, block all-$\varepsilon$ independence assertion, or two-copy assertion is assumed. The two draft ideas only motivate the route. Library searches for the target terms, singular Gaussian zero-covariance independence, and BH rank monotonicity/measurability returned no analogue; the finite-count and conditioning details are to be checked directly during execution.

## Outcome

All six checklist items were established in writing and the complete proof is now under `## Proof` in [Baseline-subtracted pivotal identity for arbitrary Gaussian covariance](../assets/gaussian_bh_baseline_subtracted_pivotal_core.md). The proof covers every finite $N\ge1$, all $q\in(0,1)$, arbitrary admissible singular or nonsingular Gaussian covariance, positive Borel frozen ranks, exact mean-one baseline subtraction, the three-case upper bound, and the empty-movers consequence. The independent-coordinate FDR consequence uses the approved dependency's explicitly all-$q$ A1(d); its threshold notation was identified directly, and singular Gaussian independence and conditioning were proved explicitly. No draft definition or unproved dependency is assumed. No block all-$\varepsilon$ independence or two-copy claim is used or established.

The target Statement and frontmatter were compared byte-for-byte with their pre-edit contents and remain unchanged, including `status: draft`. Notation was checked against all four approved definitions in the context pack and the configured `macros.tex` and `notations.tex` (both contain only comments); no undefined or conflicting notation or missing relation was found. Asset validation returned `0 problem(s)`. Links preview and apply each returned `0 file(s) proposed; 0 review item(s)`. This execution is a proof candidate awaiting independent native verification; no approval or verification verdict is recorded here.


## Verdict

confirmed

Independent fresh verification of the Statement and all six Proof steps in the native context pack. The scope is every finite positive N, every q in (0,1), every admissible Gaussian covariance including singular matrices, arbitrary alternative means, and every two-sided true null. Approved dependency statements were checked for applicability; their proofs were not re-audited.

1. Step 1: finite Borel counts give measurable ranks; coordinatewise monotonicity and the forced zero give 1 <= R_i^flat <= R_i <= N. Thus both thresholds are positive and both normalized indicators are bounded by N/q. This is enough for all expectations at each allowed N,q; no uniform integrability assertion is needed.
2. Step 2: the residual identity identifies exactly the dependency's forced-zero vector. The maximal-rank count argument proves that the BH rejection count equals its rank. The forced-zero rejection equivalence and displayed pointwise identity retain inclusive ties and the R=0 case. The dependency's A1 clauses explicitly have the required all-q scope despite its separate small-q notation.
3. Step 3: theta_i=0 makes (T_i,Y_i) a centered joint Gaussian linear image, with zero cross covariance. Characteristic-function factorization proves joint independence of T_i and the entire residual vector without invertibility. The frozen nonmover vector is a Borel function of that residual alone; the resulting threshold is finite-valued, positive, and independent of T_i. The zero-dimensional residual and the constant-vector cases cause no exception.
4. Step 4: the two-sided null p-value is exactly uniform. Conditioning on the residual at each possible threshold t_k therefore gives a mean-one baseline, with every hypothesis of A1(c) established.
5. Step 5: bounded integrability licenses subtraction. The three stated p-value intervals are exhaustive, have the correct weak endpoints, and give exactly the stated difference and upper bound, also when the thresholds coincide.
6. Step 6: empty movers make the two vectors and thresholds identical, hence Delta_i=0. For Sigma=I this holds for every true null regardless of alternative means; A1(d) gives the exact FDR equality. The empty-null sum also agrees with the FDR definition.

No additional hypothesis, proof repair, block-baseline independence claim, or two-copy claim is required for this core statement. The verification does not establish any broader compound claim or unrestricted Gaussian BH bound.
