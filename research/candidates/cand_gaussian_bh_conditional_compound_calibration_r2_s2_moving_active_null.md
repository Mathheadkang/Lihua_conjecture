---
type: candidate
title: Arbitrarily large conditional product law with one moving active null
status: failed
target_asset: gaussian_bh_conditional_compound_calibration
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T15:58:20.713Z'
extension_version: 0.0.4
---

## Object

Let $N\ge2$, choose an integer $B\in\{0,\ldots,N-1\}$, and set $m=N-B$ and the fixed original null set $I_0=\{1,\ldots,m\}$. Choose $0<q\le a<1/2$ and set $b=q/(aN)$. Let the real random variable $Z$ be uniform on the integers $\{1,\ldots,m\}$. Independently sample $U\sim\operatorname{Uniform}(0,1)$. Given $Z=j$, define

$$
P_j=bU,\qquad P_i=1\quad(i\in I_0\setminus\{j\}),\qquad
P_i=0\quad(i\notin I_0).
$$

Thus exactly one of the original true-null coordinates is active in any conditional state. Its identity changes with the common conditioning variable. All $m$ original null labels stay null; no relabeling into an alternative is performed. This family permits $N\to\infty$, $m/N\to1$, $B$ fixed or growing, and $q\downarrow0$ while keeping the proposed bound nonsaturated. It is a continuous moving-label kernel, rather than a parameter change of the earlier finite tied-atom candidate.

A concrete member has $N=1000$, $B=10$, $m=990$, $q=1/1000$, $a=1/100$, and $b=1/10000$.

## Checks

### H1

$N$ is positive, $I_0$ is fixed independently of $Z$, and $q\in(0,1)$. Every $P_i\in[0,1]$ because $0<b\le1/N\le1$.

### H2

Given any state $Z=j$, all coordinates except $P_j$ are constants; $P_j$ has its indicated uniform law. The joint conditional law is exactly the product of the coordinate laws. These finite-state measurable kernels are regular conditional coordinate distributions given a real random variable. Marginal dependence of the moving active-null coordinates does not violate this hypothesis.

### H3

For every state $j$ and every $0<t\le q<1$, the summed original-null conditional CDF is

$$
A_j(t)=\sum_{i\in I_0}F_{i,j}(t)=\min\{t/b,1\}.
$$

For $0<t\le\min\{b,q\}$, $A_j(t)/(Nt)=1/(Nb)=a/q$. Above $b$, when such levels occur in the envelope interval, that ratio decreases. Consequently

$$
M_q(j)=K_q(j)=a/q,\qquad
\min\{1,2qK_q(j)\}=2a<1.
$$

There is no null atom at zero, no infinite-envelope state, and no clipping at one. These are exactly the nonsaturated finite-envelope states in which a violation would be informative.

### H4

In state $j$, the $B$ original nonnull zero coordinates are always rejected when $B>0$. Every inactive null equals one and cannot be rejected, since all BH thresholds are at most $q<1$. The only other potentially rejected coordinate is the original null $j$.

Write $t_* = q(B+1)/N$. The largest qualifying BH rank is $B+1$ exactly when $P_j\le t_*$, and otherwise it is $B$ (including rank zero if $B=0$). The actual rejection count equals that rank. Hence

$$
\operatorname{FDP}=\frac{\mathbf 1\{P_j\le t_*\}}{B+1},
\qquad
\mathbb P(P_j\le t_*\mid Z=j)=\min\{t_*/b,1\}=\min\{a(B+1),1\}.
$$

This calculation uses the actual rank, the non-strict threshold, and the original fixed null labels.

### NOT

For every conditional state,

$$
\mathbb E[\operatorname{FDP}\mid Z=j]
=\min\left\{a,\frac1{B+1}\right\}
\le a<2a=\min\{1,2qK_q(j)\}.
$$

The unconditional expectation is the same, since this quantity does not depend on $j$. For the concrete member the active null is rejected with probability $11/100$, the FDP on that event is $1/11$, and conditional and unconditional FDR are $1/100$, whereas the claimed bound is $1/50$.

## Failure

NOT fails for the whole family: the exact conditional FDR is $\min\{a,1/(B+1)\}\le a$, while the nonsaturated proposed bound is $2a$.
