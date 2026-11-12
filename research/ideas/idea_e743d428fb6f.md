---
type: idea
title: Replace the ambient radial cutoff in higher-rank frozen-ray mixtures
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
tags:
  - frozen-ray
  - proof-obstruction
  - search-round-5
---

## Proposed proof step
Replace the ambient Gaussian radial-tail payment by a bound that retains the active common maximizing scale or active directions, uniform in covariance rank.

## Verified obstruction to a direct radial extension
Represent the finite Gaussian model as Z_i=<u_i,G>, where G~N_r(0,I_r), ||u_i||=1 and r is the covariance rank. The rank-two radial proof splits at a=sqrt(2 log c). In rank r the corresponding upper-bound payment is c P(||G||>a)=Gamma(r/2,log c)/Gamma(r/2). Already for r=4 this equals 1+log c, exceeding the desired sqrt(log c) order. Thus that direct radial split does not deliver either the order or sharp truncated-moment assertion uniformly in rank. This is an obstruction to this proof estimate only: the payment is an upper-bound term and gives no lower bound or counterexample for the actual frozen-ray maximum.

## Remaining obligation
Construct and justify a replacement cutoff or crossing estimate that uses the same w for all summands and pays at most the required truncated-moment scale. No such estimate is proved here. This does not exclude high-rank diffuse, near-complete-correlation, product-sign, or simplex families and establishes no maximal-tail assertion or BH reduction.
