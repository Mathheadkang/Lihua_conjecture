---
type: idea
title: >-
  Provenance correction and completed standard-library diagnostic for the
  equicorrelation endpoint idea
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_common_loading_uniform_submodel_compression
  - gaussian_bh_exchangeable_array_variational_compactification
tags: []
---

Correction to the recording sequence of idea_ed169268dd35: its numerical-diagnostic sentence was written before successful execution. The first attempted SciPy call failed immediately because SciPy is not installed and produced NO numerical evidence. A subsequent Python-standard-library diagnostic has now actually run. It used math.erfc for moderate normal tails, an alternating Mills expansion for large positive arguments, Newton inversion of log survival, and golden-section minimization over scaled contact z in [0.2,8]. No files, packages or heavy workloads were created.

At q=.05, candidate S(sqrt(2log20))=0.0071876312. For rho=.1,.01,.001,.0001,.00001, the computed fixed-rho population-limit FDRs were approximately .00762277,.00722863,.00719171,.00718804,.00718767. The associated barriers were approximately2.4264933,2.4456964,2.4475425,2.4477264,2.4477448. These support the proposed endpoint asymptotic but are NOT certified interval bounds, a proof of the global infimum limit, or a counterexample to the active fixed-positive-loading theorem. The global escape regimes and order-of-limits argument remain to be proved. The original idea and the failed first-call history are preserved here explicitly.
