---
type: plan
title: Native reconstruction of the exact two-sided Gaussian BH pivotal identity
status: succeeded
target_asset: gaussian_bh_two_sided_exact_pivotal_identity
inspired_by:
  - idea_17dce9a06c63
adapts: []
proof_digest: 8989beec6bf2bf813e32f91a3a73be2bcb75f6c49ee9115e81557aa72d5a4cee
statement_digest: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 8989beec6bf2bf813e32f91a3a73be2bcb75f6c49ee9115e81557aa72d5a4cee
---

## Goal

Target: [Exact exogenous-pivotal identity for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_exact_pivotal_identity.md).

Prove precisely clauses (a)–(f) for every $q\in(0,1)$, every admissible Gaussian model (including singular covariance), and every two-sided true null. Preserve the Statement and the extracted proof. The extracted argument guides reconstruction but is not an established dependency or verdict. Introduce no asymptotic restriction on $q$ and no bound on the pivotal excess beyond the target.

## Plan

1. [x] Establish the deterministic BH counting facts from the approved step-up definition, without invoking a failed plan. For $z\in[0,1]^N$, put $n_z(t)=\#\{j:z_j\le t\}$ and $t_k=qk/N$. Prove that qualifying ranks are exactly those with $n_z(t_k)\ge k$, that $R_q(z)=\widehat k_q(z)$ including zero, and that entrywise lowering p-values can only increase the rank. For positive rank $r$, prove $n_z(t_r)=r$ by showing that a larger count would itself qualify. Retain non-strict comparisons at ties.
2. [x] Prove (a) directly. Compute the mean and full covariance of $(T_i,Y_i)$ using $\theta_i=0$ and $\Sigma_{ii}=1$. The cross covariance is zero and the residual covariance is $\Sigma_{-i,-i}-c_ic_i^{\mathsf T}$. Obtain PSD as the covariance of the residual, or by the corresponding quadratic form. Factor the jointly Gaussian characteristic function to establish independence even when the covariance is singular.
3. [x] Reconstruct the pointwise forced-zero identity (b). Fix an arbitrary p-value vector $z$ and replace only $z_i$ by zero, giving $z^0$ and $r^0=\widehat k_q(z^0)\ge1$. For $t\ge0$, prove $n_{z^0}(t)=n_z(t)+\mathbf1\{z_i>t\}$. If $z_i\le t_{r^0}$, rank $r^0$ qualifies for $z$; monotonicity gives equality of the two ranks, rejection of $i$, and $R=r^0$. If $z_i>t_{r^0}$, monotonicity gives $\widehat k_q(z)\le r^0$ and nonrejection of $i$, including rank zero. Identify $z^0$ with the vector defining $\rho_i(T_i,Y_i)$ using the residual identity coordinate by coordinate. Convert $1/r^0$ into $(q/N)/\tau_i$ to obtain exactly (b). Check $N=1$, ties, and $R=0$ explicitly.
4. [x] Prove (c), including measurability. Express rank qualification for the forced vector using finitely many Borel inequalities in $(x,y)$; hence $\rho_i$, $\tau_i$, and the pivotal integrand are Borel. Prove $\mathbb P(p(|T_i|)\le t)=t$ for $t\in(0,1)$ from the standard normal marginal. For every Borel grid-valued $g$, independence gives $\mathbb E[a(T_i;g(Y_i))\mid Y_i]=1$. Check that $y\mapsto\tau_i(0,y)$ is Borel and grid-valued. Record $0\le a\le N/q$ for integrability.
5. [x] Derive (d) by summing (b) over true nulls and taking expectations. Separate the constant $q|I_0|/N$ from $(q/N)\sum_i\Delta_i$. Nonnegativity gives $\Delta_i\ge-1$, and $0\le\mathrm{FDP}\le1$ gives the final sum bound. Include the empty true-null set as a zero sum.
6. [x] Prove the branch formula in (e). Establish the independence of $s=|T_i|$ and its uniform sign, assigning either sign on the null event $T_i=0$. Use (a) to obtain independence of their pair from $Y_i$. Integrate the bounded Borel integrand over $s$ with density $2\phi$ and then over sign, obtaining exactly the displayed expression with $\tfrac12(\Psi(f^+)+\Psi(f^-))$. Use Tonelli to justify the integration and measurability in $y$.
7. [x] Prove the entire step-structure assertion in (e) without citing source A4. At each $(j,k)$ solve $|b_j+\sigma c_{ij}s|<u_k$ on $s\ge0$. For $c_{ij}\ne0$, this is an open interval intersected with the half-line; for zero loading it is either the whole half-line or empty. Since $u_k=p^{-1}(qk/N)>0$ for every $q\in(0,1)$, there are at most two finite boundary locations per pair. Thus at most $2N(N-1)$ locations determine the constant indicator vectors and rank between them. Keep the actual equality values at boundaries; do not assert right continuity there. Construct the right-continuous representative by taking its right-hand constant value at each boundary (including zero if needed). It remains grid-valued, differs only on a finite set, and therefore has the same $\Psi$. The source reference to applying A2 describes this representative; no conclusion of A2 is required by this identity.
8. [x] Prove (f) for every positive integer $M$. For the duplicated vector $z'$, use $n_{z'}=Mn_z$. Every positive original qualifying rank $r$ gives qualifying rank $Mr$. Conversely, if a duplicated rank $k>M\widehat k_q(z)$ qualifies, put $m=\lceil k/M\rceil$. Monotonicity of thresholds and integrality of $n_z$ force original rank $m>\widehat k_q(z)$ to qualify, a contradiction. Cover original rank zero by the same upper-bound argument. Conclude the exact rank and threshold equalities, with zero threshold and empty rejection set in the zero-rank case. All copies have their original rejection and null indicators; derive identical FDP also at zero rejections. Repeated Gaussian coordinates give an admissible, possibly singular model. For each copied true null, use the newly proved (b) in both dimensions: its expected FDP contribution is exactly $1/M$ of the original contribution. Multiplying by $MN/q$ proves $1+\Delta'_{i'}=1+\Delta_i$, hence equality of every copied excess.

## Verification

Steps 2–8 yield (a), (b), (c), (d), both assertions of (e), and (f), with step 1 supplying rederived deterministic facts. Check all quantifiers against the unchanged Statement: arbitrary $q\in(0,1)$, singular covariance, non-strict BH comparisons, $R=0$, zero loadings, and every duplicated null. The small-level notation $U,J_q,K_q,L_q$ is unused here and imposes no restriction on the identity's asserted range. No failed B4 claim or external A2/A4 conclusion is a black box. Successful execution supplies a complete proof for independent native verification; a pending plan itself is not proof approval.

## Assumed definitions

Use the approved definitions gaussian_multiple_testing_model, gaussian_test_pvalues, benjamini_hochberg_step_up, and false_discovery_rate already listed by the target. No draft definitions or unproved dependencies are assumed. Use Gaussian characteristic-function factorization, finite Borel operations, and Tonelli in their standard forms as specified above. Library searches for Gaussian BH pivotal identity and Benjamini Hochberg forced zero returned no matching results; no library proof is adapted or cited. No pending or failed target plan is listed in the stage pack. The older source plan supplies provenance only; none of its proof conclusions is assumed.

## Outcome

All eight checklist items were established sequentially in saved Progress substeps and then transferred in full to the target asset, under `## Proof`, subsection `### Native execution details (2026-11-06)`. The extracted source proof was promoted from the pending heading to `## Proof` without changing any of its wording or formulas. The target Statement is unchanged and its status remains draft. The native details prove all clauses (a)–(f), including every $q\in(0,1)$, singular covariance, ties, $N=1$, $R=0$, zero loadings, finite branch modifications, and all duplicated true nulls. No A2/A4 conclusion or failed-plan conclusion is assumed. The retained source A0 aside mentions an absent displayed bound; it is explicitly excluded from the target proof and is not a claimed new bound. The source duplication argument's zero-rank case is resolved explicitly in native step 8.

Only the four approved definitions listed by the target and the standard Gaussian characteristic-function, finite Borel-operation, and Tonelli facts in the plan are assumed. No draft definition or unproved asset is assumed. Check-notation reviewed those definitions, `.research-assistant.json`, `macros.tex` and `notations.tex`; both TeX files contain only comments, and there is no conflicting notation. The inverse thresholds are explicitly defined for all levels in native step 4. The existing A0 source-reference ambiguity is disclosed above rather than silently rewritten. Maintenance validate reports 0 problems; target-scoped links preview and apply each report 0 changes and 0 review items. Native independent proof verification remains outstanding; this execution is not researcher approval.

## Verdict

confirmed

Independently checked the statement and proof against the four supplied definitions, without reading the plan reasoning. The counting argument proves the forced-zero identity pointwise with ties and zero rejections; every denominator is positive. The Gaussian covariance calculation and characteristic-function factorization cover singular covariance and the zero-dimensional residual at N=1. Independence, exact null-uniformity, Borel measurability and bounded integrability justify the exogenous expectation, FDR decomposition and branch integration for every q in (0,1).

The explicit inactive-interval calculation covers zero loadings and all endpoint values, establishes the finite boundary bound, and justifies the right-continuous representative without altering Psi. The duplication argument covers zero rank, preserves Gaussian admissibility and null membership, and proves equality of every copied excess through the per-null contribution identity. Native steps 7 and 8 supply the source text's external interval reference and omitted zero-rank qualification case. No unresolved proof gap remains in clauses (a)-(f); no claim from the unrelated source A0 aside or source A2/A4 is needed.
