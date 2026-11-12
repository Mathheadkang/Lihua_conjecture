---
type: idea
title: Private-noise regularization may erase first-order rare-clone responses
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
  - gaussian_bh_rare_clone_mills_variation
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

A scope risk for later use, not a refutation of either target. Fix positive private smoothing s, common loading sigma and cutoff a, and a fixed directing population with finite second moment. A rare mean clone changes a pre-noise fraction O(epsilon) by a displacement O(epsilon). Every conditional Gaussian-smoothed total/true score-tail changes by at most O(epsilon^2/s), whereas the approved unsmoothed finite/growing-clone variation can have order-epsilon responses. To justify an o(epsilon) response after averaging moving BH folds, establish uniform integrability of the posterior selector gradients over this rare-transport path (the energy truncation and bounded macro-quantile argument in the signed-complementarity idea is a possible route); pointwise conditional O(epsilon^2) alone is insufficient when its random constant is not integrable. Therefore do not transfer the old rare-clone derivative to a fixed private-noise optimizer or exchange s,a with epsilon without a separate uniform estimate. Value recovery as s,a decrease does not provide such derivative recovery. This is an unproved diagnostic obligation; preserve all approved statements.
