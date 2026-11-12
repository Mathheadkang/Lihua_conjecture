---
type: idea
title: >-
  Conditional-density envelope and finite BH leave-one-out reduction for
  opposite singular alternatives
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_one_sided_private_noise_floor_order
tags:
  - gaussian-bh
  - fixed-private-noise-floor
  - search-round-3
---

## Proposed step

The round-3 failure line reports that, for the tested family with opposite singular alternatives and growing dimension, a conditional density envelope together with the exact finite largest-rank BH leave-one-out identity bounds FDR divided by q sqrt(log(1/q)) uniformly. Retain this as a family-specific proof route: derive the envelope under that family's actual conditioning, then apply the finite leave-one-out identity while preserving the original BH rule, multiplicities, and non-strict inequalities.

## Scope and verification needed

This draft records only the supplied search-summary context pack, not an independent reconstruction of the candidate's argument. The pack supplies neither an explicit envelope nor its constant. The reported bound is at the target order; no linear-in-q bound is asserted. Arbitrary null loading geometry, varying private-noise levels, and unrestricted alternative dependence remain uncovered. A future generalization must identify which assumptions make the envelope uniform before applying this step to the full structured class.

## Earlier approaches

Keep the [endpoint and bounded-dimension reductions](idea_d7fe1abf6391.md) and [three family-specific growing-dimension reductions](idea_3faef74c8989.md) as separate earlier approaches. Their linear bounds are not duplicated here and are not inferred for this opposite-singular family. Near-zero alternative-mean selector heuristics supply no quantified exclusion or counterexample.
