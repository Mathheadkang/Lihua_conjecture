---
type: candidate
title: Two antialigned nulls with fixed private noise
status: failed
target_asset: gaussian_bh_one_sided_private_noise_floor_order
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
slot: 2
direction: small_cases
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:15:04.651Z'
extension_version: 0.0.4
---

## Object

Fix $s_0=1/2$. For every $q\in(0,1)$ take $N=2$, $d=1$, $\theta=(0,0)$, $A=(\sqrt{3}/2,-\sqrt{3}/2)^{\mathsf T}$, and $D=(1/2)I_2$. Let $G,\varepsilon_1,\varepsilon_2$ be independent standard normal variables and set

$$
T_1=(\sqrt{3}/2)G+\varepsilon_1/2,\qquad
T_2=-(\sqrt{3}/2)G+\varepsilon_2/2.
$$

Use $p_i=\overline\Phi(T_i)$ and ordinary BH at level $q$.

## Checks

### H1

The floor is fixed independently of $q$, with $s_0=1/2\in(0,1]$.

### H2

$N=2,d=1$ are positive integers; $\theta\in\mathbb R^2$, $A\in\mathbb R^{2\times1}$, and $D$ is diagonal with nonnegative entries.

### H3

Each row satisfies $\|a_i\|^2+s_i^2=3/4+1/4=1$.

### H4

$I_0^{(1)}(\theta)=\{1,2\}$ and both private standard deviations equal $s_0$.

### H5

The driving variables have exactly the stipulated independent standard normal law. The resulting joint normal covariance has diagonal entries $1$ and off-diagonal entries $-3/4$, hence is positive definite.

### H6

The p-values are the required one-sided Gaussian p-values and the procedure is exactly ordinary BH, including multiplicities, non-strict inequalities and the largest qualifying rank. Each null p-value is marginally uniform.

### NOT

Fails. Since every coordinate is null, the FDR is the probability of any rejection. For $N=2$, this event is exactly

$$
\{\min(p_1,p_2)\le q/2\}\;\cup\;
\{q/2<p_1\le q,\ q/2<p_2\le q\}.
$$

The two displayed events are disjoint. Marginal uniformity and the union bound give probability at most $q$ for the first event, while the second event is contained in $\{q/2<p_1\le q\}$ and has probability at most $q/2$. Therefore

$$
0\le\frac{\operatorname{FDR}(q)}{q\sqrt{\log(1/q)}}
\le\frac{3}{2\sqrt{\log(1/q)}}\longrightarrow0.
$$

The same estimate applies to every two-null Gaussian covariance, including a covariance depending on $q$. More generally, for any model with $N$ hypotheses, any false rejection requires at least one true-null p-value at most $q$; null super-uniformity yields $\operatorname{FDR}\le Nq$. Consequently, any family with uniformly bounded $N$ has a vanishing normalized ratio. This excludes only bounded-size families and supplies no dimension-uniform bound when $N$ grows with $q$.

## Failure

NOT fails: the normalized FDR vanishes as $q$ decreases, despite strong negative correlation and a fixed positive private-noise floor.
