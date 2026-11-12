---
type: idea
title: >-
  Use second-moment tail control to exclude Wasserstein escape in a fixed moment
  cap
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_quadratic_penalized_population_maximizers
tags:
  - compactness
  - wasserstein
  - search-obstruction
---

Round 4's positive- and negative-mean escaping-atom candidates fail to refute the target because a finite uniform second-moment cap C gives the uniform bound integral_{|theta|>R} |theta| d pi <= C/R. An atom of mass p at mean magnitude R obeys p R <= C/R whenever p R^2 <= C. Consequently, escape of second-moment mass may produce a strict second-moment drop at a Wasserstein limit without causing nonvanishing first-moment tail cost; this is consistent with lower semicontinuity. Use this tail estimate as an ingredient in a fixed-dimension Wasserstein compactness proof, together with a separately justified weak compactness argument and preservation of the closed tagged domain. Neither general compactness nor penalized attainment has been proved by these candidate failures. Source: round-4 candidate summaries in the search_summary context pack.
