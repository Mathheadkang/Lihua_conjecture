---
type: plan
title: >-
  Route to gaussian_bh_heavy_cluster_strip_chaining_bound from Gaussian-width
  bound for few angular null clusters in one-sided Gaussian BH
status: pending
target_asset: gaussian_bh_heavy_cluster_strip_chaining_bound
route_lemmas:
  - gaussian_bh_heavy_cluster_gaussian_width_bound
route_title: >-
  from Gaussian-width bound for few angular null clusters in one-sided Gaussian
  BH
origin: agent
route_round: 1
inspired_by: []
tags:
  - route
---

## Goal

Target: [gaussian_bh_heavy_cluster_strip_chaining_bound](../assets/gaussian_bh_heavy_cluster_strip_chaining_bound.md)

## Route

- gaussian_bh_heavy_cluster_gaussian_width_bound: Given a heavy separated family at scale kappa, exponent C (unit loadings, r_i=1): H<=q^{-C}; ||w_i-v_h||<=kappa/u gives w_i^T v_h>=1-kappa^2/(2u^2)>=cos(2kappa/u) for u>=1, so the width lemma applies with kappa'=2kappa, J=H, I_* the union. Its bound on the full contribution of I_* dominates the strip sum, and E max v_h^T Z<=sqrt(2C log(1/q))<=2 sqrt(C) u for small q, giving A q(1+u). Separation and the mass floor are not needed.

## Plan

1. [ ] Derive gaussian_bh_heavy_cluster_strip_chaining_bound from gaussian_bh_heavy_cluster_gaussian_width_bound.

## Verification

The derivation gives the exact statement of gaussian_bh_heavy_cluster_strip_chaining_bound.
