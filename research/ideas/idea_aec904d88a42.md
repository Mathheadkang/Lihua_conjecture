---
type: idea
title: >-
  Canonical zero-mean retagging is a moment-preserving dominance step for array
  extrema
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_exchangeable_array_variational_compactification
tags:
  - gaussian-bh
  - marked-arrays
  - canonical-retagging
  - search-obstruction
---

Round 1 search-summary proof step, supported by the stated failure of the two-mark zero-mean candidate. On each lawful parameter array replace every mark (theta_i,ell_i)=(0,0) by (0,1), leaving all means and covariances unchanged. This measurable coordinatewise transformation preserves joint exchangeability, lawfulness, and M_2, including its possible infinite value. Couple the observations identically before and after retagging: all p-values, the selected BH rank R_n, and rejection indicators agree. The finite FDP increases exactly by sum_{i<=n} 1{theta_i=0,ell_i=0}1{i rejected}/(R_n vee 1), hence F_n cannot decrease. Once the target's uniform completion is separately proved, the limiting F cannot decrease either. Thus, conditional on existence of a finite-second-moment maximizer, its retagging gives a canonical maximizer at the same level and penalty; this proves neither existence nor that every maximizer is canonical. The round's explicit q/2-to-q two-mark example is an illustration, not a proof of the remaining compactification claims. General value/continuity assertions may apply outside P_2, whereas penalized attained maxima are claimed within P_2.
