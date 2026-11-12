---
type: idea
title: >-
  Use the finite simplex to verify the dimension-one zero-cap compactness
  boundary
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_quadratic_penalized_population_maximizers
tags:
  - compactness
  - zero-cap
  - search-obstruction
---

The round-3 failed candidate isolates a boundary proof step for part 1. For d=1 and M_2 <= 0, nonnegativity forces the mean to be zero almost surely; the unit directions are +1 and -1, and both tags are allowed at zero in the analytic completion. Every such law is therefore a weight vector on four fixed tagged atoms. Match common atom mass and transport only unmatched mass: W_1 is at most (D/2) times the sum of absolute differences of the four weights, where D is the diameter of these atoms in the stipulated parameter metric. The continuous image of the compact probability simplex is compact in W_1. This verifies only this boundary case and rules out irrational weights or antipodal directions as noncompactness mechanisms there. It does not prove general positive-cap compactness, penalized attainment, or any other part of the target. Evidence: the sole round-3 candidate failure line in the search_summary context pack.
