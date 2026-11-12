---
type: candidate
title: Nonatomic flat crossing destroyed by a downward mean perturbation
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
round: 2
slot: 1
direction: known_counterexamples
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:46:49.625Z'
extension_version: 0.0.4
---

## Object

Set $q=1/4$, $\sigma=1/2$, $\mathcal H=\mathbb R$, and use direction $v=1$ and true tag $\ell=1$ everywhere. Put $a=1/4$, $b=1/2$, $h(r)=S^{-1}(qr)$, $g_*=h(a)$, and $L=h(1)-g_*-1$. Define the parameter law
$$
\pi=a\delta_{(0,1,1)}+\int_a^b\delta_{(h(u)-g_*,1,1)}\,du+(1-b)\delta_{(L,1,1)}.
$$
The integral is with respect to ordinary Lebesgue measure, so its mass is $b-a$. Let $\pi_n$ be the pushforward of $\pi$ under $(\theta,v,\ell)\mapsto(\theta-1/n,v,\ell)$. With independent standard normals $\xi,Z$, put $G=\sqrt{3}\xi/2+Z/2$. Every score under $\pi$ is $\theta+G$.

The motivating pathology is a whole interval of non-strict crossings at one realization, followed by disappearance of every crossing under an arbitrarily small downward shift. Unlike the previously tested coincident-score law, the mean distribution here has a nonzero nonatomic component.

## Checks

### H1

Pass: $q=1/4\in(0,1/2)$.

### H2

Pass: $\sigma=1/2\in(0,1)$, with $\tau=\sqrt{3}/2$.

### H3

Pass: $\mathbb R$ is a nonzero separable real Hilbert space and every direction is $1$, of norm one.

### H4

Pass: all tags are true, and all means are nonpositive: $h(u)-g_*\le0$ for $u\in[a,b]$, while $L<0$. The means are bounded, as are those of each shifted law, so these deterministic laws belong to $\mathcal P_1(\mathcal E)$.

### H5

Pass: $X(v)=v\xi$ is isonormal on $\mathbb R$ and $Z$ is independent. Thus $G$ is standard normal and the scores have exactly the prescribed common-loading construction. The laws are independent of these Gaussian variables.

### H6

Pass: coupling each parameter to its mean-shifted copy gives cost exactly $1/n$, so $W_1(\pi_n,\pi)\le1/n\to0$.

### NOT

Fail: the full FDR converges, despite the pathwise flat-crossing discontinuity.

At $G=g_*$, the lower atom has score $h(1)-1<h(1)$ and never qualifies. Directly integrating the other part of the law gives
$$
H_\pi(r)=\begin{cases}0,&0<r<a,\\r,&a\le r\le b,\\b,&b<r\le1.\end{cases}
$$
Consequently the actual largest crossing is $b$ at this realization.

If $G=g<g_*$, the lower atom still never qualifies. For $r<a$, even the highest-mean atom fails the threshold. For $r\ge a$, put $u_*=S(h(r)+g_*-g)/q<r$. If $u_*<a$, neither the upper atom nor the nonatomic component qualifies. If $u_*\ge a$, their total qualifying mass is $\min(b,u_*)<r$. Therefore no positive crossing exists for any $g<g_*$. If $g\ge g_*$, the upper atom qualifies at $r=a$, so a positive crossing exists. Hence
$$
\{\rho_\pi>0\}=\{G\ge g_*\}.
$$
All parameters are true-tagged. At every positive largest crossing the count equals that crossing: the count function is nondecreasing and right-continuous, so its positive supremal qualifying crossing is attained; a strict count excess would give a larger qualifying rank. Thus $D_\pi=1$ on this event and is zero otherwise. Applying the same calculation to the shifted law yields
$$
F_\pi=S(g_*)=qa=1/16,\qquad F_{\pi_n}=S(g_*+1/n)\longrightarrow1/16.
$$
The downward perturbation changes the rank from $b$ to zero at $G=g_*$, but that realization has Gaussian probability zero. Moreover every positive rank in these laws is at least $a$, because its rejection event implies that the upper atom qualifies at rank $a$. Thus this example also has no microscopic positive-rank obstruction.

## Failure

NOT fails: the nonatomic flat-crossing pathology produces a discontinuity only at a Gaussian-null common score, and its exact full FDR converges under the Wasserstein perturbation.
