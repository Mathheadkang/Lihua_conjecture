---
type: search_round
title: Fractional-frame surface-kernel round 1 exposure obstructions
target_asset: gaussian_bh_fractional_frame_surface_kernel
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_fractional_frame_surface_kernel_r1_s1_rank_one_boundary
  - cand_gaussian_bh_fractional_frame_surface_kernel_r1_s2_orthogonal_axis
  - cand_gaussian_bh_fractional_frame_surface_kernel_r1_s2_scalar_aligned
  - cand_gaussian_bh_fractional_frame_surface_kernel_r1_s2_scalar_opposed
  - cand_gaussian_bh_fractional_frame_surface_kernel_r1_s2_three_vector_frame
  - cand_gaussian_bh_fractional_frame_surface_kernel_r1_s3_frame_epsilon_excess
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T19:56:58.081Z'
extension_version: 0.0.4
---

## Obstructions

- Aligned rank-one constraints with exposure along their common line cannot refute the target. If all v_i=v and w=+v or -v, the PSD hypothesis gives beta<=1. Set A=max_i a_i>=u. The canonical conditional event is deterministic, so its surface kernel is either zero or at most phi(A)<=phi(u). Meanwhile sqrt(e)h(u)S(u)^beta=sqrt(e)phi(u)S(u)^(beta-1)>=sqrt(e)phi(u). This covers the duplicate scalar-aligned and rank-one-boundary candidates, including equality at the deterministic threshold, for every u>=1 and every admissible choice of weights and thresholds in this family.
- Any family containing opposite constraint vectors v_i=v and v_j=-v with positive thresholds has an empty conjunction: v.G>=a_i and -v.G>=a_j imply 0>=a_i+a_j>0. Hence its kernel is zero for every exposure and every admissible frame weighting. This explains the opposed scalar candidate without relying on numerical evaluation.
- An orthonormal constraint family exposed along one of its axes cannot refute the target. For v_i=e_i, w=e_1 and n<=d, the conditional kernel is phi(y)1_{y>=a_1} product_{i=2}^n S(a_i)<=phi(u)S(u)^(n-1). Each c_i<=1, so beta<=n; dividing by the proposed bound gives at most exp(-1/2)S(u)^(n-beta)<=exp(-1/2). The reported n=2, c_i=1, u=a_i=y=1 object attains this ratio within the family.
- In the reported three-vector geometry v_1=w=e_1, v_2=(1/2,sqrt(3)/2), v_3=(1/2,-sqrt(3)/2), c_i=2/3, with u=a_i=1, every exposure y>=3 is too far into the Gaussian tail to refute the target: the kernel is at most phi(y)<=phi(3). The proposed bound is phi(0)S(1)>phi(0)phi(2)>phi(3), since S(1)>integral_1^2 phi(2) dz and phi(3)/(phi(0)phi(2))=sqrt(2*pi)exp(-5/2)<1. At the tested y=3 the exact kernel is phi(3)[2 Phi(1/sqrt(3))-1]. This obstruction is restricted to the stated geometry, thresholds and exposure range.
- Scalar frame-excess perturbations cannot refute the stated lemma: in dimension one, sum_i c_i v_i v_i^T=beta, so any beta>1 violates the PSD hypothesis before the conclusion is tested. The candidate with excess 10^-6 therefore supplies no conclusion-level evidence.

## Limitations

The six submitted candidates contain no survivor; two are the same scalar boundary object. Failed NOT checks and the elementary restricted-family bounds above are not a proof of the all-dimensional target. The frame-excess candidate fails a hypothesis, so it does not test the asserted conclusion.

This round does not cover arbitrary nonorthogonal frames and arbitrary exposure directions, general higher-dimensional fractional tight frames, or general correlated near-degenerate configurations. In particular, the three-vector calculation above does not establish the bound for all exposure values, all u, or all threshold choices even in that geometry. No reduction from arbitrary dimension to the displayed families was established. Arbitrary zero-weight constraints and singular joint covariances were only encountered in special configurations; their unrestricted behavior remains uncovered. The universal constant sqrt(e), its possible sharpness, and any application to a BH FDR bound remain unproved by this search.
