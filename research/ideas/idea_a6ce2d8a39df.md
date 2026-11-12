---
type: idea
title: Separate the exact bulk response for kernel-preserving tag transfers
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_private_cutoff_particle_mass_variation
tags:
  - particle_mass
  - signed_bulk
  - kernel_preserving
---

Round 1's two failed coincident zero-mean tag-swap candidates suggest isolating the kernel-preserving part of the mass variation as an exact identity. At fixed level (lambda=0), whenever the lawful laws pi and nu have identical conditional total score kernels H_nu,X=H_pi,X, the mixture keeps Q_X, every competing suffix minimum M_X, and the actual globally largest rank R unchanged. The true-tail kernel remains affine, so for interior ranks dot f_X(r)=rho[V_nu,X(Q_X(r))-V_pi,X(Q_X(r))]/r, and the full cutoff payoff has the exact affine bulk response rho E[chi_a(R)(f_nu,X(R)-f_pi,X(R))]. In particular, transferring mass from a true-tagged zero mean to an otherwise identical false-tagged zero mean gives -rho E[chi_a(R)], agreeing with the asserted derivative and preventing this family from yielding a counterexample by rank cancellation. This is a proposed first step for the kernel-preserving subcase, supported by the round's reported failures; it is not a proof of the general theorem. Different kernels, moving or competing minima, and the required L1 and expectation interchanges remain unresolved.
