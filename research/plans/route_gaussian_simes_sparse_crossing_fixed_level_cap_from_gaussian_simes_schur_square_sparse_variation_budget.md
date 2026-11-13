---
type: plan
title: >-
  Route to gaussian_simes_sparse_crossing_fixed_level_cap from
  Downward-variation budget for sparse Simes crossings along the Schur-square
  path
status: pending
target_asset: gaussian_simes_sparse_crossing_fixed_level_cap
route_lemmas:
  - gaussian_simes_schur_square_sparse_variation_budget
route_title: >-
  from Downward-variation budget for sparse Simes crossings along the
  Schur-square path
origin: agent
route_round: 1
inspired_by: []
tags:
  - route
---

## Goal

Target: [gaussian_simes_sparse_crossing_fixed_level_cap](../assets/gaussian_simes_sparse_crossing_fixed_level_cap.md)

## Route

- gaussian_simes_schur_square_sparse_variation_budget: Same set S_q. The two-point partition gives f(0) <= f(1) + V_-(f) <= f(1) + 1 - eta. At t=1 the matrix Sigma∘Sigma has nonnegative entries and p_i = barPhi(T_i) is a concordant decreasing transform with uniform marginals, so the positive-Gaussian Simes theorem (singular allowed) bounds the full Simes event, which contains S_q, by q. Hence P_Sigma(S_q) <= q + 1 - eta, and the cap holds with q_S = min(q_V, eta/2) and cap constant eta/2.

## Plan

1. [ ] Derive gaussian_simes_sparse_crossing_fixed_level_cap from gaussian_simes_schur_square_sparse_variation_budget.

## Verification

The derivation gives the exact statement of gaussian_simes_sparse_crossing_fixed_level_cap.
