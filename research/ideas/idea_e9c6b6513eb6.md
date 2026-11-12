---
type: idea
title: Monotonicity gives attainment and equality at the largest population crossing
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_rare_clone_mills_variation
tags:
  - rare-clones
  - population-crossing
  - boundary-cases
---

For the rare downward-mean clone population crossing, fix any deterministic score vector t. Write H(x)=H_epsilon(x;t) for 0<x<=N and rho=sup({0} union {x in (0,N]:H(x)>=x}). The defining count and offset CDF show H is nondecreasing and 0<=H(x)<=N. If rho>0, choose qualifying x_n with x_n<=rho and x_n->rho. Monotonicity gives H(rho)>=H(x_n)>=x_n, so H(rho)>=rho and the supremum is itself qualifying. If rho<N and H(rho)>rho, choose x with rho<x<=N and x<H(rho). Then H(x)>=H(rho)>x, contradicting the definition of rho. If rho=N, the bound H(N)<=N gives equality directly. Thus every positive rho is attained and satisfies H(rho)=rho, including contacts with atoms and the endpoint rho=N. No continuity assumption is needed for this argument.

Scope: this is only the deterministic attainment/equality step. It does not prove convergence from finite K, stability at tangencies, identification of exceptional score sets, interchange with expectation, or the first-order inverse-Mills variation.
