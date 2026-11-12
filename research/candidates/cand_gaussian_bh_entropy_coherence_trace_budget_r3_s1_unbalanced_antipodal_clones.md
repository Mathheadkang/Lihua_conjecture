---
type: candidate
title: >-
  Unbalanced antipodal null clones make the entropy-coherence trace ratio
  diverge
status: survived
target_asset: gaussian_bh_entropy_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: pass
tags:
  - boundary-degenerate
  - singular-gaussian
  - antipodal-clones
  - unbalanced-posterior
mode: refute
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:31:00.636Z'
extension_version: 0.0.4
---

## Object

For any finite integer $N\ge2$ and $0<q\le\overline\Phi(3)$, let $d=1$, let $G$ be standard normal, and take $N$ original true nulls, all with mean zero:
$$
T_1=\cdots=T_{N-1}=G,\qquad T_N=-G.
$$
Thus $v_1=\cdots=v_{N-1}=1$ and $v_N=-1$. Define
$$
p=\frac1N,\quad U=\overline\Phi^{-1}(q),\quad H=h(U),\quad
a=\overline\Phi^{-1}(q(1-p)),\quad A=\overline\Phi^{-1}(qp),
$$
$$
c_+=\frac1{h(a)},\qquad c_-=\frac1{h(A)},\qquad d_*=c_++c_-.
$$
The finite counterfamily used below is indexed by integers $k\ge3$:
$$
q_k=\overline\Phi(k),\qquad
N_k=\left\lceil\frac{q_k}{\overline\Phi(k^4)}\right\rceil.
$$
Every $N_k$ is a finite integer. The construction is analytic and requires no computation with an array of size $N_k$.

This family is not the balanced two-test antipodal model already excluded on the board. The number of positive copies grows, the actual positive rejection rank is $N-1$, the negative rank is $1$, their tilted masses are $1-1/N$ and $1/N$, and their terminal Mills-field magnitudes are different. The all-null parallel family has only one orientation and does not cover it. The nonpositive-correlation two-null calculation has only two tests and does not cover these unequal multiplicities.

## Checks

### H1

For every finite $k$, $N_k$ and $d=1$ are finite positive integers and each loading has Euclidean norm one. The covariance is the Gram matrix of these loadings, so it is positive semidefinite with unit diagonal, although singular. Every original mean is zero, so the original one-sided true-null set is all $N_k$ indices. No non-Gaussian statistic, modified null label or covariance approximation is used.

### H2

We use the original ordinary BH rule, its largest qualifying rank, all multiplicities and non-strict threshold inequalities. Since $q<1/2$, on $G\ge0$ the negative statistic has p-value at least $1/2$ and cannot be selected. The $N-1$ equal positive p-values qualify at some rank if and only if they qualify at their largest possible rank $N-1$. Similarly, on $G<0$ no positive copy can be selected and the only possible rejection rank is $1$. Consequently the exact actual rejection counts are
$$
R(G)=
\begin{cases}
N-1,&G\ge a,\\
1,&G\le-A,\\
0,&-A<G<a.
\end{cases}
$$
Both endpoint equalities are included. This is an actual BH partition, not a freely chosen rank or threshold.

### H3

All hypotheses are null, so $f=\mathbf1_{\{G\ge a\}\cup\{G\le-A\}}$. Therefore
$$
F=\overline\Phi(a)+\overline\Phi(A)=q(1-p)+qp=q>0,
\qquad D=\log(1/q).
$$
The terminal tilt $Q$ is the standard normal conditioned on these two tails, and its negative-tail mass is exactly $p$. Its full path tilt is exactly the Wiener measure weighted by $f(W_1)/q$, as in the target definition.

### H4

The actual terminal field is $b(G)=c_+$ on the positive tail and $b(G)=-c_-$ on the negative tail. Write $s=\sqrt{1-t}$ and, for $t<1$, put
$$
L_+(t,z)=\overline\Phi\!\left(\frac{a-z}{s}\right),\qquad
L_-(t,z)=\overline\Phi\!\left(\frac{A+z}{s}\right),\qquad
\pi(t,z)=\frac{L_-(t,z)}{L_+(t,z)+L_-(t,z)}.
$$
Then $\pi_t=\pi(t,W_t)$ is the conditional probability of the negative terminal branch under the actual path tilt. The full heat-posterior Mills field, with the conventions in the statement, is precisely
$$
a_t=c_+-d_*\pi_t.
$$
No component or interface has been dropped.

For completeness all cutoff integrals are finite. On every time interval $[0,\tau]$, $\tau<1$, the strictly positive density martingale $(L_++L_-)/q$ gives, by the local change of measure, a Brownian innovation with drift $\partial_z\log(L_++L_-)$. The bounded conditional martingale $a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t]$ has stochastic differential $da_t=K_t\,d\widetilde W_t$, obtained by Itô's formula for its smooth heat quotient. Localization and the bounded-martingale Itô isometry give
$$
\mathbb E_{\mathbb Q}\int_0^\tau K_t^2dt
=\mathbb E_{\mathbb Q}a_\tau^2-a_0^2\le c_+^2\le H^{-2}.
$$
Here $A\ge a\ge U$, $h$ is increasing, and hence $0<c_-\le c_+\le H^{-1}$. Monotone convergence followed by Cauchy--Schwarz yields
$$
\mathbb E_{\mathbb Q}\int_0^1|K_t|dt\le H^{-1}<\infty.
$$
Also $0\le x\le H^2c_+^2<1$, since $a>U$ for finite $N$. Thus the signed trace $M$ exists absolutely and the deficit $1-x$ is strictly positive. Entropy finiteness was already computed exactly in H3.

### H5

The parameters may vary with $q$, exactly as the target permits. The displayed $q_k$ tend to zero and lie in $(0,\overline\Phi(3)]$. For any proposed universal positive $q_0$, all sufficiently large $k$ have $q_k\le q_0$. The construction retains the original means and actual singular covariance at every finite $k$; there is no replacement of a finite model by a population limit.

### NOT

We show that the target's normalized positive trace is unbounded. All estimates below are finite-model inequalities.

#### 1. A uniform upper bound for the coherence deficit

The exact martingale relation $\mathbb E_{\mathbb Q}\pi_t=p$ gives
$$
x=H^2\left(c_+^2-2c_+d_*p
   +d_*^2\int_0^1\mathbb E_{\mathbb Q}\pi_t^2dt\right).
$$
Moreover,
$$
Hc_+=\frac{h(U)}{h(a)}
=(1-p)\exp\!\left(\frac{a^2-U^2}{2}\right)\ge1-p.
$$
Using $Hc_+\le1$ and $Hd_*\le2$, and dropping the nonnegative last term in $x$, gives the exact upper bound
$$
0<1-x\le 1-H^2c_+^2+2H^2c_+d_*p
\le2p+4p=6p.
$$
The same identity also gives $c_+\ge(1-p)/H\ge1/(2H)$.

#### 2. The complete trace is nonnegative

Let $\beta_\pm=\partial_z\log L_\pm$ denote the two component drifts, not the full marginal drift. Conditional terminal means on the two branches are separated by at least $A+a$. Therefore, for every $t<1,z$,
$$
\beta_+(t,z)-\beta_-(t,z)
=\frac{\mathbb E[W_1\mid W_t=z,W_1\ge a]
       -\mathbb E[W_1\mid W_t=z,W_1\le-A]}{1-t}
\ge\frac{A+a}{1-t}\ge A.
$$
Differentiating the actual posterior quotient yields
$$
K_t=d_*\pi_t(1-\pi_t)(\beta_+-\beta_-)(t,W_t)\ge0.
$$
Thus $M_+=M$, and a lower bound from an initial time interval is a lower bound for the full signed trace.

#### 3. The rare branch remains posterior-uncertain over a fixed time interval

Assume the explicit finite inequalities
$$
A\ge\max\{12,6\overline\Phi^{-1}(q/2)\}.
$$
Since $a\le\overline\Phi^{-1}(q/2)$, this implies $a\le A/6$. Let $\mathbb Q_-$ denote the actual path measure conditional on $W_1\le-A$. Given its endpoint $G=W_1$, its path is the original Brownian bridge; in particular
$$
W_t=tG+\sqrt{t(1-t)}Z,
$$
with a standard normal bridge marginal $Z$ independent of the endpoint at that time.

For $0\le t\le1/8$, split off endpoints $G<-2A$. Their conditional probability is
$$
\frac{\overline\Phi(2A)}{\overline\Phi(A)}\le e^{-3A^2/2}.
$$
On $-2A\le G\le-A$, the bridge mean is at least $-A/4$ and its standard deviation is at most $1/2$. Hence
$$
\mathbb Q_-(W_t<-A/3)
\le e^{-3A^2/2}+\overline\Phi(A/6)
\le e^{-3A^2/2}+\tfrac12e^{-A^2/72}.
$$
The last two Gaussian-tail comparisons follow by integrating $h(y)\ge y$; the second starts at $\overline\Phi(0)=1/2$.

For $z\ge-A/3$, $L_-$ decreases and $L_+$ increases with $z$, so
$$
\pi(t,z)\le\frac{L_-(t,z)}{L_+(t,z)}
\le\frac{\overline\Phi(2A/(3s))}{\overline\Phi(A/(2s))}
\le e^{-7A^2/(72s^2)}\le e^{-7A^2/72}.
$$
Here $a\le A/6$ was used in the denominator, and again the tail ratio follows by integrating $h(y)\ge y$. Combining the two regions gives, uniformly on $0\le t\le1/8$,
$$
\mathbb E_{\mathbb Q_-}\pi_t
\le e^{-3A^2/2}+\tfrac12e^{-A^2/72}+e^{-7A^2/72}<\tfrac12.
$$
The strict last inequality already holds at $A=12$, and each term decreases thereafter. Finally the posterior identity
$$
\mathbb E_{\mathbb Q}\pi_t^2
=\mathbb E_{\mathbb Q}[\mathbf1_{\{W_1\le-A\}}\pi_t]
=p\mathbb E_{\mathbb Q_-}\pi_t
$$
implies
$$
\mathbb E_{\mathbb Q}[\pi_t(1-\pi_t)]\ge p/2
\qquad(0\le t\le1/8).
$$

#### 4. The finite trace-to-deficit ratio diverges

Using the full nonnegative trace, the preceding finite bounds give
$$
M=q\mathbb E_{\mathbb Q}\int_0^1 K_tdt
\ge qd_*A\int_0^{1/8}\mathbb E_{\mathbb Q}[\pi_t(1-\pi_t)]dt
\ge\frac{qpA}{32H}.
$$
Consequently
$$
\frac{M_+}{q\sqrt{1+D}(1-x)}
\ge\frac{A}{192H\sqrt{1+\log(1/q)}}.
$$
At any fixed allowed $q$, the right side diverges as $N\to\infty$ while every individual model remains finite. To invalidate any proposed universal small-level interval explicitly, use the family in Object. Then $U=k$ and $A\ge k^4$. Integrating $h(y)\ge y$ gives
$$
\overline\Phi^{-1}(q_k/2)\le k+\frac{\log2}{k},
$$
so $A\ge\max\{12,6\overline\Phi^{-1}(q_k/2)\}$ for all $k\ge3$. Elementary Mills bounds give
$$
H\le k+1/k,\qquad
D=\log(1/q_k)\le\frac{k^2}{2}+
\log\!\left(\sqrt{2\pi}(k+1/k)\right)\le k^2
\quad(k\ge3).
$$
For the last inequality the difference is positive at $k=3$ and increasing. Thus $H\sqrt{1+D}\le2k^2$, and
$$
\frac{M_+}{q_k\sqrt{1+D}(1-x)}\ge\frac{k^2}{384}\longrightarrow\infty.
$$
For any proposed finite $C$ and any $q_0>0$, choose a sufficiently large finite $k$ so that $q_k\le q_0$ and $k^2/384>C$. This finite original Gaussian model satisfies every hypothesis and violates the claimed trace budget.

## Scope of the counterexample

This is a candidate counterexample to the auxiliary entropy-coherence trace lemma only. Its original ordinary BH FDR is exactly $q$ for every member of the family. It therefore does not refute either unrestricted $O(q\sqrt{\log(1/q)})$ main target. The imbalance between the two genuine rejection ranks creates an unbounded auxiliary trace-to-deficit ratio even though their FDP is identically one on the rejection event. The candidate requires fresh independent verification before any confirmed verdict or downstream use.
