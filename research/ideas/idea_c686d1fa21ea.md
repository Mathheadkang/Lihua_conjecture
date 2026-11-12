---
type: idea
title: >-
  Retain private Gaussian variance and microscopic-rank FDR defects in
  overlap-array limits
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
tags:
  - cross_field
  - spin_glass
  - defect_measure
---

Suggested by the teaching chat during the researcher's requested cross-field brainstorm. This is a lower-priority fallback for sequences whose covariance dimension escapes. It is not a proof of FDR continuity or the uniform order bound, and it should not interrupt the more concrete fixed-common-loading continuity route.

## Physics-inspired representation
Strong Wasserstein convergence of unit loading vectors is not a compactness principle: orthogonal directions can escape every compact subset of a Hilbert sphere. Instead, consider the distribution of the marked Gram array obtained by uniformly sampling coordinate indices from a finite model, keeping means, true-null tags, and overlaps. At fixed finite array size, overlaps lie in [-1,1]; diagonal subsequences preserve positive semidefiniteness and exchangeability. Unbounded means require an explicit tightness/compactification argument and are not automatically handled.

Dovbysh-Sudakov represents a weakly exchangeable positive-semidefinite array as
$$
R_{ab}=h_a\cdot h_b+d_a\mathbf1_{\{a=b\}}.
$$
At unit diagonal, d_a=1-||h_a||^2. This diagonal remainder preserves private Gaussian variance when diffuse orthogonal directions disappear from the shared overlap description. It is essential: replacing weakly vanishing loadings by zero without the remainder destroys the model. Extension to jointly carried means and null tags must be justified; the unmarked representation alone does not supply it.

## Keep the missing small-rank FDR explicitly
Overlap/empirical-law convergence alone does not determine full BH FDR. For a finite model define the positive measure on [0,1]
$$
\Lambda_N(B)=
\mathbb E\!\left[
\frac{V_N}{R_N\vee1}\,
\mathbf1_{\{R_N/N\in B\}}
\right].
$$
Its total mass is the actual FDR and is at most 1. At fixed q, subsequential weak limits exist on [0,1]. The candidate defect is the mass at zero of the limiting rank-weighted measure, not the probability of no rejections: each finite model contributes zero FDP at R_N=0, but nonzero FDP can concentrate at R_N/N->0.

Mandatory calibration: for independent all-null Gaussian tests, finite ordinary BH has FDR=q while R_N/N->0 in probability. Therefore Lambda_N tends to q times the point mass at zero. A naive limiting CDF G(t)=t has no positive BH crossing at q<1 and would erase exactly this contribution. This tests the representation; it is not a counterexample to the project's fixed sigma>0 continuity target.

## Concrete next lemma if the strong-W1 route stalls
For fixed q, establish a joint subsequential description of (marked overlap law, Lambda_N). On ranks bounded away from zero, identify the regular part using the actual largest crossing of the limiting model WITH its private variance. Retain Lambda({0}) as an explicit unresolved boundary contribution instead of declaring it zero.
For fixed positive common loading sigma, the separately proposed uniform microscopic-rank estimate should imply Lambda({0})=0. As sigma tends to zero, analyze whether and how this defect can reappear. No exchange of the N, sigma, or q limits is licensed.

This is useful only if the representation leads to a quantitative bound on the total regular part plus the defect. Compactness of Lambda_N at fixed q follows from FDR<=1 and gives no q sqrt(log(1/q)) bound. Do not normalize by the target rate and then assume bounded mass, which would be circular.

## Primary sources and their limited role
Dmitry Panchenko, On the Dovbysh-Sudakov representation result, arXiv:0905.1524v1 (2009), published Electronic Communications in Probability 15 (2010), 330-338, DOI 10.1214/ECP.v15-1562. https://arxiv.org/html/0905.1524v1 , Proposition 1 and equation (1.2), supplies the PSD exchangeable-array representation with a diagonal remainder. It does not contain a BH or rank-weighted limit theorem.

J.J. Alibert and G. Bouchitte, Non-Uniform Integrability and Generalized Young Measures, Journal of Convex Analysis 4 (1997), 129-147. https://www.heldermann-verlag.de/jca/jca04/jca04006.pdf , Theorems 2.5 and 2.9, separates ordinary oscillation limits from concentration defects for its specified linear-growth integrands. It motivates preserving a defect rather than throwing away microscopic mass. BH's moving denominator and discontinuous selection are outside a direct application; the Lambda_N construction above must be proved directly.

## Stop tests
Independent all-null dust must reproduce q delta_0; exact clones must preserve FDR under replication; mixed-label models must retain numerator labels. If two sequences have the same retained state but different limiting FDR or incompatible clone variations, enrich the state or abandon that compactification. No replica symmetry, ultrametricity, mean-field independence, or physical cavity closure is assumed.
