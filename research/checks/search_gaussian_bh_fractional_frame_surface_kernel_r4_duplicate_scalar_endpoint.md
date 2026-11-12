---
type: search_round
title: 'Round 4: repeated scalar boundary endpoint without new coverage'
target_asset: gaussian_bh_fractional_frame_surface_kernel
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_fractional_frame_surface_kernel_r4_s1_zero_dimensional_boundary
  - >-
    cand_gaussian_bh_fractional_frame_surface_kernel_r4_s2_zero_dimensional_boundary_atom
  - >-
    cand_gaussian_bh_fractional_frame_surface_kernel_r4_s3_zero_dimensional_boundary
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:21:53.988Z'
extension_version: 0.0.4
---

## Obstructions

- **A deterministic zero-dimensional boundary event still pays its exposure density.** All three workers submitted the same scalar endpoint: d=n=1, v_1=w=1, c_1=beta=1, and u=a_1=y=1. The canonical conditional law is the point mass at 1, so the closed threshold event has probability one and the kernel is phi(1). The proposed bound is sqrt(e) h(1) S(1)=sqrt(e) phi(1), giving the exact ratio exp(-1/2)<1. Thus every submission passes H1--H9 and fails NOT. Positive conditional mass at this deterministic boundary does not produce a violation. This endpoint had already been tested in round 1 and generalized there; these three submissions supply one repeated check, no new family, coverage, or mathematical mechanism. The round is not three distinct exclusions.

The round pack supplied only the failure lines. The Object section of cand_gaussian_bh_fractional_frame_surface_kernel_r4_s1_zero_dimensional_boundary was retrieved with native show solely to verify the scalar parameters stated above; no other candidate bodies or proofs were read.

## Limitations

No worker departed from the previously tested scalar endpoint. In particular, this round added no coverage of nonorthogonal frames, genuinely higher-dimensional conditional slices, arbitrary exposure directions or exposure levels, different feasible weights, general singular covariance, or arbitrary zero-weight constraints. It did not extend the prior scalar-family generalization or establish any reduction from general frames to that family.

No counterexample survived, but duplication is not independent breadth of evidence. The target's full uniform inequality, the universality or sharpness of sqrt(e), and any BH FDR implication remain unproved by this round. The exposure-density calculation is recorded only as an already-known local proof step; it supplies no uniform control of general conditional events.
