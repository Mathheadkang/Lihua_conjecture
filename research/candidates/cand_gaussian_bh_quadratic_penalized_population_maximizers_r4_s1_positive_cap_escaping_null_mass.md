---
type: candidate
title: Positive-cap escaping true-null mass with a strict moment drop
status: failed
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 4
slot: 1
direction: boundary_degenerate
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:54:43.765Z'
extension_version: 0.0.4
---

## Object

Fix $q=1/4$, $\sigma=1/2$, $d=1$, and $C=1$. For integers $n\ge2$, let
$$
a_n=1-n^{-2},\qquad
\pi_n=a_n\delta_{(0,1,1)}+n^{-2}\delta_{(-n,1,1)},\qquad
\pi_*=\delta_{(0,1,1)}.
$$
The proposed obstruction is escape of a vanishing mass of true nulls to arbitrarily negative means while saturating the positive second-moment cap. Unlike the board's zero-cap simplex and empty-null family, this sequence loses its entire second moment in its Wasserstein limit.

## Checks

### H1

Pass. The fixed level and loading satisfy $0<q<1/2$ and $0<\sigma<1$, the ambient dimension is the positive integer one, and the cap $C=1$ is finite and nonnegative.

### H2

Pass. Each displayed law is deterministic and independent of all Gaussian randomness. Both directions are the unit vector $1$. All tags are true-null tags, and their means are nonpositive, so all atoms lie in the closed tagged domain. The weights are positive and sum to one. The first mean moment is $1/n$ for $\pi_n$, and the second mean moment is finite, so these are members of $\mathcal P_2(\mathcal E)$; the same holds for $\pi_*$.

### H3

Pass. Directly,
$$
M_2(\pi_n)=n^{-2}n^2=1,\qquad M_2(\pi_*)=0.
$$
Thus the whole sequence and its proposed limit belong to $\mathcal K_1$.

### NOT

Fail. This escape mechanism does not violate compactness in $W_1$. Couple the common mass at $(0,1,1)$ identically and move the remaining mass $n^{-2}$ from $(-n,1,1)$ to $(0,1,1)$. Its transportation cost is $1/n$. Conversely the function $\theta$ is one-Lipschitz for the stated parameter metric, and its expectations differ by $1/n$, so
$$
W_1(\pi_n,\pi_*)=1/n\longrightarrow0.
$$
The strict moment drop also respects precisely the claimed lower semicontinuity:
$$
M_2(\pi_*)=0\le\liminf_n M_2(\pi_n)=1.
$$
The target does not claim convergence of second moments for every convergent sequence in a cap set; its moment-convergent approximation is an existence assertion for each fixed law.

The full actual largest-crossing FDR can also be checked without a continuity assumption here. Put
$$
G=\frac{\sqrt3}{2}X(1)+\frac12Z\sim N(0,1),\qquad z_t=S^{-1}(t).
$$
The two p-values are $S(G)$ and $S(G-n)$, in that order. The only possible positive attained largest ranks are $a_n$ and $1$. A positive rank occurs exactly when
$$
S(G)\le qa_n\quad\hbox{or}\quad S(G-n)\le q.
$$
All tags are true, so the FDP is one on this event and zero otherwise. Consequently
$$
F(\pi_n)=S\!\left(\min\{z_{qa_n},\ n+z_q\}\right)
=\max\{qa_n,\ S(n+z_q)\}\longrightarrow q=F(\pi_*).
$$
This includes both competing ranks and rank zero, rather than replacing BH by one selected crossing. No discontinuity of the full FDR arises. The object therefore supplies no counterexample to the target.

## Failure

NOT fails: the escaping second-moment mass costs only $1/n$ in $W_1$, gives a lawful strict lower-semicontinuity inequality, and has full BH FDR converging to the limit law's FDR.
