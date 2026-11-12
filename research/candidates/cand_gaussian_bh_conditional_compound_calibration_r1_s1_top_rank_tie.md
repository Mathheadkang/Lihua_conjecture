---
type: candidate
title: Deterministic equality at the largest BH rank
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

Take the one-point probability space, Z=0, N=3, the fixed original true-null set I_0={1}, q=1/10, and deterministic coordinates P_1=P_2=P_3=1/10. All conditional laws are their Dirac coordinate laws.

## Checks

### H1

The dimension N=3 is an integer at least one.

### H2

I_0={1} is fixed and is a subset of {1,...,3}. These labels are retained when counting false discoveries.

### H3

The level q=1/10 belongs to (0,1).

### H4

Every coordinate lies in [0,1].

### H5

Z=0 is real-valued. On this one-point space the joint conditional law is exactly the product of the Dirac coordinate laws; thus the coordinates are mutually conditionally independent and have regular conditional CDFs. No superuniformity is needed.

### NOT

All three order statistics are 1/10. Only rank 3 qualifies because 1/10>q/3 and 1/10>2q/3, while 1/10=q. Thus the largest qualifying rank and actual rejection count are R=3, and the rejection set is {1,2,3}. The original null set is {1}, so V=1 and FDP=1/3. The null CDF is zero for t<1/10 and one at t=1/10. Hence M_q=1/(3q)=10/3 and K_q=10/3. The claimed upper bound is min{1,2qK_q}=2/3. The required strict violation 1/3>2/3 is false. Because Z is constant, the conditional expected FDP and unconditional FDR equal the displayed deterministic FDP. All comparisons use the actual largest non-strict BH rule and original null labels. The last check fails.

## Failure

NOT fails: FDP=1/3 is below the bound 2/3.
