---
type: lemma
title: Dense Simes crossings under arbitrary Gaussian correlation cost order q
status: approved
source:
  kind: original
depends_on:
  - lehec2015_semilogconvex_density_tail
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
tags:
  - simes_positive_cover_route
---

# Dense Simes crossings under arbitrary Gaussian correlation cost order q

## Statement

There exist universal constants $C_D<\infty$ and $q_D\in(0,1/4]$ such that the following holds. Let $N$ be a positive integer, $\Sigma\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) (singular matrices allowed), $T\sim\mathcal N_N(0,\Sigma)$, and $p_i=\overline\Phi(T_i)$ the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md). For $q\in(0,1)$ put $u_q=\overline\Phi^{-1}(q)$ and, for $\delta>0$, define the dense-crossing event
$$
D_{q,\delta}=\Bigl\{\exists k\in[N]:\ \frac{qk}{N}\ge\overline\Phi(u_q+\delta)\ \text{ and }\ \#\Bigl\{i\in[N]:p_i\le\frac{qk}{N}\Bigr\}\ge k\Bigr\}.
$$
Then for every $\delta\in(0,1]$ and every $q\in(0,q_D]$,
$$
\mathbb P_{N,0,\Sigma}(D_{q,\delta})\le C_D\,q.
$$
The constants do not depend on $N$, $\Sigma$, $\delta$, the signs of the correlations, or the rank of $\Sigma$.

## Proof

Throughout, $\varphi(t)=(2\pi)^{-1/2}e^{-t^2/2}$, logarithms are natural, and $C_L$ denotes the universal constant of [Lehec's tail bound](lehec2015_semilogconvex_density_tail.md). We prove the statement with
$$
q_D=\overline\Phi(3),\qquad C_D=8\sqrt{2\pi}\,e^{1/2}\,C_L .
$$
Note $q_D\in(0,1/4]$, since $0<\overline\Phi(3)\le\varphi(3)/3<1/4$ by the Mills bound (a) below.

**Step 1 (Gaussian representation).** Since $\Sigma\in\mathcal C_N$ is symmetric positive semidefinite, it has a symmetric positive semidefinite square root $A=\Sigma^{1/2}\in\mathbb R^{N\times N}$ with $AA^{\mathsf T}=\Sigma$. Put $n=N$ and let $a_i\in\mathbb R^n$ be the $i$-th row of $A$; then $|a_i|^2=(AA^{\mathsf T})_{ii}=\Sigma_{ii}=1$. If $g\sim\gamma_n$, then $Ag$ is centered jointly Gaussian with covariance $AA^{\mathsf T}=\Sigma$, so $Ag$ has the law of $T$ under $\mathbb P_{N,0,\Sigma}$ (singular $\Sigma$ included). Since $D_{q,\delta}$ is determined by $T$ through the p-values $p_i=\overline\Phi(T_i)$, we get $\mathbb P_{N,0,\Sigma}(D_{q,\delta})=\gamma_n(\widetilde D)$, where $\widetilde D\subset\mathbb R^n$ is the set of $x$ for which $D_{q,\delta}$ occurs with $T_i$ replaced by $a_i\cdot x$. By Step 2 below, $\widetilde D$ is a finite union over $k$ (and over $k$-subsets of $[N]$) of finite intersections of closed half-spaces $\{a_i\cdot x\ge t_k\}$, hence Borel.

**Step 2 (thresholds).** Fix $\delta\in(0,1]$ and $q\in(0,q_D]$. Since $\overline\Phi$ is a continuous strictly decreasing bijection $\mathbb R\to(0,1)$ and $q\le\overline\Phi(3)$, we have $u_q=\overline\Phi^{-1}(q)\ge3$. For $k\in[N]$, $qk/N\in(0,q]\subset(0,1)$; put $t_k=\overline\Phi^{-1}(qk/N)$. Then $p_i\le qk/N\iff\overline\Phi(T_i)\le\overline\Phi(t_k)\iff T_i\ge t_k$. Since $qk/N\le q$, $t_k\ge u_q$. If moreover $qk/N\ge\overline\Phi(u_q+\delta)$, then $t_k\le u_q+\delta\le u_q+1\le2u_q$ (as $u_q\ge1$).

**Step 3 (the averaged tilt is an admissible Lehec density).** Put $\lambda=u_q>0$ and
$$
f(x)=\frac1N\sum_{i=1}^N\exp\Bigl(\lambda\,a_i\cdot x-\frac{\lambda^2}{2}\Bigr),\qquad x\in\mathbb R^n .
$$
Then $f$ is $C^\infty$ and takes values in $(0,\infty)$. By the Gaussian moment generating function, $\int e^{\lambda a_i\cdot x}\,\gamma_n(dx)=e^{\lambda^2|a_i|^2/2}=e^{\lambda^2/2}$, so $\int f\,d\gamma_n=1$. Finally $\log f(x)=\log\sum_j e^{\lambda a_j\cdot x}-\log N-\lambda^2/2$; with the weights $\pi_i(x)=e^{\lambda a_i\cdot x}/\sum_je^{\lambda a_j\cdot x}$ and $m(x)=\sum_i\pi_i(x)a_i$, direct differentiation gives $\nabla\log f=\lambda m$ and
$$
\nabla^2\log f(x)=\lambda^2\Bigl(\sum_i\pi_i(x)a_ia_i^{\mathsf T}-m(x)m(x)^{\mathsf T}\Bigr)=\lambda^2\sum_i\pi_i(x)\,(a_i-m(x))(a_i-m(x))^{\mathsf T}\succeq0 .
$$
Hence $f$ satisfies every hypothesis of Lehec's tail bound (smooth, positive, normalized, global log-Hessian bound) with $n=N\ge1$ and $\beta=0$, so $\max(\beta,1)=1$, and Lehec's tail bound gives
$$
\gamma_n(\{f>r\})\le\frac{C_L}{r\sqrt{\log r}}\qquad\text{for every }r>1. \tag{L}
$$
No supremum, truncation or limit of densities is involved.

**Step 4 (Mills bounds).** For $t>0$:

(a) $\overline\Phi(t)\le\varphi(t)/t$, because $\overline\Phi(t)=\int_t^\infty\varphi(u)\,du\le\int_t^\infty\frac ut\varphi(u)\,du=\varphi(t)/t$.

(b) $\overline\Phi(t)\ge\frac{t}{1+t^2}\varphi(t)$. Indeed let $h(t)=\overline\Phi(t)-t\varphi(t)/(1+t^2)$. Using $\varphi'(t)=-t\varphi(t)$,
$$
\frac{d}{dt}\frac{t\varphi(t)}{1+t^2}=\varphi(t)\frac{(1-t^2)(1+t^2)-2t^2}{(1+t^2)^2}=\varphi(t)\frac{1-2t^2-t^4}{(1+t^2)^2},
$$
so $h'(t)=-\varphi(t)\frac{(1+t^2)^2+1-2t^2-t^4}{(1+t^2)^2}=-\frac{2\varphi(t)}{(1+t^2)^2}<0$. As $h(t)\to0$ when $t\to\infty$, $h$ is decreasing to $0$, hence $h\ge0$.

Also $t/(1+t^2)\ge1/(2t)$ for $t\ge1$, since this is $2t^2\ge1+t^2$.

**Step 5 (lower bound for $f$ on the event).** Let $x\in\widetilde D$ and choose a witness $k\in[N]$: $qk/N\ge\overline\Phi(u_q+\delta)$ and at least $k$ indices $i$ satisfy $a_i\cdot x\ge t_k$ (Step 2). For each such $i$, $\exp(\lambda a_i\cdot x-\lambda^2/2)\ge\exp(\lambda t_k-\lambda^2/2)$ because $\lambda>0$, and all other terms of $f$ are positive. Hence, using $k/N=\overline\Phi(t_k)/q$,
$$
f(x)\ge\frac kN\,e^{u_qt_k-u_q^2/2}=\frac1q\,\overline\Phi(t_k)\,e^{u_qt_k-u_q^2/2}.
$$
By Step 4(b) and $\varphi(t_k)e^{u_qt_k-u_q^2/2}=(2\pi)^{-1/2}e^{-(t_k-u_q)^2/2}$,
$$
\overline\Phi(t_k)\,e^{u_qt_k-u_q^2/2}\ge\frac{t_k}{1+t_k^2}\,(2\pi)^{-1/2}e^{-(t_k-u_q)^2/2}.
$$
By Step 2, $0\le t_k-u_q\le1$ and $1\le u_q\le t_k\le2u_q$, so $\frac{t_k}{1+t_k^2}\ge\frac1{2t_k}\ge\frac1{4u_q}$ and $e^{-(t_k-u_q)^2/2}\ge e^{-1/2}$. Therefore
$$
\widetilde D\subset\{f\ge r_q\},\qquad r_q=\frac{c_0}{q\,u_q},\quad c_0=\frac{e^{-1/2}}{4\sqrt{2\pi}} .
$$

**Step 6 (size of $r_q$).** By Step 4(a) at $t=u_q$, $q\,u_q=\overline\Phi(u_q)\,u_q\le\varphi(u_q)$, so
$$
r_q\ge c_0\sqrt{2\pi}\,e^{u_q^2/2}=\tfrac14e^{-1/2}e^{u_q^2/2},\qquad \log r_q\ge\frac{u_q^2}{2}-\frac12-\log4\ge\frac{u_q^2}{4},
$$
the last inequality because $u_q^2/4\ge9/4>1/2+\log4$. In particular $r_q>1$ and $\sqrt{\log r_q}\ge u_q/2$.

**Step 7 (apply Lehec).** For every $r\in(1,r_q)$, $\{f\ge r_q\}\subset\{f>r\}$, so by Step 5 and (L), $\gamma_n(\widetilde D)\le C_L/(r\sqrt{\log r})$. The right side is continuous in $r>1$; letting $r\uparrow r_q$ and using Step 6,
$$
\gamma_n(\widetilde D)\le\frac{C_L}{r_q\sqrt{\log r_q}}\le C_L\cdot\frac{q\,u_q}{c_0}\cdot\frac{2}{u_q}=\frac{2C_L}{c_0}\,q=8\sqrt{2\pi}\,e^{1/2}C_L\,q=C_D\,q .
$$
By Step 1, $\mathbb P_{N,0,\Sigma}(D_{q,\delta})=\gamma_n(\widetilde D)\le C_Dq$. The constants $q_D=\overline\Phi(3)$ and $C_D$ involve only the universal constant $C_L$, which is independent of $n$ and $f$; hence they do not depend on $N$, $\Sigma$ (its rank or the signs of its entries), $\delta\in(0,1]$ or $q\in(0,q_D]$. The hypothesis $\delta\le1$ is used only for $t_k\le u_q+1$ in Step 2. $\blacksquare$
