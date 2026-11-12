---
type: candidate
title: Strictly negative singleton null at the dimension boundary
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
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
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:25:30.473Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $\theta_1=-1$, $\Sigma=(1)$, $q=1/5$, and $T_1=-1+Z$, where $Z$ is standard normal. Select $i=1$. The attempted violation concerns the strictly negative-null baseline and the endpoint at zero.

## Checks

### H1

$N=1$ is a finite positive integer.

### H2

$\theta_1=-1$ is real.

### H3

$\Sigma=(1)$ is positive semidefinite with unit diagonal.

### H4

$0<q=1/5<1/2$.

### H5

The specified observation has exactly the required Gaussian law.

### H6

$\theta_1<0$, so $i=1\in I_0$.

### NOT

Fail. Here $\xi_1=0$, $T_1^1(t)=u(t)$, and $R_1(t)=1$ for every $0<t<q$. Thus $A_1(t)=t/q$, with endpoints zero and one, no internal event points or jumps, and derivative $1/q$. The weight is $g(t)=\exp\{-u(t)-1/2\}$, with $g(0+)=0$. Integration by parts gives
$$
q\left[g(q)-\int_{(0,q)}\frac{t}{q}\,dg(t)\right]
=\int_0^q g(t)\,dt
=S(u(q)+1)
=F_1.
$$
The equality follows from the substitution $t=S(x)$ and $g(t)\phi(x)=\phi(x+1)$. The baseline lies in $[0,1]$ because $0\leq g(t)\leq1$. All residual/path objects are deterministic and measurable; the jump sum is empty, and the final bound is $F_1\leq q$. Thus the attempted negative-null singleton violation does not occur.

## Failure

NOT fails: the strictly negative singleton null satisfies the claimed identity, endpoints, derivative, and bound exactly.
