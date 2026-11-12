---
type: lemma
title: Factor-model BH bounds and the critical-background return obstruction
status: draft
source:
  kind: original
depends_on: []
uses_definitions: []
tags: []
---

## Statement

Let S and phi denote the standard Gaussian survival function and density, and h=phi/S. All logarithms are natural. In parts (a)-(c), for arbitrary finite integers N,K>=1, take
$$
T_i=\theta_i+\langle b_i,Z\rangle+s_i\varepsilon_i,\qquad
s_i=\sqrt{1-\|b_i\|^2},\quad \|b_i\|\le1,
$$
where Z~N_K(0,I_K) and the independent standard normal epsilon_i are independent of Z. Zero residual variances, repeated directions, and arbitrary alternative means are permitted. In one-sided testing use P_i=S(T_i), with true null set I_0={i:theta_i<=0}; in two-sided testing use P_i=2S(|T_i|), with I_0={i:theta_i=0}. In either mode let pi_0=|I_0|/N, let R be the largest rank r satisfying P_(r)<=qr/N (R=0 if none), and let FDR=E[V/(R vee 1)], where V counts rejected members of I_0 among all N tests.

(a) In the one-sided model group the loaded true nulls (b_i not zero) by the SAME oriented direction b_i/||b_i||. For group g let w_g be its cardinality divided by N, and set H=sum_g w_g log(1/w_g), with H=0 for no such groups. For every 0<q<1/2, writing u_1=S^{-1}(q),
$$
\mathrm{FDR}_1\le q\pi_0\,\frac{u_1}{\sqrt{2\pi}}+\frac32q+qH.
$$
Consequently, for every prescribed integer bound D_q>=1 on the number of loaded-null directions, if log D_q=o(sqrt(log(1/q))), the limsup as q decreases to zero of the supremum of FDR_1/[q sqrt(log(1/q))] over ALL finite N,K and all such models with at most D_q directions is at most 1/sqrt(pi). The same conclusion holds for independent one-factor blocks with at most B_q blocks when log B_q=o(sqrt(log(1/q))), since each block contributes at most two oriented directions.

(b) There exist absolute constants C,u_0>0 such that, in the two-sided model, for EVERY finite K,N and every q with u_2=S^{-1}(q/2)>=u_0,
$$
\mathrm{FDR}_2\le q\pi_0\left\{
\frac{u_2}{2\sqrt{2\pi}}+
C\left[(K+1)\log u_2+K^{1/4}u_2^{3/4}\right]\right\}+Cq.
$$
In particular, for each integer-valued K_q>=1 with K_q log log(1/q)=o(sqrt(log(1/q))), the analogous uniform limsup over factor dimension at most K_q and unrestricted finite N is at most 1/(2 sqrt(pi)). This includes every fixed K.

(c) Set v_i=b_i/||b_i|| for the loaded true nulls and define W_+=max_i <v_i,Z>, W=max_i |<v_i,Z>|; each maximum is defined to be zero if this index set is empty. There is an absolute C_0 such that, for ALL finite K,N and every U>=u_1, 0<q<1/2,
$$
\mathrm{FDR}_1\le P(W_+>U)+q\pi_0\max\left\{1,\frac12+
\frac{u_1}{\sqrt{2\pi}}+C_0(U-u_1)(1+U)\right\}.
$$
For every U>=u_2 and 0<q<=2S(1),
$$
\mathrm{FDR}_2\le P(W>U)+q\pi_0\max\left\{1,\frac{1-q}{2}+
\frac{u_2}{\sqrt{2\pi}}+C_0(U-u_2)(1+U)\right\}.
$$
In particular the second display by itself has the larger leading constant 1/sqrt(pi), and does not assert the sharp two-sided constant in unrestricted dimension.

(d) The following proposed uniform per-cell return estimate is FALSE, even within finite one-sided Gaussian models. Given a selected unit-loading block with one null score X and L alternative scores 1+X, X~N(0,1), put m=N. Let B(j) count all scores OUTSIDE this block exceeding y_j=S^{-1}(qj/m), define
$$
D(j)=j-B(j),\qquad
\rho(c)=\max\bigl(\{0\}\cup\{j\in\{1,\ldots,m\}:D(j)\le c\}\bigr),
$$
and for an integer b>=1 and real s>=2 set
$$
E_{b,s}=\left\{\exists c\in\{2,\ldots,L+1\}:
b\le\rho(c)<sb,\quad \rho(c)\ge s\rho(c-1)\right\}.
$$
For EVERY delta>0, s_0>=2, u_0>=1 and C>0, there exist a FIXED q in (0,1/2), a FIXED s>=s_0 with s<=exp(S^{-1}(q)), and a sequence of finite models indexed by n, with integer b_n tending to infinity, m_n tending to infinity, L_n=floor(10 sqrt(b_n)), and s b_n<=min(delta,1)m_n, such that
$$
\liminf_n P(E_{b_n,s})>0,\qquad
\frac{2\log s}{\sqrt{2\pi}\,h(S^{-1}(qsb_n/m_n))}
+C\frac{(L_n+1)s}{b_n}\longrightarrow0,
\quad S^{-1}(q)\ge u_0.
$$
These models can have background scores consisting only of M_n independent N(theta_n,1) alternatives with theta_n=kappa_n S^{-1}(q)/sqrt(b_n)>0 and kappa_n decreasing to zero, and remaining independent N(-A_n,1) null fillers, all independent of X; choose M_n to be the nearest integer to (b_n-sqrt(b_n))/S(y_{b_n}-theta_n), and choose m_n,A_n sufficiently large. Hence no universal C,s_0,u_0 can make the displayed vanishing expression an upper bound for P(E_{b,s}) throughout this class. This is an obstruction to that per-cell certificate, not a counterexample to either original BH FDR main bound.

Provenance for this composite draft is the sibling project /Users/xiaosheng/Desktop/Research/Lihua_conjecture_claude/BH_FDR_Claude_Independent, Statement sections of research/assets/onesided_direction_entropy_upper.md, twosided_kfactor_sharp_upper.md, twosided_kfactor_growing_sharp_upper.md, onesided_factor_width_upper_v2.md, twosided_factor_width_upper_v2.md, and Statement plus independent Verdict of cx_block_extreme_window_lemma_r1_s2_critical_iid_background.md. All four parts require local proof and independent verification. Sibling approvals and historical descriptions of its open problems are provenance only and confer no local approval.
