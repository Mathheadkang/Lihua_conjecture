---
type: candidate
title: Dilute diverging alternatives with a fixed second moment
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:53:03.140Z'
extension_version: 0.0.4
---

## Object

Fix any $0<\sigma<1$, $0<q\le S(1)$, and $\eta,\delta>0$. For each integer $k\ge2$, draw iid $B_i\sim\operatorname{Bernoulli}(k^{-2})$ and set
$$
\theta_i=kB_i,\qquad \ell_i=1-B_i,\qquad C_{ij}=1\quad(i,j\ge1).
$$
Let $P_k$ be the resulting parameter law. The proposed extremal defect is that a vanishing fraction of diverging alternatives retains unit second moment while disappearing from every finite subarray, potentially disrupting moment compactness, FDR continuity, or penalized attainment. Unlike the board's zero-mean all-copy and zero-tag examples, this family has heterogeneous strictly positive alternative means escaping to infinity and a nonvanishing moment loss in its limit; it tests that additional mechanism.

Use independent standard normals $X,Z$, independent of every $B_i$, and write
$$
Y=\sqrt{1-\sigma^2}X+\sigma Z,\qquad T_i=kB_i+Y.
$$
The finite-subarray limit $P_\infty$ has $\theta_i=0$, $\ell_i=1$, and $C_{ij}=1$ for every pair.

## Checks

### H1

Pass. The chosen common loading lies in $(0,1)$, the testing level lies in $(0,1/2)$ and in the normalized objective's allowed level interval, and both penalties are strictly positive.

### H2

Pass. When $B_i=0$, $(\theta_i,\ell_i)=(0,1)$; when $B_i=1$, $(\theta_i,\ell_i)=(k,0)$. These are lawful, canonical marks. The limiting marks $(0,1)$ are also lawful and canonical.

### H3

Pass. The residual matrix is symmetric, unit diagonal, and has entries in $[-1,1]$. Every finite principal matrix is positive semidefinite because
$$
x^{\mathsf T}C_{1:n,1:n}x=\left(\sum_{i=1}^nx_i\right)^2\ge0.
$$
The displayed score representation therefore has exactly the required conditional covariance.

### H4

Pass. Iid marks and the constant covariance array give joint exchangeability. The parameter randomness is independent of $X,Z$. For each fixed $m$, the probability that any of the first $m$ marks is alternative is at most $m/k^2$, proving $P_k\to P_\infty$ in finite-subarray weak convergence.

### H5

Pass. The sequence lies in the unit moment sublevel:
$$
M_2(P_k)=k^2\mathbb P(B_1=1)=1,
\qquad M_2(P_\infty)=0.
$$
Thus each proposed competitor belongs to $\mathfrak P_2$.

### NOT

Fail. The exact finite FDR is continuous along this sequence, and the moment drop favors attainment rather than obstructing it. To compute it, let $K=\sum_{i=1}^n B_i$. All true scores equal $Y$ and all alternative scores equal $Y+k$. If $S(Y)\le q$, terminal rank $n$ qualifies, so every coordinate is rejected and the FDP is $1-K/n$. If $S(Y)>q$, no true coordinate can be rejected: its p-value exceeds every BH threshold $qr/n\le q$. Consequently, including $K=0,n$,
$$
D_n=(1-K/n)\mathbf1_{\{S(Y)\le q\}}.
$$
Since $Y\sim N(0,1)$ and is independent of $K$,
$$
\mathcal F_n(P_k;q,\sigma)=q(1-k^{-2})
\quad\text{for every }n\ge1.
$$
Hence the limit functional exists explicitly on these laws and
$$
\mathcal F(P_k;q,\sigma)=q(1-k^{-2})\longrightarrow q
=\mathcal F(P_\infty;q,\sigma).
$$
The proposed escaping family itself has a lawful limit within its moment sublevel, and its moments satisfy the asserted lower semicontinuity inequality $0\le\liminf_k1$. No global compactness theorem is inferred from this example.

For the fixed-level penalized functional, the values are $q(1-k^{-2})-\eta$, whereas the lawful limit has value $q$. For the normalized functional, put $U=S^{-1}(q)$; then
$$
\mathcal L_{\eta,\delta}(P_k,q;\sigma)
=\frac{1-k^{-2}}{U}-\eta-\delta\log(1/q),
$$
while
$$
\mathcal L_{\eta,\delta}(P_\infty,q;\sigma)
=\frac1U-\delta\log(1/q).
$$
The limit therefore improves the limiting penalized value by $\eta$. This family supplies no counterexample to the target.

## Failure

NOT fails: dilute diverging alternatives preserve exact FDR continuity, and loss of their unit moment at the lawful limit strictly improves each positively penalized objective.
