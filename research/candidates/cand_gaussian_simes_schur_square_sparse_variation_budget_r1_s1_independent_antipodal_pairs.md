---
type: candidate
title: 'Many independent antipodal pairs (block signed rank-one, entries in {0,-1,1})'
status: failed
target_asset: gaussian_simes_schur_square_sparse_variation_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 86f7bdd265309432fe20f975ae839c30202be6cc9ff8b792c372f7c4362c61e9
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T00:43:09.753Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$q\in(0,1/100]$, $N=2M$, $\Sigma=I_M\otimes\begin{pmatrix}1&-1\\-1&1\end{pmatrix}$: $M$ independent exact antipodal pairs $(T_{2b-1},T_{2b})=(Z_b,-Z_b)$. This is the degenerate boundary of $\mathcal C_N$ (rank $M$, entries in $\{0,\pm1\}$) with the maximal number $2M$ of distinct directions among such matrices. Then $\Sigma\circ\Sigma=I_M\otimes J_2$ and $R_t^\Sigma=I_M\otimes\begin{pmatrix}1&r\\r&1\end{pmatrix}$, $r=2t-1$: independent pairs $(X_b,Y_b)$, each with correlation $r$.

## Checks

### H1

$q$ free and small.

### H2

$N=2M\ge2$.

### H3

Block diagonal of PSD rank-one blocks $ss^{\mathsf T}$, $s=(1,-1)$, unit diagonal.

### NOT

Let $K$, $x_k=\overline\Phi^{-1}(qk/N)$ be as in the statement's sparse ranks ($K\ge1$, else $f\equiv0$). Give block $b$ its own correlation $r_b$; $f$ is smooth in $(r_1,\dots,r_M)\in(-1,1)^M$, continuous up to the boundary, and along the diagonal $f'(r)=\sum_b\partial_{r_b}f$. Fix $b$ and the rest; with $R_k=\sum_{b'\ne b}c_{b'}(x_k)$, $c_{b'}(x)=1\{X_{b'}\ge x\}+1\{Y_{b'}\ge x\}$, set $d_k=k-R_k$. If some $d_k\le0$ the event is certain and $\partial_{r_b}$ vanishes. Otherwise the conditional event in $(X_b,Y_b)$ is $U=\{\max\ge a\}\cup\{\min\ge c\}$ with $a=x_{k_1}$, $k_1=\max\{k:d_k=1\}$, $c=x_{k_2}$, $k_2=\max\{k:d_k=2\}$ (a missing term is dropped). Writing $1_U=1\{X\ge a\}+1\{Y\ge a\}-1\{X\ge a,Y\ge a\}+1_{[c,a)^2}$ and using Plackett,
$$
\partial_{r_b}P(U)=\varphi_2(c,c;r_b)-2\varphi_2(a,c;r_b)\quad(c<a),\qquad -\varphi_2(a,a;r_b)\ \text{or}\ \varphi_2(c,c;r_b)\ \text{otherwise}.
$$
Here $a,c\in\{x_j:j\le k^*\}$ with $k^*=\max(k_1,k_2)$, and block $b$ matters only if $R_{k^*}\ge k^*-2$. Bounding $|\partial_{r_b}P(U)|\le3\sum_{j,l\le k}\varphi_2(x_j,x_l;r)$ on $\{k^*=k\}\subset\{R_k\ge k-2\}$, and $P_r(R_k\ge k-2)\le C_k$ uniformly in $r$ (below), we get
$$
\mathcal V_-(f)\le\int_{-1}^1|f'(r)|dr\le 3M\sum_{k\le K}C_k\sum_{j,l\le k}\int_{-1}^1\varphi_2(x_j,x_l;r)dr\le3M\sum_kC_k\sum_{j,l\le k}\frac{q\min(j,l)}{N}\le\frac{3q}{2}\sum_k k^3C_k .
$$
Uniform tail: the $c_{b'}(x_k)/2\in[0,1]$ are independent with total mean at most $qk/2$ for every $r$ (each $X_{b'},Y_{b'}$ is $N(0,1)$), so Chernoff gives $C_1=C_2=1$ and $C_k=(eqk/(k-2))^{(k-2)/2}$ for $k\ge3$. For $q=1/100$: $\sum_kk^3C_k\le1+8+27(0.0816)^{1/2}+64(0.0544)+125(0.0453)^{3/2}+\cdots\approx22$, so $\mathcal V_-(f)\le0.33$; and the bound is $O(q)$ as $q\to0$. The conclusion holds for every $M$.

## Failure

NOT fails: each block is pivotal only when the rest already has $R_k\ge k-2$, a Poisson-type tail of mean $\le qk$ uniform in $r$, so the Plackett corner terms total $O(q)$ and $\mathcal V_-\to0$ as $q\to0$, uniformly in $M$.
