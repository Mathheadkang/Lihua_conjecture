---
type: lemma
title: >-
  One-sided Simes crossings force a large Mills-normalized penalized subset
  supremum
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_test_pvalues
tags:
  - gaussian_bh
  - one_sided
  - global_null
  - simes
  - hinge_form
---

# One-sided Simes crossings force a large Mills-normalized penalized subset supremum

## Statement

Write $\phi$ for the standard normal density, $\overline\Phi$ for the standard normal survival function of the [Gaussian test p-values](../definitions/gaussian_test_pvalues.md), and $h=\phi/\overline\Phi$ for the inverse Mills ratio. For a positive integer $N$, a real $A\ge2$ and a nonempty $K\subseteq\{1,\ldots,N\}$ put
$$
\kappa_K=\frac{|K|}{N},\qquad z_K=\overline\Phi^{-1}\!\Bigl(\frac{\kappa_K}{A}\Bigr),\qquad \tau_A(K)=h(z_K),
$$
so that $z_K\ge0$ because $\kappa_K/A\le1/2$. For a deterministic vector $t=(t_1,\ldots,t_N)\in\mathbb R^N$ define
$$
X_K(t)=\frac1{|K|}\sum_{i\in K}t_i,\qquad
M_A(t)=\max_{\varnothing\ne K\subseteq\{1,\ldots,N\}}\tau_A(K)\bigl(X_K(t)-\tau_A(K)\bigr).
$$
Let $p_i=\overline\Phi(t_i)$, with order statistics $p_{(1)}\le\cdots\le p_{(N)}$ including multiplicities. Let $A\ge2$ and $0<q\le e^{-1}/A$. If there is $k\in\{1,\ldots,N\}$ with $p_{(k)}\le qk/N$, then
$$
M_A(t)\ge\frac12\sqrt{\log\frac1{Aq}}-1 .
$$
The statement is deterministic: it holds for every $N$, every $t\in\mathbb R^N$, ties included, and the logarithm is natural.

## Motivation

This is a scale-invariant variant of the hinge reformulation in [the hinge form of the Simes event](../ideas/idea_e1c816206945.md) and [the convex hinge acceptance region](../ideas/idea_9dc45fd77c4b.md). There the ratio $X(x)/\psi(x)$ exceeds its threshold by only about $\log a/x$ at sparse scales. Multiplying the excess of a subset average over its Gaussian top-fraction mean $\tau_A(K)$ by $\tau_A(K)$ itself makes the gain from a crossing at level $q$ grow with $\log(1/(Aq))$ uniformly over all rank scales. Sparse crossings are therefore no longer charged per threshold window. The intended argument takes $K$ to be $k$ coordinates with $t_i\ge\overline\Phi^{-1}(qk/N)$, writes $\log(\overline\Phi(z_K)/\overline\Phi(u))=\int_{z_K}^u h$, and uses $0<h'=h(h-\mathrm{id})<1$.

## Proof

Throughout, $\phi(s)=e^{-s^2/2}/\sqrt{2\pi}$, $h=\phi/\overline\Phi$ and $L=\log(1/(Aq))$. Since $Aq\le e^{-1}$, we have $L\ge1$.

**Step 1 (basic facts on $\overline\Phi$).** By the fundamental theorem of calculus, $\overline\Phi$ is $C^\infty$ with $\overline\Phi'=-\phi<0$. Since $\int_{\mathbb R}\phi=1$, dominated convergence gives $\overline\Phi(s)\to1$ as $s\to-\infty$ and $\overline\Phi(s)\to0$ as $s\to\infty$, and $\overline\Phi(s)\in(0,1)$ for every $s$ because $\phi>0$. Hence $\overline\Phi$ is a strictly decreasing continuous bijection $\mathbb R\to(0,1)$, so $\overline\Phi^{-1}:(0,1)\to\mathbb R$ is well defined and strictly decreasing. By symmetry of $\phi$, $\overline\Phi(0)=1/2$. Consequently, for $t_i\in\mathbb R$ we have $p_i=\overline\Phi(t_i)\in(0,1)$, and for $c\in(0,1)$,
$$
p_i\le c\iff\overline\Phi(t_i)\le\overline\Phi\bigl(\overline\Phi^{-1}(c)\bigr)\iff t_i\ge\overline\Phi^{-1}(c).
$$
In particular $h=\phi/\overline\Phi$ is a well-defined positive $C^\infty$ function on $\mathbb R$.

**Step 2 (derivative of $h$).** Using $\phi'(s)=-s\phi(s)$ and $\overline\Phi'=-\phi$,
$$
h'(s)=\frac{\phi'(s)\overline\Phi(s)-\phi(s)\overline\Phi'(s)}{\overline\Phi(s)^2}=\frac{-s\phi(s)\overline\Phi(s)+\phi(s)^2}{\overline\Phi(s)^2}=h(s)\bigl(h(s)-s\bigr),
$$
and $(\log\overline\Phi)'=\overline\Phi'/\overline\Phi=-h$.

**Step 3 ($h'>0$ and $h\ge\sqrt{2/\pi}$ on $[0,\infty)$).** We claim $h(s)>s$ for every $s\in\mathbb R$. For $s\le0$ this holds because $h(s)>0\ge s$. For $s>0$, since $(-\phi)'(x)=x\phi(x)$ and $\phi(x)\to0$ as $x\to\infty$, we have $\int_s^\infty x\phi(x)\,dx=\phi(s)$; as $x/s>1$ for $x>s$ and $\phi>0$,
$$
\overline\Phi(s)=\int_s^\infty\phi(x)\,dx<\int_s^\infty\frac xs\,\phi(x)\,dx=\frac{\phi(s)}s,
$$
so $h(s)>s$. By Step 2, $h'(s)=h(s)(h(s)-s)>0$ for every $s$, so $h$ is strictly increasing. For $s\ge0$ this gives $h(s)\ge h(0)=\phi(0)/\overline\Phi(0)=(2\pi)^{-1/2}/(1/2)=\sqrt{2/\pi}$.

**Step 4 ($h'<1$).** Fix $s\in\mathbb R$ and let $\mu_s$ be the probability measure on $\mathbb R$ with density $\phi(x)\mathbf 1_{\{x>s\}}/\overline\Phi(s)$. As in Step 3, $\int_s^\infty x\phi(x)\,dx=\phi(s)$, so $\int x\,d\mu_s=h(s)$. Integrating by parts with $x\phi(x)=(-\phi)'(x)$, and using $x\phi(x)\to0$ as $x\to\infty$,
$$
\int_s^\infty x^2\phi(x)\,dx=\bigl[-x\phi(x)\bigr]_s^\infty+\int_s^\infty\phi(x)\,dx=s\phi(s)+\overline\Phi(s),
$$
so $\int x^2\,d\mu_s=1+s\,h(s)$. Therefore, by Step 2,
$$
\int\bigl(x-h(s)\bigr)^2\,d\mu_s(x)=1+s\,h(s)-h(s)^2=1-h(s)\bigl(h(s)-s\bigr)=1-h'(s).
$$
The left side is strictly positive: the integrand $(x-h(s))^2$ vanishes only at the single point $x=h(s)$, while the density of $\mu_s$ is strictly positive on $(s,\infty)$. Hence $h'(s)<1$ for every $s\in\mathbb R$. By the mean value theorem, for $s\ge z$ there is $\xi\in[z,s]$ with $h(s)-h(z)=h'(\xi)(s-z)\le s-z$, that is,
$$
h(s)\le h(z)+(s-z)\qquad(s\ge z).
$$

**Step 5 (the crossing subset).** Fix $k\in\{1,\ldots,N\}$ with $p_{(k)}\le qk/N$, and put $\kappa=k/N\in(0,1]$ and $c=q\kappa$. Since $A\ge2$ and $Aq\le e^{-1}$, we have $0<q<1$, so $c\in(0,1)$; put $u=\overline\Phi^{-1}(c)$. Choose indices $i_1,\ldots,i_k$, distinct, such that $p_{i_j}=p_{(j)}$ for $j=1,\ldots,k$ (possible because the order statistics are listed with multiplicity; ties are broken arbitrarily), and let $K=\{i_1,\ldots,i_k\}$. Then $|K|=k$ and $p_i\le p_{(k)}\le c$ for every $i\in K$, so by Step 1, $t_i\ge u$ for every $i\in K$, whence
$$
X_K(t)=\frac1k\sum_{i\in K}t_i\ge u .
$$
For this $K$, $\kappa_K=\kappa$ and $\kappa/A\in(0,1/2]$ since $A\ge2$; thus $z:=z_K=\overline\Phi^{-1}(\kappa/A)$ is well defined and $z\ge0$ because $\overline\Phi(z)=\kappa/A\le1/2=\overline\Phi(0)$ and $\overline\Phi$ is decreasing. Put $\tau:=\tau_A(K)=h(z)$; by Step 3, $\tau\ge\sqrt{2/\pi}>0$.

**Step 6 (exact Mills integral).** We have $\overline\Phi(u)=q\kappa<\kappa/A=\overline\Phi(z)$ because $Aq\le e^{-1}<1$; since $\overline\Phi$ is strictly decreasing, $d:=u-z>0$. By Step 2 and the fundamental theorem of calculus,
$$
\int_z^u h(s)\,ds=\log\overline\Phi(z)-\log\overline\Phi(u)=\log\frac{\kappa/A}{q\kappa}=\log\frac1{Aq}=L\ge1 .
$$

**Step 7 (lower bound for the $K$ term).** The maximum defining $M_A(t)$ runs over finitely many nonempty subsets and includes $K$. Since $\tau>0$ and $X_K(t)\ge u=z+d$,
$$
M_A(t)\ge\tau\bigl(X_K(t)-\tau\bigr)\ge\tau(u-\tau)=\tau d-\tau(\tau-z)=\tau d-h'(z)>\tau d-1,
$$
where $\tau(\tau-z)=h(z)(h(z)-z)=h'(z)$ by Step 2 and $h'(z)<1$ by Step 4.

**Step 8 (upper bound for $L$).** Integrating the inequality $h(s)\le h(z)+(s-z)$ of Step 4 over $s\in[z,z+d]$ and using Step 6,
$$
L=\int_z^{z+d}h(s)\,ds\le\tau d+\frac{d^2}2 .
$$
Put $a:=\tau d>0$. Since $\tau^2\ge2/\pi$ by Step 5, $d^2/2=a^2/(2\tau^2)\le\frac\pi4a^2$, and therefore
$$
g(a):=\frac\pi4a^2+a-L\ge0 .
$$

**Step 9 ($a>\frac12\sqrt L$).** The function $g$ is strictly increasing on $[0,\infty)$, since $g'(x)=\frac\pi2x+1>0$ there. Put $a_0=\frac12\sqrt L$. Then
$$
g(a_0)=\frac\pi{16}L+\frac12\sqrt L-L=\sqrt L\Bigl(\frac12-\Bigl(1-\frac\pi{16}\Bigr)\sqrt L\Bigr)\le\sqrt L\Bigl(\frac12-1+\frac\pi{16}\Bigr)=\sqrt L\Bigl(\frac\pi{16}-\frac12\Bigr)<0,
$$
where the first inequality uses $1-\pi/16>0$ and $\sqrt L\ge1$, and the last uses $\sqrt L>0$ and $\pi<8$. If $a\le a_0$, monotonicity would give $g(a)\le g(a_0)<0$, contradicting Step 8. Hence $a>a_0$.

**Step 10 (conclusion).** By Steps 7 and 9,
$$
M_A(t)>\tau d-1=a-1>\frac12\sqrt{\log\frac1{Aq}}-1 .
$$
Only the crossing hypothesis at the single rank $k$ was used, with no restriction on $N$, on $t$, or on ties, so the inequality of the statement holds (even strictly). $\square$
