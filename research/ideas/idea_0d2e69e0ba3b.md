---
type: idea
title: >-
  Two obstructions to conditional tail-ratio routes: duplication defeats
  leave-one-out regression, over-revealing conditioning defeats
  alternative-conditioning
status: draft
idea_kind: risk
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - obstruction
  - conditioning
---

(1) Rigorous. For a true null i let r_i be the multiple correlation of T_i with T_{-i}, S_i its standardized best linear predictor, s_i^2=1-r_i^2. Given T_{-i}, T_i=theta_i+r_i S_i+s_i eps_i with eps_i independent of T_{-i}, and the forced-zero BH threshold tau^(i) is T_{-i}-measurable, so E[1{i in R}/R]=(q/N)E[F_{r_i,S_i}(tau^(i))/tau^(i)] with F the conditional null CDF (singular Sigma allowed). Lei's integrated tail-ratio bound on {S_i<=u} then gives, for EVERY admissible model, FDR <= q pi0 (1/2+u/sqrt(2pi)) + B, B=E[#{i in R cap I0: S_i>u}/(R v 1)]; the main term already has the conjectured constant. But duplicating every coordinate leaves BH rejections essentially unchanged and forces r_i=1, S_i=T_i-theta_i, hence B=FDR. So bounding B is exactly as hard as the conjecture; any per-null conditioning on T_{-i} is not duplication-robust. (2) Heuristic estimate, to be checked. Conditioning instead on the full alternative vector T_A is duplication-robust and gives a flood floor: tau >= t_A, the BH threshold of the alternatives alone with denominator N. Under conditional PRDS of the nulls given T_A, E[FDP|T_A] <= min{1,(q/N) sum_i sup_{t in [t_A,q]} F_i(t)/t}. Proposed obstruction: nulls r_0 Z_0+r_1 Z_g+s eps (common factor Z_0 plus G independent block factors Z_g, r_0=r_1 small), alternatives that adapt the threshold to Z_0 (Lei-type), plus never-significant alternatives that reveal every Z_g. The true FDR stays about q gamma u/sqrt(2pi), yet the bad-region part from nulls whose alternative-predicted value exceeds u is about (1-1/sqrt 2) of the target, while the good-region bound alone is already about the target: total about 1.29 times the target. General lesson: conditioning on a sigma-field G and taking sup_t of G-conditional tail ratios is sharp only if the BH threshold actually adapts to G's information about the nulls. A sharp proof must use only threshold-relevant information (pivotality), not all available information.
