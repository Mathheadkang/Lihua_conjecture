---
type: lemma
schema_version: 2
title: >-
  Pathwise clump-bracket bound for the BH false discovery proportion of a null
  subset
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - current_phase
  - universal_order
  - one_sided
  - compound_poisson_route
---

# Pathwise clump-bracket bound for the BH false discovery proportion of a null subset

## Statement

Fix an integer $N\ge1$, a level $q\in(0,1)$, a set $I_0\subseteq\{1,\ldots,N\}$, and a deterministic vector $p=(p_1,\ldots,p_N)\in[0,1]^N$. Let $\mathcal R_q(p)$ be the rejection set of the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $q$ (largest qualifying rank, multiplicities, non-strict comparisons), and $R=|\mathcal R_q(p)|$. Let $S\subseteq I_0$ and let $K_1,\ldots,K_L$ be nonempty sets partitioning $S$ (the clumps). For $x\in[0,1]^N$ write $R_q(x)=|\mathcal R_q(x)|$.

For $i\in K_l$ define the vectors $p^{(i,0)},p^{(i,*)}\in[0,1]^N$ by
$$
p^{(i,0)}_j=\begin{cases}0,&j=i,\\1,&j\in K_l\setminus\{i\},\\p_j,&j\notin K_l,\end{cases}
\qquad
p^{(i,*)}_j=\begin{cases}0,&j\in K_l,\\p_j,&j\notin K_l,\end{cases}
$$
and put
$$
R_{i,0}=R_q(p^{(i,0)}),\qquad R_{i,*}=R_q(p^{(i,*)}),\qquad
D_i=\bigl|\{j\in K_l:p_j\le p_i\}\bigr|,
$$
$$
\Psi_i=\frac{\mathbf 1\{p_i\le qR_{i,*}/N\}}{\max\{R_{i,0},\,D_i,\,Np_i/q\}}.
$$
Then $R_{i,0}\ge1$ and $D_i\ge1$, so $\Psi_i$ is well defined, $R_{i,0}$ and $R_{i,*}$ are functions of $(p_j)_{j\notin K_l}$ alone, and
$$
\frac{|\mathcal R_q(p)\cap S|}{R\vee1}\le\sum_{l=1}^L\sum_{i\in K_l}\Psi_i .
$$
Consequently, for random p-values on any probability space, with the original null labels and the actual BH rejection count, the [false discovery rate](../definitions/false_discovery_rate.md) contribution of $S$ satisfies
$$
\mathbb E\!\left[\frac{|\mathcal R_q\cap S|}{R\vee1}\right]\le\mathbb E\Bigl[\sum_{i\in S}\Psi_i\Bigr].
$$
No independence, positive dependence, or distributional assumption is made. Here $R\vee1=\max\{R,1\}$. The clumps only group terms; $R$, $R_{i,0}$ and $R_{i,*}$ are always counts of the same ordinary BH procedure on all $N$ coordinates.

## Proof

Throughout, for $x\in[0,1]^N$ and $t\in\mathbb R$ put $F_x(t)=|\{j\in\{1,\ldots,N\}:x_j\le t\}|$, write $\widehat k(x)=\widehat k_q(x)$, and say that a rank $k\in\{1,\ldots,N\}$ *qualifies* for $x$ if $x_{(k)}\le qk/N$, where $x_{(1)}\le\cdots\le x_{(N)}$ are the order statistics with multiplicities, as in the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md). Inequalities between vectors are coordinatewise.

**Step 1 (order-statistic counting).** For $k\in\{1,\ldots,N\}$ and $t\in\mathbb R$, $x_{(k)}\le t$ if and only if $F_x(t)\ge k$. If $x_{(k)}\le t$, then $x_{(1)},\ldots,x_{(k)}$ are the values of $k$ distinct coordinates, all at most $t$, so $F_x(t)\ge k$. Conversely, if at least $k$ coordinates are at most $t$, then the $k$ smallest coordinates (with multiplicities) are all at most $t$, in particular $x_{(k)}\le t$. Hence $k$ qualifies for $x$ if and only if $F_x(qk/N)\ge k$.

**Step 2 ($R_q(x)=\widehat k(x)$).** If $\widehat k(x)=0$, then $\mathcal R_q(x)=\varnothing$ by definition and $R_q(x)=0$. Let $k:=\widehat k(x)\ge1$. By definition $\mathcal R_q(x)=\{j:x_j\le qk/N\}$, so $R_q(x)=F_x(qk/N)$, and since $k$ qualifies, Step 1 gives $R_q(x)\ge k$. Suppose $F_x(qk/N)\ge k+1$. Since $F_x(qk/N)\le N$, this forces $k<N$, and as $F_x$ is nondecreasing, $F_x(q(k+1)/N)\ge F_x(qk/N)\ge k+1$; by Step 1 the rank $k+1$ qualifies, contradicting the maximality of $k$. Hence $R_q(x)=k=\widehat k(x)$.

**Step 3 (monotonicity).** If $x\le y$, then $F_x(t)\ge F_y(t)$ for every $t$ (every coordinate $y_j\le t$ has $x_j\le y_j\le t$). By Step 1 every rank qualifying for $y$ qualifies for $x$, so $\widehat k(x)\ge\widehat k(y)$, and by Step 2 $R_q(x)\ge R_q(y)$.

**Step 4 (zeroing a rejected coordinate).** Let $R=R_q(p)\ge1$, $i\in\mathcal R_q(p)$, and let $p'$ agree with $p$ except $p'_i=0$. By the definition of the rejection set and Step 2, $p_i\le q\widehat k(p)/N=qR/N$. For every $t\ge p_i$ both $p_i\le t$ and $0\le t$ hold, while the other coordinates coincide, so $F_{p'}(t)=F_p(t)$. For every rank $k\in\{R,\ldots,N\}$ we have $qk/N\ge qR/N\ge p_i$, so by Step 1 the rank $k$ qualifies for $p'$ if and only if it qualifies for $p$. The rank $R=\widehat k(p)$ qualifies for $p$ and no rank $k>R$ does; hence the same holds for $p'$, so $\widehat k(p')=R$ and, by Step 2, $R_q(p')=R$.

**Step 5 (well-definedness and dependence).** Fix $l$ and $i\in K_l$. Since $p^{(i,0)}_i=0$, we get $p^{(i,0)}_{(1)}=0\le q/N$, so rank $1$ qualifies for $p^{(i,0)}$, $\widehat k(p^{(i,0)})\ge1$, and $R_{i,0}\ge1$ by Step 2. Also $D_i\ge1$, because $j=i$ satisfies $p_i\le p_i$. Thus $\max\{R_{i,0},D_i,Np_i/q\}\ge1$, $\Psi_i$ is well defined, and $0\le\Psi_i\le1$. For fixed $i$ and $K_l$, the coordinates of $p^{(i,0)}$ and of $p^{(i,*)}$ indexed by $K_l$ are the constants $0$ or $1$ prescribed by $i$ and $K_l$, and the coordinates indexed by $j\notin K_l$ equal $p_j$. Hence $p^{(i,0)}$ and $p^{(i,*)}$, and therefore $R_{i,0}=R_q(p^{(i,0)})$ and $R_{i,*}=R_q(p^{(i,*)})$, are functions of $(p_j)_{j\notin K_l}$ alone.

**Step 6 (termwise charge).** Assume $R\ge1$ and $i\in\mathcal R_q(p)\cap K_l$. We show $\Psi_i\ge1/R$. Recall $p_i\le qR/N$ from Step 4.

- *Indicator.* $p^{(i,*)}\le p$, since coordinates in $K_l$ are lowered to $0$ and the others are unchanged. By Step 3, $R_{i,*}\ge R$, so $p_i\le qR/N\le qR_{i,*}/N$ and the indicator in $\Psi_i$ equals $1$.
- *Third entry.* $p_i\le qR/N$ gives $Np_i/q\le R$.
- *Second entry.* Every $j\in K_l$ with $p_j\le p_i$ satisfies $p_j\le qR/N=q\widehat k(p)/N$, hence $j\in\mathcal R_q(p)$. So $\{j\in K_l:p_j\le p_i\}\subseteq\mathcal R_q(p)$ and $D_i\le R$.
- *First entry.* With $p'$ as in Step 4, $p^{(i,0)}\ge p'$: coordinate $i$ is $0$ in both, coordinates $j\in K_l\setminus\{i\}$ satisfy $p^{(i,0)}_j=1\ge p_j=p'_j$, and coordinates outside $K_l$ coincide. By Step 3 and Step 4, $R_{i,0}=R_q(p^{(i,0)})\le R_q(p')=R$.

Therefore $1\le\max\{R_{i,0},D_i,Np_i/q\}\le R$, and $\Psi_i=1/\max\{R_{i,0},D_i,Np_i/q\}\ge1/R$.

**Step 7 (pathwise inequality).** If $R=0$, then $\mathcal R_q(p)=\varnothing$ and the left side is $0\le\sum_{l}\sum_{i\in K_l}\Psi_i$, as every $\Psi_i\ge0$ by Step 5. If $R\ge1$, then $R\vee1=R$, and since $K_1,\ldots,K_L$ partition $S$, Step 6 for the rejected $i\in S$ and $\Psi_i\ge0$ for the others give
$$
\frac{|\mathcal R_q(p)\cap S|}{R}=\sum_{i\in\mathcal R_q(p)\cap S}\frac1R\le\sum_{i\in\mathcal R_q(p)\cap S}\Psi_i\le\sum_{i\in S}\Psi_i=\sum_{l=1}^L\sum_{i\in K_l}\Psi_i .
$$

**Step 8 (expectation).** Let $p$ be a random vector with values in $[0,1]^N$ on some probability space. Each order statistic $x\mapsto x_{(k)}$ is continuous on $[0,1]^N$, so $\widehat k(x)=\max_{1\le k\le N}k\,\mathbf 1\{x_{(k)}\le qk/N\}$ is Borel, and so are the indicators $\mathbf 1\{j\in\mathcal R_q(x)\}=\mathbf 1\{\widehat k(x)\ge1\}\mathbf 1\{x_j\le q\widehat k(x)/N\}$; hence $R_q(x)$ and $|\mathcal R_q(x)\cap S|$ are Borel functions of $x$. The maps $x\mapsto x^{(i,0)}$ and $x\mapsto x^{(i,*)}$ (defined by the same formulas) are continuous, $D_i=\sum_{j\in K_l}\mathbf 1\{x_j\le x_i\}$ is Borel, and so $\Psi_i$ is a Borel function of $x$ with values in $[0,1]$ (its denominator is at least $1$ by Step 5). Thus both sides of the inequality of Step 7, evaluated at $p$, are bounded nonnegative random variables, the inequality holds at every sample point, and taking expectations gives
$$
\mathbb E\!\left[\frac{|\mathcal R_q\cap S|}{R\vee1}\right]\le\mathbb E\Bigl[\sum_{i\in S}\Psi_i\Bigr].
$$
No independence or distributional assumption was used; $S\subseteq I_0$ only fixes which coordinates are summed, so the left side is the contribution of $S$ to the [false discovery rate](../definitions/false_discovery_rate.md) with the original null labels and the actual BH count $R$. $\blacksquare$
