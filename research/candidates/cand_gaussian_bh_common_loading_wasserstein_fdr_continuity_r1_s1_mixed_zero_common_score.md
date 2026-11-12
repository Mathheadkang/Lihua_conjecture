---
type: candidate
title: Mixed true and alternative zero atoms with a common score
status: failed
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:42:21.565Z'
extension_version: 0.0.4
---

## Object

Test the continuity conclusion at the alternative-zero completion boundary with perfectly coincident limiting scores, both labels present, irrational atom masses, and endpoint ranks zero and one.

Set $q=1/4$, $\sigma=1/2$, $\mathcal H=\mathbb R$, $v=1$, $w=\sqrt{2}/2$, and $Y=\sqrt{3}G/2+Z/2$ for independent standard normal variables $G,Z$. For $n\ge1$, put $N_n=n+2$, $k_n=\lfloor N_nw\rfloor$, $w_n=k_n/N_n$, and $\epsilon_n=1/N_n$. Define
$$
\pi=w\delta_{(0,1,1)}+(1-w)\delta_{(0,1,0)},
$$
$$
\pi_n=w_n\delta_{(0,1,1)}+(1-w_n)\delta_{(\epsilon_n,1,0)}.
$$
Thus the limiting true and alternative scores are both $Y$, whereas the approximating scores are $Y$ and $Y+\epsilon_n$. The candidate seeks a discontinuity of $F$ at this tied mixed-label law.

## Checks

### H1

The fixed testing level satisfies $0<q=1/4<1/2$.

### H2

The fixed common loading satisfies $0<\sigma=1/2<1$ and $\tau=\sqrt{3}/2$.

### H3

The space $\mathbb R$ is a nonzero separable real Hilbert space, and every displayed direction has norm one. Set $X(1)=G$ and $X(-1)=-G$; the isonormal evaluations are measurable finite sums.

### H4

The law $\pi$ is deterministic and belongs to $\mathcal P_1(\mathcal E)$. Both zero-mean tags are admitted by the closed tagged domain. Its absolute first mean moment is zero.

### H5

Each law $\pi_n$ is deterministic and belongs to $\mathcal P_1(\mathcal E)$: the true point has mean zero and the alternative point has strictly positive mean $\epsilon_n$. Since $N_n\ge3$ and $0<w<1$, both $k_n$ and $N_n-k_n$ are positive integers. The labels are canonical and its first absolute mean moment is $(1-w_n)\epsilon_n<\infty$. All scores use the same independent $G,Z$; the resulting finite observation has unit marginal variances and rank-one covariance, which is admissible.

### H6

The prescribed laws converge in $W_1$. First change the alternative mean of $\pi$ from zero to $\epsilon_n$, at cost $(1-w)\epsilon_n$. Next change its true mass from $w$ to $w_n$, transporting mass $|w_n-w|$ between the two atoms at cost $1+\epsilon_n$ per unit mass. Consequently
$$
W_1(\pi_n,\pi)\le(1-w)\epsilon_n+|w_n-w|(1+\epsilon_n)\longrightarrow0,
$$
because $|w_n-w|<1/N_n$.

### NOT

Fail: there is no FDR discontinuity. More generally, for any $a\in(0,1)$ and $\epsilon\ge0$, let
$$
\nu_{a,\epsilon}=a\delta_{(0,1,1)}+(1-a)\delta_{(\epsilon,1,0)}.
$$
The true p-value is $p_0=S(Y)$ and the alternative p-value is $p_1=S(Y+\epsilon)\le p_0$. If $p_0\le q$, every parameter qualifies at rank one; hence the actual largest rank is one and the FDP is $a$. If $p_0>q$, no true parameter can be rejected at any positive rank $r\le1$, since $qr\le q<p_0$; hence the FDP is zero, whether an alternative-only crossing exists or not. Therefore, pointwise,
$$
D_{\nu_{a,\epsilon}}=a\mathbf1_{\{S(Y)\le q\}},\qquad F_{\nu_{a,\epsilon}}=aq.
$$
Since $Y$ is standard normal, $\mathbb P(S(Y)\le q)=q$. It follows that $F_\pi=wq$ and $F_{\pi_n}=w_nq\to wq$. At the limit, the rank is exactly one on $S(Y)\le q$ and zero otherwise. The finite arrays associated to $\pi_n$ have exactly $k_n$ true copies and $N_n-k_n$ alternative copies, and the same pointwise FDP formula. Thus their canonical finite FDRs agree exactly with these population values despite the singular covariance and the alternative-zero limit.

## Failure

NOT fails: tied zero-mean scores with both labels have exact full FDR equal to $q$ times the true mass; positive alternative shifts and rational approximation preserve convergence.
