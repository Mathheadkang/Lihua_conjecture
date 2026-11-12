---
type: idea
title: >-
  Covariance-specific shifted-BH bounds do not yet provide a clone-invariant
  universal bound
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_universal_order_upper
  - gaussian_bh_one_sided_universal_order_upper
tags: []
---

Primary source verified live: Deepra Ghosh and Sanat K. Sarkar, Further Results on Controlling the False Discovery Rate in Two-Sided Gaussian Mean Testing, arXiv:2608.21267v2 (24 August 2026), https://arxiv.org/html/2608.21267v2 . The v1 title differs; use v2 for any future import. Theorem 3.1, equation (6) gives original two-sided Gaussian BH upper bound sum over true nulls of G_tau_i{G_tau_i^{-1}(q)/N}, with G_tau(u)=barPsi_1(tau barPsi_1^{-1}(u)) and tau_i=1/(Sigma^{-1})_ii for a positive-definite correlation matrix. It is a covariance-specific result, not the unrestricted order target. For fixed N and q, as tau down to zero, G_tau{G_tau^{-1}(q)/N} tends to q, by normal tail asymptotics (z_{u/N}/z_u tends to one as u down to zero); summing can therefore cost N_0 q. Exact coordinate cloning is singular and drives these conditional variance parameters to zero, so this theorem alone does not supply the needed dimension-free, clone-invariant estimate. No claim that the source theorem is false; no paper/asset/Bib import made because applicability to our bottleneck remains missing.
