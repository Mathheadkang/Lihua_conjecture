---
type: candidate
title: Singular pair with a genuine downward A jump
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:25:30.473Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $q=1/5$, $a=1/20$, $c=u(a)+u(q)$, $\theta=(0,c)$, and
$$
\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}.
$$
Use $Z=(X,-X)$ for standard normal $X$. The proposed failure mechanism is a downward $A_1$ jump caused by the second coordinate entering BH as the first p-value increases.

## Checks

### H1

$N=2$ is finite and positive.

### H2

Both means are finite and real; $c>0$ and $I_0=\{1\}$.

### H3

$\Sigma=vv^{\mathsf T}$ with $v=(1,-1)$ is positive semidefinite, singular, and unit diagonal. The displayed Gaussian realization has exactly this covariance.

### H4

$q=1/5\in(0,1/2)$.

### NOT

Fail. The residual vector for $i=1$ is zero, and the score path is $(u(t),c-u(t))$. Its largest BH rank is one for $0<t<a$ and two for $a\le t<q$. Consequently
$$
A_1(t)=2t/q\quad(0<t<a),\qquad A_1(t)=t/q\quad(a<t<q).
$$
The only actual net jump is at $a$, of size $A_1(a^-)-A_1(a^+)=a/q=1/4$. Extra threshold and clipping events have no net jump. All event sets are finite deterministic sets, endpoints are zero and one, and derivatives agree with the asserted rejection/rank formula. Since $\theta_1=0$, $g_1=1$ and the baseline is one. The first p-value is uniform and is rejected exactly on $(0,q)$, so
$$
F_1=\int_0^a 1\,dt+\int_a^q\frac12\,dt
=\frac{q+a}{2}=\frac18
=\frac q2\left(1+\frac14\right).
$$
The signed sum and its positive part both equal $1/4$ and are deterministic and integrable. Thus the identity and its FDR upper bound both hold, with equality in the bound.

## Failure

NOT fails: the genuine downward jump is present with exactly the coefficient required by the signed identity.
