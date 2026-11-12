---
type: candidate
title: Singular rank-one path with an isolated three-rejection spike
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

Set $N=4$, $q=1/5$, $a=q/8$, $h=3q/4$, and
$$
b=u(h)-u(a),\qquad c=u(h)+u(a),\qquad
\theta=(0,b,c,-10),\qquad s=(1,1,-1,-1),\qquad\Sigma=ss^{\mathsf T}.
$$
Let $T=\theta+sX$ for a standard normal $X$ and select $i=1$. Every residual relative to $i=1$ is zero. This attempts to violate the identity through omission of a non-strict BH spike at a simultaneous opposing crossing.

## Checks

### H1

$N=4$ is a finite positive integer.

### H2

All means are real because $a,h\in(0,1)$.

### H3

$v^{\mathsf T}\Sigma v=(s^{\mathsf T}v)^2\geq0$ and $\Sigma_{jj}=s_j^2=1$. The covariance is singular of rank one.

### H4

$0<q=1/5<1/2$.

### H5

$T=\theta+sX$ has exactly the required jointly Gaussian law, including the specified singular covariance.

### H6

$\theta_1=0$, so the selected label $i=1$ is a true null.

### NOT

Fail for the attempted identity violation at the selected label. Write
$$
\alpha=S(u(q/2)-b),\qquad
\beta=S(c-u(q/2)).
$$
Their approximate values are $\alpha=0.0137241648350372$ and $\beta=0.0431867501975214$, with $0<\alpha<a<\beta<q/4<q/2$. Coordinate four never qualifies at any BH threshold on $(0,q)$ because its score is $-10-u(t)<0<u(q)$.

The other scores are $u(t)$, $u(t)+b$, and $c-u(t)$. Rank three requires all three corresponding p-values to be at most $h$. The last two conditions are respectively $t\leq a$ and $t\geq a$, so rank three occurs precisely at $a$. Rank two occurs on $(0,\alpha]$ and $[\beta,q/2]$: these intervals arise respectively from coordinates one and two passing $q/2$, and coordinates one and three passing $q/2$. On the remainder of $(0,q)$ the rank is one, except for $R_1(a)=3$. Coordinates two and three cannot both pass $q/2$, since their score sum is $b+c=2u(h)<2u(q/2)$.

At $a$, the neighboring ranks are one, so
$$
A_1(a^-)=A_1(a^+)=4a/q=1/2,
\qquad A_1(a)=4a/(3q)=1/6.
$$
This is a removable point discrepancy, exactly as omitted by the statement. The only actual net jumps are
$$
A_1(\alpha^-)-A_1(\alpha^+)=-2\alpha/q,
\qquad
A_1(\beta^-)-A_1(\beta^+)=2\beta/q.
$$
The change from rank two to rank one at $q/2$ produces no jump because both clipped values are one. The endpoints are zero and one. Event points are finite and deterministic, and each open event interval has the asserted derivative. Since $g_1=1$, direct integration using the uniform p-value of label one yields
$$
F_1=\frac{\alpha}{2}+(\beta-\alpha)+\frac{q/2-\beta}{2}
=\frac q4+\frac{\beta-\alpha}{2}
=\frac q4\left[1-\frac{2\alpha}{q}+\frac{2\beta}{q}\right].
$$
Thus $F_1\approx0.0647312926812421$ agrees with the claimed net signed-jump formula. All sums here are finite and deterministic. This candidate tests the selected-label identity; it does not independently audit every other true-null label in this model.

## Failure

NOT fails for the selected-label attack: the isolated rank spike contributes no net jump, and the two genuine jumps reproduce the exact rejection contribution.
