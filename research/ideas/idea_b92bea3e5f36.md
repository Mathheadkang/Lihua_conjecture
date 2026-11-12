---
type: idea
title: >-
  Reduce a canonical Gaussian conjunction to a nonnegative aggregate residual
  tail
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_fractional_frame_surface_kernel
tags:
  - gaussian-bh
  - fractional-frame
  - conditional-gaussian
  - search-obstruction
---

For the canonical conditional law G=yw+(I-ww^T)G_0, choose deterministic lambda_i>=0 and define A=sum_i lambda_i a_i, m=sum_i lambda_i(v_i dot w), and r=(I-ww^T)sum_i lambda_i v_i. Every conjunction v_i dot G>=a_i implies r dot G_0>=A-ym. If ||r||>0, its conditional probability is therefore at most S((A-ym)/||r||), and its surface kernel is at most phi(y)S((A-ym)/||r||). If r=0 and A-ym>0 the conjunction is empty; if r=0 and A-ym<=0 this aggregate alone supplies no restriction. This elementary implication is a possible proof step, not a proof of the fractional-frame target. In round 3, three unit vectors with pairwise inner product 1/4, weights 2/3, w=v_1, a_i=u=y=1, and lambda_2=lambda_3=1, lambda_1=0 give A=2, m=1/2, ||r||=3/2. Thus P(conjunction|w dot G=1)<=S(1) and K<=phi(1)S(1)=exp(-1/2) times the proposed beta=2 bound. This also covers threshold enlargements at the same baseline and exposure. The unresolved step is whether an appropriate nonnegative aggregate, or another argument when this bound is loose, yields sqrt(e)h(u)S(u)^beta for every admissible frame and exposure. Source: cand_gaussian_bh_fractional_frame_surface_kernel_r3_s2_three_equicorrelated_axis and search_gaussian_bh_fractional_frame_surface_kernel_r3_conditional_tail_obstructions.
