---
type: lemma
title: Random positive-class cover transfer for the all-null Gaussian Simes event
status: approved
source:
  kind: original
depends_on:
  - lib_chi2024_positive_gaussian_simes
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
tags:
  - simes_positive_cover_route
---

# Random positive-class cover transfer for the all-null Gaussian Simes event

## Statement

Let $N$ be a positive integer, $\Sigma\in\mathcal C_N$ in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) (singular matrices allowed), $T\sim\mathcal N_N(0,\Sigma)$, and $p_i=\overline\Phi(T_i)$ the [one-sided Gaussian p-values](../definitions/gaussian_test_pvalues.md). Call a nonempty set $S\subseteq[N]$ a positive class of $\Sigma$ if $\Sigma_{ij}\ge0$ for all $i,j\in S$. Let $\pi$ be a probability measure on the positive classes of $\Sigma$; it is deterministic, that is, it may depend on $N$, $\Sigma$ and the constants below but not on $T$.

Fix $q\in(0,1)$ and $c\in(0,1]$ with $q<c$. Let $\mathcal A=\mathcal R_q(p)$ be the rejection set of the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $q$, put $r=|\mathcal A|$, and let $E_q=\{\exists k\in[N]:p_{(k)}\le qk/N\}=\{r\ge1\}$. Define the hitting mass
$$
h(T)=\pi\Bigl(\Bigl\{S:\ |\mathcal A\cap S|\ge\max\Bigl(1,\ \frac{c\,|S|\,r}{N}\Bigr)\Bigr\}\Bigr)
\quad\text{on }E_q,\qquad h(T)=0\ \text{off }E_q.
$$
Then for every $c_*\in(0,1]$,
$$
\mathbb P_{N,0,\Sigma}\bigl(E_q\cap\{h(T)\ge c_*\}\bigr)\le\frac{q}{c\,c_*}.
$$

## Proof

Throughout, write $\mathbb P=\mathbb P_{N,0,\Sigma}$, $\widehat k=\widehat k_q(p)$, and $S_K$ for the Simes function $S_K(x)=\min_{1\le k\le K}\frac Kk x_{(k)}$ on $[0,1]^K$, as in [the Simes function and uniform p-values](../library/chi2024_negative_dependence/definitions/lib_chi2024_simes_function_uniform_pvalues.md). For $S\subseteq[N]$ put $p_S=(p_i)_{i\in S}$, ordered by increasing index, and write $p^S_{(1)}\le\cdots\le p^S_{(|S|)}$ for its order statistics with multiplicities.

**Step 1 (finiteness and measurability).** A positive class is a nonempty subset of $[N]$, so there are at most $2^N-1$ positive classes. Hence $\pi$ is determined by the weights $\pi_S=\pi(\{S\})\ge0$, which sum to $1$ over the positive classes; these weights do not depend on $T$. The map $T\mapsto p=(\overline\Phi(T_i))_{i\in[N]}$ is continuous from $\mathbb R^N$ to $(0,1)^N\subseteq[0,1]^N$, and each order statistic $p_{(k)}$ is a continuous function of $p$. So each event $\{p_{(k)}\le qk/N\}$ is Borel, and $\widehat k$ takes finitely many values, each on a Borel set. For each $i$ the event $\{i\in\mathcal A\}=\bigcup_{k=1}^N\bigl(\{\widehat k=k\}\cap\{p_i\le qk/N\}\bigr)$ is Borel. Hence $r=\sum_i\mathbf 1\{i\in\mathcal A\}$, each $|\mathcal A\cap S|=\sum_{i\in S}\mathbf 1\{i\in\mathcal A\}$, and $E_q=\bigcup_k\{p_{(k)}\le qk/N\}$ are Borel. Then
$$
h(T)=\mathbf 1_{E_q}\sum_{S}\pi_S\,\mathbf 1\Bigl\{|\mathcal A\cap S|\ge\max\Bigl(1,\frac{c|S|r}{N}\Bigr)\Bigr\},
$$
the sum running over positive classes, is a finite combination of Borel indicators. Thus $E_q\cap\{h\ge c_*\}$ is an event. Similarly each $\{S_{|S|}(p_S)\le q/c\}$ is Borel, because $S_{|S|}$ is continuous.

We also check the identity $E_q=\{r\ge1\}$ used in the statement. If some $k$ has $p_{(k)}\le qk/N$, then $\widehat k\ge1$, and the $\widehat k$ indices carrying the values $p_{(1)},\ldots,p_{(\widehat k)}$ all have $p_i\le p_{(\widehat k)}\le q\widehat k/N$. They lie in $\mathcal A$, so $r\ge\widehat k\ge1$. Conversely, if no such $k$ exists then $\widehat k=0$ and $\mathcal A=\varnothing$.

**Step 2 (deterministic per-class Simes reduction).** Fix a realization in $E_q$, so $\widehat k\ge1$ and $r\ge1$. As just shown, $r\ge\widehat k$. Every $i\in\mathcal A$ satisfies $p_i\le q\widehat k/N\le qr/N$.

Fix a positive class $S$ in the set defining $h(T)$. Put $K=|S|$ and $m=|\mathcal A\cap S|$, so that $m\ge1$ and $m\ge cKr/N$. Since $\mathcal A\cap S\subseteq S$, we have $1\le m\le K$. The vector $p_S$ has at least $m$ coordinates, namely those indexed by $\mathcal A\cap S$, that are $\le qr/N$. Hence its $m$-th smallest value satisfies $p^S_{(m)}\le qr/N$. Taking $k=m$ in the minimum defining $S_K$, and then using $m\ge cKr/N>0$,
$$
S_K(p_S)\le\frac Km\,p^S_{(m)}\le\frac{qKr}{Nm}\le\frac{qKr}{N}\cdot\frac{N}{cKr}=\frac qc .
$$
So on $E_q$ the set of classes defining $h(T)$ is contained in $\{S:S_{|S|}(p_S)\le q/c\}$. Since all $\pi_S\ge0$, this gives
$$
h(T)\le g(T):=\sum_S\pi_S\,\mathbf 1\{S_{|S|}(p_S)\le q/c\}\qquad\text{on }E_q .
$$

**Step 3 (the library theorem for one fixed positive class).** Fix a positive class $S$ with $K=|S|\ge1$. Under $\theta=0$, the vector $Y=T_S$ is a linear image of $T$. By the definition of joint Gaussianity in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), $Y$ is jointly Gaussian and centered, with covariance equal to the principal submatrix $\Sigma_S=(\Sigma_{ij})_{i,j\in S}$. This submatrix is symmetric and positive semidefinite, since $x^{\mathsf T}\Sigma_Sx=\tilde x^{\mathsf T}\Sigma\tilde x\ge0$ for the zero extension $\tilde x$ of $x$, and it has unit diagonal. So the marginal variances of $Y$ equal $1>0$, and the correlation matrix of $Y$ is $\Sigma_S$, possibly singular. With $f_i=\overline\Phi$ for every $i\in S$, a continuous, hence measurable, nonincreasing function, we have $p_S=(f_i(Y_i))_{i\in S}$. Hence $p_S\in\mathcal G_{\Sigma_S}$ in the sense of [Gaussian dependence](../library/chi2024_negative_dependence/definitions/lib_chi2024_gaussian_dependence.md).

Each $T_i\sim\mathcal N(0,1)$, and $\overline\Phi$ is a continuous strictly decreasing bijection $\mathbb R\to(0,1)$. So for $u\in(0,1)$,
$$
\mathbb P(p_i\le u)=\mathbb P\bigl(T_i\ge\overline\Phi^{-1}(u)\bigr)=\overline\Phi\bigl(\overline\Phi^{-1}(u)\bigr)=u .
$$
Also $\mathbb P(p_i\le0)=0$ and $\mathbb P(p_i\le1)=1$. Hence each $p_i$ is uniform on $[0,1]$, and $p_S\in\mathcal U^K$. Because $S$ is a positive class, $(\Sigma_S)_{ij}=\Sigma_{ij}\ge0$ for all distinct $i,j\in S$; for $K=1$ this condition is vacuous. Finally, $\alpha:=q/c\in(0,1)$ because $0<q<c\le1$. All hypotheses of [the positive Gaussian Simes inequality](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) (Theorem 8(I); the mixture extension is not used) hold. It gives
$$
\mathbb P\bigl(S_K(p_S)\le q/c\bigr)\le\frac qc .
$$

**Step 4 (Markov's inequality).** Since $c_*>0$ and $h=0$ off $E_q$, Step 2 gives $E_q\cap\{h\ge c_*\}\subseteq\{g\ge c_*\}$. The function $g$ is a nonnegative finite combination of Borel indicators, and its weights $\pi_S$ are deterministic. Markov's inequality, linearity of expectation, and Step 3 applied to each positive class $S$ give
$$
\mathbb P\bigl(E_q\cap\{h\ge c_*\}\bigr)\le\mathbb P(g\ge c_*)\le\frac{\mathbb E g}{c_*}=\frac1{c_*}\sum_S\pi_S\,\mathbb P\bigl(S_{|S|}(p_S)\le q/c\bigr)\le\frac1{c_*}\sum_S\pi_S\,\frac qc=\frac{q}{c\,c_*}.
$$
This is the claimed bound. No assumption was made on $N$, on the singularity of $\Sigma$, or on the signs of entries of $\Sigma$ outside the classes charged by $\pi$. $\blacksquare$
