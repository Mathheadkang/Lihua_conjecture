---
type: project
schema_version: 2
required_results:
  - id: gaussian_bh_one_sided_universal_order_upper
    role: Primary mathematical target - unrestricted one-sided universal expected-FDR order bound
  - id: gaussian_bh_two_sided_universal_order_upper
    role: Final deliverable - unrestricted two-sided order bound, allowing the verified signed-duplication corollary
  - id: gaussian_simes_one_sided_uniform_linear_bound
    role: Researcher-added goal (12 November 2026) - global-null one-sided Gaussian Simes rejection probability at most Cq under arbitrary correlation
---

# Gaussian BH: universal expected-FDR order

## Main Problem

Prove the [one-sided universal order bound](assets/gaussian_bh_one_sided_universal_order_upper.md): there exist finite universal constants $C>0$ and $q_0\in(0,1)$ such that
$$
F_1(q)\le Cq\sqrt{\log(1/q)}\qquad(0<q\le q_0).
$$
Here $F_1(q)$ is the supremum of the expected false discovery rate of ordinary one-sided BH over all finite Gaussian testing models below. Both $C$ and $q_0$ must be uniform over the entire model class. Any finite constant is acceptable; sharp leading coefficients and pointwise maximal-tail inequalities are not required.

## Scope and Assumptions

For every finite positive integer $N$, let $T\sim\mathcal N_N(\theta,\Sigma)$ with arbitrary $\theta\in\mathbb R^N$ and arbitrary symmetric positive-semidefinite $\Sigma$ with $\Sigma_{ii}=1$, including singular matrices. All parameters, dimension, rank and null proportions may vary with $q$. No dimension, dependence, factor, entropy or positive-noise restriction is imposed.

Use $p_i=\overline\Phi(T_i)$ and the complete one-sided null set $I_0=\{i:\theta_i\le0\}$, including strictly negative null means. With ordered p-values including multiplicities, ordinary BH uses the largest qualifying rank and non-strict comparisons:
$$
\widehat k=\max\bigl(\{0\}\cup\{k:p_{(k)}\le qk/N\}\bigr),\qquad
\mathcal R=\{i:p_i\le q\widehat k/N\}\quad(\widehat k>0),
$$
with $\mathcal R=\varnothing$ when $\widehat k=0$. Put $R=|\mathcal R|$, $V=|\mathcal R\cap I_0|$ and $\mathrm{FDR}=\mathbb E[V/(R\vee1)]$. The supremum is taken anew at each $q$, including all ties and singular cases. The [approved worst-case-FDR definition](definitions/gaussian_worst_case_bh_fdr.md) fixes the precise conventions.

## Intended Contribution

The sole primary proof problem is the one-sided bound above. The [two-sided universal order bound](assets/gaussian_bh_two_sided_universal_order_upper.md) remains the second final deliverable, using $p_i=2\overline\Phi(|T_i|)$ and null set $\{i:\theta_i=0\}$ over the same unrestricted models. The approved [signed-duplication reduction](assets/gaussian_bh_two_to_one_signed_duplication.md) gives $F_2(q)\le F_1(q)$ for $0<q<1/2$; a complete corollary proof on $q\le\min(q_0,1/4)$, independently verified, suffices. No separate two-sided analytic route is required.

Reuse applicable verified results, including the existing approved [fractional-frame surface kernel](assets/gaussian_bh_fractional_frame_surface_kernel.md), without making any previous proof strategy mandatory. Auxiliary conjectures, frozen-ray targets, noise-floor subclasses and maximal-tail claims are optional tools, never additional completion roots. New strategies are permitted; their full-model applicability must be proved. Disproved auxiliary claims remain invalid, and failed plans remain historical evidence rather than proof. Revised auxiliary statements require new IDs.

Revision of 12 November 2026, after the parallel round of routes: the compound-Poisson rare-clump cap, an auxiliary lemma of one route, is refuted by a verified counterexample showing that its clump bracket charge can be of order $q\log(1/q)$. The charge only bounds the FDR from above, so neither required result is affected and both stay unchanged; that route needs a sharper charge to continue. The round also found that the rare-direction cap and the rare-clump cap each contain the global-null Gaussian Simes problem under arbitrary correlation, which remains an optional auxiliary target, not a completion root.

Second revision of 12 November 2026: the [Ghirlanda-Guerra lemma at the null-overlap maximizer](assets/gaussian_bh_null_overlap_ghirlanda_guerra_maximizer.md), an auxiliary lemma of the ultrametric null-tree route only, is refuted by a verified counterexample: at noise variance $0.3$ and $q=0.1$, antipodal nulls with zero moments give FDR above $q$ for every large smoothing parameter, while the Ghirlanda-Guerra identities would force nonnegative null overlaps and hence FDR at most $q$ there. So penalized worst cases may need negative null correlations, and the null-tree route cannot continue as planned. Neither required result depends on the refuted lemma, so both stay unchanged. Any revised maximizer-selection statement must allow negative null overlaps and needs a new ID.

Extension of 12 November 2026, at the researcher's request: the [uniform linear bound for the one-sided Gaussian Simes rejection probability](assets/gaussian_simes_one_sided_uniform_linear_bound.md) becomes a third required result, with its statement unchanged. Under the global null $T\sim\mathcal N_N(0,\Sigma)$ with arbitrary $\Sigma$, including negative and singular correlations, it asks that the probability that one-sided BH rejects anything is at most $Cq$ for universal constants. This is stronger than the global-null case of the one-sided order bound, which only needs $Cq\sqrt{\log(1/q)}$, and the round of routes showed that the rare-direction and rare-clump caps each contain it. The result was set aside earlier: an exponential-kernel approach loses a factor of order $\sqrt{\log N}$ on sparse crossings, and the hinge-kernel reduction to normalized top-fraction excesses still lacks a dimension-free tail bound summed over dyadic scales. The researcher's new ideas are the intended input for a renewed attempt.

## Completion and Scheduling

Exactly the three IDs in `required_results` are required. At the researcher's request (12 November 2026) the global-null Simes bound is worked on first; the one-sided theorem and then the two-sided corollary follow. Each needs a complete proof, fresh independent verification and native approval. All three remain draft and unproved. Preserve all prior research and approvals; use only native workflow commands to reopen parked work. Do not add further completion roots to escape reassessment. No paper-writing or extra ledger requirement applies.

## Background

Historical specifications and sharp conjectures are preserved in [the project archive](../research-local/project_spec_archive_20261111_562f4203/project_history.md) and [the source-goal archive](../research-local/project_spec_archive_20261111_562f4203/RESEARCH_GOAL_history.md), with exact source snapshots and hashes. They are provenance, not active instructions or mandatory proof routes. The current [source-goal pointer](../bh_fdr_research/RESEARCH_GOAL.md) defers to this document. Immutable source materials and every existing mathematical node remain unchanged.
