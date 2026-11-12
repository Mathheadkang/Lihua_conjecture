---
type: candidate
title: Exact cutoff atom with deterministic alternative
status: failed
target_asset: gaussian_bh_conditional_compound_calibration
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T15:48:26.048Z'
extension_version: 0.0.4
---

## Object

Set $N=2$, $I_0=\{1\}$, $q=1/10$, and $Z=0$ deterministically. Let $P_1=q$ with probability $1/2$ and $P_1=1$ otherwise. Set $P_2=q$ deterministically. Use the coordinate laws themselves as conditional kernels at every $z$.

## Checks

### H1

The dimension is a positive integer, the null set is fixed, and $q\in(0,1)$.

### H2

Both coordinates take values in $[0,1]$. A deterministic second coordinate is independent of the first. The constant conditional kernels are regular conditional distributions, and their product is the conditional joint law.

### H3

For the sole null coordinate, $F_{1,0}(t)=0$ for $0\leq t<q$, $F_{1,0}(t)=1/2$ for $q\leq t<1$, and $F_{1,0}(1)=1$. Thus
$$
M_q(0)=\frac{1/2}{2q}=\frac52,\qquad K_q(0)=\frac52.
$$
The envelope is finite and measurable. The explicitly included endpoint $t=q$ attains it. For a general right-continuous finite sum of CDFs, each $t<q$ can be approached by rationals from above within $(0,q)$, preserving the ratio in the limit; this is why irrational interior atoms do not evade the countable supremum.

### H4

On $P_1=q$, both sorted p-values equal $q$ and rank $2$ qualifies by equality, so the actual rejection count is $2$, the false count is $1$, and FDP is $1/2$. On $P_1=1$, the smaller value is $q>q/2$ and the larger value exceeds $q$, so no rank qualifies and FDP is zero. This uses the original null label and the actual ordinary-BH rejection count.

### NOT

The conditional FDR is $\tfrac12\cdot\tfrac12=1/4$, whereas the asserted bound is
$$
\min\{1,2qK_q(0)\}=\frac12.
$$
The conclusion holds, so NOT fails. Omitting the endpoint from the envelope would instead give $K=1$ and the false bound $1/5<1/4$; that is a different statement, not a counterexample to the target.

## Failure

NOT fails: the correctly endpoint-inclusive envelope yields $1/4\leq1/2$.
