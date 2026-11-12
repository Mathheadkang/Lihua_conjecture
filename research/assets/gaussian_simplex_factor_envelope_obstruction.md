---
type: lemma
title: Singular simplex obstruction to full-factor conditional envelopes
status: draft
source:
  kind: original
depends_on: []
uses_definitions: []
tags: []
---

## Statement

Let S(x)=(2*pi)^(-1/2) integral_x^infinity exp(-z^2/2) dz and let phi be its standard normal density. For every 0<q<1/2 set
$$
m=m(q)=\left\lceil e^{2/q}/q\right\rceil,\qquad
T_i=\frac{X_i-\bar X}{\sqrt{1-1/m}},\quad
\bar X=m^{-1}\sum_{j=1}^m X_j,
$$
where X_1,...,X_m are independent standard Gaussians. All hypotheses are true one-sided nulls, P_i=S(T_i), and ordinary BH uses its largest non-strict qualifying rank R_q on all m physical tests. Then the following hold.

(i) The covariance is Sigma=(m I_m-11^T)/(m-1), with unit diagonal, rank m-1 and kernel span{1}. In EVERY finite-dimensional independent-residual Gaussian factor representation
$$
T=A Z+D^{1/2}\varepsilon,\qquad
Z\sim N_K(0,I_K),\quad\varepsilon\sim N_m(0,I_m),\quad
Z\perp\varepsilon,\quad D\text{ diagonal and }D\succeq0,\quad
AA^T+D=\Sigma,
$$
one has D=0. For the natural conditional CDF F_i(t|Z)=P(P_i<=t|Z) and the full-factor envelope
$$
E_i=\sup_{0<t\le q}\frac{F_i(t|Z)}{t},
$$
one consequently has E_i=1{P_i<=q}/P_i almost surely, independently of the chosen representation.

(ii) Write Y_i=min(E_i,m). For every such representation,
$$
E Y_i=1+\log(qm),\quad E Y_i^2=2m-1/q,\quad
\operatorname{Var}\!\left(m^{-1}\sum_iY_i\right)\le2,
$$
and
$$
1\ge E\min\!\left\{1,\frac q m\sum_iE_i\right\}
\ge1-\frac{2q^2}{(1+q)^2}.
$$
In particular even the infimum of this capped envelope certificate over ALL representations just specified tends to 1 as q decreases to zero.

(iii) The actual global-null BH FDR in this SAME finite family satisfies
$$
\mathbb E[V_q/(R_q\vee1)]=P(R_q>0)=q(1+o(1))\qquad(q\downarrow0).
$$
Thus the obstruction concerns complete-factor conditioning with independent diagonal residuals, not the unrestricted Gaussian BH main conjectures. Every representation, expectation and infimum above is taken at the same fixed q and finite m(q); the asymptotic statement allows m to grow as explicitly prescribed. No approval or independent verification of this promoted draft is asserted.
