---
type: candidate
title: Zero-mean chosen singleton is excluded before the clone conclusions
status: failed
target_asset: gaussian_bh_growing_clone_compensated_variation
checks:
  H1: pass
  H2: pass
  H3: fail
  H4: unknown
  H5: unknown
  H6: unknown
  H7: unknown
  NOT: unknown
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T22:49:51.760Z'
extension_version: 0.0.4
---

## Object

Attempt the fixed singleton data N=d=1, theta_1=0, Sigma=[1], i=1 and q=0.49, with the positive compensation in the target. This is the exact zero-mean endpoint suggested by bringing a chosen negative null toward zero.

## Checks

### H1

Pass. N=1 is finite, theta_1=0 is real and fixed, and [1] is positive definite with unit diagonal.

### H2

Pass. The fixed q=0.49 belongs to (0,1/2).

### H3

Fail. The target explicitly requires theta_i nonzero, whereas theta_1=0. The positive compensation is d_epsilon=s(t_s+1/t_s)>0 for each admissible positive epsilon, explaining why this endpoint cannot be silently substituted into the fixed-label construction.

### H4

Unknown after the first failure H3.

### H5

Unknown after the first failure H3.

### H6

Unknown after the first failure H3.

### H7

Unknown after the first failure H3.

### NOT

Unknown after the first failure H3. No counterexample to the stated target is claimed.

## Failure

H3 fails: the chosen original mean is zero, an explicitly excluded endpoint.
