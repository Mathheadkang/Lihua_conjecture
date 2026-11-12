---
type: candidate
title: Zero-dimensional canonical slice at an active threshold
status: failed
target_asset: gaussian_bh_fractional_frame_surface_kernel
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  H9: pass
  NOT: fail
mode: refute
round: 4
slot: 3
direction: drop_hypothesis
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:20:47.811Z'
extension_version: 0.0.4
---

## Object

Take d=n=1, G standard Gaussian on the real line, v_1=w=1, c_1=1, beta=1, u=1, a_1=1, and y=1. The canonical conditional law is the point mass at 1. Unlike the positive-dimensional supporting slice excluded on the board, its threshold boundary has conditional probability one. This tests the zero-dimensional exception explicitly left open by that obstruction.

## Checks

### H1

Pass: d=n=1 are positive integers.

### H2

Pass: G has the standard one-dimensional Gaussian law.

### H3

Pass: v_1=w=1 both have Euclidean norm one.

### H4

Pass: c_1=1 is nonnegative.

### H5

Pass: the frame operator is c_1 v_1 v_1^T=1=I_1, so the positive-semidefinite constraint is saturated.

### H6

Pass: beta=sum_i c_i=1.

### H7

Pass: u=1 satisfies u>=1 at equality.

### H8

Pass: the deterministic threshold is a_1=1=u.

### H9

Pass: y=1 is real, and the specified canonical conditional vector is y w+(I_1-w w^T)G_0=1. Thus this is precisely the canonical conditional law stipulated in the target, including at the deterministic threshold boundary.

### NOT

Fail: the conditional event v_1 G>=a_1 holds with probability one, so the surface kernel is phi(1). The proposed right side is

$$
\sqrt e\,h(1)S(1)^\beta=\sqrt e\,\phi(1)>\phi(1).
$$

The exact kernel-to-bound ratio is e^(-1/2). More generally this calculation holds for any u>=1 with a_1=y=u. Indeed the entire one-dimensional admissible family is excluded: feasibility gives beta<=1; if both signs occur among the constraint vectors the event is empty, while otherwise any nonempty canonical event requires |y|>=u. Hence its kernel is at most phi(u), whereas S(u)^beta>=S(u) gives a proposed bound at least sqrt(e) phi(u).

## Failure

NOT fails first: the zero-dimensional canonical boundary event has probability one, but its surface kernel remains a factor e^(-1/2) below the claimed bound.
