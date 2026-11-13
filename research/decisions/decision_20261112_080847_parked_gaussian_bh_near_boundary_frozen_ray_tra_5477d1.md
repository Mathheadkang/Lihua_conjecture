---
type: decision
title: 'Parked: gaussian_bh_near_boundary_frozen_ray_transfer'
kind: parked
target: gaussian_bh_near_boundary_frozen_ray_transfer
reason: agent_gave_up
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T08:08:47.102Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

The transfer reduces to the leave-one-out BH cutoff tracking each null's statistic inside a thin layer just above the cutoff; for a fixed null and fixed residual this tracking loses the full Benjamini-Yekutieli factor, so any gain must come from averaging over the residual or summing over nulls. Cameron-Martin smoothing fails for clone or antithetic alternatives, and a budget on how many nulls an alternative can steer becomes counting cutoff crossings along moving lines, the obstruction already met on the main result. Getting past it needs a collective anti-concentration of the leave-one-out cutoffs across nulls (for example an exchangeability or second-moment bound on simultaneous tracking), not a per-null estimate.
