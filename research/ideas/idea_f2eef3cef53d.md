---
type: idea
title: >-
  Focused online resource pass for signed selection boundaries and Gaussian
  mixture transport
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - primary-source-search
  - boundary-stein
  - gaussian-mixtures
  - scope-audit
---

Focused online pass, 8 November 2026; not an exhaustive literature review. Google Scholar query 'Gaussian Benjamini Hochberg worst case FDR arbitrary dependence' was inaccessible through the available tool; discovery continued through arXiv, author pages and publisher records. Queries also covered Gaussian least-favourable configurations, polyhedral selection/Stein formulas, FDR thresholding penalties, and Gaussian mixture transport. A citation-graph expansion from DOI 10.1214/19-AIHP1038 and DOI 10.5802/crmath.486 resolved both seeds, returned 124 neighboring candidates, and inspected a top-12 shortlist; neighbors are leads, not verified applicable results.

New directly relevant checked source: Mikkelsen-Hansen, arXiv:1601.03524v3 and DOI 10.1214/17-AIHP822. Assumption 2.2, Theorem 2.4 and Appendix A.2 give the complete signed Stein jump-boundary framework; p.8 explicitly notes that individual boundary integrands need not have one sign. This helps audit and motivate full-face pairing, but supplies no dimension-free BH trace estimate. It is the primary pointer for the separate signed-null-fibre idea recorded in this pass.

Another verified candidate is Ronen Eldan and Michel Ledoux, A dimension-free reverse logarithmic Sobolev inequality for low-complexity functions in Gaussian space, arXiv:1903.07093v1, https://arxiv.org/pdf/1903.07093v1. Read the hypotheses and Theorem 1 on pp.1-2 and Theorem 3 on p.6. Its gradient Gaussian-width and Laplacian-complexity quantities are additional obligations, not the BH entropy D or the coherence deficit. It also starts from smooth log densities and finite information. No such complexity or smoothing bound has been established for the actual BH tilt; calling this result dimension-free does not eliminate these obligations.

The graph also surfaced Mikulincer-Shenfeld, The Brownian transport map, published 2024, DOI 10.1007/s00440-024-01286-0, arXiv:2111.11521. Official author/publication records were checked, but the attempted PMC full text encountered a challenge and theorem-level applicability was not established in this pass. Keep as an unread-theorem lead, not a usable dependency. ABDJ's FDR-thresholding penalty work and Birge-Massart's Gaussian model-selection work appeared as further leads; no arbitrary-covariance BH implication was checked or asserted.

No bibliography or paper-index entry, source asset, dependency or manuscript citation was added. All potentially loadbearing results still need native import/extraction or full inline reproving with their exact hypotheses.
