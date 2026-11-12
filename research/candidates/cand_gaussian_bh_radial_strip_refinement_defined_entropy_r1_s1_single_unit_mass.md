---
type: candidate
title: Single unit-loading null with unit group mass
status: failed
target_asset: gaussian_bh_radial_strip_refinement_defined_entropy
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 582355e827b2c8daf9f48064719117ca7fdba4dbdf5b11f0c912cc329dca2dad
performed_by: unknown
created_at: '2026-11-06T23:19:24.051Z'
extension_version: 0.0.4
---

## Object

For every $q\in(0,1/2)$ take $N=d=1$, $\theta_1=0$, $a_1=1$, and independent standard normal variables $Z,\varepsilon_1$. Then $T_1=Z$, $r_1=1$, $s_1=0$, $\gamma_1=0$. Take $G_1=\{1\}$ and $v_1=1$. This tests the simultaneous boundaries $s_1=0$ and $\pi_1=1$; the same family is considered along $q\downarrow0$.

## Checks

### H1

Pass: $N=d=1$ are positive finite integers.

### H2

Pass: the mean and loading are deterministic and $\|a_1\|=1$. The covariance is the admissible one-dimensional matrix $[1]$.

### H3

Pass: $Z$ and $\varepsilon_1$ are mutually independent standard normals, and the stated representation gives $T_1=Z+0\varepsilon_1$.

### H4

Pass: $0<q<1/2$, $I_0=\{1\}$, $m_0=1>0$, and ordinary BH rejects exactly when $\overline\Phi(Z)\le q$. Hence $\operatorname{FDR}=q$ and $\pi_0=1$.

### H5

Pass: the single group is a nonempty partition of $I_0$, $v_1$ is a unit vector, and $a_1=r_1v_1$. The group mass normalized by $N$ is $\pi_1=1$.

### NOT

Fail: every claimed conclusion holds. Here $b_1=U>0$, $A(1,0)=0$, $C_{11}=+\infty$, and therefore $\mathcal E_{\min}=\min\{+\infty,0\}=0$, $\mathcal E_s=\mathcal E_0=0$, and $\overline\gamma_0=0$. The finite bound reads $q\le(3/2)q$. The threshold comparison reads $0\le0$ and both entropy comparisons read $0\le0\le0$, including the extended quotient convention. Along $q\downarrow0$, all three sufficient entropy conditions hold identically, while
$$
\frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}=\frac1{\sqrt{\log(1/q)}}\longrightarrow0\le\frac1{\sqrt\pi}.
$$
There is no violated finite bound, comparison, or asymptotic corollary in this object.

## Failure

NOT fails: the defined $A(1,0)=0$ and $C_{11}=+\infty$ conventions give zero strip cost, and the exact FDR is $q$.
