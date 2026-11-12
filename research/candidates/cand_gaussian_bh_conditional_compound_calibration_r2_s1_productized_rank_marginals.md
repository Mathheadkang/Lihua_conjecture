---
type: candidate
title: Independent product adaptation of a rank-mixture pathology
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

Take N=4, q=1/10, I_0={1,2,3,4}, and Z=0. All four coordinates are independent and identically distributed, with probability 1/40 at each of 1/40, 2/40, 3/40, 4/40 and probability 9/10 at 1. This is the independent product law formed from marginals of a rank-mixture construction: the coordinate marginals are preserved but its shared rank event is removed. No external source identity is needed for the specified finite object.

## Checks

### H1

N=4 is a positive integer.

### H2

The fixed original null set I_0={1,2,3,4} labels every coordinate null.

### H3

q=1/10 belongs to (0,1).

### H4

All coordinates take values in [0,1], and their five probabilities sum to 4/40+9/10=1.

### H5

By construction the law is a product of four finite coordinate laws, with real Z=0 constant. Hence the finite CDFs are regular conditional CDFs and the required mutual conditional independence holds.

### NOT

At t=j/40, for j=1,2,3,4, each null CDF is j/40=t, so the summed null CDF divided by Nt equals 1. Between jumps it decreases as t increases, and below the first jump it is zero. Hence M_q=K_q=1.

Exact enumeration of all 5^4=625 support outcomes, multiplying their independent probabilities and taking the largest rank satisfying p_(k)<=qk/4, gives the following probabilities for the actual rejection count, all with common denominator 160000:

| R | numerator |
|---|---:|
| 0 | 144000 |
| 1 | 13689 |
| 2 | 2052 |
| 3 | 243 |
| 4 | 16 |

The rejection set uses every original coordinate at or below q times the qualifying rank divided by 4, including ties. Every original coordinate is null, so FDP is the indicator of R>0. It follows exactly that

$$
\mathbb E[\operatorname{FDP}\mid Z]=\operatorname{FDR}=\frac{16000}{160000}=\frac1{10}<\frac15=\min\{1,2qK_q\}.
$$

Thus preserving the marginals while enforcing independence does not preserve a dependent rejection-event pathology. The NOT check fails.

## Failure

NOT fails: exact conditional FDR 1/10 is below the stated bound 1/5.
