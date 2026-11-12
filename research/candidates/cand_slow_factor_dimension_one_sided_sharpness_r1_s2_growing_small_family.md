---
type: candidate
title: Slowly growing all-null regular-simplex family
status: failed
target_asset: slow_factor_dimension_one_sided_sharpness
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 41c776b5ba7a93e0fc85e9c920013f0df855975e6702b5c0f76f09e9b822fd15
performed_by: unknown
created_at: '2026-11-04T07:10:23.174Z'
extension_version: 0.0.4
---

## Object

Write $\ell=\log(1/q)$, take $0<q<e^{-16}$, and set
$$
m(q)=\lfloor\ell^{1/4}\rfloor,\qquad D(q)=d(q)=m(q),
\qquad\theta_i=0\quad(1\leq i\leq m).
$$
In $\mathbb R^m$, let $\mathbf1=(1,\ldots,1)^{\mathsf T}$ and define
$$
a_i=\sqrt{\frac m{m-1}}\left(e_i-\frac1m\mathbf1\right).
$$
Use $T_i=a_i^{\mathsf T}Z$ and the ordinary one-sided BH procedure.

## Checks

### H1

Here $m\geq2$, the budget is finite, and
$$
\frac{D(q)\log\log(1/q)}{\sqrt{\log(1/q)}}
\leq\frac{\log\ell}{\ell^{1/4}}\longrightarrow0.
$$

### H2

The representation has allowed positive dimension $d=D=m$. Direct calculation gives $\|a_i\|^2=1$ and $a_i^{\mathsf T}a_j=-1/(m-1)$ for distinct coordinates. Hence it is a valid singular Gaussian model with pairwise negative correlations and zero residual variances. Every marginal is standard normal and every hypothesis is a true null.

### H3

All-null FDP is the indicator that BH makes at least one rejection. If BH rejects anything, at least one p-value is at most its BH threshold, and every BH threshold is at most $q$. Thus
$$
\{R_q>0\}\subseteq\bigcup_{i=1}^m\{p_i\leq q\}.
$$
Each one-sided p-value is uniform, irrespective of the negative dependence.

### NOT

The union bound supplies the uniform family estimate
$$
0\leq\operatorname{FDR}(q)\leq m(q)q,\qquad
0\leq\frac{\operatorname{FDR}(q)}{q\sqrt\ell}
\leq\ell^{-1/4}\longrightarrow0.
$$
Thus this admissible increasing-size family cannot exceed the proposed upper constant. A low FDR within a subclass does not challenge the lower bound for the full supremum.

The same obstruction applies to every admissible model with $m(q)=o(\sqrt\ell)$: a false rejection requires a true-null p-value at most $q$, each such marginal has probability at most $q$ even for negative null means, so FDR is at most $m_0(q)q\leq m(q)q$. This closes the low-test-count corner without a fixed-dimension quantile expansion.

## Failure

NOT fails: every family with $m=o(\sqrt{\log(1/q)})$ has normalized FDR tending to zero, including this negatively correlated simplex family.
