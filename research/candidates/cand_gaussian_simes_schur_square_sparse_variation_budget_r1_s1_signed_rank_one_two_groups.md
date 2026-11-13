---
type: candidate
title: Signed rank-one correlation with two antipodal clone groups
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

$q\in(0,1/4]$, $N=a+b$ with $a,b\ge1$, $s=(\mathbf 1_a,-\mathbf 1_b)\in\{\pm1\}^N$ and $\Sigma=ss^{\mathsf T}$ (rank one, singular for $N\ge2$; the most degenerate sign pattern, entries $\pm1$ only). Then $\Sigma\circ\Sigma=J_N$, and $R_t^\Sigma$ has within-group entries $1$ and cross-group entries $r=2t-1\in[-1,1]$. So under $R_t^\Sigma$ the first $a$ statistics equal one $X$, the last $b$ equal one $Y$, with $(X,Y)$ standard bivariate normal with correlation $r$.

## Checks

### H1

$q$ free in $(0,1/4]$.

### H2

$N=a+b\ge2$.

### H3

$ss^{\mathsf T}$ is PSD, symmetric, with diagonal $s_i^2=1$.

### NOT

Let $K=\max\{k:qk/N<\overline\Phi(u_q+1)\}$; if $K=0$ then $S_q=\emptyset$ and $\mathcal V_-=0$, so assume $K\ge1$ (then $K<N$). Put $x_m=\overline\Phi^{-1}(qm/N)$. The count at threshold $\tau$ takes values in $\{0,a,b,N\}$, and count $\ge k$ with value $a$ is best used with $k=\min(a,K)$. Therefore
$$
\{T\in S_q\}=A\cup B\cup C,\quad A=\{X\ge\alpha\},\ B=\{Y\ge\beta\},\ C=\{X\ge\gamma,\ Y\ge\gamma\},
$$
with $\alpha=x_{\min(a,K)}$, $\beta=x_{\min(b,K)}$, $\gamma=x_K\le\alpha,\beta$. Write $1_{A\cup B\cup C}=1_A+1_B-1_{A\cap B}+1_{[\gamma,\alpha)\times[\gamma,\beta)}$. By Plackett's identity $\partial_rP_r(X\ge x,Y\ge y)=\varphi_2(x,y;r)$, for $r\in(-1,1)$,
$$
\frac{d}{dr}P_r(A\cup B\cup C)=-\varphi_2(\alpha,\beta)+\bigl[\varphi_2(\gamma,\gamma)-\varphi_2(\gamma,\beta)-\varphi_2(\alpha,\gamma)+\varphi_2(\alpha,\beta)\bigr]=\varphi_2(\gamma,\gamma)-\varphi_2(\gamma,\beta)-\varphi_2(\alpha,\gamma).
$$
The function is continuous on $[-1,1]$ (the boundary is in coordinate lines of probability zero) and $C^1$ inside, so its downward variation is at most $\int_{-1}^1|d/dr|\,dr$, and $\int_{-1}^1\varphi_2(x,y;r)dr=P_1(X\ge x,Y\ge y)-P_{-1}(X\ge x,Y\ge y)\le\overline\Phi(\max(x,y))\le\overline\Phi(\gamma)$. The reparametrization $r=2t-1$ is increasing, so
$$
\mathcal V_-(f_{q,\Sigma})\le3\,\overline\Phi(\gamma)=\frac{3qK}{N}<3\,\overline\Phi(u_q+1)<3q .
$$
For $q\le1/4$ this is below $3\overline\Phi(1.67)\approx0.14$, and it tends to $0$ with $q$. The conclusion holds with room.

## Failure

NOT fails: with two clone directions the Plackett corner terms integrate to at most $3qK/N<3q$, so $\mathcal V_-\to0$ as $q\to0$.
