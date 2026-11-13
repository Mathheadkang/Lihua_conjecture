---
type: decision
title: 'Parked: gaussian_simes_one_sided_uniform_linear_bound'
kind: parked
target: gaussian_simes_one_sided_uniform_linear_bound
reason: agent_gave_up
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T07:47:10.210Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

No new plan for the linear Simes bound: the Gibbs (exponential-kernel) form I directed loses a Mills factor of about the square root of log N on sparse crossings, and its soft version is already false for independent coordinates at fixed level.
The usable replacement is a hinge kernel: rejection forces the supremum over thresholds of the normalized excess (1/N) sum (T_i - x)_+ over E(G - x)_+ to be at least a constant times sqrt(log 1/q), a union of half-spaces on top-fraction averages whose means are controlled for every correlation.
Missing: a dimension-free bound, summed over dyadic scales, for the probability that this ratio exceeds a, of order 1/a; it holds for independent, fully correlated and block models but fails without Gaussian structure, and no available tool gives it. Recorded as an idea; the result goes back to set aside.
