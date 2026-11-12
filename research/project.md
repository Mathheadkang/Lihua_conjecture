---
type: project
schema_version: 2
required_results:
  - id: gaussian_bh_one_sided_universal_order_upper
    role: Primary mathematical target - unrestricted one-sided universal expected-FDR order bound
  - id: gaussian_bh_two_sided_universal_order_upper
    role: Final deliverable - unrestricted two-sided order bound, allowing the verified signed-duplication corollary
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

## Completion and Scheduling

Exactly the two IDs in `required_results` are required. Prioritize the one-sided theorem, then the two-sided corollary. Each needs a complete proof, fresh independent verification and native approval. Both remain draft and unproved. Preserve all prior research and approvals; use only native workflow commands to reopen parked work. Do not add completion roots to escape reassessment. This cleanup ends paused; a separate authorization is required to begin research. No paper-writing or extra ledger requirement applies.

## Background

Historical specifications and sharp conjectures are preserved in [the project archive](../research-local/project_spec_archive_20261111_562f4203/project_history.md) and [the source-goal archive](../research-local/project_spec_archive_20261111_562f4203/RESEARCH_GOAL_history.md), with exact source snapshots and hashes. They are provenance, not active instructions or mandatory proof routes. The current [source-goal pointer](../bh_fdr_research/RESEARCH_GOAL.md) defers to this document. Immutable source materials and every existing mathematical node remain unchanged.
