---
type: candidate
title: Empty null set with all coordinates zero
status: failed
target_asset: gaussian_bh_conditional_compound_calibration
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T15:48:26.048Z'
extension_version: 0.0.4
---

## Object

Take the one-point probability space, Z=0, N=2, the fixed original true-null set I_0=emptyset, q=1/10, and deterministic coordinates P_1=P_2=0. All conditional laws are their Dirac coordinate laws.

## Checks

### H1

The dimension N=2 is an integer at least one.

### H2

I_0=emptyset is fixed and is a subset of {1,...,2}. These labels are retained when counting false discoveries.

### H3

The level q=1/10 belongs to (0,1).

### H4

Every coordinate lies in [0,1].

### H5

Z=0 is real-valued. On this one-point space the joint conditional law is exactly the product of the Dirac coordinate laws; thus the coordinates are mutually conditionally independent and have regular conditional CDFs. No superuniformity is needed.

### NOT

Both ranks qualify, so the largest qualifying rank is 2 and the actual rejection set is {1,2}. Thus R=2, V=0, and FDP=0 with the original empty null set. The summed null CDF is identically zero, so M_q=0 and K_q=1. The claimed bound is 2q=1/5. The required violation 0>1/5 is false. Because Z is constant, the conditional expected FDP and unconditional FDR equal the displayed deterministic FDP. All comparisons use the actual largest non-strict BH rule and original null labels. The last check fails.

## Failure

NOT fails: an empty null set gives FDP=0.
