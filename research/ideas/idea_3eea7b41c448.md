---
type: idea
title: >-
  Rare downward-mean clones can realize the inverse-Mills rank cost without
  unlawful zero-null compensation
status: resolved
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_growing_clone_compensated_variation
  - gaussian_bh_correlated_clone_first_variation
tags: []
resolved_by: gaussian_bh_rare_clone_mills_variation
---

New concrete route to audit; no theorem or main bound claimed. It targets the nonlinear rank-cost obstruction more directly than Gaussian private noise. Fix q<1/2, N, U=S^{-1}(q)>0, m(u)=S(u)/phi(u), h=1/m, A(u)=q/[N phi(u)], so A_r=A(u_r)=1/[r h(u_r)]. Elementary identities give d^2 m(u(A))/dA^2=1/[A^2 u(A)^3]>0 and m_A=(m(u)-1/u)/A. Hence psi(A)=1/U-m(u(A)) is increasing concave for A>=A(U); extend linearly to0 with slope L=psi'(A(U))=N[h(U)/U-1]. This extension has psi(0)=0 and tangent match at A(U). Explicit realization: for sufficiently small epsilon with epsilon L<1, a deterministic copy-offset distribution puts mass1-epsilon L at0, and mass epsilon*(N/q)*phi(v)/v^2 dv at downward mean offset epsilon*(1/U-1/v), v in[U,infinity). Total minority mass is epsilon L because integral_U^infty phi(v)/v^2 dv=phi(U)/U-S(U). Uniformly copy every original coordinate K times; only chosen coordinate i's copies get these nonnegative downward offsets, approximated by a deterministic quantile array as K->infinity FIRST. Unit directions stay v_i, so all finite arrays are exactly jointly Gaussian with unit variance. Every true-null label is preserved even when theta_i=0; other nonzero chosen means retain their sign for epsilon small. No positive mean compensation or private noise is needed. At a putative r-face, discarding the worst minority tail indexed v costs lost rank mass epsilon z(v), where z(v)=(N/q)[phi(v)/v-S(v)]. The first contact cost is heuristically epsilon inf_{v>=U}{A_r z(v)+1/U-1/v}. Its derivative in v equals [1-A_r/A(v)]/v^2, so the unique minimum is v=u_r and its value is epsilon[1/U-m(u_r)]. Thus a candidate exact variation is (lim_K F_{K,epsilon}-F)/epsilon -> -sum_r [1/U-m(u_r)] mu_{i,r}(total). The crucial new feature is a nonlinear inverse-Mills coefficient with lawful zero-null labels. Fractional deficit is bounded by epsilon L and occurs only in an O(epsilon) chosen-score band, suggesting O(epsilon^2) FDP/clipping errors under fixed original PD joint densities; prove this globally at the COMMON largest rank, not per-block optima. Need a full finite-copy limit, exact atom/quantile convention, actual-rank comparison, signed jumps, all boundaries, and independent verification. Even if proved, it does not solve near-extremizer comparison. At a hypothetical stable maximum it only yields sum m(u_r)mu <=(1/U)sum mu, leaving a potentially large unmatched boundary mean-flux term at zero-null coordinates; no q-scaled payment for that term has been shown.
