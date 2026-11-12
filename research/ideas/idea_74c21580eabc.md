---
type: idea
title: >-
  Prune infeasible frames and exposure tails before bounding conditional surface
  mass
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_fractional_frame_surface_kernel
tags:
  - surface-kernel
  - support-pruning
  - positive-circuits
---

Round-2 search suggests a preliminary support reduction, not a proof of the surface-kernel lemma. First discard any constraint family with nonzero lambda>=0 and sum_i lambda_i v_i=0: summing v_i dot g>=a_i>=u>=1 makes its conjunction empty. More generally, if lambda_i>=0 and sum_i lambda_i v_i=t w with t>0, then any nonempty conditional event must have y>=b=(sum_i lambda_i a_i)/t. If b>=0, the entire exposure range is bounded by K(y)<=phi(b): below b the event is empty, and above b phi(y)<=phi(b). Hence checking phi(b)<=sqrt(e)h(u)S(u)^beta would settle that particular frame and thresholds without estimating its conditional probability. The cap with alignment squared 9/10 and beta=10/9 at u=1 admits such a certificate; its zero-sum simplex residuals give b>=sqrt(10/9). At supporting exposure levels, an event contained in a proper affine subspace of the positive-dimensional exposure hyperplane has zero canonical conditional probability. Zero-dimensional slices must be handled separately. Remaining step: prove a sufficiently strong certificate or a complementary conditional-mass estimate for arbitrary feasible fractional frames, including cases with no useful nonnegative conic representation of w. No such global step has been established, and the round contains no surviving counterexample.
