---
type: candidate
title: Growing common-factor null block with vanishing-mean tied alternatives
status: failed
target_asset: gaussian_bh_one_sided_private_noise_floor_order
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:19:23.549Z'
extension_version: 0.0.4
---

## Object

For every $q\in(0,1)$ fix $s_0=1/2$, set $M=\lceil1/q\rceil$, $N=2M$, $d=1$, and $c=\sqrt{3}/2$. Let $G,\varepsilon_1,\ldots,\varepsilon_N$ be independent standard normals. With the original labels retained, set
$$
T_i=cG+\tfrac12\varepsilon_i,\quad \theta_i=0,\ a_i=c,\ s_i=\tfrac12\quad(1\leq i\leq M),
$$
$$
T_i=q+G,\quad \theta_i=q,\ a_i=1,\ s_i=0\quad(M<i\leq2M).
$$
Use $p_i=\overline\Phi(T_i)$ and exactly the ordinary largest-qualifying-rank BH procedure at level $q$.

Unlike the recorded full-private-noise endpoint, every true null has a nonzero common loading and actual private noise $1/2$. Dimension grows without bound, the alternative covariance block is singular and tied, and alternative means approach the classification boundary from above. These changes leave a separate obstruction: nonnegative Gaussian conditional shifts.

## Checks

### H1

Pass. The floor $s_0=1/2$ is fixed independently of $q$ and belongs to $(0,1]$.

### H2

Pass. For every positive $q$, $N=2\lceil1/q\rceil$ and $d=1$ are positive finite integers, and all parameters are finite deterministic real arrays of their prescribed sizes. Moreover $N\to\infty$ as $q\downarrow0$.

### H3

Pass. Original means give exactly $I_0^{(1)}(\theta)=\{1,\ldots,M\}$. In particular, the last $M$ coordinates remain alternatives for every $q>0$ even though their means tend to zero. No relabeling is used.

### H4

Pass. Every $s_i$ is nonnegative. Null coordinates satisfy $c^2+(1/2)^2=3/4+1/4=1$; alternatives satisfy $1^2+0^2=1$. Thus every marginal variance is one, including all tied alternatives.

### H5

Pass. Every original true null has $s_i=s_0=1/2$. Zero private noise occurs only on alternatives, as the statement permits.

### H6

Pass. The specified independent standard Gaussian factor and private noises give precisely $T=\theta+AG+D\varepsilon$ and $\Sigma=AA^{\mathsf T}+D^2$. This is a finite jointly Gaussian vector; singularity of the alternative block is allowed.

### H7

Pass. All p-values use the specified one-sided standard Gaussian survival function. Every true-null p-value is exactly uniform on $(0,1)$.

### H8

Pass. Apply the original ordinary BH rule to all $2M$ p-values, retaining multiplicities, non-strict inequalities, and the largest qualifying rank. Count false rejections only in the first $M$ original labels and use $V/(R\vee1)$. No conditional procedure or alternative threshold is substituted.

### NOT

Fail. In fact the full finite BH FDR is at most $q/2$, uniformly in $M$ and $q$.

Here is a direct argument including ties and singularity. For a null $i$, replace only $p_i$ by zero and let $R_i$ denote the ordinary BH rejection count for that modified vector. Deterministically $R_i\geq1$, and
$$
i\in\mathcal R_q\quad\Longleftrightarrow\quad p_i\leq qR_i/N;
\qquad R=R_i\text{ on this event}.
$$
For justification, changing a rejected p-value to zero cannot create a new qualifying rank above the old rejection count: at any such rank that already rejected p-value was below the rank's threshold. Conversely, when $p_i\leq qR_i/N$, restoring it keeps rank $R_i$ qualifying, and monotonicity gives equality of the two counts. This argument uses the largest qualifying rank and remains valid with ties.

All covariances $\Sigma_{ji}$, $j\ne i$, are nonnegative: they equal $c^2$ for other nulls and $c$ for alternatives. Consequently, conditional on $T_i=t$, the other coordinates admit the joint representation
$$
T_j=\theta_j+\Sigma_{ji}t+W_j\quad(j\ne i),
$$
where the jointly Gaussian residual vector $W$ has a law independent of $t$; it may be singular. The coordinatewise coupling makes $R_i$ nondecreasing in $t$, hence nonincreasing in $u=\overline\Phi(t)$. For $U=p_i$ and
$$
a_r(t)=\mathbb P(R_i\geq r\mid U\leq t),
$$
each $a_r(t)$ is nonincreasing in $t$, because $U$ is uniform and the pointwise conditional probabilities are nonincreasing in $u$.

Writing $t_r=qr/N$, the false-discovery contribution of null $i$ is therefore
$$
\begin{aligned}
\mathbb E\left[\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}\right]
&=\sum_{r=1}^N\frac1r\mathbb P(U\leq t_r,R_i=r)\\
&=\frac qN\sum_{r=1}^N\{a_r(t_r)-a_{r+1}(t_r)\}\\
&\leq\frac qN a_1(t_1)=\frac qN,
\end{aligned}
$$
where $a_{N+1}=0$ and the last sum telescopes using $a_r(t_r)\leq a_r(t_{r-1})$ for $r\geq2$. Summing over the original $M$ nulls gives $\operatorname{FDR}\leq Mq/N=q/2$. Thus
$$
\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}\leq\frac1{2\sqrt{\log(1/q)}}\longrightarrow0.
$$
This obstruction concerns this positively oriented family only; it does not cover mixed loading signs or establish the general fixed-floor assertion.

## Failure

NOT fails: nonnegative Gaussian conditional shifts bound the original finite BH FDR by $q/2$, despite growing dimension, nontrivial null common loading, vanishing positive alternative means, and singular tied alternatives.
