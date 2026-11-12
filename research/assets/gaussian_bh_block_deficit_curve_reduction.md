---
type: lemma
title: Block deficit-curve reduction for Gaussian BH
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - gaussian_multifactor_representation
tags:
  - gaussian_bh
  - two_sided
  - deficit_curve
  - extracted_unverified
---

## Source

Extracted verbatim from [the central deficit-curve plan](../plans/plan_two_sided_central_deficit_curve_lei_20261105.md), Fixed notation, Plan step 3(i)–(iii), and Progress / Step 3 (curve reduction): complete proof (lines 175–191). The source plan failed at a later step; this extracted lemma has not been independently verified.

## Local notation

- $p(u)=2\overline\Phi(u)$, $\phi$ the standard normal density, $U=p^{-1}(q)$, $t_k=qk/N$, $u_k=p^{-1}(t_k)$ (so $u_k$ decreases in $k$ and $u_k\ge U$ for all $k\le N$), $J=\lceil\sqrt U\rceil$, $K=8\log U$, $L=K+\sqrt U$ (Lei's (204) constants $K_q,L_q$ are used as in the source).
- $\rho_r(u,z)=[\overline\Phi(\frac{u-rz}s)+\overline\Phi(\frac{u+rz}s)]/p(u)$, $s=\sqrt{1-r^2}$ (for $r=1$: $\mathbf 1\{|z|\ge u\}/p(u)$), $\gamma_r=\sqrt{(1-r)/(1+r)}$. $\rho_r$ is even in $z$, $\rho_r\ge0$ and $\int\phi(z)\rho_r(u,z)\,dz=1$ for every $u$.
- Class $\mathfrak B$: independent one-factor blocks, $T_j=\theta_j+a_jZ_{g(j)}+\sqrt{1-a_j^2}\,\varepsilon_j$, $a_j\in[-1,1]$, $G\ge1$ blocks, all $Z_h,\varepsilon_j$ independent. For a null $i$ in block $g$ with $\theta_i=0$: $r=|a_i|$, *mates* $=B_g\setminus\{i\}$, *background* $=$ coordinates outside $B_g$. Given $Z=z$ all $T_j$ are independent.
- For a null $i$ and $z=Z_g$: $M_z(k)=\#\{j\in B_g\setminus\{i\}:P_j\le t_k\}$, $\beta(k)=\#\{\ell\notin B_g:P_\ell\le t_k\}$ (independent of $(Z_g,\varepsilon_j)_{j\in B_g}$), $D(k)=k-1-\beta(k)$, $D^*(k)=\min_{k\le j\le N}D(j)$.
- A *universal constant* $C$ does not depend on $q,N,\theta,\Sigma$, block data or loadings. Every $\eta(q)$ depends on $q$ only and tends to $0$.
- **The central quantity.** $\Delta^{\rm c}_i:=\mathbb E\big[(\rho_r(u_{R_i},Z_g)-\rho_r(u_{R^\flat_i},Z_g))\mathbf 1\{|Z_g|\le U\}\big]$.

*Class of curves.* $\mathcal D_N$: nondecreasing $D^*:\{1,\dots,N\}\to\mathbb Z$ with $D^*(k+1)-D^*(k)\in\{0,1\}$, $D^*(k)\le k-1$, $k_f:=\max\{k:D^*(k)\le0\}\ge1$ (so $D^*(k)\ge1$ for $k>k_f$).

$$
\Delta^{\rm c}(D^*)\ :=\ \int_{-U}^U\phi(z)\,\mathbb E\big[\rho_r(u_{R(z)},z)-\rho_r(u_{k_f},z)\big]\,dz .
$$

## Statement

Setting. Block $B_g\ni i$ null; $P_j=p(|T_j|)$; $t_k=qk/N$ strictly increasing; $\beta(k)=\#\{\ell\notin B_g:P_\ell\le t_k\}$ (integer, nondecreasing, $0\le\beta\le N-|B_g|$), $M(k)=M_z(k)=\#\{j\in B_g\setminus\{i\}:P_j\le t_k\}$ (integer, nondecreasing in $k$), $D(k)=k-1-\beta(k)\in\mathbb Z$, $D^*(k)=\min_{k\le j\le N}D(j)$. All counts use closed inequalities $P\le t_k$ and BH takes the largest qualifying rank, so ties among p-values and with the $t_k$ are handled by the same convention throughout; no probability-zero event is discarded.

(i) $R_i=\max\{k\le N:1+\beta(k)+M_z(k)\ge k\}=\max\{k:M_z(k)\ge D(k)\}$ and $R^\flat_i=\max\{k:D(k)\le0\}$; $R^\flat_i\ge1$ because $D(1)=-\beta(1)\le0$.

(ii) $D^*$ is nondecreasing, $D^*(k+1)-D^*(k)\in\{0,1\}$, $D^*\le D\le k-1$, $D^*(k)\le0$ iff $k\le R^\flat_i$, $D^*(k)\ge1$ for $k>R^\flat_i$, and $R_i=\max\{k:M_z(k)\ge D^*(k)\}$.

(iii) *Consequence.* The background enters $R_i$ only through the curve $D^*$ (nondecreasing in $k$, so a nonincreasing function of the level $u_k$), and $D^*$ is independent of $(Z_g,(\varepsilon_j)_{j\in B_g})$. Hence a bound for $\Delta^{\rm c}_i$ valid for every deterministic nondecreasing integer curve $D^*\le k-1$ with $D^*(k)\le 0$ exactly for $k\le k_f=R^\flat$ and unit increments implies the bound for every random background (Fubini over $\beta$).

## Proof

Fix $N\ge1$, $q\in(0,1)$ and a model in the stated independent one-factor-block class $\mathfrak B$. All comparisons below are closed. We first work deterministically with realized p-values.

**Closed counts and forced-zero ranks.** For any p-value vector $v\in[0,1]^N$, put $C_v(k)=\#\{j:v_j\le t_k\}$. With multiplicities included, $v_{(k)}\le t_k$ if and only if $C_v(k)\ge k$. Thus the step-up rank is the largest qualifying $k$, or zero when none qualifies. If this rank is $h>0$, let $c=C_v(h)\ge h$. Were $c>h$, we would have $v_{(c)}\le t_h\le t_c$, contradicting maximality of $h$. Hence $c=h$, so the rejection count equals the maximal qualifying rank, including ties. At rank zero the rejection set is empty by definition.

With coordinate $i$ forced to zero the closed count is $1+\beta(k)+M_z(k)$ and rank $1$ qualifies. Consequently

$$
R_i=\max\{k:1+\beta(k)+M_z(k)\ge k\}
=\max\{k:M_z(k)\ge D(k)\}.
$$

For the mate-removed count, retain $N$ and the thresholds $qk/N$; equivalently set the mate coordinates to $1$, which exceeds every $t_k\le q<1$. Its count is $1+\beta(k)$, giving

$$
R_i^\flat=\max\{k:D(k)\le0\}\ge1,
$$

since $D(1)=-\beta(1)\le0$. This proves (i).

**Suffix envelope and baseline interval.** The integer nondecreasing vector $\beta$ gives

$$
D(k)\le k-1,\qquad
D(k+1)-D(k)=1-(\beta(k+1)-\beta(k))\le1.
$$

Every suffix is finite and nonempty, so its minimum is attained and integer valued. Shrinking the suffix gives $D^*(k)\le D^*(k+1)$, and

$$
D^*(N)=D(N),\qquad
D^*(k)=\min\{D(k),D^*(k+1)\},\qquad D^*(k)\le D(k).
$$

If $D^*(k+1)=D^*(k)$ their increment is zero. Otherwise the recursion gives $D^*(k)=D(k)<D^*(k+1)$, while

$$
D^*(k+1)\le D(k+1)\le D(k)+1.
$$

The positive integer increment must therefore be $1$. This proves the envelope and unit-increment assertions, without requiring $D$ itself to be nondecreasing.

Write $k_f=\max\{k:D(k)\le0\}=R_i^\flat$. If $k\le k_f$, the suffix contains $k_f$, and $D^*(k)\le D(k_f)\le0$. If $k>k_f$, maximality of $k_f$ makes every $D(j)$ for $j\ge k$ a strictly positive integer; hence $D^*(k)\ge1$. We have proved

$$
D^*(k)\le0\quad\Longleftrightarrow\quad k\le k_f,
$$

including the asserted strict positivity beyond $k_f$. In particular $D^*\in\mathcal D_N$ with exactly this baseline endpoint.

**Equality of maximal ranks.** Let

$$
A=\{k:M_z(k)\ge D(k)\},\qquad
A^*=\{k:M_z(k)\ge D^*(k)\}.
$$

Both contain $1$, and $A\subseteq A^*$ because $D^*\le D$. Conversely, given any $k\in A^*$, choose a suffix minimizer $j\ge k$ with $D(j)=D^*(k)$. Monotonicity of the mate count yields

$$
M_z(j)\ge M_z(k)\ge D^*(k)=D(j),
$$

so $j\in A$ and $\max A\ge j\ge k$. Taking the largest $k\in A^*$ proves $\max A\ge\max A^*$; the opposite inequality follows from inclusion. Thus

$$
R_i=\max\{k:M_z(k)\ge D^*(k)\}.
$$

Only the maxima have been equated, not the qualifying sets at every rank. This completes (ii). It also shows $R_i\ge k_f$, because every $k\le k_f$ qualifies for $A^*$. For completeness, $R_i$ is a right endpoint of a plateau of $D^*$: if $R_i<N$ and $D^*(R_i+1)=D^*(R_i)$, then

$$
M_z(R_i+1)\ge M_z(R_i)\ge D^*(R_i)=D^*(R_i+1),
$$

contradicting maximality. When $R_i=N$ it is already the domain endpoint. Likewise $k_f<N$ implies $D^*(k_f)\le0<D^*(k_f+1)$, so $k_f$ is a right plateau endpoint; the increment property then gives $D^*(k_f)=0$ and $D^*(k_f+1)=1$. When $k_f=N$, no value at $N+1$ is needed. If $N=1$, then $D^*(1)=0$ and both ranks are $1$. Empty background gives $D^*(k)=k-1$, $k_f=1$; a singleton selected block has $M_z\equiv0$ and hence $R_i=R_i^\flat$. These cases also follow directly from the preceding arguments.

**Independence of the entire selected-block tuple.** Let $\mathcal F_{\rm out}$ be generated by $(Z_h)_{h\ne g}$ and $(\varepsilon_\ell)_{\ell\notin B_g}$, and let $\mathcal F_{\rm in}$ be generated by $Z_g$ and $(\varepsilon_j)_{j\in B_g}$. They are independent sigma-fields because their primitive random variables are disjoint subfamilies of the mutually independent variables in $\mathfrak B$. For each $\ell\notin B_g$, $T_\ell$ is an affine measurable function of $\mathcal F_{\rm out}$-measurable primitives and deterministic means and loadings. Thus $P_\ell$, the full background count vector $\beta=(\beta(1),\ldots,\beta(N))$, and its deterministic transform $D^*$ are $\mathcal F_{\rm out}$-measurable. This proves independence of $D^*$, and also of $\beta$, from the full tuple $(Z_g,(\varepsilon_j)_{j\in B_g})$. Conditional on a positive-probability value of $\beta$, this tuple retains its original product standard-normal law. The argument uses no inverse covariance or positive residual variance, so it includes arbitrary means, both loading orientations, zero and unit loadings, conditionally deterministic coordinates, singular Gaussian laws, every finite number of blocks and the deterministic empty background.

**Signed conditioning and Fubini.** For any deterministic $d\in\mathcal D_N$, write $e=(\varepsilon_j)_{j\in B_g\setminus\{i\}}$ and define the mate count $M_z(k;e)$ using the stated block formula, and

$$
R_d(z,e)=\max\{k:M_z(k;e)\ge d(k)\},\qquad
k_f(d)=\max\{k:d(k)\le0\}.
$$

Both maxima exist since $d(1)\le0\le M_z(1;e)$. Each threshold indicator is Borel measurable in $(z,e)$, including at zero or unit loadings. Taking finite maxima preserves measurability, so $R_d$ is measurable. For $r<1$, the numerator of $\rho_r(u_k,z)$ is the probability of the event $|rz+\sqrt{1-r^2}\varepsilon|\ge u_k$ for a standard normal $\varepsilon$. Its two tails are disjoint because $u_k>0$, so the numerator lies in $[0,1]$. For $r=1$, the displayed closed-threshold indicator in Local notation has the same bound; for $r=0$ the ratio is identically $1$. Therefore, for every $k\ge1$ and $z$,

$$
0\le\rho_r(u_k,z)\le\frac1{p(u_k)}=\frac1{t_k}\le\frac Nq.
$$

All these functions are Borel, including the indicator at $r=1$. In particular the signed central integrand satisfies

$$
\left|\bigl(\rho_r(u_{R_d(z,e)},z)-\rho_r(u_{k_f(d)},z)\bigr)
\mathbf1\{|z|\le U\}\right|\le\frac{2N}{q}.
$$

This bound is finite for the fixed $N,q$ and establishes absolute integrability under all probability measures used here.

The vector $\beta$ has finite range. For each value $b$ with positive probability, put $d_b(k)=\min_{j\ge k}(j-1-b(j))$. The preceding deterministic results give $d_b\in\mathcal D_N$, $R_i=R_{d_b}(Z_g,e)$ and $R_i^\flat=k_f(d_b)$ conditional on $\beta=b$. Independence supplies the product law of $Z_g$ and the mate residuals under this conditioning. Bounded signed Fubini and conditioning yield

$$
\begin{aligned}
\Delta_i^{\rm c}
&=\sum_{b:\,\mathbb P(\beta=b)>0}\mathbb P(\beta=b)
  \int_{-U}^{U}\phi(z)\,
  \mathbb E_e\!\left[\rho_r(u_{R_{d_b}(z,e)},z)
       -\rho_r(u_{k_f(d_b)},z)\right]dz\\
&=\mathbb E_\beta\!\left[\Delta^{\rm c}(D^*(\beta))\right].
\end{aligned}
$$

Here $\mathbb E_e$ is solely over the mate residuals; an empty mate vector has its point-mass law. The unused residual $\varepsilon_i$ integrates out. Null-probability values of $\beta$ contribute nothing, and no tie event has been discarded. A common deterministic bound for every curve in $\mathcal D_N$ therefore transfers to the random background by expectation. The integrability bound need not be uniform as $N$ varies.

Finally, both ranks depend on the background only through $D^*$, including its nonpositive-interval endpoint $k_f$. Since $u_k$ strictly decreases with $k$, a nondecreasing $D^*(k)$ is nonincreasing as a function on the discrete levels $u_k$. This proves exactly (iii). The proof uses only the declared approved definitions and local setup, for the full stated finite-$N$ block class, and requires no small-$q$ restriction or tail-ratio bound. $\square$

## Extracted source candidate (historical)

Setting. Block $B_g\ni i$ null; $P_j=p(|T_j|)$; $t_k=qk/N$ strictly increasing; $\beta(k)=\#\{\ell\notin B_g:P_\ell\le t_k\}$ (integer, nondecreasing, $0\le\beta\le N-|B_g|$), $M(k)=M_z(k)=\#\{j\in B_g\setminus\{i\}:P_j\le t_k\}$ (integer, nondecreasing in $k$), $D(k)=k-1-\beta(k)\in\mathbb Z$, $D^*(k)=\min_{k\le j\le N}D(j)$. All counts use closed inequalities $P\le t_k$ and BH takes the largest qualifying rank, so ties among p-values and with the $t_k$ are handled by the same convention throughout; no probability-zero event is discarded.

(i) $R_i:=\max\{k:\ \#\{\ell:\ P_\ell\le t_k\}\ \text{with } P_i\text{ replaced by }0\ \ge k\}=\max\{k:1+\beta(k)+M(k)\ge k\}=\max\{k:M(k)\ge D(k)\}$; the set contains $k=1$ ($1\ge1$), so $R_i\ge1$. (BH0, recheck.) Let $S(k)=\beta(k)+M(k)+\mathbf 1\{P_i\le t_k\}$ be the true count and $S^0(k)=\beta(k)+M(k)+1$ the count with $P_i\to0$; $S\le S^0$. If $P_i\le t_{R_i}$: for $k\ge R_i$, $\mathbf 1\{P_i\le t_k\}=1$ so $S(k)=S^0(k)$; hence $S(k)<k$ for $k>R_i$ and $S(R_i)\ge R_i$, so $R=R_i$ and $i$ is rejected ($P_i\le t_R$). If $P_i>t_{R_i}$: $S\le S^0$ gives $S(k)<k$ for $k>R_i$, so $R\le R_i$, and $t_R\le t_{R_i}<P_i$, so $i$ is not rejected. So $i$ is rejected iff $P_i\le t_{R_i}$, and then $R=R_i$ (including the case $R=0$, which only happens when $i$ is not rejected, and singular $\Sigma$: nothing about $\Sigma$ was used). The forced-zero rank without mates is $R^\flat_i:=\max\{k:1+\beta(k)\ge k\}=\max\{k:D(k)\le0\}$ ($M\equiv0$); $D(1)=-\beta(1)\le0$ so $R^\flat_i\ge1$.

(ii) Facts about $D^*$.
 1. $D^*$ is integer valued, nondecreasing (min over a smaller set as $k$ grows), $D^*(N)=D(N)$ and $D^*(k)=\min\{D(k),D^*(k+1)\}$.
 2. $D^*\le D\le k-1$ because $\beta\ge0$.
 3. Increments in $\{0,1\}$: $D(k+1)-D(k)=1-(\beta(k+1)-\beta(k))\le1$. If $D^*(k)=D^*(k+1)$ done. Otherwise $D^*(k)=D(k)<D^*(k+1)\le D(k+1)\le D(k)+1$; integers force $D^*(k+1)=D^*(k)+1$.
 4. $D^*(k)\le0\iff k\le R^\flat_i$: if $k\le R^\flat_i$ then $D^*(k)\le D(R^\flat_i)\le0$. If $k>R^\flat_i$ every $D(j)$, $j\ge k$, is an integer $>0$ (maximality of $R^\flat_i$), so $D^*(k)\ge1$. Together with 3: $D^*(R^\flat_i)=0$, $D^*(R^\flat_i+1)=1$ (when $R^\flat_i<N$).
 5. $R_i=\max\{k:M(k)\ge D^*(k)\}$. "$\le$": $M(k)\ge D(k)\ge D^*(k)$. "$\ge$": let $k^*$ be the largest $k$ with $M(k)\ge D^*(k)$ (nonempty: $k=1$ since $D^*(1)\le D(1)\le0\le M(1)$) and pick $j\ge k^*$ with $D(j)=D^*(k^*)$. By monotonicity of $M$, $M(j)\ge M(k^*)\ge D^*(k^*)=D(j)\ge D^*(j)$; so $j$ is in the set, and $j\le k^*$ by maximality, so $j=k^*$ and $M(k^*)\ge D(k^*)$, i.e. $k^*\le R_i$.
 6. Consequently $R_i\ge R^\flat_i$ (for $k\le R^\flat_i$, $D^*(k)\le0\le M(k)$), and $R_i=R^\flat_i$ iff $M(k)<D^*(k)$ for all $k>R^\flat_i$.

(iii) The background enters only through $D^*$. $\beta$ depends on $(T_\ell)_{\ell\notin B_g}$, which is independent of $(Z_g,(\varepsilon_j)_{j\in B_g})$ in the class $\mathfrak B$, and $M$ depends only on the latter. Hence conditionally on $\beta$ the pair $(R_i,R^\flat_i)$ is the pair $(R(z),k_f)$ of DCL for the deterministic curve $D^*(\beta)\in\mathcal D_N$ ($D^*$ integer, nondecreasing, increments in $\{0,1\}$, $D^*\le k-1$, $k_f=R^\flat_i\ge1$). Any bound for $\Delta^{\rm c}(D^*)$ valid for every element of $\mathcal D_N$ gives, by Fubini over $\beta$, the same bound for $\Delta^{\rm c}_i=\mathbb E_\beta\Delta^{\rm c}(D^*(\beta))$. $\square$ (Checked: the empty-background case gives $D^*(k)=k-1$, $k_f=1$.)

Remark (not a proof step): the integer constraints in $\mathcal D_N$ are exactly what step 6a uses: $R(z)$ is a right end of a plateau of $D^*$ (if $M(k)\ge D^*(k)$ and $D^*(k+1)=D^*(k)$ then $M(k+1)\ge M(k)\ge D^*(k+1)$).
