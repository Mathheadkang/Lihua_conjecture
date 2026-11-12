---
type: candidate
title: Rank-one frame saturation at the conditioning boundary
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
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
performed_by: unknown
created_at: '2026-11-10T19:55:21.135Z'
extension_version: 0.0.4
---

## Object

Take d=n=1, G and G_0 standard scalar Gaussian, v_1=w=1, c_1=1, beta=1, u=a_1=1, and y=1. Use the stipulated canonical conditional law.

## Checks

### H1

d=n=1 are positive integers.

### H2

G is standard Gaussian in R.

### H3

v_1=w=1 have norm one.

### H4

c_1=1 is nonnegative.

### H5

The frame matrix is c_1 v_1 v_1^T=1=I_1, so the positive-semidefinite bound holds with equality and beta=1.

### H6

u=1 satisfies u>=1 with equality.

### H7

a_1=1 is deterministic and satisfies a_1>=u with equality; equivalently theta_1=0.

### H8

The stipulated conditional random vector is y*w+(I_1-w*w^T)G_0=1. Hence the canonical conditional law is the point mass at 1, including at this zero-probability conditioning event.

### H9

y=1 is real.

### NOT

The event v_1*G>=a_1 has canonical conditional probability one. Thus the left-hand side is phi(1). Since h(1)S(1)=phi(1) and beta=1, the right-hand side is sqrt(e)*phi(1)>phi(1). The conclusion holds strictly, so NOT fails.

## Failure

NOT fails: the boundary surface kernel equals phi(1), below sqrt(e)*phi(1).
