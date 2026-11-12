---
type: search_round
title: 'Round 5: all-false boundary extremality failure'
target_asset: gaussian_bh_global_particle_potential_certificate
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_global_particle_potential_certificate_r5_s1_all_false_boundary
statement_digest: 5c18aaddd67e681c31bff48ee957bb54c0681a855d0bfd853d043ea65e593f90
performed_by: unknown
created_at: '2026-11-09T09:50:07.613Z'
extension_version: 0.0.4
---

## Obstructions

- A proposed all-false boundary maximizer fails H4 whenever a lawful zero-mean all-true population strictly improves the normalized regularized objective at the same level. The round's sole candidate has exactly this strict improvement, so its H4 is **fail**, not unknown. H1--H3 pass; NOT remains unknown because the checks stop at H4. This rules out the proposed maximizing object, without testing the certificate conclusion at a genuine global maximizer.
- More generally, stationarity or potential failure at a lawful population cannot refute a statement restricted to genuine deterministic canonical global maximizers unless global optimality over the entire lawful comparison class is certified. The reported single-particle and parameter-edge checks provide no additional qualifying object or family-level exclusion in this pack.

## Limitations

- The pack supplies one failed candidate and its first-failure line, not its calculation body. The summary records the stated strict competing-law improvement without inventing objective values or extending that comparison to every all-false law.
- No explicit genuine deterministic canonical global maximizer was certified. The matching potential, matching level coordinate, and coherent mean-flux conclusions therefore remain untested at an object satisfying every hypothesis; the failed candidate is not a counterexample to the lemma.
- General compactness remains unproved: hybrid selector nonemptiness and measurability, conditional-realization-uniform bounds, derivative bounds and equicontinuity, preservation of analytic extensions under convex limits, and continuity of the required integral pairings still require proof. Noncompactness of the strong parameter ball alone does not settle compactness of the potential classes.
- Exact all-active support formulas, nested-hull limits, Gaussian interchanges, centered product-space separation, and a matching mass-and-level pair coherent with lawful mean variations remain unproved. The total-flux identity and finite false-particle comparison also remain obligations.
- The H4 failure is a search-admissibility obstruction, not an established proof step toward the target, so it does not warrant an approach idea. The reported absence of other contradictions supplies no proof of the certificate or its draft prerequisites. Zero-true-mean flux control, removal of regularizers, and both unrestricted Gaussian BH bounds remain separate unresolved obligations.
