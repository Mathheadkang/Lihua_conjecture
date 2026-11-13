---
title: Pairwise Plackett corner count for the clone-block Schur-square variation
type: plan
status: succeeded
target_asset: gaussian_simes_clone_block_schur_variation_bound
inspired_by:
  - idea_83407c80a0c7
  - idea_a0805e98f90d
adapts: []
proof_digest: 77b310651f3a2c29a6abd4f7d5f58ead3d0640b259418d7e023f96394490b988
statement_digest: 9745c7f1d8f7ae5518e033eec521fe69f3dee7d75adf2262924621d839195795
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
verified_proof_digest: 77b310651f3a2c29a6abd4f7d5f58ead3d0640b259418d7e023f96394490b988
---

# Pairwise Plackett corner count for the clone-block Schur-square variation

## Goal

Target: [asset](../assets/gaussian_simes_clone_block_schur_variation_bound.md)

Prove $\mathcal V_-(f_{q,\Sigma})\le\mathcal V(f_{q,\Sigma})\le K^2 4^K q$ for every clone-block $\Sigma$ with at most $K$ blocks and every $q\in(0,1/2)$. The route is the [pairwise Plackett corner bound](../ideas/idea_83407c80a0c7.md): reduce to the $K$ block scores, regularize the block matrix so that the path is positive definite, write $f'$ by Plackett's identity as a sum over block pairs, bound each pair's mixed derivative by bivariate densities at at most $(2^K-1)^2$ corners, integrate along the monotone pair correlation, and remove the regularization by pointwise convergence and lower semicontinuity of variation. It extends the two-block and trivariate calculations of [the partial variation calculation](../ideas/idea_a0805e98f90d.md) to every $K$; the case analysis by frozen coordinate is replaced by a staircase decomposition of the two-dimensional section.

Notation: $\phi_2(x,y;\rho)$ and $\overline\Phi_2(x,y;\rho)=\mathbb P(U\ge x,V\ge y)$ for a centered bivariate normal $(U,V)$ with unit variances and correlation $\rho\in(-1,1)$.

## Plan

1. [x] **Reduction to block scores.** Drop empty blocks, so $a$ is onto $\{1,\ldots,K'\}$ with $K'\le K$ and sizes $n_b=|a^{-1}(b)|\ge1$; replace $\Gamma$ by its principal submatrix on these blocks (still in $\mathcal C_{K'}$). Claim: $(\Sigma\circ\Sigma)_{ij}=\Gamma_{a(i)a(j)}^2$, so $R_t^\Sigma$ is the clone-block matrix of $R_t^\Gamma=(1-t)\Gamma+t(\Gamma\circ\Gamma)$, and if $Y\sim\mathcal N_{K'}(0,R_t^\Gamma)$ then $(Y_{a(1)},\ldots,Y_{a(N)})\sim\mathcal N_N(0,R_t^\Sigma)$. Hence $f_{q,\Sigma}(t)=\mathbb P(Y\in A)$ for a fixed set $A\subset\mathbb R^{K'}$ defined in step 2. If $K'=1$ the path is constant and $\mathcal V=0$; assume $K'\ge2$.

2. [x] **Orthant form of the Simes event.** For nonempty $S\subseteq\{1,\ldots,K'\}$ put $n(S)=\sum_{b\in S}n_b$ and $l_S=\overline\Phi^{-1}(q\,n(S)/N)$. Claim: the Simes event equals $\{Y\in A\}$ with
$$
A=\bigcup_{\emptyset\ne S}\{y:\ y_b\ge l_S\ \text{for all } b\in S\}.
$$
Proof to write: if $p_{(k)}\le qk/N$, let $S$ be the blocks with $\overline\Phi(Y_b)\le qk/N$; then $n(S)\ge k$ and every $b\in S$ has $\overline\Phi(Y_b)\le q\,n(S)/N$, i.e. $Y_b\ge l_S$. Conversely, if $Y_b\ge l_S$ for all $b\in S$, then with $k=n(S)$ at least $k$ p-values are $\le qk/N$, so $p_{(k)}\le qk/N$. Since $n(S)/N\le1$ and $q<1/2$, every level satisfies $l_S\ge\overline\Phi^{-1}(q)>0$, so $\overline\Phi(l)\le q$ for every $l$ in the level set $L=\{l_S\}$, and $|L|\le 2^{K'}-1$.

3. [x] **Regularization.** For $\varepsilon\in(0,1)$ put $\Gamma_\varepsilon=(1-\varepsilon)\Gamma+\varepsilon I_{K'}$, positive definite with unit diagonal. Claim: $R_t^{\Gamma_\varepsilon}=(1-t)\Gamma_\varepsilon+t(\Gamma_\varepsilon\circ\Gamma_\varepsilon)$ is positive definite for all $t\in[0,1]$, with smallest eigenvalue bounded below by some $\lambda_\varepsilon>0$ uniformly in $t$ (Schur product of positive definite matrices is positive definite; convex combination; continuity on compact $[0,1]$). Its off-diagonal entries are $\rho^\varepsilon_{bc}(t)=(1-t)g+tg^2$ with $g=(1-\varepsilon)\Gamma_{bc}\in(-1,1)$: affine in $t$, so monotone, with $\dot\rho^\varepsilon_{bc}=g^2-g$. Put $f_\varepsilon(t)=\mathbb P(Y^{\varepsilon,t}\in A)$, $Y^{\varepsilon,t}\sim\mathcal N_{K'}(0,R_t^{\Gamma_\varepsilon})$.

4. [x] **Plackett identity for the indicator.** With $\varphi_R$ the density of $\mathcal N_{K'}(0,R)$ for positive definite $R$, the heat-equation identity $\partial\varphi_R/\partial R_{bc}=\partial_b\partial_c\varphi_R$ ($b\ne c$, entries $R_{bc}=R_{cb}$ moved together) and differentiation under the integral (justified by a uniform Gaussian bound on $\partial_b\partial_c\varphi_{R}$ over $\{R_t^{\Gamma_\varepsilon}:t\in[0,1]\}$, using $\lambda_\varepsilon$) give that $f_\varepsilon\in C^1[0,1]$ with
$$
f_\varepsilon'(t)=\sum_{b<c}\dot\rho^\varepsilon_{bc}\,J_{bc}(t),\qquad J_{bc}(t)=\int_A\partial_b\partial_c\varphi_{R_t^{\Gamma_\varepsilon}}(y)\,dy .
$$

5. [x] **Staircase decomposition of a section.** Fix $b<c$ and the other coordinates $y'$. Claim: the section $A_{y'}=\{(y_b,y_c):y\in A\}$ is a finite union of sets of the forms $\mathbb R^2$, $[l,\infty)\times\mathbb R$, $\mathbb R\times[l,\infty)$, $[l,\infty)\times[l',\infty)$ with $l,l'\in L$ (according as $S$ avoids $b,c$, contains one of them, or both; the constraints on $y'$ decide which $S$ contribute). Hence $A_{y'}$ is an upper staircase set, and $1_{A_{y'}}=\sum_{(x,y)}\epsilon_{x,y}1_{[x,\infty)\times[y,\infty)}$ with $(x,y)\in(L\cup\{-\infty\})^2$, coefficients $\epsilon_{x,y}\in\{-1,0,1\}$ (outer corners $+1$, inner corners $-1$, each grid point at most one corner). Prove this by induction on the number of quadrants, or directly by inclusion-exclusion along the sorted staircase.

6. [x] **Face integrals.** Claim: for $x,y$ finite, $\int_{[x,\infty)\times[y,\infty)}\partial_b\partial_c\varphi\,dy_b\,dy_c=\varphi(x,y,y')$ (the density with $(y_b,y_c)=(x,y)$), and the integral is $0$ when $x=-\infty$ or $y=-\infty$ (integral of a derivative over a full line of an integrable function vanishing at infinity). Integrating over $y'$ by Fubini,
$$
|J_{bc}(t)|\le\sum_{(x,y)\in L^2}\int\varphi(x,y,y')\,dy'=\sum_{(x,y)\in L^2}\phi_2\bigl(x,y;\rho^\varepsilon_{bc}(t)\bigr).
$$
The coefficients depend on $y'$ but are bounded by $1$ in absolute value, which is all that is used.

7. [x] **Integration along the monotone pair correlation.** For fixed $x,y\in L$, substitute $\rho=\rho^\varepsilon_{bc}(t)$: since $\partial_\rho\overline\Phi_2(x,y;\rho)=\phi_2(x,y;\rho)$,
$$
\int_0^1|\dot\rho^\varepsilon_{bc}|\,\phi_2(x,y;\rho^\varepsilon_{bc}(t))\,dt=\bigl|\overline\Phi_2(x,y;\rho_1)-\overline\Phi_2(x,y;\rho_0)\bigr|\le\overline\Phi(\max(x,y))\le q,
$$
with $\rho_0=g$, $\rho_1=g^2$ (if $g^2=g$ the integral is $0$). The last step uses $0\le\overline\Phi_2\le\overline\Phi(\max(x,y))$ and step 2.

8. [x] **Variation of the regularized profile.** Since $f_\varepsilon\in C^1$, $\mathcal V(f_\varepsilon)=\int_0^1|f_\varepsilon'|\,dt\le\sum_{b<c}\sum_{(x,y)\in L^2}q\le\binom{K'}{2}(2^{K'}-1)^2q$, by steps 4, 6, 7.

9. [x] **Removing the regularization.** Claim: $f_\varepsilon(t)\to f_{q,\Sigma}(t)$ for every $t$ as $\varepsilon\to0$. Covariances converge, so $Y^{\varepsilon,t}\Rightarrow Y^{t}\sim\mathcal N_{K'}(0,R_t^\Gamma)$; the boundary of $A$ lies in $\bigcup_b\bigcup_{l\in L}\{y_b=l\}$, which has probability $0$ since every $Y^t_b$ is standard normal; the portmanteau theorem gives the convergence. For each fixed partition, the partition sum of $f_{q,\Sigma}$ is the limit of those of $f_\varepsilon$, each at most the bound of step 8; taking the supremum over partitions, $\mathcal V(f_{q,\Sigma})\le\binom{K'}{2}(2^{K'}-1)^2q$.

10. [x] **Constant.** $\binom{K'}{2}(2^{K'}-1)^2\le\tfrac{K^2}{2}4^K<K^24^K$, and $\mathcal V_-\le\mathcal V$ termwise since $[a]_+\le|a|$.

## Verification

Steps 1-2 express $f_{q,\Sigma}$ as the probability of a fixed union of orthants under the block-score law $\mathcal N_{K'}(0,R_t^\Gamma)$, with levels all at least $\overline\Phi^{-1}(q)$. Steps 3-8 bound the total variation of the regularized profile by counting, for each of the $\binom{K'}2$ moving block pairs, at most $|L|^2\le(2^{K'}-1)^2$ corners, each contributing at most $q$ after integrating along the monotone pair correlation. Step 9 transfers the bound to $\varepsilon=0$, including singular $\Gamma$ and $\pm1$ correlations, by pointwise convergence and lower semicontinuity of variation. Step 10 gives the stated constant. Nothing depends on $N$, block sizes, or $\Gamma$: $N$ and the sizes enter only through the levels $l_S$, and $\Gamma$ only through the swept correlation ranges, which are bounded by the full range in step 7. Checks to make during execution: the sign-coefficient claim of step 5 (each grid point at most one corner, coefficient in $\{-1,0,1\}$) and the domination in step 4.

## Assumed definitions

- [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) (approved) and [Gaussian test p-values](../definitions/gaussian_test_pvalues.md) (approved), as used in the statement.
- Standard facts used as black boxes: the Schur product theorem (positive definite case), the Gaussian heat-equation identity $\partial\varphi_R/\partial R_{bc}=\partial_b\partial_c\varphi_R$, $\partial_\rho\overline\Phi_2=\phi_2$, and the portmanteau theorem. No draft dependency is assumed.

## Outcome

The complete proof is under `## Proof` in [the asset](../assets/gaussian_simes_clone_block_schur_variation_bound.md), following steps 1-10 with these precisions. Step 3: the uniform eigenvalue bound is explicit, $R_t^{\Gamma_\varepsilon}\succeq\varepsilon I$, from $\Gamma_\varepsilon\circ\Gamma_\varepsilon=(1-\varepsilon)^2(\Gamma\circ\Gamma)+(2\varepsilon-\varepsilon^2)I$. Step 4: the heat identity is verified directly (Jacobi's formula against the Hessian of $\varphi_R$), and differentiation under the integral is dominated by $(K'|y|^2/\varepsilon^2+K'^2/\varepsilon)(2\pi\varepsilon)^{-K'/2}e^{-|y|^2/(2K')}$, uniform in $t$. Step 5: the corner coefficients are the second differences of a monotone $0/1$ grid function $H$, hence in $\{-1,0,1\}$, one per grid point of $(L\cup\{-\infty\})^2$; only the at most $(2^{K'}-1)^2$ points of $L^2$ give nonzero face integrals. Step 6: the $y'$-dependent coefficients are bounded by $1$, so each corner contributes at most the marginal bivariate density $\phi_2(\alpha,\beta;\rho_{bc})$. Nothing beyond the standard facts listed under Assumed definitions (Schur product theorem, Plackett's identity $\partial_\rho\overline\Phi_2=\phi_2$, portmanteau theorem) and the two approved definitions is assumed.

## Verdict

confirmed

Checked step by step against the statement. Step 1: the clone-block path stays clone-block with block matrix $R_t^\Gamma$, and dropping empty blocks keeps $\Gamma$ in $\mathcal C_{K'}$; the $K'=1$ case is constant. Step 2: the Simes event equals $\{Y\in A\}$ with $A$ a union of orthants $O_S$ at levels $l_S$, $\overline\Phi(l_S)=q\,n(S)/N\le q$; both inclusions check. Step 3: $\Gamma_\varepsilon\circ\Gamma_\varepsilon=(1-\varepsilon)^2\Gamma\circ\Gamma+(2\varepsilon-\varepsilon^2)I$ (uses $\Gamma\circ I=I$), so $R_\varepsilon(t)\succeq\varepsilon I$, and the pair correlations are affine in $t$ with constant slope. Step 4: the heat identity $\partial_t\varphi=\sum_{b<c}\dot\rho_{bc}\partial_b\partial_c\varphi$ and the domination constants ($\|R^{-1}\|\le1/\varepsilon$, $\|\dot R\|_F\le2K'$, $R^{-1}\succeq I/K'$) are correct.

On the points flagged for scrutiny. (i) The proof never uses conditional densities. It differentiates the full joint density, and the heat identity already accounts for every entry of $R$ that moves; after that, $y'$ is only a variable of integration in Fubini, with the full density $\varphi(u,v,y')$ evaluated at fixed $y'$. So the other blocks moving with $t$ is fully handled. (ii) For fixed $y'$, the section $A_{y'}$ is a finite union of quadrants with corners in $G^2$, $G=L\cup\{-\infty\}$. The identity $1_{A_{y'}}=H(i(u),j(v))$ holds because every corner coordinate lies in $G$, and the second differences of a monotone $\{0,1\}$-valued $H$ lie in $\{-1,0,1\}$. The face integral gives $\varphi(\alpha,\beta,y')$ at finite corners and $0$ whenever one coordinate is $-\infty$, since a full-line integral of a derivative of a Gaussian-decaying function vanishes. So only points of $L^2$ contribute. (iii) Since $|\epsilon|\le1$ and $\varphi\ge0$, integrating $\sum_{L^2}\varphi(\alpha,\beta,y')$ over $y'$ gives the nondegenerate bivariate marginal density $\phi_2(\alpha,\beta;\rho_{bc}(t))$. Measurability in $y'$ holds because $\mathcal S(y')$ is determined by finitely many coordinate comparisons. (iv) Because $\dot\rho_{bc}$ has constant sign, changing variables and applying Plackett's identity gives $\int_0^1|\dot\rho|\phi_2\,dt=|\overline\Phi_2(\rho_1)-\overline\Phi_2(\rho_0)|\le\overline\Phi(\max(\alpha,\beta))\le q$. (v) For $\varepsilon\to0$: $\partial A$ lies in $\bigcup_b\{y_b\in L\}$, which has probability zero because each $Y^t_b$ is standard normal. With $R_\varepsilon(t)\to R_t^\Gamma$ entrywise, the portmanteau theorem gives pointwise convergence $f_\varepsilon(t)\to f_{q,\Sigma}(t)$, which passes to every finite partition sum and then to the supremum.

Minor remarks, not gaps. In Step 8, $|f_\varepsilon'(t)|\le\sum_{b<c}|\dot\rho_{bc}|\sum_{L^2}\phi_2(\alpha,\beta;\rho_{bc}(t))$, a continuous function of $t$, so the integral is well defined. The hypothesis $q<1/2$ is used only to remark that $l>0$; the argument goes through for any $q\in(0,1)$. The proof's constant $\binom{K'}{2}(2^{K'}-1)^2q$ is sharper than the stated $K^24^Kq$, and Step 10 checks this comparison correctly.
