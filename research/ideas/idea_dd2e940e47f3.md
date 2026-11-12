---
type: idea
title: >-
  Simultaneous finite value and moment recovery for one deterministic directing
  law
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_exchangeable_array_variational_compactification
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
tags: []
---

Candidate constructive recovery for a FIXED deterministic finite-second-moment directing law mu, not an arbitrary outer mixture. Draw iid parameters x_i=(theta_i,v_i,ell_i) from mu once, independently of innovations. For a fixed m, the conditional expected m-test full-FDP kernel K_m(x_1,...,x_m) is bounded and continuous in the strong parameter topology: its unit-diagonal Gaussian covariance is continuous, and each marginal has zero probability of every finite BH threshold even when the joint covariance is singular. The analogous cutoff-weighted kernel is also continuous, since actual ranks are locally constant away from those threshold hyperplanes. Empirical parameter laws mu_N converge weakly almost surely, so integrals of K_m against mu_N^m converge to the mu^m integral. A sampled finite original submodel duplicates the original private noise on repeated indices, whereas K_m(mu_N^m) gives independent private noises to repeated parameter atoms; these kernels differ only on an index collision, probability <=m(m-1)/(2N). Uniform fixed-sigma compression now bounds the difference from the entire N-test conditional FDR by e_m (or (1+Lip chi)e_m for cutoff-weighted FDR). Let N tend to infinity at each fixed m, then m tend to infinity: conditional finite-model values converge almost surely to the directing-population value once its identification is proved. Simultaneously, the ordinary strong law gives empirical theta^2 moment convergence. Thus one deterministic sample path recovers values AND moment, unlike an unjustified selection from an arbitrary outer mixture. Each finite false-tagged zero may then be moved to a sufficiently small positive mean, using finite-model continuity and moment control. For a transport endpoint fixed after epsilon is chosen, choose N and these small shifts so all required errors are o(epsilon), e.g. epsilon^2. Supply the elementary empirical-law/strong-law details or declare any external prerequisites; do not transfer derivatives across the recovery limit.
