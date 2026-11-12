---
type: example
title: >-
  Counterexample to gaussian_bh_one_sided_translated_cell_mehler_congestion:
  Vanishing common loading yields a divergent fine-scale Mehler average
status: approved
source:
  kind: original
refutes: gaussian_bh_one_sided_translated_cell_mehler_congestion
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_ornstein_uhlenbeck_semigroup
tags: []
---

## Statement

For every sufficiently large integer $L$, set
$$
q=e^{-L},\quad \eta=L^{-1},\quad m=\lceil e^{L^3/10}\rceil,
\quad N=2m,\quad d=m+1,\quad M=N/q,
\quad u_r=S^{-1}(r/M)\quad(1\le r\le N).
$$
In the orthonormal basis $e_0,e_1,\ldots,e_m$, set, for $1\le i,j\le m$,
$$
\theta_i=0,\quad a_i=\eta e_0+\sqrt{1-\eta^2}\,e_i,
\qquad \theta_{m+j}=(1+\eta)u_j,\quad a_{m+j}=-e_0.
$$
Use precisely the physical BH procedure and its one-coordinate-zero forced ranks from the target. Let $H_q$ be the target's full translated density. Put
$$
v=1-e^{-2/L},\qquad Y=\sqrt v\,G,\quad G\sim N_d(0,I_d).
$$
The counterexample is the sequence of these finite models, evaluated at the Mehler center $x=0$. We prove, with a fixed numerical constant $c>0$ independent of $L$,
$$
\mathbb E H_q(Y)\ge c q L^{3/2}
$$
for every sufficiently large integer $L$. In particular its ratio to $q\sqrt{\log(1/q)}$ tends to infinity. The conclusion violated is part (b), not part (a) or an original BH FDR bound.

## Assumptions

### H1

The dimensions $N,d$ are positive finite integers for each $L$. The level $q=e^{-L}$ lies in $(0,S(1)]$ for every sufficiently large $L$, and tends to zero. Consequently the sequence eventually lies below every fixed positive proposed $q_0$. No uniform bound on dimensions is a hypothesis.

### H2

All directions are deterministic and have Euclidean norm one. With $Z\sim N_d(0,I_d)$ the scores are exactly jointly Gaussian with covariance $\langle a_i,a_j\rangle$, a positive semidefinite unit-diagonal Gram matrix. Thus there is no approximation to joint Gaussianity or to the permitted covariance class.

### H3

All means are finite deterministic real numbers. For $j\le m$, $qj/N\le q/2<S(1)$ eventually, so $u_j>1$ and $\theta_{m+j}>0$. Therefore the null set specified by the target is exactly $I_0=\{1,\ldots,m\}$. Every one of these $m$ physical nulls is retained in the calculations below.

### H4

The p-values are $S(T_j)$ and BH uses the largest qualifying physical rank, with the target's non-strict comparisons. For a forced null $i$, at any source point $z$, write $A_l(z)$ and $B_l(z)$ for the numbers of alternative scores and of other null scores at least $u_l$, respectively. Its rank $l$ qualifies exactly when
$$
1+A_l(z)+B_l(z)\ge l.
$$
The first term is the single p-value forced to zero. This criterion counts all physical multiplicities and applies also to ranks later than any proposed rank $k$; none are discarded.

### H5

Since $\theta_i=0$ for nulls, the target translation for rank $k$ is exactly $z=Y+u_k a_i$. At this source point, the common coordinate is $z_0=Y_0+\eta u_k$. The alternative scores and all other null scores are, exactly,
$$
T_{m+j}(z)=(1+\eta)u_j-Y_0-\eta u_k,
$$
$$
T_j(z)=\eta Y_0+\eta^2u_k+\sqrt{1-\eta^2}\,Y_j
\qquad(j\le m,\ j\ne i).
$$
The translated half-space is $\langle a_i,Y\rangle\ge0$ and the exponential factor is
$\exp(-u_k\langle a_i,Y\rangle-u_k^2/2)$. These are the source coordinates and weights used below; there is no replacement by independently optimized cells.

### H6

Here $\log(1/q)=L$, so the stipulated time is exactly $\tau_q=1/L$ and its variance exactly $v=1-e^{-2/L}$. At $x=0$ the target Mehler law is the independent-coordinate Gaussian vector $Y$ just defined. We will use $v\sim2/L$ and $v\le2/L$, both following directly from this formula.

## Calculation

We first prove exact full forced ranks on positive-measure events, and then bound their contributions. Every estimate below holds uniformly over the displayed selected indices, for all sufficiently large integers $L$. The lower bound on $L$ is an absolute constant; it does not depend on any proposed constants in part (b).

**Selected integer ranks and their gaps.** Put
$$
B=L^{3/2}/3,\qquad a=\lceil M S(B)\rceil,
\qquad b=\lfloor M S(L)\rfloor,\qquad K=\{a,a+1,\ldots,b\}.
$$
Mills bounds give
$$
\log M=L^3/10+L+O(1),\qquad
\log(M S(B))=\frac{2}{45}L^3+L-O(\log L),
$$
$$
\log(M S(L))=L^3/10-L^2/2+L-O(\log L).
$$
Thus $2\le a\le b\le m-1$ eventually, and $L\le u_k\le B$ for every $k\in K$. The integer rounding causes no loss at the upper endpoint: since
$$
M[S(B-1)-S(B)]\ge M\phi(B)\longrightarrow\infty,
$$
we have $u_a\ge B-1$ eventually. Also $b+1>M S(L)$, so $u_{b+1}<L$. With $\Delta_k=u_k-u_{k+1}>0$,
$$
\sum_{k\in K}\Delta_k=u_a-u_{b+1}\ge B-L-1\ge B/2.
$$
The real interpolation $u(t)=S^{-1}(t/M)$ has
$$
u'(t)=-\frac1{M\phi(u(t))},\qquad
u''(t)=\frac{u(t)}{M^2\phi(u(t))^2}>0
$$
through the ranks in use. Hence the gaps decrease with the rank. Moreover for $k\in K$,
$$
\Delta_k\le D_L:=\frac1{M\phi(B)},\qquad
\log D_L=-\frac{2}{45}L^3-L+O(1).
$$
Define positive intervals
$$
J_k=((1+\eta/4)\Delta_k,(1+\eta/2)\Delta_k).
$$
They have length $\eta\Delta_k/4$. In particular $Y_0\in J_k$ implies $0<Y_0\le2D_L\le1$, $Y_0\le\sqrt v$, and $\eta B Y_0\le1$ eventually.

**A single event excludes the other nulls at every necessary rank.** For a fixed forced index $i$, let
$$
W_j=\sqrt{1-\eta^2}\,Y_j\quad(j\ne i),\qquad
s^2=v(1-\eta^2)\le2/L,\qquad
\beta_L=L^{-1}+(3\sqrt L)^{-1}.
$$
The $W_j$ are independent $N(0,s^2)$. On $Y_0\in J_k$, $k\in K$, the source common shift is bounded uniformly by
$$
\eta Y_0+\eta^2u_k\le\beta_L.
$$
Define $E_i$ using only the private coordinates $\{Y_j:j\ne i,\ 1\le j\le m\}$, by requiring both
$$
\max_{j\ne i}W_j<0.8L-\beta_L
$$
and, for every physical grid rank $l$ with $u_l<0.8L$,
$$
\#\{j\ne i:W_j\ge u_l-\beta_L\}\le l/4.
$$
We now check that $\mathbb P(E_i)\to1$ uniformly in $i$; in particular this probability is at least $1/2$ eventually. The first failure has probability at most
$$
m\exp\left(-\frac{(0.8L-\beta_L)^2}{2s^2}\right)
\le\exp(-0.05L^3)
$$
eventually, because the leading exponent is $(1/10-0.8^2/4)L^3=-0.06L^3$.

For the second requirement, $u_N=S^{-1}(e^{-L})\ge\sqrt L$ eventually. Uniformly for $t\in[u_N,0.8L]$, $\beta_L/t\to0$, so $(t-\beta_L)^2\ge0.9t^2$ eventually. Writing $p(t)=S((t-\beta_L)/s)$, the Gaussian tail bound and the lower Mills bound $S(t)\ge\phi(t)/(2t)$ give
$$
\frac{q p(t)}{S(t)}
\le 2\sqrt{2\pi}\,t\exp\{-L-(0.225L-1/2)t^2\}
\le e^{-0.1L^2}
$$
eventually. For rank $l$ with $t=u_l$, the count in question is a binomial variable of mean $\mu_l=(m-1)p(u_l)$; since $S(u_l)=ql/N$,
$$
\mu_l/l\le q p(u_l)/S(u_l)\le e^{-0.1L^2}.
$$
The binomial Chernoff bound, valid also for the real cutoff $l/4$, therefore bounds its probability of exceeding $l/4$ by
$$
(4e\mu_l/l)^{l/4}\le e^{-0.02L^2l}.
$$
Every lower-threshold rank satisfies $l>M S(0.8L)=:\ell_L$, where
$$
\log\ell_L=L^3/10-0.32L^2+L-O(\log L).
$$
Union over all at most $N$ grid ranks gives a failure probability at most $N e^{-0.02L^2\ell_L}\to0$. This proves the asserted uniform probability and covers all grid ranks, not only ranks near $k$.

**The full forced rank equals $k$.** Fix $i$, $k\in K$, $Y_0\in J_k$, and private coordinates in $E_i$. For ranks $l$ with $u_l\ge0.8L$, the source scores of all other nulls are strictly below $0.8L$; hence $B_l=0$.

The alternative scores are ordered by their physical index $j$. If only these scores and the forced zero were present, a rank $2\le l\le m+1$ would qualify exactly when
$$
Y_0+\eta u_k\le F_l:=(1+\eta)u_{l-1}-u_l
=\eta u_{l-1}+\Delta_{l-1}.
$$
Both terms on the right decrease with $l$, so $F_l$ decreases. At $l=k$ the inequality holds because
$$
Y_0<(1+\eta/2)\Delta_k\le(1+\eta)\Delta_{k-1}.
$$
At every $l\ge k+1$ up to $m+1$, it fails because
$$
F_l\le F_{k+1}=\eta u_k+\Delta_k<\eta u_k+Y_0.
$$
Ranks beyond $m+1$ cannot qualify without other nulls. Therefore rank $k$ qualifies (even without using any other null), and no later rank at a threshold at least $0.8L$ qualifies.

It remains to exclude every later rank $l$ with $t=u_l<0.8L$. At the source point the alternative count is exactly
$$
A_l=\min\left\{m,\left\lfloor M S\left(\frac{t+Y_0+\eta u_k}{1+\eta}\right)\right\rfloor\right\}.
$$
This floor formula includes equality in BH and all alternative multiplicities. Since $u_k\ge L$ and $t<0.8L$, the argument of $S$ exceeds $t$ by at least
$$
\frac{\eta(u_k-t)}{1+\eta}>\frac{0.2}{1+\eta}\ge0.19
$$
eventually. The Gaussian hazard satisfies $\phi(t)/S(t)\ge t$ for positive $t$, so
$$
A_l\le M S(t)e^{-0.19t}=l e^{-0.19t}\le l/4
$$
eventually, uniformly since $t\ge u_N\to\infty$. The event $E_i$ also gives $B_l\le l/4$. As $l>\ell_L\to\infty$,
$$
1+A_l+B_l\le1+l/2<l.
$$
Thus every later lower-threshold rank fails as well. Combining both ranges proves the exact target mask
$$
R_i(Y+u_k a_i)=k
$$
on $\{Y_0\in J_k\}\cap E_i$. This uses every later physical rank through $N$ and imposes no condition on the private coordinate $Y_i$.

**Integrating the translated density.** Further restrict $0\le Y_i\le1/u_k$. Then
$$
0\le\langle a_i,Y\rangle=\eta Y_0+\sqrt{1-\eta^2}\,Y_i,
\qquad u_k\langle a_i,Y\rangle\le2.
$$
Both intervals $J_k$ and $[0,1/u_k]$ lie within $[0,\sqrt v]$ eventually. Their Gaussian densities are therefore at least $\phi(1)/\sqrt v$. The coordinates $Y_0,Y_i$ are independent of $E_i$, whose probability is at least $1/2$. The individual $(i,k)$ term $h_{ik}$ in the target sum consequently satisfies
$$
\mathbb E h_{ik}(Y)
\ge c_0\frac{\eta\Delta_k}{v}\,
\frac{e^{-u_k^2/2}}{k u_k},
\qquad c_0=e^{-2}\phi(1)^2/8>0.
$$
This lower bound uses the original density including its $1/k$ factor. The upper Mills bound $S(u)\le\phi(u)/u$ yields
$$
\frac{e^{-u_k^2/2}}{u_k}\ge\sqrt{2\pi}S(u_k)
=\sqrt{2\pi}\,\frac{qk}{N}.
$$
All summands are nonnegative, so finite-sum linearity permits summing these separate events over all $m$ physical nulls and all selected $k$; their events need not occur simultaneously. Since $m/N=1/2$, $\sum_K\Delta_k\ge L^{3/2}/6$, $\eta=1/L$, and $v\le2/L$,
$$
\mathbb E H_q(Y)
\ge\frac{c_0\sqrt{2\pi}}2\,q\frac{\eta}{v}\sum_{k\in K}\Delta_k
\ge\frac{c_0\sqrt{2\pi}}{24}\,q L^{3/2}.
$$
Therefore, for every proposed finite $C$ and every proposed positive admissible $q_0$, some sufficiently large integer $L$ has $q=e^{-L}\le q_0$ and
$$
\sup_x T_{1/L}H_q(x)\ge T_{1/L}H_q(0)>Cq\sqrt L.
$$
This is the negation of the universal assertion (b). All objects at each such $L$ are finite. The calculation does not infer failure of part (a), whose mass identity is compatible with a large density average under this narrower Gaussian law.

Promoted from search candidate cand_gaussian_bh_one_sided_translated_cell_mehler_congestion_r2_s3_vanishing_loading.

## Verdict

confirmed — All model hypotheses and physical null labels hold. Independently checking the rounded rank endpoints, uniform Gaussian/binomial events, and every later rank through $N$ gives the exact mask $R_i(Y+u_k a_i)=k$ on the stated events. Independence of $E_i$ from $(Y_0,Y_i)$ and the original $1/k$ weight yield $T_{1/L}H_q(0)\ge[c_0\sqrt{2\pi}/24]qL^{3/2}$, so its ratio to $q\sqrt L$ diverges and refutes precisely part (b).
