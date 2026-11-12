---
type: search_round
title: 'Fractional-frame surface kernel round 2: support and slice obstructions'
target_asset: gaussian_bh_fractional_frame_surface_kernel
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_fractional_frame_surface_kernel_r2_s1_simplex_positive_circuit
  - cand_gaussian_bh_fractional_frame_surface_kernel_r2_s2_balanced_tail
  - cand_gaussian_bh_fractional_frame_surface_kernel_r2_s2_simplex_cap
  - >-
    cand_gaussian_bh_fractional_frame_surface_kernel_r2_s3_zero_weight_oblique_vertex
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:02:44.120Z'
extension_version: 0.0.4
---

## Obstructions

- **Positive circuits make the conjunction empty, even without an antipodal pair.** If nonnegative numbers lambda_i, not all zero, satisfy sum_i lambda_i v_i=0, then every a_i>=u>=1 implies sum_i lambda_i a_i>0. Summing the constraints gives the contradiction 0>=sum_i lambda_i a_i. Thus the conditional kernel vanishes for every exposure, every canonical slice, and every admissible frame weighting. This rules out all positively dependent families, including the round's three-vector regular simplex with weights 2/3; singular coordinate covariance alone does not evade this obstruction.

- **Balanced orthogonal exposure cannot refute the bound along the tested tail scaling, for any u>=1.** For v_1=e_1, v_2=e_2, c_1=c_2=1, w=(e_1+e_2)/sqrt(2), equal thresholds u, and y=sqrt(2)u+1/(sqrt(2)u), put delta=1/(sqrt(2)u). The canonical conditional event is abs(Z)<=delta, so K=phi(y)[2 Phi(delta)-1]. Bounding its interval probability by 2 delta phi(0) and using S(u)>=phi(u)u/(u^2+1) gives
  $$
  \frac{K}{\sqrt e\,h(u)S(u)^2}
  \le \sqrt2(1+u^{-2})\exp\{-3/2-1/(4u^2)\}
  \le 2\sqrt2\,e^{-3/2}<1.
  $$
  The final strict inequality follows from e^(3/2)>29/8>3>2 sqrt(2). Raising either threshold with the same u only decreases the kernel. This covers the submitted u=10 object and this exposure scaling, not arbitrary y for the same frame.

- **A fixed simplex-cap alignment is excluded in every dimension by a necessary exposure threshold.** Let n=d>=2, let w be unit, and let z_i be unit regular-simplex residuals in w-perp with sum_i z_i=0 and sum_i z_i z_i^T=n(I-ww^T)/(n-1). Set v_i=sqrt(9/10)w+sqrt(1/10)z_i and c_i=10/(9n). Then beta=10/9 and the frame operator is ww^T+(I-ww^T)/(9(n-1))<=I. At u=1 and any deterministic a_i>=1, summing constraints forces y>=sqrt(10/9); outside that region the event is empty. Inside it K<=phi(sqrt(10/9)). With S(1)>=phi(1)/2,
  $$
  \frac{\phi(\sqrt{10/9})}{\sqrt e\,\phi(1)S(1)^{1/9}}
  =e^{-5/9}S(1)^{-1/9}
  \le [2\sqrt{2\pi}\,e^{-9/2}]^{1/9}<1.
  $$
  This excludes the cap family at this alignment and u=1 for every y, including the submitted n=1000, y=11/10 instance. It does not exclude other alignments or arbitrary u.

- **A supporting slice of zero intrinsic Gaussian measure contributes zero kernel; zero frame weights create no atom.** With v_1=e_1, v_2=e_2, c_1=c_2=1, w=(e_1+e_2)/sqrt(2), equal thresholds u>=1, and y=sqrt(2)u, the canonical conditional vector is (u,u)+Z(1,-1)/sqrt(2). Both constraints force Z=0, so the conditional probability is zero. The additional constraint v_3=w, c_3=0, a_3=u is satisfied deterministically and does not change that conclusion. More generally, any conditional event contained in a proper affine subspace of the exposure hyperplane has zero probability when that hyperplane has positive dimension. This argument concerns the conditional Gaussian's intrinsic support; it does not apply to a zero-dimensional canonical slice, where deterministic boundary events can have probability one.

## Limitations

All four round-2 candidates passed their hypotheses and failed NOT. None survived. The generalizations above follow from explicit inequalities and support calculations for the stated families; failed search checks do not prove the all-dimensional target.

The round does not control arbitrary nonorthogonal feasible frames, arbitrary exposure directions, unequal thresholds beyond monotone enlargement in the displayed families, or general correlated near-degenerate configurations. The balanced-frame estimate covers one exposure scaling; the simplex-cap estimate fixes the alignment at 9/10 and u=1. No reduction from arbitrary frames or arbitrary exposure levels to these configurations was established. Positive-circuit exclusion only removes geometrically infeasible conjunctions, leaving general feasible pointed geometries open. Conditional Gaussian-null slices were checked at supporting boundaries, not throughout neighborhoods of those boundaries.

Zero weights and singular coordinate covariances were tested in special configurations only. The universal constant sqrt(e), its sharpness, and any BH FDR implication remain unproved by this search. The earlier round's restrictions remain in force; this record adds no counterexample and no proof of the target.
