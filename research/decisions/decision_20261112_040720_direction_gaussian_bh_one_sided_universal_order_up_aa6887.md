---
type: decision
title: 'New direction: gaussian_bh_one_sided_universal_order_upper'
kind: direction
target: gaussian_bh_one_sided_universal_order_upper
reason: autonomous
failed_plans_at_direction:
  - plan_252211621cea
  - plan_503f8fddcbb5
  - plan_ee2f7b97740a
  - plan_one_sided_order_actual_mean_global_flux_20261106
  - plan_one_sided_order_common_anchor_rotation_20261107
  - plan_one_sided_order_convex_proxy_label_curvature_20261107
  - plan_one_sided_order_fdp_entropy_mills_coherence_20261107
  - plan_one_sided_order_gaussian_interpolation_sdp_20261106
  - plan_one_sided_order_mixed_trace_replica_cells_20261108
  - plan_one_sided_order_negative_contact_transport_20261106
  - plan_one_sided_order_peeling_history_kernel_20261107
  - plan_one_sided_order_three_face_noise_packing_20261106
rounds: 20
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T04:07:20.445Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

Directional entropy to multi-scale chaining with a rare-cluster cap (researcher-selected route; full write-up idea_2251f0ebf933): group null directions at angular scale about 1/U, prove that clusters of mass below q^C contribute O(q) through competition at the single BH cutoff, first for a dimension-free q log(1/q) bound, then generic chaining for q sqrt(log(1/q)).
What the failures show: every earlier plan either kept all cancellation and was left with a remainder equal to the FDR up to O(q) (the chronological-pairing checkpoint), or dropped signs and met a verified counterexample. New plans must bring an external Gaussian inequality (the approved directional-entropy bound, angular stability at scale 1/U, Talagrand chaining, stopped density martingales, Ghirlanda-Guerra ultrametricity, refined FDR linking, compound-Poisson clumping) and state the remainder before executing. The researcher asked for these routes to run in parallel; their selected routes are recorded as researcher ideas.
