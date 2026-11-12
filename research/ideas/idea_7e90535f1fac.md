---
type: idea
title: Quantified radial tubes control full-rank null noise around a two-factor span
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Let the original true-null coordinates admit a Gaussian representation T_i=theta_i+v_i dot G+eta_i, with G standard Gaussian in R^2, theta_i<=0, ||v_i||<=1, eta_i centered Gaussian independent of G, and Var(eta_i)<=sigma^2. The eta_i may have arbitrary mutual covariance, and all alternatives may have arbitrary Gaussian coupling to this representation. For any b>=0, U=barPhi^{-1}(q), and U>=b sigma, any false rejection in the full original largest-crossing BH rule forces some T_i>=U. On the event eta_i<=b sigma for all original nulls, this forces ||G||>=U-b sigma. A union bound using marginal Gaussian tails, including zero-variance residuals, therefore gives FDR<=P(V>0)<=exp(-(U-b sigma)^2/2)+|I_0|barPhi(b). For b=0 zero-variance endpoints obey eta_i<=0 surely, so their union contribution can simply be omitted. No rank, coordinate or label is modified.

Hence a family with b sigma<=c/U and |I_0|barPhi(b)<=C q U, where c and C are fixed constants, has FDR<=e^c exp(-U^2/2)+CqU=O(qU). This remains valid with growing full null rank and arbitrary rare-alternative rank. Unlike the exact span-two radial obstruction, this covers quantified Gaussian tubes around that span, but it does not cover unrestricted residual noise or factor dimension.

The concrete failed round-2 slot-3 candidate has q_j=barPhi(j), n_j=ceil(exp(j^2)), sigma_j=j^-3, circular two-factor null directions, means -1/j, and independent rare alternatives of mean j/2. Taking b_j=2j and retaining the helpful negative mean gives FDR<=2exp(-j^2/2)<=8q_j sqrt(log(1/q_j)). Thus simultaneously vanishing residuals at this rate do not escape through the growth of full covariance rank.
