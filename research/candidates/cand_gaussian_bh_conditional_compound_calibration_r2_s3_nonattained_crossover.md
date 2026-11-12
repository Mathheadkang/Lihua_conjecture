---
type: candidate
title: Nonattained finite envelope with continuously varying crossover
status: failed
target_asset: gaussian_bh_conditional_compound_calibration
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
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
performed_by: unknown
created_at: '2026-11-11T15:58:20.713Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $I_0=\{1\}$, $q=1/10$, and $Z\sim\operatorname{Unif}[0,1]$. Put $m(z)=3/4+z/2$. Given $Z=z$, let $P_1$ and $P_2$ be independent, with $P_2\sim\operatorname{Unif}[0,1]$ and null CDF
$$
F_z(t)=\begin{cases}
2m(z)t(1-t),&0\leq t\leq q,\\
2m(z)q(1-q)+\bigl(1-2m(z)q(1-q)\bigr)\dfrac{t-q}{1-q},&q<t\leq1.
\end{cases}
$$
For real $z$ outside $[0,1]$, extend $m$ by clipping $z$ to $[0,1]$ in this formula. These laws specify Borel probability kernels on the full real conditioning space. This family tests a finite nonattained level supremum, nonconstant conditional distributions, and the $K=1$ crossover; it does not rely on a zero atom, endpoint mass, empty null set, or absence of rejections.

## Checks

### H1

The positive dimension, fixed true-null set, and level $q\in(0,1)$ satisfy the structural hypotheses.

### H2

Here $3/4\leq m(z)\leq5/4$. On $[0,q]$ the derivative $2m(z)(1-2t)$ is positive. At $q$ the CDF equals $9m(z)/50\leq9/40<1$, and the continuation is increasing to $1$. The CDF is continuous with $F_z(0)=0$, so it has no atom at zero or at the cutoff. Its dependence on $z$ is Borel. Independent conditional draws from this kernel and the uniform kernel give mutually independent regular conditional coordinate distributions given $Z$.

### H3

For every $0<t\leq q$,
$$
\frac{F_z(t)}{2t}=m(z)(1-t).
$$
Consequently $M_q(z)=m(z)$, with no positive level attaining the supremum. Rational $t\downarrow0$ attain its limit, so the prescribed countable supremum gives the same finite measurable envelope. The crossover is
$$
K_q(z)=\begin{cases}1,&z\leq1/2,\\m(z),&z>1/2.\end{cases}
$$
All conditional states remain in the nontrivial region $2qK_q(z)\leq1/4<1$.

### H4

If $P_2>q$, rank $2$ cannot qualify and the null is rejected alone exactly when $P_1\leq q/2$, giving FDP $1$. If $P_2\leq q$, the null is rejected exactly when $P_1\leq q$; then rank $2$ qualifies and FDP is $1/2$. Other outcomes have FDP zero. Null labels and rejection counts are the original ones, and the largest qualifying BH rank is used throughout. Conditional independence therefore gives
$$
\mathbb E[\operatorname{FDP}\mid Z=z]
=(1-q)F_z(q/2)+\frac q2 F_z(q)
=m(z)q(1-q)(1+q/2)
=\frac{189}{2000}m(z).
$$

### NOT

The claimed right side is $\frac15\max\{1,m(z)\}$. Since $189/2000<1/5$ and $m(z)\leq\max\{1,m(z)\}$, the conditional conclusion holds strictly for every $z\in[0,1]$. Unconditionally, $\mathbb E[m(Z)]=1$ and $\mathbb E[\max\{1,m(Z)\}]=17/16$, so FDR is $189/2000$, below the expected bound $17/80$. Thus NOT fails in both the conditional and unconditional forms.

## Failure

NOT fails: the exact conditional FDR is $(189/2000)m(z)<(1/5)\max\{1,m(z)\}$ even with a nonattained supremum and nonconstant envelope crossing one.
