---
type: decision
title: 'Parked: gaussian_frozen_ray_order_bound'
kind: parked
target: gaussian_frozen_ray_order_bound
reason: agent_gave_up
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T05:38:48.931Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

Two plans and a third search for a plan all stop at one missing estimate: where the maximizing scale sits must obey a log-scale occupation bound (equivalently, an overlap-variance term without sign must be small). Proved partial reductions: the truncated mean is at most a constant times (1 + sqrt(log c)) plus a misalignment term, and also e^2 + 2 sqrt(log c) plus two explicit remainders; small maximizing scales are settled. Getting past it needs a genuinely two-scale tool, comparing curvature at one scale under the tilt of a later one, for example a maximal Ornstein-Uhlenbeck regularization estimate. The other routes do not depend on this lemma.
