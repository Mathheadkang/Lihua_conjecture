---
type: candidate
title: >-
  Six interacting nulls with off-threshold supports and a random nonnull in two
  conditional states
status: failed
target_asset: gaussian_bh_conditional_compound_calibration
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 3
slot: 2
direction: small_cases
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T16:05:02.429Z'
extension_version: 0.0.4
---

## Object

Take $N=7$, $q=1/100$, the fixed original null set $I_0=\{1,2,3,4,5,6\}$, and $\mathbb P(Z=0)=\mathbb P(Z=1)=1/2$. Conditional on either value of $Z$, sample all seven coordinates independently.

A normalized position $x$ in the table means the p-value $p=x/700$. Coordinate $i\le6$ has two such positions $(x_i,y_i)$, with respective probabilities $(a_{i,z},b_{i,z})$, and equals one with the remaining probability $1-a_{i,z}-b_{i,z}$.

| Original null label $i$ | $x_i$ | $y_i$ | $(a_{i,0},b_{i,0})$ | $(a_{i,1},b_{i,1})$ |
|---|---:|---:|---:|---:|
| 1 | $7/4$ | $19/4$ | $(1/2,1/8)$ | $(1/4,1/8)$ |
| 2 | $11/4$ | $23/4$ | $(1/8,1/8)$ | $(1/8,1/4)$ |
| 3 | $23/8$ | $27/4$ | $(1/8,1/8)$ | $(1/8,1/4)$ |
| 4 | $15/4$ | $55/8$ | $(1/8,1/8)$ | $(1/8,1/4)$ |
| 5 | $39/8$ | $47/8$ | $(1/8,1/8)$ | $(1/8,1/4)$ |
| 6 | $11/2$ | $13/2$ | $(1/8,1/8)$ | $(1/8,1/4)$ |

In both conditional states, the original nonnull coordinate $P_7$ is zero with probability $1/2$, is $(13/4)/700$ with probability $1/4$, and equals one with probability $1/4$.

All twelve positive null support values are distinct and lie strictly between BH thresholds; ties at rejected positive values play no role. There are six interacting active null coordinates and a random nonnull, rather than the earlier one-active-null family or the earlier four-coordinate tied-atom object. The conditional states change masses at fixed supports while preserving every original null label.

## Checks

### H1

$N$ is a positive integer, $q\in(0,1)$, and the original null set is fixed. All listed probabilities are nonnegative and sum to one for each coordinate; all p-values belong to $[0,1]$.

### H2

The coordinate kernels are explicitly sampled as a product conditional on $Z$. They are regular conditional distributions on the two-state real-valued conditioning space. No individual superuniformity is imposed.

### H3

Let $A_z(x)=\sum_{i\in I_0}\mathbb P(P_i\le x/700\mid Z=z)$. The envelope satisfies

$$
qM_q(z)=\max_x\frac{A_z(x)}x,
$$

where $x$ ranges over the twelve positive null atoms. Between atoms the numerator is constant and the ratio decreases; after the last atom through $x=7$ it also decreases. There is no null atom at zero. The exact cumulative masses are:

| $x$ | $A_0(x)$ | $A_1(x)$ |
|---|---:|---:|
| $7/4$ | $1/2$ | $1/4$ |
| $11/4$ | $5/8$ | $3/8$ |
| $23/8$ | $3/4$ | $1/2$ |
| $15/4$ | $7/8$ | $5/8$ |
| $19/4$ | $1$ | $3/4$ |
| $39/8$ | $9/8$ | $7/8$ |
| $11/2$ | $5/4$ | $1$ |
| $23/4$ | $11/8$ | $5/4$ |
| $47/8$ | $3/2$ | $3/2$ |
| $13/2$ | $13/8$ | $7/4$ |
| $27/4$ | $7/4$ | $2$ |
| $55/8$ | $15/8$ | $9/4$ |

Thus $qM_q(0)=2/7$, attained at $x=7/4$, while $qM_q(1)=18/55$, attained at $x=55/8$. In both states $M_q>1$ and $2qK_q<1$, so the proposed conditional bounds are the nonsaturated values $4/7$ and $36/55$.

### H4

For exact BH evaluation, use the normalized support coordinates above and represent p-value one by the sentinel $x=1000$, which exceeds every normalized BH threshold $1,\ldots,7$. For each support vector, sort its seven positions, set $k=\max(\{0\}\cup\{r:x_{(r)}\le r\})$, reject positions at most $k$, and count $V$ only among the original first six labels. The actual rejection count equals this largest qualifying rank.

There are exactly $3^7=2187$ support vectors in each conditional state. Exact rational multiplication and collection by $(R,V)$ gives the following certificate. Each integer entry is the probability numerator over the common denominator $2^{20}=1048576$; the entries sum to that denominator in each state.

| $(R,V)$ | State 0 numerator | State 1 numerator |
|---|---:|---:|
| $(0,0)$ | 515923 | 519022 |
| $(1,0)$ | 257676 | 386160 |
| $(2,1)$ | 200544 | 99800 |
| $(3,2)$ | 53472 | 29900 |
| $(3,3)$ | 1792 | 896 |
| $(4,3)$ | 14175 | 7290 |
| $(4,4)$ | 220 | 108 |
| $(5,4)$ | 2763 | 1545 |
| $(5,5)$ | 35 | 21 |
| $(6,5)$ | 1476 | 1620 |
| $(6,6)$ | 20 | 27 |
| $(7,6)$ | 480 | 2187 |

This certificate retains the original labels and the actual largest qualifying BH rank, with non-strict comparisons.

### NOT

Multiplying the preceding probabilities by $V/(R\vee1)$ gives

$$
\mathbb E[\operatorname{FDP}\mid Z=0]
=\frac{21345811}{146800640}<\frac47,
\qquad
\mathbb E[\operatorname{FDP}\mid Z=1]
=\frac{3394163}{44040192}<\frac{36}{55}.
$$

The unconditional FDR is $97979063/880803840$, below the claimed averaged bound $236/385$. Hence neither conditional state nor their mixture violates the conclusion.

## Failure

NOT fails: the exact two-state product-law certificate gives conditional FDRs strictly below both finite nonsaturated envelope bounds.
