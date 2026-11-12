---
type: idea
title: >-
  Finite-support posterior domination reduces gradient integrability to
  selector-mass control
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_averaged_signed_mean_level_complementarity
tags:
  - finite-support
  - posterior-gradient
  - uniform-integrability
---

For a fixed finite directing law pi=sum_i alpha_i delta_{x_i}, alpha_i>0, every nonnegative posterior density p relative to pi with integral p d pi=1 satisfies p(x_i)<=1/alpha_i. Thus any integrated selector density G(x)=integral p_u(x) d nu(u), with nu nonnegative and total mass at most C uniformly over the allowed selectors and j, satisfies 0<=G(x_i)<=C/alpha_i. This proves uniform integrability of that finite-support family and explains why the reported fixed finite-support searches did not produce a density-concentration counterexample. Before applying this reduction to V_+ or V_-, verify the normalization of p and the uniform total selector-weight bound from the approved definitions/variation result; the current summary pack does not reproduce those definitions. The target's proposed bound integral_a^1 |g_X'(r)| dr<=1+log(1/a), together with bounded Gaussian phi and fixed sigma, suggests the required weight control. This is only a draft finite-support proof step. It gives no bound for diffuse or infinite-support laws, no uniformity over varying pi or vanishing regularizers, and no maximum-specific complementarity conclusion.
