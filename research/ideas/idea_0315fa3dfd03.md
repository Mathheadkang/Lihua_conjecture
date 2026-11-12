---
type: idea
title: Two-sided finite-ray bound under a null-loading norm lower bound
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags: []
---

Unverified candidate from source-bottleneck analysis. In the Gaussian multifactor conditional-independent representation, suppose true-null loading vectors occupy H unoriented lines and every nonzero null norm r_i>=3/5 (exclude zero-null loadings or handle their independent contribution separately). Source Lemma 4.3 (lem:upper-null-ratio, TeX 5531–5656) suggests FDR<=q[H+pi0(1/2+u_q/(2sqrt(2pi)))], u_q=barPhi^{-1}(q/2), q<=2barPhi(1). Group by line; on |v_h^T Z|<=u_q integrate the per-null conditional envelope, whose coefficient gamma_r=sqrt((1-r)/(1+r))<=1/2; exceptional group probability=q. Handle r=1 separately. If H=o(sqrt(log(1/q))), upper leading constant <=1/(2sqrt(pi)) even with arbitrary alternative directions and growing latent dimension. This is only a restricted upper bound; sharpness and novelty are unestablished, and it excludes the small-norm nulls driving the supplied lower construction. Needs separately stated asset and independent adversarial verification.
