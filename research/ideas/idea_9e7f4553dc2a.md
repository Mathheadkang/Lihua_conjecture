---
type: idea
title: Exact single-score reduction for common-loading compression
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_common_loading_uniform_submodel_compression
tags:
  - compression
  - search-obstruction
  - tied-scores
---

A proof step isolated by round 1: handle a single tied-score atom exactly before treating multiple crossings. When every T_i equals T, both the full and resampled ordinary BH procedures have normalized actual largest rank 1{S(T) <= q}, including equality. With original true-tag fraction pi and sampled fraction pi_m, their FDP difference is 1{S(T) <= q}|pi_m-pi|. Index sampling is independent of T, and m pi_m is Binomial(m,pi), so its expectation is at most 1/(2 sqrt(m)); for admissible mixed tags the common mean is zero, S(T) is uniform, and the bound improves to q/(2 sqrt(m)). Singleton replication has zero error exactly. This rules out the entire one-score family as a source of nonvanishing compression error. It is a bounded proof step only: distinct score levels, competing crossings and microscopic ranks remain unresolved; it does not establish the target.
