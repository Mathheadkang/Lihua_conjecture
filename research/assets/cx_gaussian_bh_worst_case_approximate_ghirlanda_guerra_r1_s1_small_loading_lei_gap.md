---
type: example
title: >-
  Counterexample to gaussian_bh_worst_case_approximate_ghirlanda_guerra: Small
  common loading with Lei's gap, where GG-approximate arrays cannot reach
  W_sigma(q)
status: approved
source:
  kind: original
refutes: gaussian_bh_worst_case_approximate_ghirlanda_guerra
depends_on: []
uses_definitions:
  - gaussian_bh_marked_exchangeable_parameter_array
  - gaussian_worst_case_bh_fdr
tags: []
---

## Statement

Fix any level $q\in(0,q_{\max}]$, for instance $q=1/20$. By the approved [Lei lower bound](../assets/lei2026_one_sided_fdr_lower.md) there is a finite model $(N,\theta^{L},\Sigma^{L})$ with $\Sigma^L$ positive definite, nulls $\theta^L_i=0$ and alternatives $\theta^L_i>0$, and
$$
\operatorname{FDR}^{(1)}_{\rm BH}(q;N,\theta^L,\Sigma^L)>\tfrac12\bigl(\ell_{\le}(q)+q\bigr)>q .
$$
Here $\ell_\le(q)>q$ because $\log(1/q)>\pi/4$ for $q\le q_{\max}\approx0.1587$. Take $\sigma\in(0,\sigma_0(q))$, where $\sigma_0(q)>0$ is chosen so that $W_\sigma(q)>q$ for all $0<\sigma<\sigma_0(q)$ (existence is shown under NOT). The object is the parameter pair $(\sigma,q)$.

## Assumptions

### H1

$0<\sigma<\sigma_0(q)\le1$. Pass.

### H2

$0<q\le q_{\max}$ by choice. Pass.

## Calculation

We show that no sequence $(P_k)$ in $\mathfrak P$ with $\Delta_{P_k}(n,f,\psi)\to0$ for every $n,f,\psi$ can have $\mathcal F(P_k;q,\sigma)\to W_\sigma(q)$. The proof has two parts: (A) $W_\sigma(q)>q$, and (B) every such GG-approximate sequence has $\limsup_k\mathcal F(P_k;q,\sigma)\le q$.

**(A) $W_\sigma(q)>q$ for small $\sigma$.** The Lei model with residual matrix $C=\Sigma^L$ (unit diagonal, PSD) and canonical tags is admissible in the finite common-loading supremum, so $W_\sigma(q)\ge\operatorname{FDR}^{(1)}_{\rm BH}(q;N,\theta^L,(1-\sigma^2)\Sigma^L+\sigma^2\mathbf1\mathbf1^{\mathsf T})$. Since $\Sigma^L$ is positive definite, the Gaussian densities converge pointwise as $\sigma\downarrow0$, so the laws converge in total variation (Scheffé). The FDP is a bounded measurable function of $T$, so the right side tends to the Lei FDR, which is $>(\ell_\le(q)+q)/2>q$. Item 5 of the compactification gives the same through $W_\sigma(q)\to F_1(q)\ge\ell_\le(q)$.

**(B) GG-approximate sequences have value at most $q$.**

1. *Mark compactification.* Let $\bar E$ be the closure of $E_{\rm mark}$ in $[-\infty,\infty]\times\{0,1\}$, so $\theta\in[-\infty,0]$ if $\ell=1$ and $\theta\in[0,\infty]$ if $\ell=0$. Then $\bar E^{\mathbb N}\times[-1,1]^{\mathbb N\times\mathbb N}$ is compact metrizable, so along a subsequence $P_k\Rightarrow P_\infty$. The limit $P_\infty$ is jointly exchangeable, its $C$-array is a.s. symmetric and PSD with unit diagonal (these are closed conditions), and its marks may be infinite.
2. *Continuity of the finite conditional FDR.* For extended marks put $T_i=\theta_i+X_i$ with $X=A(C)g$. Here $A(C)$ is the PSD square root of $(1-\sigma^2)C_{1:n,1:n}+\sigma^2\mathbf1\mathbf1^{\mathsf T}$, which is continuous in $C$, and $g\sim\mathcal N_n(0,I)$. Set $p_i=\overline\Phi(T_i)\in[0,1]$, with $p_i=0$ or $1$ when $\theta_i=\pm\infty$. For fixed $g$, each $p_i$ is continuous in $(\theta_i,C)$. BH decisions depend only on the indicators $\mathbf 1\{p_i\le qk/n\}$. At a limit point these indicators are locally constant unless some $p_i=qk/n$. For finite $\theta_i$ this has probability $0$, since $X_i\sim\mathcal N(0,1)$ exactly (unit diagonal). For infinite $\theta_i$ it is impossible, since $qk/n\in(0,1/2)$. Tags are eventually constant in the discrete topology. Dominated convergence then shows that $\varphi_n(\theta_{1:n},\ell_{1:n},C)=\mathbb E[D_n\mid\omega]$ is continuous on the compact extended space. Hence $\mathcal F_n(P_k)\to\mathcal F_n(P_\infty):=\mathbb E_{P_\infty}\varphi_n$ along the subsequence.
3. *Uniform completion.* Item 1 of the compactification gives $\varepsilon_n=\sup_{P\in\mathfrak P}|\mathcal F_n(P;q,\sigma)-\mathcal F(P;q,\sigma)|\to0$, since $q<1/2$. Hence $\limsup_k\mathcal F(P_k)\le\mathcal F_n(P_\infty)+\varepsilon_n$ for every $n$, and so $\limsup_k\mathcal F(P_k)\le\liminf_n\mathcal F_n(P_\infty)$.
4. *Exact GG at the limit.* $\Delta_P(n,f,\psi)$ is a combination of expectations of bounded continuous functions of the subarray $C_{1:n+1,1:n+1}$, so $\Delta_{P_\infty}(n,f,\psi)=\lim_k\Delta_{P_k}(n,f,\psi)=0$ for all continuous $f,\psi$. Both sides are linear in $f$ and in $\psi$ and define finite signed measures, so a monotone-class argument extends the identities to bounded measurable $f,\psi$. The diagonal is identically $1$, so dependence of $f$ on it is immaterial. The $C$-array of $P_\infty$ is therefore a Gram-de Finetti array (Dovbysh-Sudakov representable; see the library node [lib_panchenko2009_dovbysh_sudakov_mixture](../library/panchenko2009_dovbysh_sudakov/assets/lib_panchenko2009_dovbysh_sudakov_mixture.md)) that satisfies the Ghirlanda-Guerra identities exactly.
5. *Positivity.* **External input, not in the library:** Talagrand's positivity principle states that an overlap array satisfying the Ghirlanda-Guerra identities has $C_{12}\ge0$ almost surely (Talagrand, *Mean Field Models for Spin Glasses*; Panchenko, *The Sherrington-Kirkpatrick Model*, 2013). No theorem number is asserted here, and it must be sourced. By exchangeability, $C_{ij}\ge0$ for all $i\ne j$, $P_\infty$-a.s. Panchenko's ultrametricity theorem would also make the array ultrametric, but only nonnegativity is used below.
6. *PRDS bound with composite and infinite nulls.* Fix $\omega$ in the full-measure set where $C_{1:n,1:n}$ has nonnegative entries. Then $\Sigma:=(1-\sigma^2)C+\sigma^2\mathbf1\mathbf1^{\mathsf T}$ has $\Sigma_{ij}\ge\sigma^2>0$ and $\Sigma_{ii}=1$. Fix a null index $i$, meaning $\ell_i=1$ and $\theta_i\in[-\infty,0]$.
   - If $\theta_i=-\infty$, then $p_i=1>qk/n$, so $i$ is never rejected.
   - If $\theta_i$ is finite, let $R=\widehat k_q$, the number of BH rejections. The variable $i$ is rejected iff $p_i\le qR/n$. $R$ is nondecreasing in every finite coordinate $T_j$, and coordinates with infinite marks are constants.
     - *Monotone conditioning.* Given $T_i=s$, the finite-mark coordinates are Gaussian with mean $\theta_j+\Sigma_{ji}(s-\theta_i)$, which is nondecreasing in $s$, and covariance free of $s$. This holds even when $\Sigma$ is singular. So $s\mapsto\Pr(R\le k\mid T_i=s)$ is nonincreasing. The law of $T_i$ given $T_i\ge s$ is stochastically increasing in $s$, so $G_k(t):=\Pr(R\le k\mid p_i\le t)$ is nondecreasing in $t$.
     - *Super-uniformity.* With $F(t)=\Pr(p_i\le t)=\overline\Phi(\overline\Phi^{-1}(t)+|\theta_i|)$, the ratio $F(t)/t$ is nondecreasing in $t$ and at most $1$. This holds because $\overline\Phi$ is log-concave: $u\mapsto\overline\Phi(u+a)/\overline\Phi(u)$ is nonincreasing for $a\ge0$.
     - *Summation.* Put $t_k=qk/n$, $a_k=F(t_k)/k$ (nondecreasing in $k$, $a_n\le q/n$) and $G_0\equiv0$. Then
$$
\mathbb E\frac{\mathbf 1\{p_i\le qR/n\}}{R\vee1}=\sum_{k=1}^n a_k\bigl[G_k(t_k)-G_{k-1}(t_k)\bigr]
\le\sum_{k=1}^n a_k\bigl[G_k(t_k)-G_{k-1}(t_{k-1})\bigr]
=a_nG_n(t_n)-\sum_{k<n}G_k(t_k)(a_{k+1}-a_k)\le\frac qn .
$$
   Summing over at most $n$ null tags gives $\varphi_n(\omega)\le q$. Non-null tags (including alternative-tagged zeros) contribute nothing to $D_n$.
7. Hence $\mathcal F_n(P_\infty)\le q$ for every $n$, and by step 3 $\limsup_k\mathcal F(P_k;q,\sigma)\le q$.

Combining (A) and (B), every GG-approximate sequence has $\limsup_k\mathcal F(P_k;q,\sigma)\le q<W_\sigma(q)$, so the required sequence does not exist. The conclusion fails for this $(\sigma,q)$. Pass, conditional only on the sourced positivity principle in step 5.

Remark. The same argument shows that the conclusion of this lemma, at any $(\sigma,q)$, forces $W_\sigma(q)\le q$. So the lemma fails at every $(\sigma,q)$ with $W_\sigma(q)>q$, which includes all $q\in(0,q_{\max}]$ with $\sigma<\sigma_0(q)$.

Promoted from search candidate cand_gaussian_bh_worst_case_approximate_ghirlanda_guerra_r1_s1_small_loading_lei_gap.

## Verdict

confirmed. Every step was rechecked from the statement of the lemma, the approved definitions, item 1 of the approved compactification, and the approved Lei lower bound. The positivity principle in step 5 is not in the library. It is not a remaining gap, though: in this setting it has the short self-contained proof below, which uses only exact GG, joint exchangeability, and the PSD unit-diagonal property of $P_\infty$. The quoted literature (Talagrand; Panchenko 2013) is background only, and no theorem number is asserted.

**Quantifiers.** The lemma asserts, for each fixed $0<\sigma<1$ and $0<q\le q_{\max}$, that there is a sequence $(P_k)\subset\mathfrak P$ with $\mathcal F(P_k;q,\sigma)\to W_\sigma(q)$ and $\Delta_{P_k}(n,f,\psi)\to0$ for every $n\ge2$ and all continuous $f,\psi$. The example fixes one such $(\sigma,q)$ and shows that every sequence with vanishing defects has $\limsup_k\mathcal F(P_k)\le q<W_\sigma(q)$. That is the negation of the conclusion.

**(A) $W_\sigma(q)>q$ for small $\sigma$.** We have $\ell_\le(q)\ge q\sqrt{\log(1/q)/\pi}+q/2>q$ as soon as $\log(1/q)>\pi/4$, i.e. $q<e^{-\pi/4}\approx0.456$, which covers $q\le q_{\max}\approx0.159$. The approved Lei node also states $\ell_\le(q)>q$. Apply it with $\delta=(\ell_\le(q)-q)/2$. This gives a finite model with positive definite $\Sigma^L$, null means $0$ and alternative means $>0$, and FDR $>(\ell_\le+q)/2$. With canonical tags it is admissible in $W_\sigma$, and its tagged FDR is $\operatorname{FDR}^{(1)}_{\rm BH}(q;N,\theta^L,(1-\sigma^2)\Sigma^L+\sigma^2\mathbf1\mathbf1^{\mathsf T})$. As $\sigma\downarrow0$ the covariance tends to the positive definite $\Sigma^L$, so the densities converge pointwise and the laws converge in total variation (Scheffé). The FDP is bounded, so the FDR converges to the Lei value. Hence some $\sigma_0(q)>0$ gives $W_\sigma(q)>q$ for $\sigma<\sigma_0(q)$. Item 5 of the compactification is not needed for this.

**(B1) Compactness and continuity.** $\bar E=([-\infty,0]\times\{1\})\cup([0,\infty]\times\{0\})$ is compact, so the product space is compact metrizable and a subsequence converges, $P_k\Rightarrow P_\infty$. Joint exchangeability passes to the limit because finite permutations act by homeomorphisms. Symmetry, unit diagonal and PSD finite principal blocks are closed conditions. On this closed set, $\varphi_n$ is continuous. Fix $g$ and a limit point. Each $p_j$ depends continuously on $(\theta_j,C)$, and the matrix square root is continuous on PSD matrices. BH depends only on the indicators $\mathbf 1\{p_j\le qk/n\}$. A tie $p_j=qk/n$ has $g$-probability $0$ for finite $\theta_j$, because $X_j\sim\mathcal N(0,1)$ exactly. For infinite $\theta_j$ a tie is impossible, because $p_j\in\{0,1\}$ while $qk/n\in(0,q]$ with $q<1/2$. Tags are locally constant. Since $D_n\le1$, dominated convergence gives continuity. Hence $\mathcal F_n(P_k)\to\mathcal F_n(P_\infty)$. By item 1 of the approved compactification, $\varepsilon_n=\sup_{\mathfrak P}|\mathcal F_n-\mathcal F|\to0$, so $\limsup_k\mathcal F(P_k)\le\mathcal F_n(P_\infty)+\varepsilon_n$ for every $n$. Only $\mathcal F_n(P_\infty)$ is used, so it does not matter that $P_\infty$ may carry infinite marks and lie outside $\mathfrak P$. If $\mathcal F(P_k)\to W_\sigma(q)$, every subsequence has the same limit, so passing to a subsequence loses nothing.

**(B2) Exact GG at the limit.** Each term of $\Delta_P(n,f,\psi)$ is the expectation of a bounded continuous function of $C_{1:n+1,1:n+1}$. Hence $\Delta_{P_\infty}(n,f,\psi)=0$ for all continuous $f,\psi$. Now let $f_m\downarrow\mathbf 1_F$ and $\psi_m\downarrow\mathbf 1_A$ for closed sets $F$ and $A$, with $f_m,\psi_m$ continuous and $[0,1]$-valued (for example $\max(0,1-m\,\mathrm{dist})$ and products of such). Dominated convergence extends the identity to $f=\mathbf 1_F$ and $\psi=\mathbf 1_A$, which is all that is used below.

**(B3) Positivity, self-contained proof.** Fix $\varepsilon>0$ and put $A=[-1,-\varepsilon]$ and $p=P_\infty(C_{12}\in A)$. Let $f_n=\prod_{1\le l<l'\le n}\mathbf 1\{C_{ll'}\in A\}$, which is the indicator of a closed set, and let $N_n=\#\{l\le n:C_{l,n+1}\in A\}$. On $\{f_n=1\}$ we have $\mathbf 1_A(C_{1l})=1$ for $2\le l\le n$, so exact GG gives
$$
\mathbb E[f_n\mathbf 1_A(C_{1,n+1})]=\tfrac1n(p+n-1)\,\mathbb E f_n .
$$
$f_n$ is symmetric in the indices $1,\dots,n$, and $P_\infty$ is invariant under permutations of these indices that fix $n+1$. So the same identity holds with $1$ replaced by any $l\le n$, and $\mathbb E[f_nN_n]=(n-1+p)\mathbb E f_n$. Since $N_n\le(n-1)+\mathbf 1\{N_n=n\}$, it follows that $\mathbb E[f_{n+1}]=\mathbb E[f_n\mathbf 1\{N_n=n\}]\ge p\,\mathbb E f_n$, and so $\mathbb E f_n\ge p^{n-1}$. On the other hand $C_{1:n,1:n}$ is PSD with unit diagonal, so on $\{f_n=1\}$
$$
0\le\mathbf 1^{\mathsf T}C_{1:n,1:n}\mathbf 1\le n-n(n-1)\varepsilon,
$$
which is impossible for $n>1+1/\varepsilon$. Hence $p=0$ for every $\varepsilon>0$, so $C_{12}\ge0$ a.s. By exchangeability $C_{ij}\ge0$ for all $i\ne j$, $P_\infty$-a.s. This argument needs neither the Dovbysh-Sudakov representation nor ultrametricity. It is Talagrand's positivity principle in the form needed here: an exchangeable array of PSD unit-diagonal correlation matrices that satisfies the GG identities exactly has nonnegative off-diagonal entries almost surely.

**(B4) BH with nonnegative correlations and composite or infinite nulls.** On this event, $\Sigma=(1-\sigma^2)C+\sigma^2\mathbf1\mathbf1^{\mathsf T}$ has nonnegative entries and unit diagonal. Rechecking each piece of step 6:
- Gaussian conditioning on $T_i=s$ shifts the other finite coordinates by $\Sigma_{ji}(s-\theta_i)\ge0$, with covariance free of $s$. This needs only $\Sigma_{ii}=1$, so it holds for singular $\Sigma$.
- $R$ is nondecreasing in each $T_j$, and infinite-mark coordinates are constants. Together these give $s\mapsto\Pr(R\le k\mid T_i=s)$ nonincreasing. Since $\{p_i\le t\}=\{T_i\ge\overline\Phi^{-1}(t)\}$, $G_k(t)$ is nondecreasing in $t$.
- $F(t)/t=\overline\Phi(u+|\theta_i|)/\overline\Phi(u)$ with $u=\overline\Phi^{-1}(t)$. This is nondecreasing in $t$ because $\overline\Phi$ is log-concave, and it is at most $1$.
- $G_0(t_1)=0$, since $p_i\le q/n$ forces $R\ge1$.
- The Abel summation is correct, with $G_n(t_n)=1$ and $a_n\le q/n$.

So each finite null contributes at most $q/n$. A null with $\theta_i=-\infty$ contributes $0$, since $p_i=1>q$. Hence $\varphi_n\le q$ a.s., so $\mathcal F_n(P_\infty)\le q$ and $\limsup_k\mathcal F(P_k)\le q<W_\sigma(q)$.

No step fails. The example refutes the lemma at every $(\sigma,q)$ with $0<q\le q_{\max}$ and $0<\sigma<\sigma_0(q)$.
