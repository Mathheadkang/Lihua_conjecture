---
type: candidate
title: Deterministic oscillating mean blocks at the exchangeability boundary
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: fail
  H6: unknown
  H7: unknown
  H8: unknown
  H9: unknown
  NOT: unknown
mode: refute
round: 5
slot: 3
direction: drop_hypothesis
statement_digest: 82e91305e89e8c5f50be87b28d54dc08a251a8adf76f9407859ccdd4f3536aee
performed_by: unknown
created_at: '2026-11-09T06:23:55.945Z'
extension_version: 0.0.4
---

## Object

Set $\sigma=1/2$, $q=1/10$, and, for the penalized clauses, $\eta=\delta=1$. For $k\ge1$ let $L_k=2^{2^k}$, $N_0=0$, and $N_k=\sum_{j=1}^kL_j$. On the deterministic block $N_{k-1}<i\le N_k$, put $\theta_i=-1$ for odd $k$ and $\theta_i=0$ for even $k$. Put $\ell_i=1$ and $C_{ij}=1$ for every $i,j$. Let $P$ be the point mass at this infinite parameter array. Standard Gaussian innovations may be supplied on an independent probability space.

This tests dropping joint exchangeability while retaining bounded means, lawful true tags and a singular lawful covariance. Increasing block lengths change empirical mean frequencies without escaping means. It is a hypothesis-boundary test, not a claimed lawful counterexample.

## Checks

### H1

Pass: the fixed common loading obeys $0<\sigma=1/2<1$.

### H2

Pass: the marks are in $E_{\rm mark}$. Every tag is true, and every mean is either $-1$ or $0$, hence $\ell_i=1\Rightarrow\theta_i\le0$.

### H3

Pass: $C_{ij}=C_{ji}=1\in[-1,1]$, and $C_{ii}=1$.

### H4

Pass: every finite principal covariance matrix is positive semidefinite. For every $n$ and $x\in\mathbb R^n$,
$$
x^{\mathsf T}C_{1:n,1:n}x=\left(\sum_{i=1}^nx_i\right)^2\ge0.
$$

### H5

Fail: $P$ is not jointly exchangeable. Here $L_1=4$, so $\theta_1=-1$ and $\theta_5=0$. Under $P$, the cylinder event $\{\theta_1=-1\}$ has probability one. Under the pushforward by the finite transposition $(1\ 5)$, the same event has probability zero. Thus simultaneous finite relabeling does not preserve $P$.

### H6

Unknown: parameter independence from Gaussian innovations was not checked after the first failure.

### H7

Unknown: the applicable level restrictions were not checked after the first failure.

### H8

Unknown: the positive-penalty restrictions for the penalized clauses were not checked after the first failure.

### H9

Unknown: membership in $\mathfrak P_2$ for clauses requiring finite moment was not checked after the first failure.

### NOT

Unknown: the conclusion was not checked after the failure of joint exchangeability. No failure of the target on its lawful class is asserted.

## Failure

H5: the transposition $(1\ 5)$ changes the deterministic mean law, so the array law is not jointly exchangeable.
