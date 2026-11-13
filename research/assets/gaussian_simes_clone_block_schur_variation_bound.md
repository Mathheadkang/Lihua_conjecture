---
type: lemma
title: >-
  Multiplicity-free Schur-square variation bound for clone-block Gaussian Simes
  models
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - simes
  - global_null
  - one_sided
  - schur_square_variation
---

# Multiplicity-free Schur-square variation bound for clone-block Gaussian Simes models

## Statement

For a positive integer $N$ and $R\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), and $q\in(0,1)$, let $Z\sim\mathcal N_N(0,R)$, form the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md) $p_i=\overline\Phi(Z_i)$ with order statistics $p_{(1)}\le\cdots\le p_{(N)}$ (including multiplicities), and put
$$
F_q(R)=\mathbb P_{N,0,R}\Bigl(\exists k\in\{1,\ldots,N\}:p_{(k)}\le\frac{qk}{N}\Bigr).
$$
For $\Sigma\in\mathcal C_N$ let $\Sigma\circ\Sigma$ be the entrywise product and define the Schur-square path and its Simes profile
$$
R_t^\Sigma=(1-t)\Sigma+t(\Sigma\circ\Sigma),\qquad f_{q,\Sigma}(t)=F_q(R_t^\Sigma),\qquad 0\le t\le1.
$$
Every $R_t^\Sigma$ lies in $\mathcal C_N$ by the Schur product theorem. For a real function $f$ on $[0,1]$ define its downward and total variations
$$
\mathcal V_-(f)=\sup\sum_{\ell=1}^m\bigl[f(t_{\ell-1})-f(t_\ell)\bigr]_+,\qquad
\mathcal V(f)=\sup\sum_{\ell=1}^m\bigl|f(t_{\ell-1})-f(t_\ell)\bigr|,
$$
both suprema over all partitions $0=t_0<t_1<\cdots<t_m=1$, with $a_+=\max(a,0)$.

A matrix $\Sigma\in\mathcal C_N$ is a clone-block covariance with at most $K$ blocks if there are a matrix $\Gamma\in\mathcal C_K$ and a map $a:\{1,\ldots,N\}\to\{1,\ldots,K\}$ with $\Sigma_{ij}=\Gamma_{a(i)a(j)}$ for all $i,j$. The block sizes $|a^{-1}(b)|$ are arbitrary (some may be zero), and $\Gamma$ may be singular.

Then for every positive integer $K$, every positive integer $N$, every clone-block covariance $\Sigma\in\mathcal C_N$ with at most $K$ blocks, and every $q\in(0,1/2)$,
$$
\mathcal V_-(f_{q,\Sigma})\le\mathcal V(f_{q,\Sigma})\le K^2\,4^K\,q .
$$
The bound does not depend on $N$, on the block sizes, or on $\Gamma$.

## Motivation

This is the model case of the [Schur-square tensor-lift approach](../ideas/idea_6b48b2fe25e1.md): the variation assertion for finitely many Gaussian directions with arbitrary multiplicities. Since $(\Sigma\circ\Sigma)_{ij}=\Gamma_{a(i)a(j)}^2$, the path stays clone-block with block matrix $R_t^\Gamma$, exact clones stay tied, and only the $K(K-1)/2$ block pairs move. For a block pair with the other blocks frozen, the rejection region in the two block scores is a union of two half-lines and a square, so the three-face identity has corners at one level for the square and one level for each half-line, each level of the form $\overline\Phi^{-1}(q\cdot\text{weight})$ with weight a sum of block masses. The [partial variation calculation](../ideas/idea_a0805e98f90d.md) carries this out for two blocks (bound $2q$) and for three coordinates (bound $16q$); the statement asks for the same argument for every $K$, with the number of attainable corner levels counted per block pair, and with the regularization $(1-\varepsilon)\Gamma+\varepsilon I_K$ of the block matrix, which keeps clones exact.

## Proof

Throughout, $\phi_2(\alpha,\beta;\rho)$ is the density at $(\alpha,\beta)$ and $\overline\Phi_2(\alpha,\beta;\rho)=\mathbb P(U\ge\alpha,V\ge\beta)$ the joint upper tail of a centered bivariate normal $(U,V)$ with unit variances and correlation $\rho\in(-1,1)$.

**Step 1 (reduction to block scores).** Let $B=a(\{1,\ldots,N\})$ be the set of nonempty blocks; relabel it as $\{1,\ldots,K'\}$ with $1\le K'\le K$, put $n_b=|a^{-1}(b)|\ge1$, so $\sum_b n_b=N$, and replace $\Gamma$ by its principal submatrix on $B$. The relation $\Sigma_{ij}=\Gamma_{a(i)a(j)}$ is unchanged, and a principal submatrix of a matrix in $\mathcal C_K$ lies in $\mathcal C_{K'}$. Since $(\Sigma\circ\Sigma)_{ij}=\Gamma_{a(i)a(j)}^2=(\Gamma\circ\Gamma)_{a(i)a(j)}$, we get $(R_t^\Sigma)_{ij}=(R_t^\Gamma)_{a(i)a(j)}$ with $R_t^\Gamma=(1-t)\Gamma+t(\Gamma\circ\Gamma)$, which lies in $\mathcal C_{K'}$ by the Schur product theorem (convex combination of positive semidefinite matrices with unit diagonal). If $Y\sim\mathcal N_{K'}(0,R_t^\Gamma)$, then $X=(Y_{a(1)},\ldots,Y_{a(N)})$ is a linear image of $Y$, hence centered jointly Gaussian with $\operatorname{Cov}(X_i,X_j)=(R_t^\Gamma)_{a(i)a(j)}=(R_t^\Sigma)_{ij}$, i.e. $X\sim\mathcal N_N(0,R_t^\Sigma)$. Since $F_q(R)$ depends only on the law $\mathcal N_N(0,R)$, $f_{q,\Sigma}(t)$ is the probability of the Simes event computed from $p_i=\overline\Phi(Y_{a(i)})$.

If $K'=1$, then $\Gamma=(1)$, all entries of $\Sigma$ equal $1$, $\Sigma\circ\Sigma=\Sigma$, the path is constant and $\mathcal V(f_{q,\Sigma})=0$. Assume $K'\ge2$ from now on.

**Step 2 (orthant form).** For nonempty $S\subseteq\{1,\ldots,K'\}$ put $n(S)=\sum_{b\in S}n_b\in\{1,\ldots,N\}$ and $l_S=\overline\Phi^{-1}(q\,n(S)/N)$, well defined since $q\,n(S)/N\in(0,1)$ and $\overline\Phi$ is a continuous strictly decreasing bijection $\mathbb R\to(0,1)$; for $u\in(0,1)$, $\overline\Phi(y)\le u$ iff $y\ge\overline\Phi^{-1}(u)$. Let
$$
A=\bigcup_{\emptyset\ne S\subseteq\{1,\ldots,K'\}}O_S,\qquad O_S=\{y\in\mathbb R^{K'}:\ y_b\ge l_S\ \text{for all } b\in S\}.
$$
Claim: the Simes event equals $\{Y\in A\}$. Note $\#\{i:p_i\le u\}=n(\{b:\overline\Phi(Y_b)\le u\})$ for every $u$, and $p_{(k)}\le u$ iff $\#\{i:p_i\le u\}\ge k$. If $p_{(k)}\le qk/N$ for some $k$, let $S=\{b:\overline\Phi(Y_b)\le qk/N\}$; then $n(S)\ge k\ge1$, so $S\ne\emptyset$, and every $b\in S$ has $\overline\Phi(Y_b)\le qk/N\le q\,n(S)/N$, i.e. $Y_b\ge l_S$; so $Y\in O_S$. Conversely, if $Y\in O_S$, put $k=n(S)$; every $b\in S$ has $\overline\Phi(Y_b)\le qk/N$, so at least $n(S)=k$ p-values are $\le qk/N$ and $p_{(k)}\le qk/N$.

Let $L=\{l_S:\emptyset\ne S\}$, so $|L|\le 2^{K'}-1$. For every $l=l_S\in L$, $\overline\Phi(l)=q\,n(S)/N\le q$ (and $l\ge\overline\Phi^{-1}(q)>0$ as $q<1/2$). The set $A$ is closed (finite union of closed sets), so it is Borel, and $f_{q,\Sigma}(t)=\mathbb P(Y^t\in A)$ with $Y^t\sim\mathcal N_{K'}(0,R_t^\Gamma)$.

**Step 3 (regularization).** For $\varepsilon\in(0,1)$ put $\Gamma_\varepsilon=(1-\varepsilon)\Gamma+\varepsilon I_{K'}$ and $R_\varepsilon(t)=(1-t)\Gamma_\varepsilon+t(\Gamma_\varepsilon\circ\Gamma_\varepsilon)$. Since $\Gamma\succeq0$, $\Gamma_\varepsilon\succeq\varepsilon I$. Since $\Gamma$ has unit diagonal, $\Gamma\circ I=I$, so
$$
\Gamma_\varepsilon\circ\Gamma_\varepsilon=(1-\varepsilon)^2(\Gamma\circ\Gamma)+\bigl(2\varepsilon(1-\varepsilon)+\varepsilon^2\bigr)I\succeq(2\varepsilon-\varepsilon^2)I\succeq\varepsilon I,
$$
using $\Gamma\circ\Gamma\succeq0$ (Schur product theorem). Hence $R_\varepsilon(t)\succeq\varepsilon I$ for all $t\in[0,1]$. It has unit diagonal, so its largest eigenvalue is at most its trace $K'$. Its off-diagonal entries are $\rho_{bc}(t)=(1-t)g_{bc}+tg_{bc}^2$ with $g_{bc}=(1-\varepsilon)\Gamma_{bc}$, $|g_{bc}|\le1-\varepsilon$; they are affine in $t$ with constant slope $\dot\rho_{bc}=g_{bc}^2-g_{bc}$, $|\dot\rho_{bc}|\le2$, and $|\rho_{bc}(t)|\le\max(|g_{bc}|,g_{bc}^2)<1$. Put $f_\varepsilon(t)=\mathbb P(Y^{\varepsilon,t}\in A)$ with $Y^{\varepsilon,t}\sim\mathcal N_{K'}(0,R_\varepsilon(t))$.

**Step 4 (Plackett identity, with domination).** Write $R=R_\varepsilon(t)$, $\dot R=\frac{d}{dt}R_\varepsilon(t)=\Gamma_\varepsilon\circ\Gamma_\varepsilon-\Gamma_\varepsilon$ (constant in $t$, zero diagonal, off-diagonal entries $\dot\rho_{bc}$), and $\varphi_R(y)=(2\pi)^{-K'/2}\det(R)^{-1/2}\exp(-\tfrac12y^{\mathsf T}R^{-1}y)$. By Jacobi's formula and $\frac{d}{dt}R^{-1}=-R^{-1}\dot RR^{-1}$,
$$
\partial_t\varphi_{R_\varepsilon(t)}(y)=\tfrac12\bigl[y^{\mathsf T}R^{-1}\dot RR^{-1}y-\operatorname{tr}(R^{-1}\dot R)\bigr]\varphi_R(y).
$$
Also $\nabla\varphi_R=-R^{-1}y\,\varphi_R$ and $\nabla^2\varphi_R=(R^{-1}yy^{\mathsf T}R^{-1}-R^{-1})\varphi_R$, so $\tfrac12\operatorname{tr}(\dot R\,\nabla^2\varphi_R)$ equals the right-hand side above. As $\dot R$ is symmetric with zero diagonal,
$$
\partial_t\varphi_{R_\varepsilon(t)}(y)=\sum_{b<c}\dot\rho_{bc}\,\partial_b\partial_c\varphi_{R_\varepsilon(t)}(y).
$$
Domination: with $\|\cdot\|$ the operator norm, $\|R^{-1}\|\le1/\varepsilon$, $\|\dot R\|\le\|\dot R\|_F\le2K'$, $\det R\ge\varepsilon^{K'}$ and $y^{\mathsf T}R^{-1}y\ge|y|^2/K'$. Therefore, for all $t\in[0,1]$ and $y\in\mathbb R^{K'}$,
$$
|\partial_t\varphi_{R_\varepsilon(t)}(y)|\le\Bigl(\frac{K'}{\varepsilon^2}|y|^2+\frac{K'^2}{\varepsilon}\Bigr)(2\pi\varepsilon)^{-K'/2}e^{-|y|^2/(2K')}=:D_\varepsilon(y),
$$
and $D_\varepsilon$ is integrable on $\mathbb R^{K'}$ and independent of $t$. Since $(t,y)\mapsto\partial_t\varphi_{R_\varepsilon(t)}(y)$ is continuous, the mean value theorem and dominated convergence give that $f_\varepsilon(t)=\int_A\varphi_{R_\varepsilon(t)}(y)\,dy$ is differentiable with $f_\varepsilon'(t)=\int_A\partial_t\varphi_{R_\varepsilon(t)}\,dy$, and dominated convergence again gives continuity of $f_\varepsilon'$. Thus $f_\varepsilon\in C^1[0,1]$ and
$$
f_\varepsilon'(t)=\sum_{b<c}\dot\rho_{bc}\,J_{bc}(t),\qquad J_{bc}(t)=\int_A\partial_b\partial_c\varphi_{R_\varepsilon(t)}(y)\,dy,
$$
each $J_{bc}$ being absolutely convergent because $|\partial_b\partial_c\varphi_R(y)|=|(R^{-1}y)_b(R^{-1}y)_c-(R^{-1})_{bc}|\varphi_R(y)\le(|y|^2/\varepsilon^2+1/\varepsilon)\varphi_R(y)$.

**Step 5 (staircase decomposition of a pair section).** Fix $b<c$ and write $y=(u,v,y')$ with $u=y_b$, $v=y_c$ and $y'\in\mathbb R^{K'-2}$ the remaining coordinates (absent if $K'=2$). Let $G=L\cup\{-\infty\}=\{\gamma_0<\gamma_1<\cdots<\gamma_m\}$ with $\gamma_0=-\infty$, and for $\alpha,\beta\in G$ let $Q(\alpha,\beta)=\{(u,v)\in\mathbb R^2:u\ge\alpha,\ v\ge\beta\}$ (so $Q(-\infty,\beta)=\mathbb R\times[\beta,\infty)$, and so on).

The section $A_{y'}=\{(u,v):(u,v,y')\in A\}$ is the union over $S$ of the sections of $O_S$. If $y'_d<l_S$ for some $d\in S\setminus\{b,c\}$, the section of $O_S$ is empty; otherwise it is $Q(\alpha_S,\beta_S)$ with $\alpha_S=l_S$ if $b\in S$ and $-\infty$ otherwise, $\beta_S=l_S$ if $c\in S$ and $-\infty$ otherwise. Thus $A_{y'}=\bigcup_{S\in\mathcal S(y')}Q(\alpha_S,\beta_S)$, a finite union of quadrants with corners in $G^2$, where $\mathcal S(y')$ is the set of contributing $S$.

Define $H(i,j)=1$ if some $S\in\mathcal S(y')$ has $\alpha_S\le\gamma_i$ and $\beta_S\le\gamma_j$, and $H(i,j)=0$ otherwise, for $0\le i,j\le m$; set $H(i,j)=0$ if $i=-1$ or $j=-1$. $H$ is nondecreasing in each argument. Put
$$
\epsilon_{ij}=H(i,j)-H(i-1,j)-H(i,j-1)+H(i-1,j-1),\qquad 0\le i,j\le m.
$$
*Coefficients lie in $\{-1,0,1\}$.* With $h_{00}=H(i-1,j-1)$, $h_{01}=H(i-1,j)$, $h_{10}=H(i,j-1)$, $h_{11}=H(i,j)$ we have $h_{00}\le h_{01},h_{10}\le h_{11}$ in $\{0,1\}$. If $h_{00}=1$ all four equal $1$ and $\epsilon_{ij}=0$; if $h_{11}=0$ all vanish and $\epsilon_{ij}=0$; if $h_{00}=0$ and $h_{11}=1$, then $\epsilon_{ij}=1-h_{01}-h_{10}\in\{-1,0,1\}$.

*Decomposition.* Telescoping gives $\sum_{i'\le i,\,j'\le j}\epsilon_{i'j'}=H(i,j)$. For $(u,v)\in\mathbb R^2$ let $i(u)=\max\{i:\gamma_i\le u\}$ and $j(v)=\max\{j:\gamma_j\le v\}$ (well defined as $\gamma_0=-\infty$). Because every corner coordinate lies in $G$, $\alpha_S\le u$ iff $\alpha_S\le\gamma_{i(u)}$, and likewise for $v$; hence $1_{A_{y'}}(u,v)=H(i(u),j(v))$, and
$$
1_{A_{y'}}(u,v)=\sum_{i'\le i(u),\,j'\le j(v)}\epsilon_{i'j'}=\sum_{i',j'=0}^m\epsilon_{i'j'}\,1_{Q(\gamma_{i'},\gamma_{j'})}(u,v).
$$
So $1_{A_{y'}}$ is a signed sum of indicators of quadrants with corners in $G^2$, one term per grid point, each coefficient in $\{-1,0,1\}$ (the coefficients depend on $y'$, through $\mathcal S(y')$). The grid points with both coordinates finite are the points of $L^2$, at most $(2^{K'}-1)^2$ of them.

**Step 6 (face integrals).** Fix $t$, $y'$ and write $\varphi=\varphi_{R_\varepsilon(t)}$. For fixed $y'$, $\varphi(u,v,y')$, $\partial_b\varphi$ and $\partial_b\partial_c\varphi$ are bounded by a polynomial in $(u,v)$ times $e^{-(u^2+v^2)/(2K')}$, so they are integrable over $\mathbb R^2$ and over every line, and tend to $0$ along every line. Hence for finite $\alpha,\beta$, by Fubini and the fundamental theorem of calculus,
$$
\int_{Q(\alpha,\beta)}\partial_b\partial_c\varphi\,du\,dv=\int_\alpha^\infty\Bigl[\partial_b\varphi(u,v,y')\Bigr]_{v=\beta}^{v=\infty}du=-\int_\alpha^\infty\partial_b\varphi(u,\beta,y')\,du=\varphi(\alpha,\beta,y'),
$$
while for $\alpha=-\infty$ (respectively $\beta=-\infty$) the integral is $\int_{\beta}^\infty\int_{\mathbb R}\partial_b(\partial_c\varphi)\,du\,dv=0$ (respectively, integrating first in $v$ over $\mathbb R$, $0$). By Step 4 the integrand of $J_{bc}$ is absolutely integrable on $\mathbb R^{K'}$, so by Fubini and Step 5,
$$
J_{bc}(t)=\int_{\mathbb R^{K'-2}}\Bigl(\int_{A_{y'}}\partial_b\partial_c\varphi\,du\,dv\Bigr)dy'=\int_{\mathbb R^{K'-2}}\sum_{(\alpha,\beta)\in L^2}\epsilon_{\alpha\beta}(y')\,\varphi(\alpha,\beta,y')\,dy',
$$
where $\epsilon_{\alpha\beta}(y')$ is the coefficient of Step 5 at the grid point $(\alpha,\beta)$ (for $K'=2$ there is no $y'$-integral). The inner sum is a measurable function of $y'$ (it equals the inner integral) and is bounded in absolute value by $\sum_{(\alpha,\beta)\in L^2}\varphi(\alpha,\beta,y')$. Since $\int\varphi(\alpha,\beta,y')\,dy'$ is the density of $(Y^{\varepsilon,t}_b,Y^{\varepsilon,t}_c)$ at $(\alpha,\beta)$, a centered bivariate normal with unit variances and correlation $\rho_{bc}(t)\in(-1,1)$,
$$
|J_{bc}(t)|\le\sum_{(\alpha,\beta)\in L^2}\phi_2\bigl(\alpha,\beta;\rho_{bc}(t)\bigr).
$$
Equivalently, the corner at $(\alpha,\beta)$ contributes at most $\phi_2(\alpha,\beta;\rho_{bc})$ times the conditional probability, given $(Y_b,Y_c)=(\alpha,\beta)$, that the remaining block scores make that corner active; that probability is at most $1$.

**Step 7 (integration along the monotone pair correlation).** Fix $b<c$ and $(\alpha,\beta)\in L^2$, and write $g=g_{bc}$. If $g^2=g$ then $\dot\rho_{bc}=0$ and $\int_0^1|\dot\rho_{bc}|\phi_2\,dt=0$. Otherwise $\rho_{bc}$ is an affine bijection from $[0,1]$ onto the segment between $\rho_0=g$ and $\rho_1=g^2$, contained in $(-1,1)$; since $\phi_2\ge0$ and $\partial_\rho\overline\Phi_2(\alpha,\beta;\rho)=\phi_2(\alpha,\beta;\rho)$ on $(-1,1)$ (Plackett's identity; it is also the case $K'=2$, $A=Q(\alpha,\beta)$ of Steps 4 and 6),
$$
\int_0^1|\dot\rho_{bc}|\,\phi_2\bigl(\alpha,\beta;\rho_{bc}(t)\bigr)\,dt=\Bigl|\int_0^1\dot\rho_{bc}\,\phi_2\bigl(\alpha,\beta;\rho_{bc}(t)\bigr)\,dt\Bigr|=\bigl|\overline\Phi_2(\alpha,\beta;\rho_1)-\overline\Phi_2(\alpha,\beta;\rho_0)\bigr|.
$$
Both values lie in $[0,\overline\Phi(\max(\alpha,\beta))]$, since $\{U\ge\alpha,V\ge\beta\}\subseteq\{U\ge\max(\alpha,\beta)\}$ or $\{V\ge\max(\alpha,\beta)\}$; so the difference is at most $\overline\Phi(\max(\alpha,\beta))\le q$ by Step 2.

**Step 8 (variation of the regularized profile).** For any partition, $\sum_\ell|f_\varepsilon(t_\ell)-f_\varepsilon(t_{\ell-1})|=\sum_\ell|\int_{t_{\ell-1}}^{t_\ell}f_\varepsilon'|\le\int_0^1|f_\varepsilon'|\,dt$. By Steps 4, 6, 7 and $|L|\le2^{K'}-1$,
$$
\mathcal V(f_\varepsilon)\le\int_0^1|f'_\varepsilon|\,dt\le\sum_{b<c}\sum_{(\alpha,\beta)\in L^2}\int_0^1|\dot\rho_{bc}|\,\phi_2\bigl(\alpha,\beta;\rho_{bc}(t)\bigr)\,dt\le\binom{K'}{2}(2^{K'}-1)^2q .
$$

**Step 9 (removing the regularization).** Fix $t$. As $\varepsilon\to0$, $R_\varepsilon(t)\to R_t^\Gamma$ entrywise (each entry is a polynomial in $\varepsilon$), so the characteristic functions $e^{-\xi^{\mathsf T}R_\varepsilon(t)\xi/2}$ converge pointwise and $Y^{\varepsilon,t}\Rightarrow Y^t\sim\mathcal N_{K'}(0,R_t^\Gamma)$ (singular $R_t^\Gamma$ allowed). The boundary of the closed set $A$ lies in $\bigcup_{b}\bigcup_{l\in L}\{y_b=l\}$: if $y\in A$ has $y_b\notin L$ for all $b$, then $y\in O_S$ for some $S$ with $y_d>l_S$ for all $d\in S$, an open subset of $A$, so $y$ is interior. Each $Y^t_b$ is standard normal (unit diagonal), so $\mathbb P(Y^t\in\partial A)=0$ and the portmanteau theorem gives $f_\varepsilon(t)\to\mathbb P(Y^t\in A)=f_{q,\Sigma}(t)$. Hence for every partition,
$$
\sum_\ell|f_{q,\Sigma}(t_\ell)-f_{q,\Sigma}(t_{\ell-1})|=\lim_{\varepsilon\to0}\sum_\ell|f_\varepsilon(t_\ell)-f_\varepsilon(t_{\ell-1})|\le\binom{K'}{2}(2^{K'}-1)^2q,
$$
and taking the supremum over partitions, $\mathcal V(f_{q,\Sigma})\le\binom{K'}{2}(2^{K'}-1)^2q$.

**Step 10 (constant).** Since $K'\le K$, $\binom{K'}{2}(2^{K'}-1)^2<\tfrac{K'^2}{2}4^{K'}\le\tfrac{K^2}{2}4^K<K^24^K$, so $\mathcal V(f_{q,\Sigma})\le K^24^Kq$ (also when $K'=1$, where $\mathcal V=0$). Finally $[x]_+\le|x|$ termwise gives $\mathcal V_-(f_{q,\Sigma})\le\mathcal V(f_{q,\Sigma})$. Neither $N$, the block sizes nor $\Gamma$ entered the bound: $N$ and the sizes only through the levels in $L$, all with $\overline\Phi(l)\le q$, and $\Gamma$ only through the swept correlation segments, which Step 7 bounds uniformly. $\blacksquare$
