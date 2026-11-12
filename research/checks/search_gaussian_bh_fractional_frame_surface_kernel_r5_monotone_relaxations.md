---
type: search_round
title: 'Round 5: exact monotone relaxations and zero candidate coverage'
target_asset: gaussian_bh_fractional_frame_surface_kernel
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:24:25.007Z'
extension_version: 0.0.4
---

## Obstructions

- **Raising individual thresholds cannot turn a nonviolating object into a counterexample.** Fix every other parameter, including the baseline u. For deterministic a_i >= u, the canonical conditional event is contained in the event with all thresholds equal to u, for every exposure y, even on degenerate slices. Hence its surface kernel is no larger, while the proposed bound is unchanged. A violating object with enlarged thresholds would therefore also violate at equal thresholds. This is a reduction, not a proof of the equal-threshold inequality.
- **Adding constraints of weight zero cannot create a violation.** Removing any zero-weight constraints enlarges the canonical conditional event and leaves beta, frame feasibility, and the proposed bound unchanged. Thus any violation with such additional constraints persists after their removal. When every weight is zero, beta=0 and K <= phi(0) < sqrt(e) h(u) for u>=1: indeed h(u)>u follows from S(u)<phi(u)/u, obtained by integrating z phi(z)/u on z>=u. The zero-weight-only case is therefore excluded exactly. This does not exclude a frame with both positive and zero weights without controlling its positive-weight constraints.
- **Reducing weights at fixed geometry and thresholds cannot create a violation.** If 0 <= c'_i <= c_i and the original weights satisfy the frame inequality, then the reduced weights do too and beta' <= beta. The kernel is independent of the weights. Since 0<S(u)<1, sqrt(e) h(u) S(u)^(beta') >= sqrt(e) h(u) S(u)^beta. Consequently, every object whose inequality is known for the original weights also satisfies it after reduction; any violation at reduced weights also violates at the original feasible weights. This comparison does not provide an admissible dominating weight vector for an arbitrary frame, or a reduction to a saturated frame.

## Limitations

All three search slots returned zero candidates. The pack supplies no new candidate object, failed-check calculation, or independently verified family exclusion for round 5. The exact monotonicity arguments above are analytic reductions; they are not inferred from unspecified numerical searches.

The earlier report mentions small-dimensional numerical exploration with arbitrary exposure directions, but supplies no objects, dimensions searched, parameter ranges, grid or sampling design, arithmetic precision, tolerances, or numerical outputs. None of those details or any numerical coverage claim can be recovered from this pack, and none is asserted here.

This round does not establish the inequality for general nonorthogonal fractional frames, arbitrary exposure directions or levels, genuinely higher-dimensional conditional events, mixed positive and zero weights, or general singular covariance. It supplies no general dominating-weight construction, no uniform control after the equal-threshold reduction, and no comparison between different baseline u values. Zero candidates is neither a proof nor independent evidence excluding these cases. The full target, the universality or sharpness of sqrt(e), and any BH FDR implication remain unproved by this round.
