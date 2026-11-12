---
type: candidate
title: >-
  Opposing null directions with a conservative-null rank jump retain a cutoff
  deficit
status: failed
target_asset: gaussian_bh_mixed_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 5
slot: 3
direction: drop_hypothesis
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:31:02.996Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$ put
$$
U=\overline\Phi^{-1}(q),\quad A=\overline\Phi^{-1}(q/3),\quad L=\overline\Phi^{-1}(2q/3),\quad H=h(U).
$$
Choose any finite $c>A-L$, and take $N=3$, $d=1$, $v=(1,1,-1)$ and $\theta=(0,-c,0)$. Write
$$
T=L+c>A,\qquad b_1=1/h(A),\qquad b_2=1/h(L),\qquad \Delta=b_2-b_1>0.
$$
The actual rank changes from one to two inside the positive rejection tail. This changes the obstruction from the previously checked exact antipodal pair: its two constant, opposite marks are replaced by three marks, including an additional positive-tail rank jump. The common-true-null-direction obstruction does not apply because the third null direction is opposite to the first two. Both $c$ and its distance from $A-L$ may depend arbitrarily on $q$.

## Checks

### H1

The dimensions $N=3,d=1$ are positive finite integers, and the means $(0,-c,0)$ are finite real numbers.

### H2

All three vectors have unit norm. Their Gram matrix is positive semidefinite, has unit diagonal, and has rank one. The exactly jointly Gaussian observations are $(G,G-c,-G)$.

### H3

The displayed level satisfies $0<q\le\overline\Phi(3)$, and $A>L>U\ge3$.

### H4

All three indices are true nulls. Rank three never qualifies: the first and third statistics cannot both exceed the positive cutoff $U$. Rank two qualifies exactly when $G\ge L+c=T$: the two positive-direction statistics must both exceed $L$, whereas a pair containing the opposite directions cannot do so. Thus the ordinary largest-rank rule gives
$$
R(z)=\begin{cases}
1,&z\le-A,\\
1,&A\le z<T,\\
2,&z\ge T,\\
0,&-A<z<A.
\end{cases}
$$
At the finitely many endpoints the non-strict rule is used. Consequently
$$
f(z)=\mathbf1_{\{|z|\ge A\}},\qquad F=2q/3>0,
$$
$$
B(z)=\begin{cases}
-b_1,&z\le-A,\\
b_1,&A\le z<T,\\
b_2,&z\ge T,\\
0,&-A<z<A.
\end{cases}
$$
In particular the actual two-rejection block has the mark $2/(2h(L))=b_2$; it is not counted as a single rejection.

### H5

Use precisely the prescribed tilt. Since $f$ is an indicator,
$$
D=\log(1/F)=\log(3/(2q)).
$$
For $s=1-t>0$, define
$$
p=\overline\Phi((A-z)/\sqrt{s}),\quad m=\overline\Phi((A+z)/\sqrt{s}),\quad j=\overline\Phi((T-z)/\sqrt{s}).
$$
The prescribed heat fields are explicitly
$$
\mathcal H=p+m,\qquad a(t,z)=\frac{b_1(p-m)+\Delta j}{p+m}.
$$
The terminal mark $b=B/f$ on FDP support lies in $[-b_1,b_2]$, so $|a|\le b_2$. The conditional-expectation identity
$$
a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t]
$$
follows directly by dividing the two heat convolutions. In particular $0\le x\le H^2b_2^2<1$.

Here are independent integrability and endpoint checks before using an endpoint representation to bound the trace. The density martingale is $\mathcal H(t,W_t)/F\in[0,1/F]$. It converges to $f(W_1)/F$ and its entropy converges to $D$, since $r\log r$ is bounded on this interval. Applying Itô's formula to its entropy, first at stopping times bounded away from zero density and $t=1$, and then taking limits, gives
$$
\mathbb E_{\mathbb Q}\int_0^1\beta_t^2dt=2D<\infty.
$$
Equivalently the finite-entropy change of measure gives a Brownian innovation
$$
Z_t=W_t-\int_0^t\beta_rdr
$$
under $\mathbb Q$, extending to $t=1$. Applying the quotient rule to the smooth heat fields gives $da_t=K_t\,dZ_t$. Bounded martingale convergence and Itô isometry then imply
$$
\mathbb E_{\mathbb Q}\int_0^1K_t^2dt
=\mathbb E_Q b^2-a_0^2\le b_2^2.
$$
Therefore
$$
\mathbb E_{\mathbb Q}\int_0^1|K_t|dt\le b_2,\qquad
\mathbb E_{\mathbb Q}\int_0^1|a_t\beta_t|dt\le b_2\sqrt{2D}.
$$
The endpoint integral is finite, and direct integration yields
$$
\int zB(z)\,d\gamma_1(z)=2b_1\phi(A)+\Delta\phi(T)=2q/3+\Delta\phi(T).
$$
For each $\tau<1$, covariance of the square-integrable martingales $a$ and $Z$ gives
$$
M_\tau=F\mathbb E_{\mathbb Q}[a_\tau Z_\tau].
$$
Their $L^2$ convergence and the preceding absolute trace bound give
$$
M=F\mathbb E_{\mathbb Q}[b(W_1)Z_1].
$$
Finally $W_1=Z_1+\int_0^1\beta_tdt$, and bounded $b$ together with finite drift energy justifies Fubini and conditional expectation:
$$
F\mathbb E_{\mathbb Q}\!\left[b(W_1)\int_0^1\beta_tdt\right]
=F\mathbb E_{\mathbb Q}\int_0^1a_t\beta_tdt.
$$
Combining these identities proves exactly the specified $M_*=M$ identity, rather than assuming it.

This candidate does have positive trace. Under the conditional terminal tilted law at $(t,z)$,
$$
K(t,z)=s^{-1}\operatorname{Cov}(b(Y),Y).
$$
The terminal mark is strictly ordered between the negative tail and the positive tail and nondecreasing within its support, so this covariance is positive. Thus $M>0$; a negative-trace obstruction is not being reused.

### NOT

Fail: a uniform square-root estimate holds for the whole displayed family. The innovation identity and $\mathbb E_{\mathbb Q}Z_1^2=1$ give
$$
M_+\le F\sqrt{\mathbb E_Q b^2}\le\frac{2q}{3h(L)}.
$$
To quantify the rank-cutoff deficit without an asymptotic limit, put $c_* =e^{-19/18}/2>0$. For every $u\ge3$, the inverse Mills ratio has
$$
h'(u)=h(u)(h(u)-u)\ge c_*.
$$
Indeed, writing $h(u)-u$ as the mean of $s\ge0$ with density proportional to $e^{-us-s^2/2}$, its numerator is at least $e^{-19/18}\int_0^{1/u}s\,ds$, while its denominator is at most $1/u$; also $h(u)\ge u$. Integrating this derivative bound and the logarithmic tail derivative gives
$$
h(L)-H\ge c_*(L-U),\qquad
\log(3/2)=\int_U^Lh(r)dr\le h(L)(L-U).
$$
Hence
$$
1-x\ge1-\frac{H^2}{h(L)^2}
\ge\frac{h(L)-H}{h(L)}
\ge\frac{c_*\log(3/2)}{h(L)^2}.
$$
Consequently the single finite constant $C_* =2/(3\sqrt{c_*\log(3/2)})$ satisfies
$$
M_+\le C_*q\sqrt{1-x}
\le C_*q\{\sqrt{1-x}+\sqrt{1+D}(1-x)\}.
$$
This is uniform over the whole level range and every allowed $c$, including a collapsing rank-one band or an arbitrarily conservative second null. It does not assert the unrestricted target beyond this rank-one three-null family.

## Failure

NOT fails: the positive trace from opposite null directions and an internal actual-rank jump is absorbed by the uniform gap between the largest achievable rank two and the reference rank three.
