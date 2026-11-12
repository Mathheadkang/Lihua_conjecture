---
type: candidate
title: Singular all-copy zero-mean boundary does not break completion continuity
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:46:20.121Z'
extension_version: 0.0.4
---

## Object

Fix $\sigma=1/2$. For $t\ge0$, let $P_t$ be the point law on the infinite deterministic array with $\theta_i=-t$, $\ell_i=1$, and $C_{ij}=1$ for every $i,j$. Test the singular covariance and zero-mean boundary through $t\downarrow0$, allowing levels $q_j\to q\in(0,1/2)$. In particular, $q=S(1)$ is allowed. The proposed failure is discontinuity of the completed FDR at $P_0$, or failure of completion convergence there.

## Checks

### H1

The chosen common loading satisfies $0<\sigma<1$, and every tested level lies in $(0,1/2)$.

### H2

Every mark is lawful: $\ell_i=1$ and $\theta_i=-t\le0$, including $t=0$. The moment is $M_2(P_t)=t^2<\infty$.

### H3

The residual covariance is symmetric, has entries in $[-1,1]$, and has diagonal one. For every finite vector $x$, $x^{\mathsf T}C x=(\sum_i x_i)^2\ge0$. Its singularity is allowed.

### H4

The constant array is invariant under every finite permutation, so $P_t$ is jointly exchangeable. Its parameters are deterministic and independent of Gaussian innovations. As $t\downarrow0$, its every finite subarray converges deterministically to the corresponding subarray of $P_0$.

### NOT

Fail. Put $\tau=\sqrt{1-\sigma^2}$ and take independent standard normals $Y,Z$. All conditional scores can be realized as the same random variable $T_i=-t+\tau Y+\sigma Z$. Its variance is $\tau^2+\sigma^2=1$. All $n$ p-values coincide. Ordinary largest-rank BH rejects every coordinate exactly when this common p-value is at most $q$: if any rank qualifies, the terminal rank $n$ qualifies, and conversely. Thus its full tagged FDP is $\mathbf1\{\tau Y+\sigma Z\ge S^{-1}(q)+t\}$, and, for every $n\ge1$,

$$
\mathcal F_n(P_t;q,\sigma)=S(S^{-1}(q)+t).
$$

The completion error is identically zero throughout this family. For arbitrary $t_j\downarrow0$ and $q_j\to q\in(0,1/2)$, continuity of $S$ and $S^{-1}$ gives $\mathcal F(P_{t_j};q_j,\sigma)\to q=\mathcal F(P_0;q,\sigma)$. This also checks the endpoint $q=S(1)$ directly. At the zero-mean boundary all tags are already canonical and the moment is zero.

## Failure

NOT fails: the singular all-copy family has exact dimension-independent FDR and remains continuous at the zero-mean boundary.
