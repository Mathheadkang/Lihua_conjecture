---
type: idea
title: >-
  BH selection weights have a tangential jump and cannot be an exact convex
  gradient
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - universal-order
  - variational-route
  - two-test-obstruction
  - draft-proof
---

This draft observation concerns a proposed auxiliary variational representation, not the main FDR upper bound. The fresh second PLAN worker found its first representation gate fails for two tests; the root gives the explicit local reconstruction below. No plan was manufactured around the failed gate.

Fix 0<q<1/2, N=2, independent T_1,T_2~N(0,1), all means zero and Sigma=I_2. Put u_1=barPhi^{-1}(q/2)>u_2=barPhi^{-1}(q). Ordinary BH has R=max({0} union {k:p_(k)<=qk/2}), with the non-strict largest-rank rule. Let w_i(T)=1{i is rejected}/(R vee 1).

Normalized weights. Choose u_1<a<b and epsilon>0 sufficiently small that u_2+epsilon<a. On the open rectangle (a,b) times (u_2-epsilon,u_2+epsilon), the BH vector is w=(1,0) below the horizontal face T_2=u_2, and w=(1/2,1/2) above it. Indeed T_1>u_1 always qualifies rank one, while rank two qualifies precisely when T_2>=u_2. If a locally Lipschitz scalar potential F had gradient w almost everywhere on this rectangle, its restrictions to the connected lower and upper halves would be respectively F(x,y)=x+C_- and F(x,y)=(x+y)/2+C_+. (A locally Lipschitz function with almost-everywhere zero gradient on a connected open set is constant; this also follows by distributional derivatives or integration on lines.) Continuity along the horizontal face would require x+C_-=x/2+u_2/2+C_+ for all a<x<b, which is impossible. Thus there is no such locally Lipschitz potential, in particular no finite convex potential on an open neighborhood with this exact gradient.

Unnormalized weights. Choose u_2<a<b<u_1 and epsilon>0 sufficiently small that u_2+epsilon<a. On the corresponding rectangle, neither score reaches u_1; rank two qualifies precisely above the same horizontal face. The rejection-indicator vector is (0,0) below and (1,1) above, including a 0-to-2 cascade with no qualifying rank one. A locally Lipschitz potential would therefore be constant below and x+y+C above, again incompatible with continuity along the face. Thus the unnormalized exact-gradient version fails as well.

Every open subrectangle has positive probability under the finite independent Gaussian model. Equality cases at the face do not affect the almost-everywhere contradiction. The failure is the nonzero tangential component of the selection-vector jump across a rank-transition face. This rules out only an exact scalar convex-gradient representation of these specified BH vectors; it does not rule out nonconvex generalized objectives, a different vector field, approximate representations with quantitatively controlled errors, or a universal-order FDR bound. No such replacement or bound is established here. This idea remains draft and is not native proof approval or a counterexample to the main asset.

## Independent scoped review

A reviewer who did not derive this representation test independently checked this observation on source SHA256 `f117456f7cfc6091b42721453a7a556026fc1405064b3821e8308b496890d413`. The reviewer confirmed both two-test BH regions for every stated q, the zero-to-two cascade without a qualifying rank one, local affine reconstruction, the continuity contradiction, positive Gaussian density, and the irrelevance of face values to the almost-everywhere obstruction. No blocking defect was found within this scope. The exact-gradient obstruction does not refute the main FDR bound and this review is not native approval; the observation remains draft.
