---
type: candidate
title: Zero-dimensional canonical boundary atom
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
slot: 2
direction: small_cases
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T20:20:47.811Z'
extension_version: 0.0.4
---

## Object

Take d=n=1, G standard normal, v_1=w=1, c_1=1, beta=1, u=a_1=y=1. This tests the zero-dimensional canonical slice at its deterministic boundary, which the supporting-slice null-measure obstruction explicitly leaves outside its scope.

## Checks

### H1

The dimensions d=n=1 are positive integers.

### H2

G has the standard Gaussian law in R.

### H3

Both v_1=1 and w=1 are unit vectors in R.

### H4

The sole weight c_1=1 is nonnegative.

### H5

The frame operator is c_1 v_1 v_1^T=1=I_1, so the positive-semidefinite inequality holds.

### H6

The defined weight sum is beta=c_1=1.

### H7

The baseline u=1 satisfies u>=1.

### H8

The threshold a_1=1 is deterministic and satisfies a_1>=u.

### H9

The exposure level y=1 is real. The canonical conditional law is the law of yw+(I_1-ww^T)G_0=1; thus the non-strict constraint v_1 dot G>=a_1 holds with probability one, even though this conditional support has dimension zero.

### NOT

The surface kernel equals phi(1). The proposed upper bound equals

$$
\sqrt e\,h(1)S(1)^\beta=\sqrt e\,\phi(1)=\phi(0).
$$

Thus the ratio of the surface kernel to the claimed bound is exactly e^(-1/2)<1. The conclusion holds strictly, so NOT fails. No null-measure argument is used for this deterministic boundary atom.

## Failure

NOT is the first failing check: the zero-dimensional boundary atom has conditional probability one but kernel-to-bound ratio exactly e^(-1/2).
