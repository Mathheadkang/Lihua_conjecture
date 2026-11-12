---
type: idea
title: Gaussian-channel covariance localization as an entropy compression diagnostic
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_mixed_coherence_trace_budget
tags: []
---

Primary source verified during restart: Ahmed El Alaoui and Andrea Montanari, An Information-Theoretic View of Stochastic Localization, arXiv:2109.00709v2 (https://arxiv.org/html/2109.00709v2), Theorem 1 equations (1.4)-(1.6), proof sections 2.1-2.3; publication DOI 10.1109/TIT.2022.3180298. For a signal law mu and positive definite channel-noise covariance S, independent noisy Gaussian observation Y=sqrt(tau)X+S^{1/2}Z, tau uniform [1,2], controls average conditional covariance by S and mutual information by one half log det(I+2 S^{-1} Cov(mu)); integrated conditional covariance square also bounded by original covariance. Potential use: replace the raw log(number of true-null directions) in the finite randomized direction-mark certificate by an actual covariance-adaptive information cost. This is NOT a proof of the mixed budget: Gaussian channel information is about the coarsened observation, while the exact BH mark vector must still be recovered, and the residual trace/payment has not been bounded. Taking isotropic noise gives trace/noise tradeoffs, and logdet can retain dimension; do not claim dimension-free closure. Source currently external, not an approved black-box dependency or full adaptation in a plan.
