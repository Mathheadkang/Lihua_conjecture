---
type: candidate
title: Four-coordinate tied-atom conditional law with nontrivial compound bound
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
slot: 2
direction: small_cases
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T15:48:26.048Z'
extension_version: 0.0.4
---

## Object

Take $N=4$, $I_0=\{1,2,3\}$, $q=1/10$, and $Z=0$ almost surely. Independently draw

$$
P_1=\begin{cases}1/20&\text{with probability }3/4,\\1&\text{with probability }1/4,\end{cases}
\quad
P_2=\begin{cases}3/40&\text{with probability }1/8,\\1&\text{with probability }7/8,\end{cases}
\quad
P_3=\begin{cases}3/40&\text{with probability }1/4,\\1&\text{with probability }3/4,\end{cases}
\quad P_4=0.
$$

The original fourth coordinate is nonnull; the first three remain the true-null labels in every outcome. This is a finite product law with atoms and positive-probability ties.

## Checks

### H1

$N$ is a positive integer, $I_0$ is a fixed subset of its original coordinate labels, and $q\in(0,1)$.

### H2

All coordinates lie in $[0,1]$. The stated finite product law is mutually independent, and conditioning on constant real $Z$ preserves it. Its coordinate CDFs form regular conditional distributions. The degenerate fourth coordinate is allowed.

### H3

Write $A(t)=\sum_{i=1}^3F_{i,0}(t)$. For $0<t\le1/10$,

$$
A(t)=\begin{cases}
0,&0<t<1/20,\\
3/4,&1/20\le t<3/40,\\
9/8,&3/40\le t\le1/10.
\end{cases}
$$

The ratio $A(t)/(4t)$ decreases between these atom locations. At $t=1/20$ and $t=3/40$ it equals $15/4$, so $M_q(0)=K_q(0)=15/4$ and

$$
\min\{1,2qK_q(0)\}=3/4.
$$

All functions are deterministic measurable functions of $Z$. There is no null atom at zero.

### H4

Set $X_i=40P_i$ when $P_i<1$, and write $X_i=5$ for $P_i=1$. The BH thresholds on the small atoms are then $k=1,2,3,4$; the symbol $5$ exceeds every threshold. The fourth original coordinate is $X_4=0$. Ordinary BH with the largest qualifying rank and non-strict comparisons gives the following exact enumeration; $V$ counts only the original first three labels.

| $(X_1,X_2,X_3)$ | Probability | Actual $R$ | $V$ | FDP |
|---|---:|---:|---:|---:|
| $(2,3,3)$ | $3/128$ | $4$ | $3$ | $3/4$ |
| $(2,3,5)$ | $9/128$ | $3$ | $2$ | $2/3$ |
| $(2,5,3)$ | $21/128$ | $3$ | $2$ | $2/3$ |
| $(2,5,5)$ | $63/128$ | $2$ | $1$ | $1/2$ |
| $(5,3,3)$ | $1/128$ | $3$ | $2$ | $2/3$ |
| $(5,3,5)$ | $3/128$ | $1$ | $0$ | $0$ |
| $(5,5,3)$ | $7/128$ | $1$ | $0$ | $0$ |
| $(5,5,5)$ | $21/128$ | $1$ | $0$ | $0$ |

In particular the tied outcome $(5,3,3)$ has largest qualifying rank $3$, although rank $2$ does not qualify. In every row the actual rejection count equals the selected rank.

### NOT

The conditional expected FDP equals the unconditional one because $Z$ is constant:

$$
\mathbb E[\operatorname{FDP}\mid Z]
=\frac{9}{512}+\frac{3}{64}+\frac{7}{64}+\frac{63}{256}+\frac{1}{192}
=\frac{653}{1536}
<\frac34=\frac{1152}{1536}.
$$

Thus the required violation fails. The ratio to $qK_q$ is $653/576<2$.

## Failure

NOT fails: exact original-label FDP expectation is $653/1536$, below the nontrivial claimed bound $3/4$.
