---
type: lemma
title: Signed-label half-line Stein identity for positive-definite Gaussian BH
status: draft
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - signed_records
  - halfline_stein
  - positive_definite
---

## Statement

Let $N\ge1$ be finite, $\theta\in\mathbb R^N$ arbitrary, and $\Sigma$ positive definite with unit diagonal. Let $Z\sim N_N(\theta,\Sigma)$, a positive-definite instance of the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md). Write $\phi,\Phi$ for the standard normal density and distribution function and $S=1-\Phi$. Fix
$$
0<q\le S(1),\qquad U=S^{-1}(q)\ge1,\qquad u_r=S^{-1}(qr/N)\quad(1\le r\le N).
$$
Use the [one-sided Gaussian p-values and original true-null labels](../definitions/gaussian_test_pvalues.md)
$$
p_j=S(Z_j),\qquad I_0=\{j\in[N]:\theta_j\le0\},\qquad X_j=Z_j-\theta_j.
$$
Apply [ordinary BH](../definitions/benjamini_hochberg_step_up.md) at level $q$, with rejection set $\mathcal R$ and count $R$. The [false discovery rate](../definitions/false_discovery_rate.md) below is $\operatorname{FDR}=\mathbb E[|I_0\cap\mathcal R|/(R\vee1)]$. The auxiliary path always counts this fixed original set $I_0$, even though its scores are translated.

For a deterministic strict descending score order $z_{\pi(1)}>\cdots>z_{\pi(N)}$, put $\tau_r=z_{\pi(r)}-u_r$. The BH rank along $z-t\mathbf1$ is
$$
R_z(t)=\max\bigl(\{0\}\cup\{r:\tau_r\ge t\}\bigr).
$$
Its complete chain consists of $0=r_{-1}<r_0<\cdots<r_m=N$: choose $r_0$ as the largest maximizer of $\tau_r$ over $[N]$, then choose each next rank as the largest maximizer over the ranks larger than the current one. For generic scores these record times strictly decrease. At an edge $e:s\to r$ put $i_e=\pi(r)$, $\tau_e=\tau_r$, and, separately for each $j\in I_0$,
$$
c_{je}=\begin{cases}
1/r,&s<\pi^{-1}(j)\le r,\\
1/r-1/s,&\pi^{-1}(j)\le s,\ s>0,\\
0,&\pi^{-1}(j)>r.
\end{cases}
$$
Then, with every edge retained with its sign,
$$
\frac{\mathbf1\{j\in\mathcal R(z)\}}{R_z(0)\vee1}
=\sum_e c_{je}\mathbf1\{\tau_e\ge0\},\qquad
\operatorname{FDP}(z)=\sum_{j\in I_0}\sum_e c_{je}\mathbf1\{\tau_e\ge0\}.
$$
Each label has one positive entry; all its subsequent coefficients are negative and their absolute values sum to $1/r_{\rm entry}-1/N$. Equal record times are coalesced with the largest-rank convention. At score ties, use the tied cohort and the same coalescing convention.

For every edge with $c_{je}\ne0$ define
$$
a_{je}=u_r+z_j-z_{i_e}=z_j-\tau_e\ge u_r,\qquad
d_{ji_e}=1-\Sigma_{ji_e}\in[0,2],\qquad b_j(a)=S(a-\theta_j).
$$
For dummy scalar arguments $x,a$, let
$$
H_j(x,a)=\frac{1}{\phi(x-\theta_j)}
\int_{-\infty}^x\phi(y-\theta_j)
\bigl(\mathbf1\{y\ge a\}-b_j(a)\bigr)\,dy.
$$
Writing $X=x-\theta_j$ and $A=a-\theta_j$, its explicit formulas are
$$
H_j(x,a)=\begin{cases}
-S(A)\Phi(X)/\phi(X),&x<a,\\
-\Phi(A)S(X)/\phi(X),&x\ge a,
\end{cases}
\qquad
H_{j,a}(x,a)=\begin{cases}
\phi(A)\Phi(X)/\phi(X),&x<a,\\
-\phi(A)S(X)/\phi(X),&x>a.
\end{cases}
$$
The value of $H_{j,a}$ at $x=a$ can be assigned arbitrarily in the expectations below. The potential $H_j$ is continuous, $|H_j|\le C:=\sqrt{\pi/2}$, and away from $x=a$ it satisfies
$$
H_{j,x}-(x-\theta_j)H_j=\mathbf1\{x\ge a\}-b_j(a).
$$
The field
$$
G_j(z)=\sum_e c_{je}H_j(z_j,a_{je})
$$
has matching limits across all record-contact and score-order interfaces, extends locally Lipschitz continuously, and has the cellwise weak derivative without surface distributions. It satisfies $|G_j|\le2C$; on its cells $|H_{j,a}|\le1$ and $|H_{j,x}|\le C|X_j|+1$. Its first weak derivatives grow at most linearly in $|X_j|$ in each fixed model. Consequently the following exact identity has absolutely integrable expectations and no interface term:
$$
\operatorname{FDR}
=\mathbb E\sum_{j\in I_0}\sum_e c_{je}b_j(a_{je})
-\mathbb E\sum_{j\in I_0}\sum_e c_{je}d_{ji_e}H_{j,a}(Z_j,a_{je}).
\tag{SF}
$$

For a fixed $j$, enumerate only its entry and subsequent nonzero edges by $\ell=0,\ldots,L_j$, with endpoint ranks $k_0<\cdots<k_{L_j}=N$. Put $b_\ell=b_j(a_{j\ell})$, so $b_\ell$ decreases along this list, and define its signed baseline by
$$
B_j=\sum_e c_{je}b_j(a_{je})
=\frac{b_0}{k_0}-\sum_{\ell=1}^{L_j}
\left(\frac1{k_{\ell-1}}-\frac1{k_\ell}\right)b_\ell.
$$
Pointwise,
$$
0\le\frac{b_0}{N}\le B_j\le\frac{b_0}{k_0}\le\frac qN.
\tag{B}
$$
In the above-threshold part $\tau_e\ge0$, the sole positive-entry term in $-\sum_e c_{je}d_{ji_e}H_{j,a}$ is nonnegative and at most $4q/N$. Every subsequent old-label term there is nonpositive, and the sum of their absolute values, including any subset, is at most $4q/N$. In particular, defining the full signed below-threshold remainder by
$$
D_<:=-\sum_{j\in I_0}\mathbb E\sum_{e:\tau_e<0}
c_{je}d_{ji_e}\frac{\phi(a_{je}-\theta_j)\Phi(X_j)}{\phi(X_j)},
$$
one has the exact decomposition (SF) and the consequence
$$
\operatorname{FDR}\le5q|I_0|/N+D_<.
$$
All assertions are for the stated finite positive-definite models and small-$q$ interval. No uniform bound on $D_<$ is part of this lemma.

## Provenance

This is the completed structural part of [the signed-label half-line Stein occupation plan](../plans/plan_252211621cea.md), extracted from `## Progress`, formal scope and sections 1–3. The source whole-file SHA256 at extraction is `bc2cbe433c0c70c04856bc5589c6efe61e68d451145a403c2b1da8e5d41f756d`; the exact native-show excerpt archived below has SHA256 `106efb1e2d0faaf042a8a554d3b7e137fdda692eabb360972c2e2cb2d8825850`. Definitions of the formulas referred to by that excerpt were read from completed Plan steps 1–3. No source claim from later Progress sections is extracted. This archive is unverified imported proof evidence; it is not a canonical proof, native verification verdict, or approval.

## Imported proof (unverified)

Formal scope of the completed partial derivation: fix a finite N, arbitrary original means theta, a positive-definite unit-diagonal Sigma, and 0<q<=S(1), where S is the standard normal survival function, phi its density, U=S^{-1}(q)>=1 and u_r=S^{-1}(qr/N). The original score vector is Z~N_N(theta,Sigma), X_j=Z_j-theta_j, and I0={j:theta_j<=0}. The auxiliary translation path counts these original labels throughout. A passage to singular covariance is conditional on first proving the unestablished uniform occupation bound; no such passage is claimed here.

### 1. Full translation records and original-label accounting (established)

Execution began with plan SHA256 `310b0ab09e0c597362eea8b5dbeeebce6c1f727d593833554c32fb6b92134438` and target SHA256 `7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305`. There is no Git HEAD at this cwd. The target is untouched.

Fix a strict score order pi and put t_r=z_pi(r)-u_r. The shifted ordered p-value at rank r qualifies exactly when t<=t_r; therefore R(t)=max({0} union {r:t_r>=t}). If the maximum rank is r>0, exactly the first r scores are rejected: if rank r+1 also passed the rank-r threshold, it would pass its own larger p-value threshold, contradicting maximality. Starting from rank zero, the first positive rank is the largest maximizer of all t_r. After a current rank s, the next is the largest maximizer among r>s. Repeating terminates at N. At generic points the resulting record times strictly decrease. Thus these are exactly the strict suffix-upper records, including a final rank N, and the rank at t=0 is the last record whose time is nonnegative.

Write F_j(r)=1{pi^{-1}(j)<=r}/r for r>0 and F_j(0)=0. At a record edge s->r, F_j(r)-F_j(s) is exactly the proposed c_je: 1/r for a new label, 1/r-1/s for an old label, and zero otherwise. This is an identity for each original label, irrespective of its mean or whether the trigger is null. Summing the increments already crossed at zero telescopes to F_j(R(0)); summing over the fixed set I_0 gives the stated pathwise FDP identity. A label enters once at rank r_0, and its later negative coefficient magnitudes sum to 1/r_0-1/N. This includes s=0, no rejection at zero, all-null paths, false triggers and cascades of arbitrary finite length. Equal contact times can be coalesced, with the same telescoping identity and the largest-rank convention. No null labels are relabeled along translation.

### 2. Half-line normalization, interfaces and Stein formula (established)

Put X=x-theta_j and A=a-theta_j. Integrating the centered indicator separately for x<a and x>=a gives exactly the two displayed formulas for H_j in Step 2; the total integral over the real line is zero since b_j(a)=S(A). Differentiating in x away from x=a gives H_x-XH=1{x>=a}-b_j(a), and differentiating in a gives the two asserted signed H_a formulas. At x=a both H formulas equal -Phi(A)S(A)/phi(A), so H is continuous, although its partial x derivative jumps there. This is marginal centering, with a fixed dummy threshold during the calculation.

For all real x,a, |H_j(x,a)|<=Phi(X)S(X)/phi(X). This last quantity is at most C=sqrt(pi/2): for X>=0 use S(X)/phi(X)=integral_0^infinity exp(-Xt-t^2/2)dt<=C; for X<=0 use the reflected formula for Phi(X)/phi(X). On a selected-label edge a>=u_r and theta_j<=0, hence A>=U>=1. Below threshold, if X<=0, |H_a|<=phi(A)C<=1/2; if 0<X<A, phi(A)/phi(X)<=1 and |H_a|<=1. Above threshold, S(X)/phi(X)<=1/X (integrate exp(-Xt-t^2/2)<=exp(-Xt)), so |H_a|<=phi(A)/X<=1. Thus on all cells |H_a|<=1 and |H_x|<=C|X|+1. For each label sum_e |c_je|=2/r_entry-1/N<=2. Consequently G_j is uniformly bounded by 2C and its cellwise first derivatives grow at most linearly in |X_j|, with constants independent of the cell (fixed finite N suffices).

The permutation/contact partition is a finite affine-hyperplane arrangement. On a contact facet t_h=t_k which changes records s->h->k into s->k, a_jh=a_jk for every label selected by rank k. An old label's two coefficients sum to (1/h-1/s)+(1/k-1/h)=1/k-1/s. A label entering in the first block has coefficients 1/h+(1/k-1/h)=1/k; one in the second has 1/k on both sides; labels outside k have zero. These identities include s=0 and do not use the truth status of either trigger. All other record edges are unchanged. Repeated merging proves the same statement when several contact times coincide; swaps of nonrecord contacts change no field.

At an adjacent score tie z_pi(h)=z_pi(h+1), one has t_h<t_{h+1} because u_h>u_{h+1}. Thus rank h cannot be a suffix-upper record, nor any internal rank of a larger tied block. The tied labels enter together, their entry/dilution coefficients agree, and an exchanged last label of that block has the same score in each threshold a_je. The limits of G_j from either score-order chamber therefore agree. Every codimension-one interface has matching limits. All their intersections also have a single limit: coalesce equal-time records and tied score blocks in either order using the preceding identities. Since the finite cellwise gradients are bounded on each compact set, restricting to a generic line segment and integrating across its finitely many faces proves local Lipschitz continuity. Limits of generic segments handle segments within faces. Hence G_j has the stated cellwise weak derivative almost everywhere, with no surface distributions.

Within a cell, partial_k H_j(z_j,a_je)=delta_kj H_x+(delta_kj-delta_ki)H_a. Since Sigma_jj=1, contraction with row j of Sigma equals H_x+(1-Sigma_ji)H_a. Positive semidefiniteness gives |Sigma_ji|<=1 by its two-by-two minors, hence d_ji in [0,2]. The bounded G_j, linearly growing weak gradients and Gaussian first moments justify a single compact cutoff and then dominated convergence. For completeness Gaussian integration by parts follows by writing Z=theta+L g with LL^T=Sigma and g standard independent normals, applying the scalar identity integral t f(t)phi(t)dt=integral f'(t)phi(t)dt first to smooth compact approximations, and then using the cutoff bounds. This introduces no inverse covariance estimate. Thus E[(Z_j-theta_j)G_j]=sum_k Sigma_jk E[partial_k G_j]. Substituting the normalized Stein equation and the pathwise identity from Section 1 proves exactly (SF), with its minus sign before sum c_je d_ji H_a. Every expectation here is absolutely integrable in each fixed positive-definite model.

### 3. Small chains and easy budgets (established; no stronger shortcut used)

For N=1 a true null has its sole entry c=1, a=u_1, trigger i=j and d=0; thus (SF) reduces to FDR=S(u_1-theta_1)<=q. If the sole label is false the empty null sum is zero. For N=2 and strict scores z_pi(1)>z_pi(2), the only two chains are 0->1->2 when t_1>t_2, and 0->2 otherwise. In the first chain the top label has coefficients 1,-1/2 and the bottom label 1/2; the second has 1/2 for both. At t_1=t_2 the top kernels coincide, yielding 1-1/2=1/2. These calculations cover any subset of original nulls. For the specified independent three-test face, label 1's old coefficients are -1/2,-1/6 versus -2/3, and label 3's entry is 1/3 versus 1/3. Their kernels coincide at t_2=t_3, so the jump is zero label by label even though trigger 2 is false. Section 2's same telescoping covers every cascade length. Padding by any finite set of scores requires recomputing u_r for the new total N; the identical rank algebra then applies. No invariance of the BH threshold under padding is assumed.

Tied blocks satisfy the coalesced deterministic identity in Section 1. To check this by finite-model approximation, couple Z_epsilon=theta+sqrt(1-epsilon)(Z-theta)+sqrt(epsilon)g. Each marginal has variance one; therefore none equals a fixed u_r with positive probability, even for singular Z. Off this finite union of events every coordinate's comparisons with all u_r stabilize as epsilon tends to zero, so the rejection set stabilizes even for permanent score ties. Bounded FDP passes to the limit. This checks the identities at duplicates; it is not a transfer of an as-yet unproved uniform bound.

For a fixed label, later record times decrease and a_l=z_j-t_l increases. Hence b_l=S(a_l-theta_j) decreases. Subtracting the later negative coefficients proves
$$
 b_0/N\le B_j\le b_0/r_0\le q/N,
$$
because their magnitudes sum to 1/r_0-1/N and a_0-theta_j>=u_r0. This establishes (B), including a nonnegative lower bound without any monotonicity in a residual scalar.

For x>0, integration by parts gives S(x)=phi(x)/x-integral_x^infinity phi(t)/t^2 dt, so
$$
 \frac{x}{x^2+1}\phi(x)\le S(x)\le\frac{\phi(x)}x.
$$
Indeed the integral is at most S(x)/x^2 for the lower bound; the upper bound follows by dropping it. At an above-threshold edge X>=A>=U>=1, these estimates imply
$$
 \phi(A)S(X)/\phi(X)\le (A+1/A)S(A)/X\le2S(A).
$$
Consequently the sole positive entry contributes at most 4b_0/r_0<=4q/N to -sum c d H_a there. Each old-null contribution there is nonpositive. Its absolute sum is at most 4sum_{l>=1}(1/r_{l-1}-1/r_l)b_l<=4b_0(1/r_0-1/N)<=4q/N, including any subset of those edges. Therefore (SF) rigorously yields FDR<=5q|I_0|/N+D_<. This is the full remaining signed D_<, without discarding its negative entry.

The primary source named by the driver was located at `bh_fdr_research/reference_arxiv/FDR_BH_v4.tex`, `thm:one-lower` at line 3754, construction (one-nu) at lines 3923--3929, and proof starting at line 5099. Its construction uses null loading r, signal loading -1, and the secondary survival W_r(a)=(1-q exp(a^2/2))S(a/r)/q, with a in [r S^{-1}(r^2),sqrt(2 log(1/q))]. The exact theorem claims finite positive-definite approximations to the integrated profile q, q exp(z^2/2), 1 on its three regimes. The population first-crossing and empirical-transfer proofs have not been independently reconstructed here, so neither that lower bound nor its constants are used as an established premise. No universal O(q) shortcut is asserted. If one is subsequently proposed, the complete lower-bound diagnostic reconstruction remains mandatory before accepting it.
