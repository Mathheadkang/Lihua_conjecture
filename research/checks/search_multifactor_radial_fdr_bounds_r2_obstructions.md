---
type: search_round
title: Round 2 obstructions for finite-level radial Gaussian multifactor BH bounds
target_asset: multifactor_radial_fdr_bounds
mode: refute
round: 2
directions:
  - idea_bf23916c98ed
  - extremal
  - boundary_degenerate
  - small_cases
candidates:
  - cand_multifactor_radial_fdr_bounds_r2_s1_four_test_mixed_prds
  - cand_multifactor_radial_fdr_bounds_r2_s2_orthogonal_unbalanced_unitblocks
  - cand_multifactor_radial_fdr_bounds_r2_s4_three_interior_loadings
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:47:21.649Z'
extension_version: 0.0.4
---

## Obstructions

- In the investigated unbalanced orthogonal unit-loading block sequence, the reported exact FDR remains $q$ for every finite member. Changing block imbalance within that sequence therefore cannot violate the radial bound, whose right-hand side is at least $q$. This does not exclude other multidirectional block constructions.
- A dependence-free FDR bound can already exclude an interior-loading family when the radial bound exceeds it. For the tested three-coordinate interior-loading family, the supplied calculation gives $11q/6$ strictly below its radial bound. Merely moving loadings away from the endpoints consequently does not produce a violation in that family.
- For the tested four-test mixed family, the supplied candidate summary reports that positive regression among its three null p-values yields the uniform upper bound $29q/24$, below the radial bound's lower bound $11q/8$. If that reported regression calculation is valid, the mechanism excludes this family even when its alternative varies. This summary does not independently confirm that calculation or extend the regression property to general mixed loading configurations.
- The root worker additionally reports that fully loaded multidirectional nulls admit the smaller upper bound $q+q\pi_0\Delta_s(d,q)$ by integrating deterministic projection tail ratios. Taken within that reported scope, this prevents direction changes among full-unit-loading nulls from violating the larger proposed bound. This is a reported boundary-family observation, not an independently verified proof here.

## Limitations

- Four directions ran, with three failed candidate files and no survivor. The fully loaded multidirectional observation produced no candidate file. Absence of a survivor is a search outcome, not proof or certification of the target.
- This record uses only the supplied context pack and the root worker's additional handoff. It does not reconstruct candidate calculations, independently establish the positive-regression assertion, or verify the deterministic projection-tail integration argument.
- General mixed multidirectional configurations were not exhaustively searched: heterogeneous intermediate loading norms, interacting loading directions, multiple alternatives, larger test collections, and parameter sequences remain unclassified beyond the particular families reported above.
- The family exclusions do not establish the proposed radial tail-strip estimate, the uniform claim for arbitrary alternatives and directions, or any unrestricted two-sided sharp constant.
