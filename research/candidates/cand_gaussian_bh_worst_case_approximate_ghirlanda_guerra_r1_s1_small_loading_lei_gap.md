---
type: candidate
title: >-
  Small common loading with Lei's gap, where GG-approximate arrays cannot reach
  W_sigma(q)
status: survived
target_asset: gaussian_bh_worst_case_approximate_ghirlanda_guerra
checks:
  H1: pass
  H2: pass
  NOT: pass
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 0fa059894da56d1c7aa170ddad938948acb823f2dc7eea7e4574aa98d3831230
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T07:26:07.964Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Fix any level $q\in(0,q_{\max}]$, for instance $q=1/20$. By the approved [Lei lower bound](../assets/lei2026_one_sided_fdr_lower.md) there is a finite model $(N,\theta^{L},\Sigma^{L})$ with $\Sigma^L$ positive definite, nulls $\theta^L_i=0$ and alternatives $\theta^L_i>0$, and
$$
\operatorname{FDR}^{(1)}_{\rm BH}(q;N,\theta^L,\Sigma^L)>\tfrac12\bigl(\ell_{\le}(q)+q\bigr)>q .
$$
Here $\ell_\le(q)>q$ because $\log(1/q)>\pi/4$ for $q\le q_{\max}\approx0.1587$. Take $\sigma\in(0,\sigma_0(q))$, where $\sigma_0(q)>0$ is chosen so that $W_\sigma(q)>q$ for all $0<\sigma<\sigma_0(q)$ (existence is shown under NOT). The object is the parameter pair $(\sigma,q)$.

## Checks

### H1

$0<\sigma<\sigma_0(q)\le1$. Pass.

### H2

$0<q\le q_{\max}$ by choice. Pass.

### NOT

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
