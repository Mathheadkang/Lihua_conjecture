---
type: search_round
title: 'Round 3: conditional Gaussian tail obstructions for fractional frames'
target_asset: gaussian_bh_fractional_frame_surface_kernel
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_fractional_frame_surface_kernel_r3_s1_independent_nullspace_slice
  - >-
    cand_gaussian_bh_fractional_frame_surface_kernel_r3_s2_three_equicorrelated_axis
  - >-
    cand_gaussian_bh_fractional_frame_surface_kernel_r3_s2_two_oblique_perpendicular
  - >-
    cand_gaussian_bh_fractional_frame_surface_kernel_r3_s3_transverse_fractional_frame
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:19:20.011Z'
extension_version: 0.0.4
---

## Obstructions

All four candidates passed H1--H9 and failed NOT. The bounds below concern their specified frames and weights at u=1. Each also covers arbitrary deterministic threshold enlargements a_i>=1 by event inclusion. Candidate Object/Checks sections were retrieved with native show because the pack's failure lines omitted the geometry needed to specify these families precisely. No numerical approximation is needed.

- **Independent nullspace exposure leaves a stronger active-coordinate tail.** For v_1=e_1, v_2=(1/2,sqrt(3)/2,0), v_3=(1/2,-sqrt(3)/2,0), w=e_3, and c_i=2/3, the active conjunction with unit thresholds is X>=2+sqrt(3)|Z|. For every real exposure y it therefore gives K<=phi(y)S(2)<=phi(0)S(2)<phi(0)S(1). Since beta=2, the last expression is the proposed bound. An independent exposure at its maximal density cannot overcome this stronger tail requirement; singularity of the frame operator creates no violation here.

- **Summing correlated residual constraints gives a one-dimensional Gaussian upper bound.** For the three unit vectors with pairwise inner product 1/4, c_i=2/3, and w=v_1 at y=1, put R_j=v_j dot G-1/4 for j=2,3 under the canonical conditional law. The residual variances are 15/16 and covariance is 3/16. The conjunction forces R_2+R_3>=3/2, while this sum is centered Gaussian with variance 9/4. Hence K<=phi(1)S(1)=exp(-1/2)B, where B=phi(0)S(1) is the beta=2 bound. Every realization of this Gram geometry with this exposure, and every threshold enlargement, is excluded. This calculation does not cover other y.

- **A constraint perpendicular to the exposure retains an unconditional scalar tail.** For v_1=(1,0), v_2=(1/3,2sqrt(2)/3), w=(2sqrt(2)/3,-1/3), and c_1=c_2=3/4, the canonical slice is yw+Zv_2. The v_2 constraint forces Z>=1 for every y, so K<=phi(y)S(1)<=phi(0)S(1)<phi(0)S(1)^(1/2)=B. Thus the entire exposure family for this fixed oblique frame is excluded, rather than only the submitted y=1 object. At y=1 and unit thresholds, K/B=exp(-1/2)S(1)^(1/2).

- **Transverse symmetric constraints raise the surviving scalar threshold.** For v_1=(sqrt(3)/2,1/2), v_2=(sqrt(3)/2,-1/2), w=e_2, and c_1=c_2=2/3, the unit-threshold conjunction on the slice (X,y) is X>=(2+|y|)/sqrt(3). Consequently, for every y,
  $$
  K=phi(y)S((2+|y|)/sqrt(3))
  <=phi(0)S(2/sqrt(3))
  <phi(0)S(1)^(1/3)=B.
  $$
  The strict inequality uses 2/sqrt(3)>1 and 0<S(1)<1. Saturation of the top frame eigenvalue with fractional weights therefore supplies no counterexample throughout this fixed frame's transverse exposure family.

## Limitations

These are exact exclusions of four specified Gram geometries, not an exhaustive classification of fractional frames. The exposure extensions for the first, third, and fourth families follow from the displayed conditional laws; the equicorrelated residual-sum bound remains restricted to y=1. All four families fix u=1 and their stated weights. Threshold monotonicity extends them only to a_i>=1 at this same baseline; it is not a proof for arbitrary u>=1, arbitrary angles, different weights, or a different exposure direction.

No worker established a reduction from arbitrary d,n and feasible nonorthogonal frames to these configurations, nor a uniform estimate over all feasible pointed constraint geometries. This round does not control general nearly singular correlated slices or arbitrary zero-weight constraints. The nullspace example treats one rank-two frame embedded in dimension three; the other examples do not resolve general singular canonical events or the zero-dimensional conditional case. Earlier positive-circuit and Gaussian-null supporting-slice obstructions remain available but were not expanded to arbitrary neighborhoods this round.

The nonnegative residual-sum argument is a useful upper-bound step, but no choice of aggregate coefficients has been shown to recover the proposed constant uniformly over frames, exposure levels, and thresholds. No counterexample survived this round. The target, universality or sharpness of sqrt(e), and any BH FDR implication remain unproved by these searches.
