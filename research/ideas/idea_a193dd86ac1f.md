---
type: idea
title: >-
  Noisy Gaussian cloning reduces finite BH models to conditional population
  mixtures
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - population-reduction
  - conditional-independence
  - finite-transfer
---

New reduction candidate under independent proof check, not an upper bound. For any fixed finite originalGaussian model Ti=θi+gi withactual labels, create M noisy clones per coordinate: Ti,l^η=θi+sqrt(1−η)gi+sqrtη εi,l, withindependentstandardε. All marginalvariances1, originalnegative/positive meanspreserved, PD forη>0. Given originalg, the clone CDFs are independent and the populationmixture is Fη(t|g)=N^{-1}Σ_i Q((Q^{-1}(t)−θi−sqrt(1−η)gi)/sqrtη), withanalogous null numerator. Candidate useful direction: asη↓0, itslargest population BH crossing and FDP converge a.s. to originalatomic BH decision, since originalp_i avoidall finitethresholds qk/N withprobability1. ForR>0 anatomic positive gap aroundt=qR/N makes the largest root transversal forsmallη; forR=0 must ruleout tiny-t ghostroots usingη≤1/4 andbounded conditional means on compact goodsets, yieldinguniformpower tail Fη(t)≤C t^{1+ε}. Boundedconvergence would transfer ANY future uniform population-mixture upper bound to the original finite model. Do NOT assert the iterated limitM→∞ at everyfixedη withoutproving rootregularity: tangency can invalidate naive uniformLLN. If finiteM transfer is wanted, choose a diagonalM(η) usinggoodset atomicmargin plus relative-tail controls. Factor dimensionremainsN and arbitrary; this is not onefactor extremality and does not solve the populationvariational bound, which remains the main difficulty.
