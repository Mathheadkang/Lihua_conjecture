---
type: candidate
title: Antipodal residual directions at the zero-moment boundary
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:53:03.140Z'
extension_version: 0.0.4
---

## Object

Fix $\sigma=1/2$ and $\tau=\sqrt{3}/2$. Let $\varepsilon_i$ be iid uniform signs, chosen before and independently of independent standard normals $G,Z$. Set
$$
\theta_i=0,\qquad \ell_i=1,\qquad C_{ij}=\varepsilon_i\varepsilon_j,
\qquad T_i=\tau\varepsilon_iG+\sigma Z.
$$
Let $P$ be this parameter-array law. Test $0<q<1/2$, including the endpoint $q=q_{\max}$ of the normalized problem. This family has two competing score atoms, a singular residual covariance, and moment zero; unlike a single all-copy atom, its largest BH rank can switch between a sign group and the entire sample.

## Checks

### H1

The common loading lies strictly between zero and one. All tested fixed levels lie in $(0,1/2)$; for the normalized conclusions restrict to $0<q\le q_{\max}$. Penalty parameters $\eta,\delta$ may be any positive numbers.

### H2

Every mark is lawful and canonical. The matrix $C$ is symmetric with unit diagonal and, for every finite vector $a$,
$$
\sum_{i,j}a_i C_{ij}a_j=\left(\sum_i a_i\varepsilon_i\right)^2\ge0.
$$
The displayed scores therefore give the required conditional Gaussian covariance $\tau^2C+\sigma^2\mathbf1\mathbf1^{\mathsf T}$, with unit marginal variances. The signs are independent of the Gaussian innovations.

### H3

The signs are iid, and all other parameters are deterministic functions of them invariant under relabeling. Thus the parameter law is jointly exchangeable.

### H4

The law belongs to $\mathfrak P_2$ and to the boundary sublevel $M_2=0$ because $\theta_1^2=0$ identically.

### NOT

Fail. There is an explicit limiting FDR, with continuous rank switching and normalized coercivity, rather than a contradiction.

Write $u(t)=S^{-1}(t)$, with $u(0)=+\infty$. Conditional on $|G|=g$, the two possible scores are $\sigma Z+\tau g$ and $\sigma Z-\tau g$. Let $W_n$ be the sample fraction in the higher-score group. Its conditional distribution given $|G|$ is $\operatorname{Bin}(n,1/2)/n$, independently of $|G|$ and $Z$. With all tags true, FDP is the indicator of at least one rejection. The actual largest-rank BH rule rejects if and only if the higher-score group qualifies at its full group rank, or the lower-score group qualifies at rank $n$. Consequently
$$
\mathcal F_n(P;q,\sigma)
=\mathbb E_{G,W_n}S\!\left(
\min\left\{\frac{u(qW_n)-\tau|G|}{\sigma},
\frac{u(q)+\tau|G|}{\sigma}\right\}\right).
$$
This formula includes $W_n=0$ by the convention $u(0)=+\infty$. For $W_n=1$, the second event is already contained in the first, so the absent lower-score group causes no spurious rejection.

Since $W_n\to1/2$ in probability, bounded convergence in probability gives
$$
\mathcal F(P;q,\sigma)
=\mathbb E_G S\!\left(
\min\left\{\frac{u(q/2)-\tau|G|}{\sigma},
\frac{u(q)+\tau|G|}{\sigma}\right\}\right).
$$
The integrand is bounded and continuous in $q\in(0,1/2)$. The equality boundary between the two crossing mechanisms is harmless because a minimum of continuous functions is continuous. Convergence is locally uniform in $q$: on $W_n\ge1/4$ the derivative of $u(qw)$ in $w$ is bounded uniformly for $q$ in a fixed compact subset of $(0,1/2)$; the remaining error is bounded by $\mathbb P(W_n<1/4)$, which tends to zero. The score threshold has no atom because $\sigma>0$.

There is also no small-level escape in the normalized objective. The limiting rejection event is
$$
\{\sigma Z+\tau|G|\ge u(q/2)\}
\ \cup\
\{\sigma Z-\tau|G|\ge u(q)\}.
$$
The first probability is at most $2S(u(q/2))=q$, by the union bound for the two standard normal variables $\sigma Z\pm\tau G$. The second event implies $\sigma Z\ge u(q)$, hence has probability at most $q$ since $u(q)>0$ and $\sigma<1$. Thus $\mathcal F(P;q,\sigma)\le2q$, and
$$
\mathcal L_{\eta,\delta}(P,q;\sigma)
\le\frac{2}{u(q)}-\delta\log(1/q)\longrightarrow-\infty.
$$
Finally this particular law already has a deterministic directing representation
$$
\mu=\tfrac12\delta_{(0,+1,1)}+\tfrac12\delta_{(0,-1,1)}
$$
in $\mathcal H=\mathbb R$, with zero diagonal-noise correction and $X(v)=vG$. This is an explicit representation of this object, not an invocation or verification of the general marked representation theorem.

## Failure

NOT fails: the two-atom antipodal law at moment zero has an explicit continuous FDR completion, lawful directing representation, and normalized small-level coercivity.
