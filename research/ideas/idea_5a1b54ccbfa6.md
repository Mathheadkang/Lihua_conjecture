---
type: idea
title: Reduce all-null spherical BH contacts to a single radial onset
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
tags:
  - spherical-population
  - population-bh
  - radial-onset
  - search-round-4
---

The round-4 candidate cand_spherical_isotropic_population_bh_bound_r4_s8_all_null_large_dimension supplies a global contact argument for the restricted all-null family W=delta_0. It works for every integer d>=4 and every u>=104, q=2Q(u), rather than only the candidate's displayed dimension.

For fixed x>u, r -> H_r(x) is continuous and strictly increasing from 0 to 1/2 on r>x. Let b(x)>x be its unique solution H_{b(x)}(x)=Q(x)/q. The spherical-tail inverse gives continuity of b. As x decreases to u, b(x) tends to infinity because Q(x)/q tends to 1/2 while a positive-cutoff cap has mass strictly below 1/2 at every finite radius. Also b(x)>x implies divergence as x tends to infinity. Hence b has a finite attained minimum b_*=b(x_*) at x_*>u.

For W=delta_0, F_r(x)=2H_r(x), so finite contact is equivalent to r>=b_*; the endpoint x=u is never admissible at finite r. All rejections are null, hence FDR_pop=P(R>=b_*). Radial monotonicity and the Gaussian marginal identity give

$$
Q(x_*)=\mathbb E H_R(x_*)\geq\mathbb P(R\geq b_*)H_{b_*}(x_*)=\operatorname{FDR}_{\mathrm{pop}}\,Q(x_*)/q.
$$

Thus FDR_pop<=q for the entire all-null family, including dimensions depending on q. This is an analytic family exclusion, not a proof of the target for nontrivial mean mixtures. For positive means, F_r(x) need not have this monotone radial structure; contact births, switches, and the mixed-law FDR remain unresolved by this step. The proposed route is to identify whether any suitably restricted mixed family admits an equally global radial-onset replacement before using local derivatives.
