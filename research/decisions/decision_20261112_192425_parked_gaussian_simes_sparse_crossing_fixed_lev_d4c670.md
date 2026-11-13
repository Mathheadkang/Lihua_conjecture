---
type: decision
title: 'Parked: gaussian_simes_sparse_crossing_fixed_level_cap'
kind: parked
target: gaussian_simes_sparse_crossing_fixed_level_cap
reason: agent_gave_up
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:24:25.424Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

Set aside: no executable plan. Any average of per-coordinate log-convex kernels (the tool that settled dense crossings) provably cannot reach sparse thresholds, since its level set must be smaller by a factor of about log N; raising the level does not make sparse ranks dense; and the bounded-spectrum second-moment estimate fails on near-clone clumps. Searches found no counterexample (any counterexample needs rank at least about 2 log(1/q) and mixed signs). What would get past it: a collective maximal inequality for the normalized excess, for example a positive lower bound on the Gaussian measure of the hinge acceptance polyhedron uniformly in the correlation, or an active-set surface bound for hinge upcrossings. The other two routes to the Simes bound do not need this lemma.
