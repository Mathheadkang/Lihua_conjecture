---
type: idea
title: >-
  Independent check confirms signed-face identities and the two-coordinate
  obstructions
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - independent-check
  - failed-plan
  - signed-gaussian-faces
---

Fresh read-only agent /root/two_face_obstruction_review independently checked failed plan plan_two_sided_signed_face_budget_20261104, SHA256 9782de6790aa8e3be53c681fc447ef28d73f37aa3ed6f582906e044750bbbf3b, on 2026-11-04. No blocking defect found in the exact auxiliary calculations; plan remains failed and target remains open. This is not native asset approval.

Verified reciprocal-rank tail telescoping and Stieltjes integration by parts: d_m'=1/[m(m+1)] before am and -1/(m+1) between am and a(m+1), endpoint terms vanish. The unrestricted estimate from 0<=A_im<=1 only yields S_i<=a(H_N-1), not the desired Gaussian-uniform remainder.

For the N=2 one-null two-sided model, independently differentiating A(u)=1/2 sum_{s=+/-1} P(|mu+s rho z(u)+vZ|>=U), v=sqrt(1-rho²), reproduces the plan's four-kernel signed bracket. Local ordering fails at rho=1/2, mu=2U, x=2U, U>=1: phi(0)+phi(4U/v)-2phi(2U/v)>0 and D_q(2U)>0. For FIXED 0<rho<1 and mu=(1+rho)U, the independently checked dominated-convergence calculation gives U*S/q ->rho log(2)/(4v sqrt(2pi))>0. This refutes integrated nonpositivity only. It is not uniform in rho, is subleading O(q/U), and cannot be used as a full sharp-constant counterexample.

The missing obligation is global correlation/Gram-based cancellation controlling the sum over all faces with a uniform o(qU) remainder. No claim that all signed-face methods fail; local/termwise simplifications in this plan are the established obstructions.
