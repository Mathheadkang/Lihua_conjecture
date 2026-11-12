---
type: idea
title: >-
  Three family-specific growing-dimension BH reductions at a fixed private-noise
  floor
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_private_noise_floor_order
tags:
  - gaussian-bh
  - one-sided
  - fixed-private-noise-floor
  - search-round-2
  - family-specific
---

## Proposed step

The round-2 search context reports three distinct reductions for the tested growing-dimension families: Gaussian upper-orthant comparison plus a BH rank union bound gives FDR <= e q/(1-e q) for 0<q<1/e in the growing simplex family; splitting into the two positively correlated clouds gives FDR <= 2q in the tested antipodal-cloud family; nonnegative Gaussian conditional shifts give FDR <= q/2 for the tested vanishing-positive-mean, tied-alternative family. Each bound is uniform within its reported family under that family's fixed positive null private-noise floor. The bounds must remain separate; they do not cover arbitrary loading geometry or arbitrary q-dependent configurations.

## Provenance and status

These are candidate failure lines from the search_summary context pack, not independently audited candidate-body arguments or an approved result. Candidate IDs: cand_gaussian_bh_one_sided_private_noise_floor_order_r2_s1_growing_simplex; cand_gaussian_bh_one_sided_private_noise_floor_order_r2_s2_growing_antipodal_clouds; cand_gaussian_bh_one_sided_private_noise_floor_order_r2_s3_vanishing_mean_tied_alternatives. A possible next proof step is to inspect which explicit structural hypotheses each reduction uses before considering any extension. No extension to the whole fixed-floor class is asserted.

## Relation to previous approach

Builds on [the endpoint and bounded-dimension obstruction approach](.research-assistant-loop/open/idea_d7fe1abf6391.md), rather than duplicating those earlier reductions. The new content is the three separately bounded growing-dimension families. The separate draft idea_f57e24a559f1 concerns inequality (K) and supplies neither a refutation nor a proof of this target.
