---
type: idea
title: >-
  Full-vector reflection retains null p-values but not the scalar small-loading
  hypotheses
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - reflection
  - variance-hypotheses
  - source-adaptation
---

Checked scope of a tempting extension of the published scalar-factor proof. For any centeredGaussian vector g andactualmeansθ, fullreflectiong↔−g preservesALLtwo-sided true-null p-values (θ_i=0). IfMnonnulls satisfy|θ_i|≥z(qM/(2N)), then each reflectedpair oftheir statistics hasmax(|θ_i+g_i|,|θ_i−g_i|)≥|θ_i|, so atleastoneof thetwo completeBH counts is≥ceil(M/2); thetrue integer candidate rankqualifies. However original LeiLemma4.5 transport uses a commonaffine scalarpathY_z=θ+αz+ξ (ξ frozen); it canbe usedalong a fixedray butnot atarbitrarynoncollinear factor points. More importantlyLemma4.6 smallloading usesσ_i²≥1−b², obtainedfromscalar α_i²+σ_i²=1. Along a multidimensionalray oneonlyhasα_i²+σ_i²≤1; noisyclones mayhaveσ²=η arbitrarily small evenwhenprojectedα=0. The adjusted densitylogcurvature atα=0 is1/(1−b²)−1/η<0 forη<1−b², so itsrequiredlogconvexityfails. Do not import the scalar rangebound underthisweakerhypothesis. Fullsource/probe record research-local/gaussian_bh_full_vector_reflection_probe_20261104_v1.md givesadditionalfirstcrossingcountergate; not anoriginalconjecturecounterexample. ThecurrentreflectionpairedLPdoesnotassumeLemma4.6 andmustproveitsownuniformfeasibility.
