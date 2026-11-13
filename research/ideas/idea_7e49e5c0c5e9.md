---
type: idea
title: >-
  Unit-loading reduction for the rare-direction cap via law-preserving
  augmentation
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_rare_direction_cap
tags: []
---

Proof step for gaussian_bh_rare_direction_cap. Replace every loading a_k by a_k'=(a_k, sqrt(1-r_k^2) e_{d+k}) in dimension d+m. The joint law of T is unchanged and every r_k'=1. For distinct nulls i,k, w_i'^T w_k' = a_i^T a_k = r_i r_k w_i^T w_k (or 0 if r_k=0). With c=cos(kappa_2/u)>0, w_i^T w_k<c implies w_i'^T w_k'<c, so each augmented neighbourhood lies inside the original one plus i itself. Hence mu_i'<=mu_i and the original rare set is contained in the augmented rare set. The left side depends only on the law and is monotone in the set, so it suffices to prove the lemma for unit loadings with zero residuals (T=theta+AZ). This is the embedding that idea_573f557a7b59 leaves open. Caveat: the same augmentation makes every null with r_i<cos(kappa_2/u) rare once m>q^{-C_2}, so the lemma already implies the order bound for the FDR contribution of all non-saturated nulls. It is nearly as strong as the main target, minus the frozen nulls near r=1, and a proof cannot rely on rarity being a property of the law.
