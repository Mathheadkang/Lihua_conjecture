---
type: idea
title: 'Cold Phase I: signed BH boundary flux under Gaussian covariance interpolation'
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_two_sided_universal_order_upper
tags:
  - cold-phase-I
  - proof-architecture
  - covariance-flow
  - unproved
---

Phase I cold-context proposal. Only the supplied original Gaussian/BH problem was used. No project context, auxiliary nodes, or history were read. All claims below that are not standard Gaussian identities are explicitly unproved.

Mechanism: covariance heat flow with signed cancellation at BH rank-changing facets. Let Sigma_t=(1-t)I_N+t Sigma for 0<=t<1. At t=0 ordinary independent Gaussian p-values give FDR<=q m0/N, including negative one-sided true-null means. At t approaching 1 one recovers the requested arbitrary, possibly singular covariance model. The specifically Gaussian ingredient is Price's covariance differentiation identity: differentiation of Gaussian expectation along Sigma_t is one half the covariance-direction contraction with the distributional Hessian of the FDP function. The decisive object is its SIGNED surface flux: changes that add alternatives dilute FDP, changes that add true nulls increase FDP, and a simultaneous BH cascade must be charged with its full net change.

Connection to original BH. Let f_s(x) be V/(R vee 1) computed from the original means, original true-null set, and nonstrict BH applied to x. Set H_s(t)=E[f_s(theta+G_t)] for G_t~N(0,Sigma_t). On every compact subinterval below 1, calculate the derivative by summing codimension-two facets at which two p-values meet their relevant BH thresholds, including all rank-cascade jumps. Integrating an upper bound for the positive signed flux yields H_s(1)<=H_s(0)+controlled error. No monotonicity in covariance, null means, or q is assumed.

FIRST UNPROVED GATE (dimension-free signed covariance flux). For each s separately, is there A_s<infinity and q_s>0 such that for every finite original model and 0<q<=q_s the absolutely continuous derivative on 0<t<1 satisfies
[d H_s(t)/dt]_+ <= A_s q sqrt(log(1/q))/sqrt(1-t)
for almost every t? If differentiability fails, formulate the same domination for the positive-variation measure on each compact subinterval of [0,1). The norm or entrywise absolute sum of Sigma-I must NOT appear. The first proof obligation is to derive the exact facet formula and establish this signed contraction estimate, rather than bounding the absolute value of each facet separately.

Why this is a mechanism rather than a new name for the final budget. The proposed gate constrains the LOCAL response along a prescribed covariance flow for every t; it is substantially stronger than a single endpoint FDR estimate. Price's identity supplies an explicit pairwise geometric quantity to calculate and refute. The hoped-for cancellation is enforced by positive semidefiniteness together with the net FDP change across a BH cascade. It is currently a conjectural cancellation.

Quick falsification/support tests. For N=2 calculate H_s(t) by bivariate Gaussian integration for rho=+1 and rho=-1 endpoints, all possible null labelings, adverse alternative means, and one-sided negative null means. Maximize sqrt(1-t) [H_s'(t)]_+/(q sqrt(log(1/q))). Next use N=3 or 4 rank-one sign-pattern endpoints, tightly clustered alternative means near different BH critical values, and dense t grids approaching 1. Compute derivatives by the analytic bivariate facet formula where possible and verify finite differences with independent integration. Growth with means, N, or t after this normalization refutes the gate. Test s=2 separately because each absolute-value threshold has two facets and new sign combinations.

Final constants and endpoints. The integral of (1-t)^(-1/2) is 2, giving C_s=1+2 A_s once the gate holds. At a fixed finite model the singular endpoint may be taken by Gaussian coupling because the finitely many fixed threshold equalities have probability zero, even when correlations are singular; p-value ties away from a critical threshold do not themselves invalidate continuity. This endpoint passage is model by model and introduces no uniform regularization parameter. Uniformity must already be in the flux bound. A principal risk is that an interpolation can have large positive and negative oscillations even when its endpoint is small; if so the positive-flux gate is too strong and this architecture fails as stated.
