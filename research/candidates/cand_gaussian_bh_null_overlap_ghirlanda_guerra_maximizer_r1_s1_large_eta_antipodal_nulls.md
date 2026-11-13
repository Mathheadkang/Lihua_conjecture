---
type: candidate
title: >-
  Large penalty: zero-moment antipodal nulls beat every law with nonnegative
  null overlaps
status: survived
target_asset: gaussian_bh_null_overlap_ghirlanda_guerra_maximizer
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: pass
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: c004cd7dd3ebba2bde77adaf595610273c90f3f1141552d69887bd909631a7ab
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T08:17:01.419Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

The parameters are $\sigma=\sqrt{0.3}\approx0.5477$, $q=0.1$, and any $\eta\ge\eta_0$, where $\eta_0=\eta_0(\sigma,q)<\infty$ exists by the argument under NOT. The argument shows existence only and gives no value for $\eta_0$. Write $\tau=\sqrt{1-\sigma^2}$, $u_s=\overline\Phi^{-1}(s)$ and $\rho=\sigma^2-\tau^2=2\sigma^2-1=-0.4$.

The witness is the zero-moment antipodal null law $P_{\rm anti}$. Let $s_i$ be iid uniform on $\{\pm1\}$, and put $\theta_i=0$, $\ell_i=1$, $C_{ij}=s_is_j$ ($i\ne j$) and $C_{ii}=1$. Equivalently, the directing measure is $\mu=\tfrac12\delta_{(0,e,1)}+\tfrac12\delta_{(0,-e,1)}$ with $\|e\|=1$. Conditionally on $\omega$, the statistics are $T_i=s_i\tau X+\sigma Z$, so they take only the two values $a=\tau X+\sigma Z$ and $b=-\tau X+\sigma Z$. These are standard normals with correlation $\rho$.

The claimed failure: at these parameters, no canonical maximizer $P$ with $P(E_0)>0$ has a null-tag overlap array satisfying the Ghirlanda-Guerra identities.

## Checks

### H1

$0<\sigma=\sqrt{0.3}<1$. Pass.

### H2

$q_{\max}=\overline\Phi(1)\approx0.1587$, so $0<q=0.1\le q_{\max}$. Pass.

### H3

$\eta\ge\eta_0>0$. Pass.

### NOT

**Step 1: the witness beats $q$.** $P_{\rm anti}$ is lawful and canonical. Its marks $(0,1)$ lie in $E_{\rm mark}$. The matrix $C=ss^{\mathsf T}$ is PSD with unit diagonal. The array is jointly exchangeable because the $s_i$ are iid, and $M_2=0$. Take $n$ indices, of which $N_+$ have $s_i=+1$. If $p_a\le p_b$, BH rejects something iff $p_a\le qN_+/n$ or $p_b\le q$, and symmetrically if $p_b\le p_a$. All tags are null, so $D_n=\mathbf 1\{R_n>0\}$. Also $N_+/n\to1/2$ almost surely, and the boundary events are null. By bounded convergence,
$$
\mathcal F(P_{\rm anti};q,\sigma)=\mathbb P\bigl(\max(a,b)\ge u_{q/2}\ \text{or}\ \min(a,b)\ge u_q\bigr)
=q+\mathbb P(u_q\le a,b<u_{q/2})-\mathbb P(a,b\ge u_{q/2}).
$$
One-dimensional quadrature (absolute error below $10^{-14}$) at $\rho=-0.4$, $q=0.1$ gives band $=6.8047\times10^{-4}$ and tail $=1.9215\times10^{-4}$. Hence
$$
a_*:=\mathcal F(P_{\rm anti};q,\sigma)=0.1+4.883\times10^{-4}>q.
$$
A Monte Carlo run with $4\times10^7$ samples gives an excess of $4.81\times10^{-4}$, with standard error $4.8\times10^{-5}$. The same formula gives a positive excess whenever $\sigma^2<1/2$, exactly $0$ at $\sigma^2=1/2$, and a negative excess for $\sigma^2>1/2$. $P_{\rm anti}\in\mathfrak P_2$ has zero moment, so $A_{\eta,\sigma}(q)\ge a_*$ for every $\eta>0$.

**Step 2: GG forces nonnegative null-null correlations.** Suppose $P$ satisfies the GG identities for its null-tag array, with $P(E_0)>0$.
- Talagrand's positivity principle gives $R^0_{12}\ge0$ almost surely under $P(\cdot\mid E_0)$. It applies to the Gram array of an iid sample from a random measure on the unit ball of a Hilbert space that satisfies the GG identities. The target's own Notes also state it ("the identities imply nonnegative overlaps"). By item 6 of [the compactification](../assets/gaussian_bh_exchangeable_array_variational_compactification.md), the null array under $P(\cdot\mid E_0)$ is such a sample: conditionally on $\mu$, null $v$'s are iid from $\mu(\cdot\mid\ell=1)$.
- The tags are exchangeable, so by de Finetti they are iid Bernoulli$(\Pi)$ given $\Pi$, and $E_0=\{\Pi>0\}$ almost surely. Hence $P(\ell_1=\ell_2=1,E_0^c)=0$.
- On $\{\ell_1=\ell_2=1\}\cap E_0$ we have $C_{12}=R^0_{12}$. So $P(\ell_1=\ell_2=1,\,C_{12}<0)=0$.
- By joint exchangeability, the same holds for every pair $i\ne j$. So $P$ is supported on the set $K=\bigcap_{i\ne j}\{\ell_i\ne1\text{ or }\ell_j\ne1\text{ or }C_{ij}\ge0\}$.
- $K$ is closed in the product topology, because tags carry the discrete topology. By the portmanteau theorem, the property "$P(K)=1$" is closed under weak convergence.

**Step 3: a limit law with zero moment.** Suppose, for contradiction, that there are $\eta_k\to\infty$ and canonical maximizers $P_k$ at $(\sigma,q,\eta_k)$ that satisfy GG, with $P_k(E_0)>0$.
- Since $\mathcal F\le1$ and $A\ge0$, we get $\eta_kM_2(P_k)\le1$, so $M_2(P_k)\to0$.
- By item 1 of the compactification (compact moment sublevels, lower semicontinuity of $M_2$, continuity of $\mathcal F$ on all of $\mathfrak P$), a subsequence converges to some $P_\infty\in\mathfrak P$ with $M_2(P_\infty)=0$, $P_\infty(K)=1$, and
$$
\mathcal F(P_\infty)=\lim_k\mathcal F(P_k)=\lim_k\{A_{\eta_k}+\eta_kM_2(P_k)\}\ge\limsup_kA_{\eta_k}\ge a_*.
$$
- In $P_\infty$, every $\theta_i=0$. Some tags may be $\ell=0$, which is allowed in the analytic completion.
- Let $\mathrm{rt}(P_\infty)$ be $P_\infty$ with every mark $(0,0)$ retagged to $(0,1)$. It is lawful, canonical, jointly exchangeable, and has $M_2=0$. So $\mathcal F(\mathrm{rt}P_\infty)\le A_{\eta_k}$ for all $k$, and therefore $\mathcal F(\mathrm{rt}P_\infty)\le\mathcal F(P_\infty)$.
- The statistics, and hence the rejection sets, are unchanged by retagging. So $\Delta_n:=\mathcal F_n(\mathrm{rt}P_\infty)-\mathcal F_n(P_\infty)=\mathbb E[A^{\rm r}_n/(R_n\vee1)]\ge0$, where $A^{\rm r}_n$ counts rejected $\ell=0$ indices.
- Hence $\Delta_n\to\Delta=0$.

**Step 4: the limit law has FDR at most $q$, a contradiction.** Fix $\omega$ in the support of $P_\infty$ and $0<\varepsilon<1$. Let $n_0$ be the number of nulls among $1..n$, and $V,R$ the BH counts.
- On $\{R\ge1,\,A^{\rm r}_n\le\varepsilon R\}$ we have $V\ge(1-\varepsilon)R\ge1$. The $V$ rejected nulls have $p\le qR/n\le\alpha V/n_0$ with $\alpha=qn_0/((1-\varepsilon)n)$. So null-only BH at level $\alpha$ rejects something, that is, the Simes statistic of the null p-values is at most $\alpha$.
- The null subvector is $\mathcal N(0,(1-\sigma^2)C_{NN}+\sigma^2\mathbf1\mathbf1^{\mathsf T})$. Its off-diagonal entries are at least $\sigma^2>0$ because $\omega\in K$, and its p-values are exactly uniform. By [the positive-Gaussian Simes inequality](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md), this event has probability at most $\min(1,\alpha)$.
- Therefore
$$
\mathcal F_n(P_\infty)\le\mathbb E\min\Bigl(1,\tfrac{q\,n_0}{(1-\varepsilon)n}\Bigr)+\mathbb P(R\ge1,\,A^{\rm r}_n>\varepsilon R)\le\mathbb E\min\Bigl(1,\tfrac{q\,n_0}{(1-\varepsilon)n}\Bigr)+\frac{\Delta_n}{\varepsilon}.
$$
- Let $n\to\infty$ ($n_0/n\to\Pi$ almost surely, and $\Delta_n\to0$), then $\varepsilon\downarrow0$. This gives $\mathcal F(P_\infty)\le q\,\mathbb E\Pi\le q<a_*$, contradicting Step 3.

So there is $\eta_0$ such that for every $\eta\ge\eta_0$, no canonical maximizer with $P(E_0)>0$ satisfies the GG identities. The conclusion fails. Pass, given the cited positivity principle, which is not yet a library node.

Mechanism: a large penalty forces almost-zero means. Then every alternative is almost a null, and retagging it as a null only helps. The only way to exceed $q$ at zero moment is negative correlation among nulls, and the GG identities forbid it.
