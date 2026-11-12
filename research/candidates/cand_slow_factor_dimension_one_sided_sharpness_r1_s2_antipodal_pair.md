---
type: candidate
title: Antipodal two-test model with a growing redundant factor budget
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

Write $\ell=\log(1/q)$ and restrict to $0<q<e^{-8}$. Set
$$
D(q)=d(q)=\lfloor\ell^{1/3}\rfloor,\qquad m=2,\qquad
\theta_1=\theta_2=0,\qquad a_1=e_1,\quad a_2=-e_1.
$$
Thus $T_1=Z_1$, $T_2=-Z_1$, and $p_1=U$, $p_2=1-U$ for a uniform random variable $U$.

## Checks

### H1

The deterministic finite budget is at least one, and
$$
\frac{D(q)\log\log(1/q)}{\sqrt{\log(1/q)}}
\leq \frac{\log\ell}{\ell^{1/6}}\longrightarrow0.
$$

### H2

The dimension is a positive integer at most $\lfloor D(q)\rfloor$. The two loadings have norm one, residual variances are zero, and both means belong to the one-sided true null. Redundant coordinates and singular covariance are explicitly allowed.

### H3

Use the ordinary one-sided BH rule. For $q<1/2$, rank two cannot qualify because $\max(U,1-U)\geq1/2>q$. Rank one qualifies precisely on the two disjoint intervals $U\leq q/2$ and $U\geq1-q/2$. Both tests are true nulls, so FDP is the indicator of at least one rejection.

### NOT

The exact asymptotic family has
$$
\operatorname{FDR}(q)=q,\qquad
\frac{\operatorname{FDR}(q)}{q\sqrt{\log(1/q)}}
=\frac1{\sqrt\ell}\longrightarrow0.
$$
It therefore produces no violation of the asserted uniform upper bound. Its small ratio cannot refute the lower bound for the supremum over all admissible models; the approved one-factor lower construction belongs to the same budget.

## Failure

NOT fails: the exact antipodal two-test FDR is only $q$, even with an admissible growing representation dimension.
