---
type: idea
title: >-
  Remove constant Mills posterior fields and charge the tested separated rank
  jump to coherence deficit
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_mixed_coherence_trace_budget
tags:
  - mixed-coherence-budget
  - search-round-1
  - scoped-obstruction
---

## Scoped approach: separate constant posterior fields from genuine posterior variation

In the round-one near-misses for gaussian_bh_mixed_coherence_trace_budget, a reusable first step is to inspect the terminal ratio B/f on the FDP support. If B(z)=f(z)b for one fixed vector b almost everywhere, heat convolution gives a(t,z)=b for every t<1, so K_t=0 and the signed trace M vanishes identically. This removes the constant-ratio families even at maximal coherence x=H^2||b||^2=1. It does not address models in which B/f varies.

For the tested two-null collinear rank-jump family only, N=2, v_1=v_2=1, theta=(0,-c), U=barPhi^{-1}(q), A=barPhi^{-1}(q/2), and c>=A-U+1/A, the field is a=k_1+Delta*pi, with k_1=1/h(A), Delta=1/h(U)-k_1 and pi the tilted conditional probability of the terminal event {W_1>=U+c}. Its positive scalar derivative obeys F E_Q K_t<=Delta phi(U+c), while 1-x>=(1-e^{-1})(1-[h(U)/h(A)]^2). Together these bounds imply M_+<=2q sqrt(1-x) throughout that family. This suggests seeking a decomposition of posterior changes and a corresponding coherence-deficit charge, but supplies no such decomposition for multiple directions, mixed true/false labels, multiple interacting actual-rank jumps, or the omitted collinear range 0<c<A-U+1/A. The entropy-linear term is not tested as essential here.
