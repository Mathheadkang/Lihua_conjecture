---
type: idea
title: >-
  Common-threshold fractional-frame surface inequality: concrete
  general-covariance extension to test
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - one-sided
  - surface-brascamp-lieb
  - fractional-frame
  - native-plan-first-tests
---

## Motivation and exact candidate

The root agent proposed extending the exposed-alternative surface factorial estimate beyond independent nulls by a fractional Gaussian frame. This record preserves the corrected common-threshold version only, after an explicit first test rejects the stronger individual-tail formulation. It is not a proved result or a new goal.

Let G be standard Gaussian in any finite dimension. Let v_i and w be unit vectors, and choose c_i>=0 such that
$$
\sum_i c_i v_i v_i^{\mathsf T}\preceq I.
$$
Write X_i=v_i dot G, Y=w dot G, s=sum_i c_i. For a common u>=1 and arbitrary higher thresholds a_i>=u, consider the explicit candidate
$$
\sup_y\phi(y)P(X_i>=a_i\ \forall i\mid Y=y)
\le C(u+1)\barPhi(u)^s. \tag{CSF}
$$
The unit exposure includes singular joint covariance. Since increasing thresholds only decreases the left side, it suffices to prove it when every a_i=u. Negative true-null means would then be included by monotonicity.

Ordinary Gaussian Hölder/Brascamp-Lieb gives an integrated probability bound with the product of marginal tails, but not this pointwise surface inequality. No such conditional implication is assumed. Native library search found no surface-frame analogue. The primary general Gaussian Hölder theorem identified by the root is Chen-Dafnis-Paouris, arXiv:1306.2410v2, Theorem 1; this record has not independently reconstructed that source's proof and does not cite it as a black-box dependency.

## First rejected stronger version

One must not replace the right side by C(u+1) product_i barPhi(a_i)^{c_i}. With one coordinate X_1=Y, c_1=1 and a_1=A much larger than fixed u, the maximum surface is phi(A), while barPhi(A) is smaller by the unbounded Mills factor A. Thus the individual-tail product version is false. This does not refute (CSF), whose right side deliberately uses only the common lower threshold u.

## Exact surviving basic checks

For one coordinate and weight c<=1, the scalar joint Gaussian tail-density bound gives a universal C(u+1)barPhi(u), which is at most the candidate's right side because barPhi(u)^c>=barPhi(u). In particular perfectly duplicate coordinates with weights summing to one reduce to this case.

For orthonormal v_i and c_i=1, (CSF) is exactly the exposed-alternative subset surface estimate proved in idea_ffde21d1df38. Fractions c_i<=1 only enlarge its right side. This covers arbitrary exposure w, not only a coordinate direction.

For two centered coordinates with correlation rho>=0, the balanced admissible weights are c_1=c_2=1/(1+rho). Take the potentially demanding sum exposure
$$
Y=(X_1+X_2)/\sqrt{2(1+rho)}.
$$
The independent contrast representation gives the exact surface function
$$
\phi(y)\left[
2\Phi\left(
\frac{\sqrt{(1+rho)/2}\,y-u}{\sqrt{(1-rho)/2}}
\right)-1
\right]_+.
$$
This formula makes the transition between a duplicate tail and a corner explicit. At fixed 0<rho<1 and u->infinity, maximizing at y=sqrt[2/(1+rho)]u+O(1/u) gives surface order
$$
\frac{e^{-u^2/(1+rho)}}{u\sqrt{1-rho}},
$$
up to rho-dependent constants. The candidate right side has order
$$
e^{-u^2/(1+rho)}u^{\,1-2/(1+rho)}.
$$
The ratio therefore has order u^{-2rho/(1+rho)}/sqrt(1-rho) for fixed rho. When (1-rho)u^2 is small the duplicate-tail scale instead gives O(u barPhi(u)), so no contradiction arises in that transition. A fully uniform rho proof, arbitrary exposure directions, and unequal frame weights still need checking; these asymptotics alone do not prove them.

For negative rho, the balanced frame uses 1/(1-rho), while the simultaneous upper-tail rate is exp[-u^2/(1+rho)]; the extra exponential deficit prevents the same fixed-rho corner test from obstructing (CSF). This also is only a concrete first calibration.

## Concrete proof attempt and BH application gate

A possible proof route is the monotone-transport proof of geometric Brascamp-Lieb applied to truncated scalar Gaussian densities, with the coarea of Y retained before integrating out the last coordinate. The desired new step is precisely to pay the exposure density by one common factor C(u+1), using the fractional-frame deficit. Replacing this by ordinary conditional Hölder is too weak even for the orthonormal frame with all correlations b_i=1/sqrt(d) and y near u sqrt(d); the negative residual dependence must be retained.

Even if (CSF) is true, it is not the BH theorem. An application needs an actual physical-rank fractional-cover allocation for the signed whole-share jump K_j in idea_ffde21d1df38. The frame weights cannot be selected from a relaxed null-only supremum or charged separately at each rank without controlling repeated payment. No such allocation is asserted here. This explicit geometric kernel, its rejected stronger version and the surviving finite checks are preserved for a real next proof attempt, rather than being presented as an established master budget.

## Subsequent concrete derivation

The root agent subsequently supplied the exact complete-frame/hyperplane argument, yielding the constant sqrt(e) h(u) in place of C(u+1). The full calculation, same-delegation scoped check and an inline monotone-transport proof of the needed geometric Brascamp-Lieb step are preserved in [Fractional-frame Gaussian surface bound by exact hyperplane Brascamp-Lieb](idea_ac8371a287d5.md). That record is still draft agent research, not a native independent verdict or an approved node. It supplies the common-threshold surface gate for full Gaussian covariance; actual signed BH rank allocation remains unproved.
