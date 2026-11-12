---
type: idea
title: >-
  A small common Gaussian factor may regularize the clone-invariant
  near-maximizer space
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_rare_clone_mills_variation
tags: []
---

Unproved route toward the missing near-maximal comparison, not permission to apply Ekeland yet. For fixed sigma in (0,1), embed every score as theta_i+sqrt(1-sigma²) v_i dot G+sigma Z with one independent common standard Gaussian Z. Every finite original model is approximated as sigma down to zero, without changing mean labels or marginal variances; fixed finite FDR continuity suffices for that approximation. Uniform replication and the rare downward-mean variation preserve the common loading sigma. Conditional on G, all scores increase by the same amount sigma Z, so the largest population BH rank is nondecreasing in Z even with general parameter laws. This may exclude almost-sure tangency instability and help prove continuity of the full mixed FDP under total-variation perturbations of parameter laws; monotonicity of rank alone is NOT continuity of FDP, and tiny ranks/label numerators still require proof. Possible complete metric domain: countably atomic probability laws on (theta,residual direction,label), TV metric; this subspace is TV closed, finite support laws dense within it, and finite rational weights represented by exact copies. Approximate the continuous rare-offset profile by finitely discrete profiles: it is not a TV limit of empirical laws, but each finite profile has small TV distance from the original atom. Main remaining gates: (1) prove actual full-FDP continuity/upper semicontinuity in this complete domain at fixed sigma, including zero ranks and competing roots; (2) prove near-maximal variation inequalities compatible with finite approximations, not just values; (3) current rare-clone theorem is finite positive-definite only, while countably atomic maximizers can be singular and give simultaneous face intersections, so its signed face formula cannot simply be applied there; (4) control the zero-null boundary flux with the required q scale and pass sigma down to zero. Do not interchange supremum and averaging, nor claim an attained finite positive-definite optimizer.
