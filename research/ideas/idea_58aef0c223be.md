---
type: idea
title: >-
  Integrate the upper-branch clone deficit to bound fractional FDP below the
  compensated scale
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_growing_clone_compensated_variation
tags: []
---

Proposed elementary estimate to verify, not an established general proof. For an active upper branch with k=r-1 unchanged selected blocks, parameterize chosen fraction nu=Phi(t) near1 and contact m(nu)=u(k+nu)-s S^{-1}(nu)=u(k+Phi(t))+s t. Let A(x)=1/[x h(u(x))], so dm/dt=s-A(k+Phi(t)) phi(t). On the stable upper branch starting at its minimum t_c, dm/dt>=0, phi(t_c)=s/A(k+Phi(t_c)), and t_c~t_s. If the conditional common-location density is bounded (original PD), then the integrated selected-fraction deficit is bounded by C integral_{m_c}^infty (1-nu_+(m)) dm <= C s integral_{t_c}^infty S(t) dt = C s[phi(t_c)-t_c S(t_c)] = O(s^2/t_s^2) at fixed N,q and background covariance. The negative -A phi term was dropped only on this stable branch; the last estimate requires a checked Gaussian Mills remainder. For k>=1 the FDP ratio is Lipschitz in nu near1, so this would make fractional-FDP error o(s/t_s). For k=0 the FDP is identically the chosen null label whenever that branch exists, independent of the selected fraction. Remaining obligations: prove upper-branch existence/classification and minimum asymptotics, handle truncation by unchanged-atom jumps and all global-largest-root switches, control lower branches and microscopic empirical roots, and bound overlap layers using the original PD joint densities. A local branch estimate cannot replace the common BH largest crossing. It suggests why fractional FDP may be lower order without assuming all-or-none rejection in the growing-K limit.
