---
type: idea
title: >-
  Rank-adaptive convex isotonic energy and its unresolved label/rank
  localization
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - universal-order
  - convex-proxy
  - isotonic-energy
  - positive-mixed-hessian
  - online-resource-trial
---

NEW DRAFT trial after exact common-anchor and peeling-history fluxes saturated at the unknown FDR. Unlike the disproved exact-gradient representation of BH weights, this constructs a DIFFERENT convex proxy and explicitly accounts for the missing transfer. It is not a main proof and no imported theorem is a black box.

For q with U=S^{-1}(q)>=3, put u_j=S^{-1}(qj/N) and lambda_j=u_j-4/u_j>0. Define the one-sided sorted-l1 prox by maximizing over b>=0

$$
F(T)=\sup_{b\ge0}\{T^\top b-\sum_{j=1}^N\lambda_j b_{(j)}-\|b\|^2/2\}=\|x(T)\|^2/2.
$$

Here x is the unique maximizer and is computed by sorting T decreasing, projecting d_j=T_(j)-lambda_j onto the decreasing nonnegative cone, and aligning back. Reprove this finite PAVA characterization inline. With fixed thresholds and positive PAVA blocks B, the a.e. Hessian of F is 1_B1_B^T/|B| on each positive block, zero elsewhere. Thus every mixed derivative is nonnegative. After mollification, Gaussian interpolation along Sigma_t=(1-t)Sigma+tJ gives

$$
\mathbb E F(\theta+Z_\Sigma)\le\mathbb E F(\theta+Z\mathbf1)
$$

for EVERY fixed theta and unit-diagonal PSD Sigma. Polynomial growth controls singular limits at fixed N. This is an exact external comparison for the unlocalized energy, not an independent Gram maximization. For theta0, common-factor prox is (Z-barlambda)_+*1, yielding E||x||^2<=N E(Z-barlambda)_+^2.

Deterministic BH margin: if ordinary BH has largest rank k>0, then every selected proxy coordinate is at least1/u_k. For any suffix a:k, w=avg u_j<=u_k+1/u_k=v by a right-Riemann Gaussian quantile integral; Jensen gives avg lambda<=w-4/w<=v-4/v<=u_k-1/u_k. Every selected score is>=u_k; the isotonic min-max formula therefore gives x_k>=1/u_k. In particular BH(q) support is inside proxy support. If proxy support has size m>0, its final positive PAVA block ends at m with d_m>=its positive block mean, hence T_(m)>lambda_m. Mills integration gives S(u-4/u)/S(u)<99 for u>=3, so when99q<1 the proxy support is inside ordinary BH(99q). Reprove both directions, ties and positivity before use.

Why easier normalizations do not finish: dividing x by sum x can lose BH false-discovery mass already for two coordinates with one arbitrarily high alternative. Capping does not remove arbitrary support inflation. With T1=u1+M and T_j=u_j-1/U for j>=2 in the OLDER fixed-shift proxy lambda_j=u_j-2/U, BH R1 while all capped scores equal1. Fixed shifts also give unbounded first-threshold inflation exp(c u1/U) as N grows even under iid nulls; this is why the rank-adaptive penalty is used. None of these pointwise failures by itself rules out a carefully proved expected Gaussian transfer, but no such transfer is supplied.

Concrete next calculation: let F_alt be the same prox energy on the original alternative coordinates only, KEEPING the first |I1| lambda thresholds from the same original N and q, so embedding b_null0 gives DeltaF=F_N-F_alt>=0. Compute its ACTUAL mixed-Hessian table on finite PAVA cells: null rows retain F's nonnegative blocks, while alternative-alternative entries can subtract a positive block and lose their sign. Do not assume label subtraction preserves the covariance comparison.

Also investigate the explicit two-parameter family F(T-a*1_I0-c*1). On a smooth positive PAVA cell H1=1 on active coordinates, so candidates to verify are partial_c^2F=R_proxy and partial_a partial_cF=V_proxy, with the original labels. Rank normalization or finite differences introduce block-interface terms; derive them before claiming any sign. Try a finite shift/Laplace localization with exact coefficients and actual covariance, and exhibit the first signed remainder if localization destroys the comparison. A successful potential must dominate the original BH FDP with a common-factor expectation O(q(1+U)), without N/R, model complexity or uncontrolled alternative means. This is the unproved gate, not a theorem already obtained from convexity.

Primary-source scoped check: Malgorzata Bogdan, Ewout van den Berg, Chiara Sabatti, Weijie Su and Emmanuel J. Candes, SLOPE—Adaptive Variable Selection via Convex Optimization (2015), original full text https://pmc.ncbi.nlm.nih.gov/articles/PMC4689150/ , Proposition2.2 and section2.3 describe the isotonic proximal mechanism. Theorem1.1 uses orthogonal design and iid Gaussian noise with two-sided zero null coefficients; it does not prove the arbitrary-covariance, arbitrary-mean one-sided target here. All one-sided proxy formulas, rank margins and Gaussian comparisons above require full reconstruction and fresh checking in the native trial. No bibliography or existing research asset has been edited.

## Resolution

Converted to native convex isotonic energy and labelled-curvature trial; source calculations are candidates until execution and independent checking.
