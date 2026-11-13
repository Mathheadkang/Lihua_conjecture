---
type: lemma
title: >-
  Compact all-null exchangeable arrays carry the Schur-square path and attain
  the loaded Simes supremum
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_exchangeable_array_variational_compactification
  - lib_chi2024_positive_gaussian_simes
uses_definitions:
  - gaussian_bh_marked_exchangeable_parameter_array
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - simes
  - global_null
  - one_sided
  - schur_square_path
  - compactness
---

# Compact all-null exchangeable arrays carry the Schur-square path and attain the loaded Simes supremum

## Statement

Fix $\sigma\in(0,1)$ and $q\in(0,1/4]$. Let $\mathfrak P$ be the space of jointly exchangeable laws of [lawful marked parameter arrays](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md) $\omega=((\theta_i,\ell_i)_{i\ge1},(C_{ij})_{i,j\ge1})$, with finite-subarray weak convergence. Let $\mathfrak P_0\subset\mathfrak P$ be the all-null laws, under which $\theta_i=0$ and $\ell_i=1$ for every $i$ almost surely.

For a symmetric positive-semidefinite $n\times n$ matrix $R$ with unit diagonal (an element of $\mathcal C_n$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), singular allowed), let $T\sim\mathcal N_n(0,R)$, let $p_i=\overline\Phi(T_i)$ be the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md) with order statistics counted with multiplicity, and put
$$
F_q(R)=\mathbb P\Bigl(\exists k\in\{1,\ldots,n\}:p_{(k)}\le\frac{qk}{n}\Bigr).
$$
Put $B(q)=\sup_{N\ge1}\sup_{\Sigma\in\mathcal C_N}F_q(\Sigma)$ and $B^\sigma(q)=\sup_{N\ge1}\sup_{\Sigma\in\mathcal C_N}F_q\bigl((1-\sigma^2)\Sigma+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}\bigr)$.

For $t\in[0,1]$ let $g_t(x)=(1-t)x+tx^2$. The Schur-path map $S_t$ keeps all marks and replaces $C_{ij}$ by $g_t(C_{ij})$ for $i\ne j$, keeping $C_{ii}=1$; for a law $P$ write $S_tP$ for its push-forward. For $P\in\mathfrak P_0$ and $n\ge1$ put
$$
\Phi_{n,\sigma}(P;q)=\mathbb E_{\omega\sim P}\,F_q\bigl((1-\sigma^2)C_{1:n,1:n}+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}\bigr).
$$
For $N\ge1$ and $\Sigma\in\mathcal C_N$ write $R^\Sigma_t=(1-t)\Sigma+t(\Sigma\circ\Sigma)$, where $\circ$ is the entrywise product, and let $P_\Sigma$ be the law of the all-null array with $C_{ab}=\Sigma_{I_aI_b}$, where $I_1,I_2,\ldots$ are independent and uniform on $\{1,\ldots,N\}$.

Then the following hold.

1. **Compactness and path invariance.** $\mathfrak P_0$ is compact. For every $t\in[0,1]$ and $P\in\mathfrak P_0$, $S_tP\in\mathfrak P_0$; the map $(t,P)\mapsto S_tP$ from $[0,1]\times\mathfrak P_0$ to $\mathfrak P_0$ is jointly continuous, and $S_0P=P$.
2. **Population functional.** For every $P\in\mathfrak P_0$ the limit $\Phi_\sigma(P;q)=\lim_{n\to\infty}\Phi_{n,\sigma}(P;q)$ exists, the convergence is uniform in $P\in\mathfrak P_0$, and $\Phi_\sigma(\cdot\,;q)$ is continuous on $\mathfrak P_0$. Consequently the path function
$$
f^\sigma_{P,q}(t)=\Phi_\sigma(S_tP;q),\qquad 0\le t\le1,
$$
is continuous on $[0,1]$.
3. **Schur endpoint.** $\Phi_\sigma(S_1P;q)\le q$ for every $P\in\mathfrak P_0$.
4. **Finite models embed with their Schur path.** For every $N\ge1$ and $\Sigma\in\mathcal C_N$, $P_\Sigma\in\mathfrak P_0$, $S_tP_\Sigma=P_{R^\Sigma_t}$, and
$$
f^\sigma_{P_\Sigma,q}(t)=F_q\bigl((1-\sigma^2)R^\Sigma_t+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}\bigr)\qquad(0\le t\le1).
$$
5. **Attained supremum.** $\max_{P\in\mathfrak P_0}\Phi_\sigma(P;q)$ exists and equals $B^\sigma(q)$.
6. **Removal of the loading in value.** $B^\sigma(q)\le B(q)$, and $\lim_{\sigma\downarrow0}B^\sigma(q)=B(q)$.

## Motivation

This lemma supplies the compact limiting objects for a contradiction or compactness route to [the uniform linear Simes bound](gaussian_simes_one_sided_uniform_linear_bound.md) built on [the Schur-square tensor lift](../ideas/idea_6b48b2fe25e1.md). The Schur-square path acts entrywise on the off-diagonal Gram array, so it commutes with taking subarray laws, and it keeps exact clones tied because $g_t(1)=1$. The common loading $\sigma$ is applied to the residual array only, so at $\sigma=0$ the path is exactly $R_t=(1-t)\Sigma+t(\Sigma\circ\Sigma)$. For $\sigma>0$, the velocity on the full covariance is $(1-\sigma^2)(\rho^2-\rho)$ in the residual correlation $\rho$, so the factor $\rho(1-\rho)$ is kept.

Expected proof ingredients:

- When all tags are true nulls, the BH false discovery proportion is the indicator of at least one rejection. So $\Phi_{n,\sigma}$ is the all-null case of the finite functional $\mathcal F_n$ of [the approved array compactification](gaussian_bh_exchangeable_array_variational_compactification.md), and part 2 should follow from its part 1.
- The all-null set is closed. The maps $g_t$ preserve positive semidefiniteness by the Schur product theorem and convexity.
- Part 3 uses [the positive-Gaussian Simes theorem](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) in every conditional finite model, because $(1-\sigma^2)g_1(C_{ij})+\sigma^2\ge0$.
- Part 4 is weighted Simes with random multiplicities tending to $1/N$. The event boundary lies in finitely many marginal threshold hyperplanes, which are Gaussian-null.
- Part 6 uses finite-dimensional continuity of $F_q$ in the covariance and the inclusion $(1-\sigma^2)\Sigma+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}\in\mathcal C_N$.

## Proof

Throughout, $\sigma\in(0,1)$ and $q\in(0,1/4]$ are fixed. For an $n\times n$ matrix $C$ write $M^\sigma(C)=(1-\sigma^2)C+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}$. If $C\in\mathcal C_n$, then $M^\sigma(C)\in\mathcal C_n$: it is symmetric, it is a sum of two positive-semidefinite matrices with nonnegative weights, and its diagonal entries are $(1-\sigma^2)+\sigma^2=1$. Since $\overline\Phi:\mathbb R\to(0,1)$ is a strictly decreasing bijection, for $x\in(0,1)$ we have $\overline\Phi(s)\le x$ if and only if $s\ge\overline\Phi^{-1}(x)$.

**Step 1 (threshold form of the Simes event).** Fix $n\ge1$ and $p\in[0,1]^n$. Then
$$
\Bigl\{\exists k\le n:p_{(k)}\le\frac{qk}{n}\Bigr\}=\Bigl\{\exists c\in\{1,\ldots,n\}:\#\{i:p_i\le qc/n\}\ge c\Bigr\}.
$$
If $p_{(k)}\le qk/n$, the $k$ coordinates $p_{(1)},\ldots,p_{(k)}$ are all $\le qk/n$, so $c=k$ works. Conversely, if at least $c$ coordinates are $\le qc/n$, then $p_{(c)}\le qc/n$. For $c\in\{1,\ldots,n\}$ we have $qc/n\in(0,1)$; put $t_c=\overline\Phi^{-1}(qc/n)$. With $p_i=\overline\Phi(T_i)$, $\{p_i\le qc/n\}=\{T_i\ge t_c\}$. Let $\chi_n(T)$ be the indicator of the Simes event as a function of $T\in\mathbb R^n$. Then $\chi_n(T)=\mathbf 1\{\exists c:\#\{i:T_i\ge t_c\}\ge c\}$. Let $H_n=\bigcup_{i,c}\{T:T_i=t_c\}$. If $T\notin H_n$ and $\|T'-T\|_\infty<\min_{i,c}|T_i-t_c|$, then $\mathbf 1\{T'_i\ge t_c\}=\mathbf 1\{T_i\ge t_c\}$ for all $i,c$, so $\chi_n(T')=\chi_n(T)$. Thus $\chi_n$ is locally constant off $H_n$. Also $F_q(R)=\mathbb E\,\chi_n(T)$ for $T\sim\mathcal N_n(0,R)$.

**Step 2 (continuity of $F_q$ on $\mathcal C_n$, singular allowed).** Let $\Gamma_k\to\Gamma$ in $\mathcal C_n$. Fix one $g\sim\mathcal N_n(0,I_n)$ and set $T^k=\Gamma_k^{1/2}g$ and $T=\Gamma^{1/2}g$, using the positive-semidefinite square root. Then $T^k\sim\mathcal N_n(0,\Gamma_k)$ and $T\sim\mathcal N_n(0,\Gamma)$. The positive-semidefinite square root is continuous on the positive-semidefinite cone, so $T^k\to T$ for every realization of $g$. Each $T_i$ is standard normal because $\Gamma_{ii}=1$, so $\mathbb P(T\in H_n)\le\sum_{i,c}\mathbb P(T_i=t_c)=0$. By Step 1, $\chi_n(T^k)\to\chi_n(T)$ almost surely. Bounded convergence gives $F_q(\Gamma_k)\to F_q(\Gamma)$. In particular $F_q$ is Borel on $\mathcal C_n$.

**Step 3 (Part 1: compactness).** Let $\Omega$ be the space of lawful marked arrays with its product topology. It is metrizable, being a subspace of a countable product of metrizable spaces. Let $K_0\subset[-1,1]^{\{(i,j):i<j\}}$ be the set of off-diagonal arrays (with $C_{ji}=C_{ij}$ and $C_{ii}=1$ understood) whose finite principal matrices are all positive semidefinite. Each such condition involves finitely many coordinates and is closed. So $K_0$ is a closed subset of a compact metrizable product, hence compact metrizable. Let $\iota:K_0\to\Omega$ be $\iota(C)=(((0,1))_{i\ge1},C)$. This map is lawful because $(0,1)\in E_{\rm mark}$. Let $\rho:\Omega\to K_0$ be the projection to the array. Both maps are continuous, $\rho\circ\iota=\mathrm{id}$, and $\iota\circ\rho=\mathrm{id}$ on $A=\iota(K_0)=\{\theta_i=0,\ \ell_i=1\ \forall i\}$. Finitary relabelings $\tau$ act continuously on $\Omega$ and on $K_0$ by permuting coordinates, and they commute with $\iota$ and $\rho$.

Let $\mathfrak E$ be the set of jointly exchangeable Borel probability laws on $K_0$, with the weak topology. Each $P\in\mathfrak P_0$ has $P(A)=1$, so $P=\iota_*\rho_*P$. Moreover $\rho_*P\in\mathfrak E$, because $\rho$ commutes with relabelings. Conversely, $\iota_*\mu\in\mathfrak P_0$ for $\mu\in\mathfrak E$. Push-forward by a continuous map is weakly continuous, so $J=\rho_*:\mathfrak P_0\to\mathfrak E$ is a homeomorphism with inverse $\iota_*$. The set of all Borel probability laws on the compact metrizable space $K_0$ is compact and metrizable in the weak topology (Prokhorov; tightness is automatic). The set $\mathfrak E$ is closed in it: if $\mu_k\to\mu$ and $h$ is bounded and continuous, then $h\circ\tau$ is bounded and continuous, so $\int h\circ\tau\,d\mu=\lim\int h\circ\tau\,d\mu_k=\lim\int h\,d\mu_k=\int h\,d\mu$. Hence $\mathfrak E$ is compact metrizable, and so is $\mathfrak P_0$.

**Step 4 (Part 1: path invariance and joint continuity).** The map $(t,C)\mapsto S_tC$, given by $(S_tC)_{ij}=g_t(C_{ij})$ for $i\ne j$, is continuous from $[0,1]\times K_0$ to $\mathbb R^{\{(i,j):i<j\}}$ with the product topology, since each coordinate is the polynomial $(t,x)\mapsto(1-t)x+tx^2$. It maps $K_0$ into $K_0$. First, $g_t([-1,1])\subset[-1,1]$, since $|g_t(x)|\le(1-t)|x|+tx^2\le1$. Second, on each finite principal matrix $C$ (unit diagonal), $S_t$ produces $(1-t)C+t(C\circ C)$, using $g_t(1)=1$ on the diagonal. Here $C\circ C$ is positive semidefinite by the Schur product theorem, so the convex combination is positive semidefinite with unit diagonal. Since $S_t$ acts entrywise, $S_t\circ\tau=\tau\circ S_t$ for every finitary relabeling $\tau$. So $(S_t)_*$ maps $\mathfrak E$ into $\mathfrak E$. Extending $S_t$ to $\Omega$ by keeping the marks, it commutes with $\iota$ and $\rho$, so $S_tP=\iota_*(S_t)_*\rho_*P\in\mathfrak P_0$ for $P\in\mathfrak P_0$. Also $g_0(x)=x$ gives $S_0P=P$.

For joint continuity, it suffices (by the homeomorphism $J$ and metrizability) to take $t_k\to t$ in $[0,1]$ and $\mu_k\to\mu$ in $\mathfrak E$, and to show $\int h\circ S_{t_k}\,d\mu_k\to\int h\circ S_t\,d\mu$ for bounded continuous $h$ on $K_0$. The function $(s,C)\mapsto h(S_sC)$ is continuous on the compact metric space $[0,1]\times K_0$, hence uniformly continuous, so $\varepsilon_k=\sup_{C\in K_0}|h(S_{t_k}C)-h(S_tC)|\to0$. Then
$$
\Bigl|\int h\circ S_{t_k}\,d\mu_k-\int h\circ S_t\,d\mu\Bigr|\le\varepsilon_k+\Bigl|\int h\circ S_t\,d\mu_k-\int h\circ S_t\,d\mu\Bigr|\to0,
$$
because $h\circ S_t$ is bounded and continuous. This proves Part 1.

**Step 5 (Part 2).** Every $P\in\mathfrak P_0$ belongs to $\mathfrak P$. Fix $\omega$ with $\theta_i=0$ and $\ell_i=1$ for all $i$, and $n\ge1$. By the definition of the marked array, conditionally on $\omega$, $T^{(n)}\sim\mathcal N_n(0,M^\sigma(C_{1:n,1:n}))$, the p-values are $\overline\Phi(T_i)$, and $D_n=\sum_{i\in\mathcal R_q}\ell_i/(R_n\vee1)=R_n/(R_n\vee1)=\mathbf 1\{R_n\ge1\}$. By the definition of BH, $R_n\ge1$ if and only if $\widehat k_q>0$. Indeed, if $\widehat k_q>0$ then $p_{(\widehat k_q)}\le q\widehat k_q/n$, so at least $\widehat k_q\ge1$ indices are rejected; if $\widehat k_q=0$ the rejection set is empty. Also $\widehat k_q>0$ if and only if $\exists k:p_{(k)}\le qk/n$. Hence $\mathbb E[D_n\mid\omega]=F_q(M^\sigma(C_{1:n,1:n}))$, and this is Borel in $\omega$ by Step 2. Integrating gives $\mathcal F_n(P;q,\sigma)=\Phi_{n,\sigma}(P;q)$ for every $P\in\mathfrak P_0$ and $n\ge1$.

Since $0<\sigma<1$ and $q\in(0,1/4]\subset(0,1/2)$, part 1 of [the approved array compactification](gaussian_bh_exchangeable_array_variational_compactification.md) applies. It gives the following on all of $\mathfrak P$, with the same finite-subarray weak topology as that used here: $\mathcal F_n(P;q,\sigma)\to\mathcal F(P;q,\sigma)$ uniformly in $P\in\mathfrak P$, and $\mathcal F(\cdot\,;q,\sigma)$ is continuous on $\mathfrak P$ (joint continuity in $(P,q)$ restricts to continuity in $P$). Restricting to the subspace $\mathfrak P_0$, the limit $\Phi_\sigma(P;q)=\lim_n\Phi_{n,\sigma}(P;q)=\mathcal F(P;q,\sigma)$ exists. The convergence is uniform over $\mathfrak P_0\subset\mathfrak P$, and $\Phi_\sigma(\cdot\,;q)$ is continuous on $\mathfrak P_0$. The map $t\mapsto S_tP$ is continuous from $[0,1]$ to $\mathfrak P_0$ by Step 4. So $f^\sigma_{P,q}=\Phi_\sigma(\cdot\,;q)\circ(t\mapsto S_tP)$ is continuous on $[0,1]$.

**Step 6 (Part 3).** Fix $P\in\mathfrak P_0$ and $n\ge1$. By definition of the push-forward,
$$
\Phi_{n,\sigma}(S_1P;q)=\mathbb E_{\omega\sim P}\,F_q\bigl(M^\sigma((S_1C)_{1:n,1:n})\bigr).
$$
Fix $\omega$ and put $M=M^\sigma((S_1C)_{1:n,1:n})$. By Step 4, $(S_1C)_{1:n,1:n}\in\mathcal C_n$, so $M\in\mathcal C_n$. For $i\ne j$, $(S_1C)_{ij}=C_{ij}^2\ge0$, so $M_{ij}=(1-\sigma^2)C_{ij}^2+\sigma^2\ge0$. Let $T\sim\mathcal N_n(0,M)$ and $p_i=\overline\Phi(T_i)$. The vector $T$ is jointly Gaussian with unit variances, so its correlation matrix is $M$. Every $p_i=f(T_i)$ for the single nonincreasing measurable function $f=\overline\Phi$. So $p$ is Gaussian dependent with Gaussian correlation $M$. Each $T_i\sim\mathcal N(0,1)$ gives $p_i$ uniform on $[0,1]$. Thus $p\in\mathcal G_M\cap\mathcal U^n$, and $M$ has nonnegative off-diagonal entries. Moreover $\{\exists k:p_{(k)}\le qk/n\}=\{\min_k(n/k)p_{(k)}\le q\}=\{\mathrm{Simes}_n(p)\le q\}$ with $\mathrm{Simes}_n$ the Simes function $S_n$ of the library definition (renamed here to avoid a clash with the Schur map $S_t$). Since $q\in(0,1)$, [the positive-Gaussian Simes theorem](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) gives $F_q(M)\le q$. Averaging over $\omega$ gives $\Phi_{n,\sigma}(S_1P;q)\le q$ for every $n$. Since $S_1P\in\mathfrak P_0$ (Step 4), letting $n\to\infty$ and using Step 5 gives $\Phi_\sigma(S_1P;q)\le q$.

**Step 7 (Part 4: embedding).** Fix $N\ge1$ and $\Sigma\in\mathcal C_N$, with $I_1,I_2,\ldots$ iid uniform on $[N]$. The array $C_{ab}=\Sigma_{I_aI_b}$ is a measurable function of $(I_a)$. It has $C_{aa}=\Sigma_{I_aI_a}=1$, it is symmetric, and its entries lie in $[-1,1]$, since $|\Sigma_{ij}|\le\sqrt{\Sigma_{ii}\Sigma_{jj}}=1$ by positive semidefiniteness. Each principal matrix $(\Sigma_{I_aI_b})_{a,b\le n}=E^{\mathsf T}\Sigma E$, where $E$ is the $N\times n$ matrix with columns $e_{I_1},\ldots,e_{I_n}$, is positive semidefinite. With the all-null marks, the array is lawful. A finitary relabeling $\tau$ maps it to the array built from $(I_{\tau(a)})$, which has the same iid law. So $P_\Sigma$ is jointly exchangeable and all-null, i.e. $P_\Sigma\in\mathfrak P_0$. By Step 4 applied to $\Sigma$, $R^\Sigma_t=(1-t)\Sigma+t(\Sigma\circ\Sigma)\in\mathcal C_N$, and $(R^\Sigma_t)_{ij}=g_t(\Sigma_{ij})$ for all $i,j$, using $g_t(1)=1$ on the diagonal. For $a\ne b$, $g_t(C_{ab})=g_t(\Sigma_{I_aI_b})=(R^\Sigma_t)_{I_aI_b}$. This also holds when $I_a=I_b$, where both sides equal $1$. Hence $S_t$ maps the array of $P_\Sigma$ built from $(I_a)$ to the array of $P_{R^\Sigma_t}$ built from the same $(I_a)$, so $S_tP_\Sigma=P_{R^\Sigma_t}$.

**Step 8 (Part 4: value of the embedded functional).** Fix $N\ge1$ and $\Sigma'\in\mathcal C_N$, and put $\Gamma=M^\sigma(\Sigma')\in\mathcal C_N$. We show $\Phi_\sigma(P_{\Sigma'};q)=F_q(\Gamma)$. By Step 5 the limit $\Phi_\sigma(P_{\Sigma'};q)=\lim_n\Phi_{n,\sigma}(P_{\Sigma'};q)$ exists, so it suffices to identify $\lim_n\Phi_{n,\sigma}(P_{\Sigma'};q)$ for this one fixed law. No uniformity in $\Sigma'$, $t$ or $N$ is needed.

Under $P_{\Sigma'}$, conditionally on $I=(I_a)$, the matrix $M^\sigma(C_{1:n,1:n})$ has entries $(1-\sigma^2)\Sigma'_{I_aI_b}+\sigma^2=\Gamma_{I_aI_b}$. This includes the diagonal and ties $I_a=I_b$, where both sides equal $1$. So it equals $E^{\mathsf T}\Gamma E$. Let $Y\sim\mathcal N_N(0,\Gamma)$ be independent of $I$. Conditionally on $I$, $(Y_{I_a})_{a\le n}\sim\mathcal N_n(0,E^{\mathsf T}\Gamma E)$. Hence
$$
\Phi_{n,\sigma}(P_{\Sigma'};q)=\mathbb E\,F_q(E^{\mathsf T}\Gamma E)=\mathbb P\bigl(\text{the size-}n\text{ Simes event holds for }p_a=\pi_{I_a},\ a\le n\bigr),\qquad\pi_j=\overline\Phi(Y_j).
$$
For a weight vector $m\in[0,1]^N$ and $\pi\in(0,1)^N$, put $L_j(m,\pi)=\sum_{i=1}^Nm_i\mathbf 1\{\pi_i\le\pi_j\}-\pi_j/q$ and $\mathcal E(m,\pi)=\{\exists j:m_j>0,\ L_j(m,\pi)\ge0\}$. Let $m^{(n)}_j=n^{-1}\#\{a\le n:I_a=j\}$, and let $G(x)=n^{-1}\#\{a\le n:p_a\le x\}=\sum_im^{(n)}_i\mathbf 1\{\pi_i\le x\}$.

*Claim: the size-$n$ Simes event for $(p_a)$ is $\mathcal E(m^{(n)},\pi)$.* Suppose $p_{(k)}\le qk/n$. Write $p_{(k)}=p_a=\pi_j$ with $j=I_a$, so $m^{(n)}_j>0$. At least $k$ of the $p$'s are $\le\pi_j$, so $G(\pi_j)\ge k/n\ge\pi_j/q$, i.e. $L_j\ge0$. Conversely, suppose $m^{(n)}_j>0$ and $G(\pi_j)\ge\pi_j/q$. Then $c=nG(\pi_j)$ is an integer, and $c\ge1$ because some $p_a=\pi_j$. At least $c$ of the $p$'s are $\le\pi_j$, so $p_{(c)}\le\pi_j\le qG(\pi_j)=qc/n$. The same argument with $n=N$ and the identity labeling shows that $\mathcal E(u,\pi)$, with $u=(1/N,\ldots,1/N)$, is the size-$N$ Simes event for $(\pi_1,\ldots,\pi_N)$. So $\mathbb P(\mathcal E(u,\pi))=F_q(\Gamma)$.

*Local constancy at $u$.* Fix $\pi$ with $L_j(u,\pi)\ne0$ for all $j$. Each $L_j(\cdot,\pi)$ is affine in $m$ with coefficients in $[0,1]$. So if $\|m-u\|_\infty<\delta(\pi)=\min\{1/N,\min_j|L_j(u,\pi)|/N\}$, then $m_j>0$ for every $j$ and $L_j(m,\pi)$ has the same sign as $L_j(u,\pi)$ for every $j$. Hence $\mathbf 1_{\mathcal E(m,\pi)}=\mathbf 1_{\mathcal E(u,\pi)}$. The exceptional set is $\{\exists j:L_j(u,\pi)=0\}$. There $\pi_j=qc/N$ with $c=\#\{i:\pi_i\le\pi_j\}\in\{1,\ldots,N\}$, so $Y_j=\overline\Phi^{-1}(qc/N)$. Since each $Y_j\sim\mathcal N(0,1)$, this finite union of marginal hyperplanes has probability zero. Singular $\Gamma$ and clone ties are allowed here.

*Limit.* By the strong law of large numbers, $m^{(n)}\to u$ almost surely, and $I$ is independent of $Y$. So almost surely $\pi$ lies outside the exceptional set and $\|m^{(n)}-u\|_\infty<\delta(\pi)$ for all large $n$. Hence $\mathbf 1_{\mathcal E(m^{(n)},\pi)}\to\mathbf 1_{\mathcal E(u,\pi)}$ almost surely. Bounded convergence gives $\Phi_{n,\sigma}(P_{\Sigma'};q)\to F_q(\Gamma)$, and so $\Phi_\sigma(P_{\Sigma'};q)=F_q(M^\sigma(\Sigma'))$.

Now fix $\Sigma\in\mathcal C_N$ and $t\in[0,1]$. Steps 7 and 8 with $\Sigma'=R^\Sigma_t\in\mathcal C_N$ give
$$
f^\sigma_{P_\Sigma,q}(t)=\Phi_\sigma(S_tP_\Sigma;q)=\Phi_\sigma(P_{R^\Sigma_t};q)=F_q\bigl((1-\sigma^2)R^\Sigma_t+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}\bigr).
$$
This proves Part 4.

**Step 9 (Part 5).** $\Phi_\sigma(\cdot\,;q)$ is continuous on the compact space $\mathfrak P_0$ (Steps 3 and 5), so it attains its maximum. *Lower bound.* For every $N$ and $\Sigma\in\mathcal C_N$, Step 8 with $\Sigma'=\Sigma$ (equivalently Part 4 at $t=0$, $R^\Sigma_0=\Sigma$) gives $\Phi_\sigma(P_\Sigma;q)=F_q(M^\sigma(\Sigma))$. Hence $\max_{\mathfrak P_0}\Phi_\sigma\ge\sup_N\sup_\Sigma F_q(M^\sigma(\Sigma))=B^\sigma(q)$. *Upper bound.* For every lawful $\omega$, not only almost every one, $C_{1:n,1:n}\in\mathcal C_n$. So $F_q(M^\sigma(C_{1:n,1:n}))\le\sup_{\Sigma\in\mathcal C_n}F_q(M^\sigma(\Sigma))\le B^\sigma(q)$. Integrating gives $\Phi_{n,\sigma}(P;q)\le B^\sigma(q)$ for every $n$ and $P\in\mathfrak P_0$, and letting $n\to\infty$ gives $\Phi_\sigma(P;q)\le B^\sigma(q)$. Therefore $\max_{P\in\mathfrak P_0}\Phi_\sigma(P;q)=B^\sigma(q)$.

**Step 10 (Part 6).** For every $N$ and $\Sigma\in\mathcal C_N$, $M^\sigma(\Sigma)\in\mathcal C_N$, so $F_q(M^\sigma(\Sigma))\le B(q)$. Taking suprema gives $B^\sigma(q)\le B(q)\le1$ for every $\sigma\in(0,1)$, and so $\limsup_{\sigma\downarrow0}B^\sigma(q)\le B(q)$. Conversely, fix $N$ and $\Sigma\in\mathcal C_N$. As $\sigma\downarrow0$, $M^\sigma(\Sigma)\to\Sigma$ in $\mathcal C_N$, so Step 2 gives $F_q(M^\sigma(\Sigma))\to F_q(\Sigma)$. Since $B^\sigma(q)\ge F_q(M^\sigma(\Sigma))$, $\liminf_{\sigma\downarrow0}B^\sigma(q)\ge F_q(\Sigma)$. Taking the supremum over $N$ and $\Sigma$ gives $\liminf_{\sigma\downarrow0}B^\sigma(q)\ge B(q)$. This uses only one fixed finite model at a time, so no uniformity in $N$ is required. Hence $\lim_{\sigma\downarrow0}B^\sigma(q)=B(q)$. $\blacksquare$
