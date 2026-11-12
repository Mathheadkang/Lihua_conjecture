---
type: search_round
title: 'Signed duplication search: sampling checks and strict-level limits'
target_asset: gaussian_bh_two_to_one_signed_duplication
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
candidates: []
statement_digest: 987e0b4167580298c08435b5d415d205e1f3153780e8613a7e16afb82038f6a6
performed_by: unknown
created_at: '2026-11-07T02:45:41.932Z'
extension_version: 0.0.4
---

## Obstructions

- Restricting the Gaussian law to a singular support cannot create a counterexample to an identity asserted for every real realization. No new singular-support mechanism beyond the existing board was found in this round.
- The exact one-test FDR calculation does not reverse the proposed comparison: with $c=\Phi^{-1}(1-q/2)$, both procedures have FDR $q$ when $\theta=0$, while for $\theta\ne0$ the original two-sided FDR is zero and the duplicated one-sided FDR is $\Phi(-c-|\theta|)\geq0$.
- Dropping Gaussianity or unit variance does not itself break the proposed deterministic rejection correspondence: the complementary normal-tail p-values are still defined for every finite realized vector. Gaussianity and unit diagonal instead ensure that the transformed sampling law belongs to the stipulated model class.
- Negative signed means do not introduce anti-conservative one-sided null calibration. For a unit-variance Gaussian coordinate of mean $\mu\leq0$ and $0<a<1$, $\mathbb P\{\overline\Phi(X)\leq a\}=\overline\Phi(\Phi^{-1}(1-a)-\mu)\leq a$.
- Joint sequences with dimension increasing and $q$ approaching $1/2$ retain, in every finite model with $q<1/2$, a strictly positive gap between every BH threshold and the larger member of each complementary signed p-value pair. Reaching the excluded limiting level is not an admissible finite-model exception.

## Limitations

All five search directions returned no concrete candidate and wrote no candidate files. The one-test calculation covers only dimension one, and the calibration and strict-level observations do not establish the full theorem. Formal proof of the exact finite ordering, rejection-set identity, false-rejection domination, and unrestricted supremum comparison remains pending, including all tie and zero-rejection conventions. This round neither proves nor tests either main uniform finite-constant FDR upper bound. Its observations refine families already on the search board; no duplicate approach idea is recorded.
