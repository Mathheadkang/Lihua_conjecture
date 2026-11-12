---
type: candidate
title: Independent heterogeneous compound law exceeding the unit constant
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
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T15:58:20.713Z'
extension_version: 0.0.4
---

## Object

Take N=2, q=1/10, I_0={1,2}, and Z=0. Let P_1 and P_2 be independent, with

- P_1=1/20 with probability 1/10, P_1=1/10 with probability 1/20, and P_1=1 with probability 17/20.
- P_2=1/10 with probability 1/20 and P_2=1 with probability 19/20.

This tests whether heterogeneous anti-conservatism allowed by an averaged CDF envelope can reproduce a stronger BH pathology. It is a counterexample to a unit-constant variant, not to the stated factor 2.

## Checks

### H1

N=2 is a positive integer.

### H2

The fixed original null set I_0={1,2} labels both coordinates null.

### H3

q=1/10 belongs to (0,1).

### H4

All displayed coordinate values belong to [0,1], and each probability list sums to one.

### H5

The sampling law is the product of the two finite coordinate laws and Z=0 is constant. These are regular conditional laws and mutually independent given Z. The fact that P(P_1<=1/20)=1/10>1/20 is permitted: individual conditional superuniformity is not assumed.

### NOT

For 0<t<1/20 the summed null CDF is zero. For 1/20<=t<1/10 it is 1/10, and at t=1/10 it is 1/5. Consequently M_q=1, attained at both jump locations, and K_q=1.

The actual largest non-strict BH rule rejects whenever P_1=1/20, regardless of P_2. In addition it rejects both coordinates when P_1=P_2=1/10. No other outcome gives a rejection. The first event has probability 1/10; the additional event has probability (1/20)^2=1/400, and they are disjoint. All original labels are null, so FDP=1 exactly on the rejection event. Thus

$$
\mathbb E[\operatorname{FDP}\mid Z]=\operatorname{FDR}=\frac{41}{400}<\frac15=\min\{1,2qK_q\}.
$$

For an independent check by rejection counts, probabilities of R=0,1,2 are respectively 359/400, 19/200, 3/400. The sum for positive R is 41/400. Although 41/400>q=1/10, the required violation of the stated factor-2 conclusion fails.

## Failure

NOT fails: exact conditional FDR 41/400 is below the stated bound 1/5.
