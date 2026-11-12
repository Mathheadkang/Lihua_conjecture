---
type: idea
title: Independent numerical check of the supplied Gaussian BH lower-bound tables
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
  - gaussian_bh_one_sided_sharp_upper
tags: []
---

Short local diagnostic (base R 4.4.1, stats::optimize/uniroot/integrate, no Monte Carlo) independently reproduced the supplied reference Tables 1–2. For q=(0.01,0.05,0.10,0.20), ell_two(q)/q=(1.35525751193,1.25712230423,1.20941382829,1.15702808525), ell_one(q)/q=(1.83105765162,1.62026232672,1.51549502673,1.39773536774). Both agree with the four-decimal reference to <8e-5. Computation used log M(y)=max_{0<=a<=y}[-a²/2+abs(ay)+log1p(exp(-2 abs(ay)))-log2], solved log M(yq)=-log q, integrated exp(log M(y)+dnorm(y,log=TRUE)) from 1 to yq. Integration rel.tol=1e-10 and abs.tol=1e-11; optimization/root tol=1e-11. Existing published benchmarks only; this is numerical evidence for implementation/formulas, not a new theorem. The default Python lacks SciPy, so the supplied Python script itself was not rerun. Configured ucd-pkbh remote SSH timed out after approved retry; no heavy computations were run locally.
