---
type: candidate
title: Equality-radius cluster with orthogonal spread just below the threshold u
status: failed
target_asset: gaussian_bh_angular_cluster_partial_entropy_bound
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
statement_digest: 736750aaadb60109c2ce46215b308676bc7a0cd9e89173948fa97978fa8123b1
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:16:00.960Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$\kappa=1$, $C\ge1$, $q$ small, $u=\overline\Phi^{-1}(q)$. $G$ has $n$ nulls ($\theta_i=0$), $d\ge n+1$, $v=e_0$, $w_i=s\,e_0+\epsilon\,e_i$ with $e_1,\dots,e_n$ orthonormal and orthogonal to $e_0$, $s^2+\epsilon^2=1$, and $\epsilon$ chosen so that $\|w_i-v\|=\kappa/u$ exactly (equality in H3). Then $T_i=sY_G+\epsilon Z_i$ with $Z_i$ i.i.d. Other coordinates: an arbitrary adversarial family (alternatives with huge means to inflate $R$, or nulls with $\theta=-\infty$ to keep $R=V_G$, or alternatives loaded on further factors to make $R$ depend on $Z$), with $\pi_G=n/m\in[q^C,1]$, $n\to\infty$. Idea: on $Y_G\in[u-a/u,u]$ (probability $\asymp q$) a constant fraction $\overline\Phi((a+b)/\kappa)$ of $G$ has $T_i\ge u+b/u$, and $\max_i T_i\to\infty$ as $n\to\infty$, so the off-strip term (a) might see order-one FDP from $G$.

## Checks

### H1, H2, H3, H4
Unit loadings, $\theta_i=0$ on $G$; $\|w_i-v\|=\kappa/u$ is the boundary case of the scale condition; $\pi_G\ge q^C$ by the choice of $m$.

### NOT
Fails, for every choice of the other coordinates. Fix $i\in G$, let $X=w_i^{\mathsf T}Z\sim\mathcal N(0,1)$, $\rho=w_i^{\mathsf T}v\ge1-\kappa^2/(2u^2)\ge1/2$, $\sigma=\sqrt{1-\rho^2}\le\|w_i-v\|\le\kappa/u$. Deterministically
$$
\frac{\mathbf 1\{p_i\le qR/m\}}{R\vee1}\le\sum_{j=1}^m\frac1j\mathbf 1\Bigl\{\tfrac{q(j-1)}m<p_i\le\tfrac{qj}m\Bigr\}\le\min\Bigl(1,\frac{q}{m\,\overline\Phi(X+\theta_i)}\Bigr)\mathbf 1\{X+\theta_i\ge u\},
$$
and $\theta_i\le0$ only helps. Given $X=x\ge u$, $Y_G\sim\mathcal N(\rho x,\sigma^2)$ and $(1-\rho)u/\sigma\le\sigma u\le\kappa$, so $\mathbb P(Y_G\le u\mid X=x)\le\Phi(\kappa-\rho(x-u)u/\sigma)\le\Phi(\kappa-(x-u)u/(2\kappa))$. With $p=\overline\Phi(x)$ and $u(x-u)\ge\log(q/p)$ (log-concavity of $\overline\Phi$),
$$
\mathbb E\Bigl[\frac{\mathbf 1\{i\in\mathcal R_q\}\mathbf 1\{Y_G\le u\}}{R\vee1}\Bigr]\le\frac qm\Bigl(1+\int_0^\infty\Phi\bigl(\kappa-\tfrac{s}{2\kappa}\bigr)ds\Bigr)=\frac qm A(\kappa).
$$
Summing over $i\in G$ gives the first term of (a) $\le A(\kappa)q\pi_G$, whatever $n$, $d$, or the other coordinates. The many large $T_i$ for $Y_G$ just below $u$ are rejected only when $R$ is of order $m$, which dilutes them to $O(q\pi_G)$ in expectation. The second term of (a) is $\le\mathbb P(Y_G>b_G)=q\pi_G$, and (b) follows from the approved entropy bound (see the round record).

## Failure

NOT fails: per null, the BH weight is at most $\min(1,q/(m\overline\Phi(X)))$, and $\mathbb P(Y_G\le u\mid X)$ decays like $\Phi(\kappa-\log(q/p)/(2\kappa))$, so the scale-$\kappa/u$ spread gives only $O(q/m)$ per null on $\{Y_G\le u\}$.
