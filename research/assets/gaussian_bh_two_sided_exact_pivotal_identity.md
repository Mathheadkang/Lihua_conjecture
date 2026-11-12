---
type: lemma
title: Exact exogenous-pivotal identity for two-sided Gaussian BH
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian
  - two_sided
  - pivotal_identity
  - extracted_20261106
---

## Statement

**Fixed notation.**
- $p(u)=2\overline\Phi(u)$ and $\phi$ is the standard normal density.
- For $0<q\le q_0\le2\overline\Phi(1)$, set $U=p^{-1}(q)\ge1$, $t_k=qk/N$, $u_k=p^{-1}(t_k)$ and $J_q=\lceil\sqrt U\rceil$. The constants $K_q=8\log U$ and $L_q=K_q+\sqrt U$ are as in Lei (204).
- A *universal constant* $C$ does not depend on $q,N,\theta,\Sigma$, or on block numbers, sizes or loadings. Every $\eta(q)$ is a function of $q$ alone with $\eta(q)\to0$.
- For a true null $i$, set $c_i=\Sigma_{-i,i}$ and $Y_i=T_{-i}-\theta_{-i}-c_iT_i$.
- For $x\in\mathbb R$ and $y\in\mathbb R^{N-1}$, let $\rho_i(x,y)$ be the largest qualifying BH rank $\widehat k_q$ of the vector with entry $0$ at $i$ and entries $p(|\theta_j+c_{ij}x+y_j|)$ at $j\ne i$. Put $\tau_i(x,y)=q\rho_i(x,y)/N\in[q/N,q]$ and $a(x;t)=\mathbf 1\{p(|x|)\le t\}/t$.
- Branch thresholds are $f^{\pm}_{i,y}(s)=\tau_i(\pm s,y)$ for $s\ge0$, and
$$
\Psi(f)=\int_0^\infty2\phi(s)\frac{\mathbf 1\{p(s)\le f(s)\}}{f(s)}\,ds .
$$


Local context from source A4: Fix $i$, $y$, a branch $\sigma\in\{\pm1\}$ and a level $k$. For $j\ne i$ put $b_j=\theta_j+y_j$ and $c=c_{ij}$.

**(A1 = G1, routine) Exact two-sided exogenous–pivotal identity.** For every $q\in(0,1)$, every admissible $(N,\theta,\Sigma)$ and every $i\in I_0=I_0^{(2)}(\theta)$:
   - (a) $Y_i\sim N(0,\Sigma_{-i,-i}-c_ic_i^{\mathsf T})$ is independent of $T_i$, and the covariance is PSD (Schur complement, $\Sigma_{ii}=1$). Singular $\Sigma$ is allowed.
   - (b) Pointwise, including ties and $R=0$:
     $$
     \mathbf 1\{i\in\mathcal R_q\}/(R_q\vee1)=(q/N)\,a(T_i;\tau_i(T_i,Y_i)).
     $$
     The forced-zero rank of $i$ equals $\rho_i(T_i,Y_i)$, and equals $R_q$ when $i$ is rejected. Reprove this; do not cite it from failed plans.
   - (c) For every Borel $g:\mathbb R^{N-1}\to\{t_1,\dots,t_N\}$, $\mathbb E\,a(T_i;g(Y_i))=1$. In particular this holds for the exogenous threshold $\tau_i(0,Y_i)$.
   - (d) With $\Delta_i:=\mathbb E\,a(T_i;\tau_i(T_i,Y_i))-1$ and $\pi_0=|I_0|/N$,
     $$
     \operatorname{FDR}^{(2)}_{\mathrm{BH}}(q;N,\theta,\Sigma)=q\pi_0+\frac qN\sum_{i\in I_0}\Delta_i ,\qquad \Delta_i\ge-1,\qquad \sum_{i\in I_0}\frac qN(1+\Delta_i)\le1 .
     $$
   - (e) Branch form. Write $T_i=\sigma s$ with $\sigma$ an independent uniform sign and $s$ of density $2\phi$ on $[0,\infty)$. Then
     $$
     \Delta_i=\mathbb E\Big[\tfrac12\big(\Psi(f^+_{i,Y_i})+\Psi(f^-_{i,Y_i})\big)\Big]-1 .
     $$
     Step structure. For fixed $(y,\sigma)$, $\rho_i(\sigma s,y)$ is a function of the indicators $\mathbf 1\{|b_j+\sigma c_{ij}s|\ge u_k\}$ for $j\ne i$ and $k\in[N]$. Each is the indicator of $[0,\infty)$ minus an open interval (A4(i)), so it changes value at most twice. Hence $f^\sigma_{i,y}$ is piecewise constant with at most $2N(N-1)$ jumps.

*Detail corrected:* at the left end of an inactive interval the indicator is left-continuous, so $f^\sigma_{i,y}$ need not be right-continuous. It agrees with its right-continuous version off a finite set. That changes no value of $\Psi$, and A2 is applied to this version.
   - (f) Duplication invariance. Repeating every coordinate $M$ times maps $\widehat k\mapsto M\widehat k$, keeps the threshold $q\widehat k/N$, keeps the FDP, and keeps every $\Delta_i$; for duplicated copies it follows from per-null expectations.


## Proof

Additional notation. For $x\in[0,1]^N$ put $n_x(t)=\#\{j:x_j\le t\}$. Then $x_{(k)}\le t$ if and only if $n_x(t)\ge k$, so
$$
\widehat k_q(x)=\max\bigl(\{0\}\cup\{k\in[N]:n_x(t_k)\ge k\}\bigr).
$$

### P0. Two facts about BH

- **(BH1)** If $\widehat k=\widehat k_q(x)\ge1$, then $R_q(x)=n_x(t_{\widehat k})=\widehat k$. Indeed $m:=n_x(t_{\widehat k})\ge\widehat k$. If $m>\widehat k$, then $m\le N$ and $n_x(t_m)\ge n_x(t_{\widehat k})=m$, so $m$ qualifies, which contradicts maximality.
- **(BH2)** If $x\le x'$ entrywise, then $n_x\ge n_{x'}$ pointwise, and hence $\widehat k_q(x)\ge\widehat k_q(x')$. The denominator $N$ is the same on both sides.

### A0 (established)

- If $I_0=\varnothing$, then $V=0$ and $\operatorname{FDP}=0$.
- If $N=1$ and $I_0=\{1\}$, then $\mathcal R=\{1\}$ exactly when $p_1\le q$. So $\operatorname{FDR}=\mathbb P(2\overline\Phi(|T_1|)\le q)=q$.
- For $q\le2\overline\Phi(1)$ we have $U\ge1$. The Mills bound $\overline\Phi(U)\le\phi(U)/U$ then gives $q=2\overline\Phi(U)\le2\phi(U)=\sqrt{2/\pi}\,e^{-U^2/2}<2e^{-U^2/2}$. Hence $U^2\le2\log(2/q)$, and the displayed bound of A0 follows with $\sqrt{\log(2/q)}=\sqrt{\log(1/q)}\,\bigl(1+\log2/\log(1/q)\bigr)^{1/2}$.

### A1 (established; gate G1)

**(a)** $(T_i,Y_i)$ is jointly Gaussian, and
$$
\operatorname{Cov}(Y_i,T_i)=\Sigma_{-i,i}-c_i\Sigma_{ii}=0 .
$$
Uncorrelated jointly Gaussian vectors are independent, also in the degenerate case, because the characteristic function factorises. Moreover $\mathbb EY_i=\theta_{-i}-\theta_{-i}-c_i\cdot0=0$. Expanding the covariance gives $\operatorname{Cov}(Y_i)=\Sigma_{-i,-i}-c_ic_i^{\mathsf T}$, which is PSD because it is a covariance matrix.

**(b)** Fix a realisation. Let $x$ be the p-value vector and let $x^0$ be $x$ with $x_i$ replaced by $0$.
- Since $T_j=\theta_j+c_{ij}T_i+(Y_i)_j$ for $j\ne i$, the vector $x^0$ is exactly the vector in the definition of $\rho_i(T_i,Y_i)$. So $k^0:=\rho_i(T_i,Y_i)=\widehat k_q(x^0)\ge1$, because $x^0_{(1)}=0\le t_1$.
- Also $n_{x^0}(t)=n_x(t)+\mathbf 1\{x_i>t\}$.

There are two cases.
- **Case $x_i\le t_{k^0}$.** Then $n_x(t_{k^0})=n_{x^0}(t_{k^0})\ge k^0$, so $\widehat k_q(x)\ge k^0$. BH2 gives the reverse inequality, so $\widehat k_q(x)=k^0$. Then $i\in\mathcal R$, and $R=k^0$ by BH1.
- **Case $x_i>t_{k^0}$.** BH2 gives $\widehat k_q(x)\le k^0$. Either $\widehat k_q(x)=0$ and $\mathcal R=\varnothing$, or $t_{\widehat k}\le t_{k^0}<x_i$. In both cases $i\notin\mathcal R$.

Hence $\mathbf 1\{i\in\mathcal R\}=\mathbf 1\{x_i\le t_{k^0}\}$, and $R\vee1=k^0$ on that event. Therefore
$$
\frac{\mathbf 1\{i\in\mathcal R_q\}}{R_q\vee1}=\frac{\mathbf 1\{p(|T_i|)\le\tau_i(T_i,Y_i)\}}{k^0}=\frac qN\,a(T_i;\tau_i(T_i,Y_i)).
$$
Only the counting function and non-strict inequalities were used, so ties and $R=0$ are included. The forced-zero rank is $k^0$, and it equals $R_q$ whenever $i$ is rejected.

**(c)** Since $\theta_i=0$ and $\Sigma_{ii}=1$, $T_i\sim N(0,1)$. So $\mathbb P(p(|T_i|)\le t)=\mathbb P(|T_i|\ge p^{-1}(t))=t$ for $t\in(0,1]$. By (a) and Fubini,
$$
\mathbb E[a(T_i;g(Y_i))\mid Y_i]=\frac{\mathbb P(p(|T_i|)\le g(Y_i)\mid Y_i)}{g(Y_i)}=1 .
$$
The map $y\mapsto\tau_i(0,y)$ is Borel: it is a finite combination of indicators of the closed sets $\{|\theta_j+y_j|\ge u_k\}$.

**(d)** Sum (b) over $i\in I_0$ and take expectations; all terms are finite because $0\le a\le N/q$. Then $\Delta_i\ge-1$ because $a\ge0$, and the last relation is $\operatorname{FDR}\le1$.

**(e)** Put $\sigma=\operatorname{sgn}T_i$ and $s=|T_i|$. By symmetry of $N(0,1)$, these are independent, $\sigma$ is uniform, $s$ has density $2\phi$, and $\{T_i=0\}$ is a null event. The pair $(\sigma,s)$ is independent of $Y_i$. Tonelli gives the branch formula. Measurability of $y\mapsto\Psi(f^\pm_{i,y})$ follows from joint Borel measurability of $(s,y)\mapsto a(\pm s;\tau_i(\pm s,y))$, so no cell decomposition is needed.

Step structure. For fixed $(y,\sigma)$, $\rho_i(\sigma s,y)$ is a function of the indicators $\mathbf 1\{|b_j+\sigma c_{ij}s|\ge u_k\}$ for $j\ne i$ and $k\in[N]$. Each is the indicator of $[0,\infty)$ minus an open interval (A4(i)), so it changes value at most twice. Hence $f^\sigma_{i,y}$ is piecewise constant with at most $2N(N-1)$ jumps.

*Detail corrected:* at the left end of an inactive interval the indicator is left-continuous, so $f^\sigma_{i,y}$ need not be right-continuous. It agrees with its right-continuous version off a finite set. That changes no value of $\Psi$, and A2 is applied to this version.

**(f)** Let $x'\in[0,1]^{MN}$ repeat each $x_j$ exactly $M$ times, and put $t'_k=qk/(MN)$. Then $n_{x'}=Mn_x$.
- At $k=M\widehat k$ we have $t'_k=t_{\widehat k}$ and $n_{x'}(t'_k)\ge M\widehat k$, so $M\widehat k$ qualifies.
- Suppose some $k>M\widehat k$ qualified for $x'$. Put $m=\lceil k/M\rceil\in(\widehat k,N]$. Then $t'_k\le t_m$ and $n_x(t_m)\ge n_x(t'_k)\ge k/M$. Since $n_x$ is an integer, $n_x(t_m)\ge m$, which contradicts maximality.

So $\widehat k'=M\widehat k$, and the threshold $q\widehat k'/(MN)=q\widehat k/N$ is unchanged. Then $\mathcal R'$ consists of all copies of $\mathcal R$, $V'=MV$, $R'=MR$, and the FDP is unchanged. For a copy $i'$ of null $i$, (b) gives
$$
\frac q{MN}(1+\Delta'_{i'})=\mathbb E\Big[\frac{\mathbf 1\{i\in\mathcal R\}}{M(R\vee1)}\Big]=\frac q{MN}(1+\Delta_i),
$$
since $R\ge1$ on $\{i\in\mathcal R\}$. Hence $\Delta'_{i'}=\Delta_i$.


### Native execution details (2026-11-06)

The extracted source text above is retained verbatim. The numbered derivation below establishes exactly clauses (a)–(f), independently of the source labels A2 and A4. The preserved A0 paragraph is a source aside: its reference to a displayed A0 bound has no corresponding target statement here, and no such bound is asserted or used in this proof. The zero-rank duplication case is supplied explicitly below. All levels $q\in(0,1)$ are covered; the small-level symbols $U,J_q,K_q,L_q$ are unused.

#### Step 1: deterministic counting facts

For $z\in[0,1]^N$, the $k$th order statistic is at most $t$ if and only if at least $k$ entries are at most $t$. Thus qualification is exactly $n_z(t_k)\ge k$. If the largest rank is $r>0$, let $m=n_z(t_r)\ge r$. Were $m>r$, the increasing grid would give $n_z(t_m)\ge n_z(t_r)=m$, contradicting maximality. Thus the rejection set has exactly $r$ elements. When the largest rank is zero its rejection set is empty by definition, so $R=0$ as well. Lowering entries increases every count and preserves every previously qualifying rank, establishing rank monotonicity. All comparisons remain non-strict, so these statements include arbitrary ties.

#### Step 2: singular Gaussian residual

For a two-sided true null, $\theta_i=0$. Linear transformation of the jointly Gaussian vector gives a centered jointly Gaussian pair $(T_i,Y_i)$ with variance of $T_i$ equal to one. Write $S=\Sigma_{-i,-i}$. The covariance expansion is
$$
\operatorname{Cov}(Y_i,T_i)=c_i-c_i=0,\qquad
\operatorname{Cov}(Y_i)=S-c_ic_i^{\mathsf T}-c_ic_i^{\mathsf T}+c_ic_i^{\mathsf T}=S-c_ic_i^{\mathsf T}=:D.
$$
For every vector $v$, $v^{\mathsf T}Dv=\operatorname{Var}(v^{\mathsf T}Y_i)\ge0$. For real $a$ and vector $v$, the joint characteristic function is
$$
\mathbb E e^{\mathrm i(aT_i+v^{\mathsf T}Y_i)}
=e^{-a^2/2-v^{\mathsf T}Dv/2}
=e^{-a^2/2}e^{-v^{\mathsf T}Dv/2}.
$$
It factors into the marginal characteristic functions without requiring $D$ to be invertible. This proves (a), including singular covariance and the zero-dimensional residual when $N=1$.

#### Step 3: pointwise forced-zero identity

Replace entry $z_i$ by zero. For every $t\ge0$, its count changes by precisely $\mathbf1\{z_i>t\}$, so $n_{z^0}(t)=n_z(t)+\mathbf1\{z_i>t\}$. The forced-zero largest rank $r^0$ is positive since its smallest entry is zero. If $z_i\le t_{r^0}$, the two counts agree at $t_{r^0}$; hence $r^0$ qualifies for $z$. Monotonicity gives the reverse rank inequality, so $R_q(z)=r^0$ and $i$ is rejected. If $z_i>t_{r^0}$, monotonicity gives rank at most $r^0$. At positive rank the rejection threshold is no larger than $t_{r^0}<z_i$, and at zero rank the rejection set is empty. Thus $i$ is not rejected in either event. Therefore
$$
\frac{\mathbf1\{i\in\mathcal R_q(z)\}}{R_q(z)\vee1}
=\frac{\mathbf1\{z_i\le t_{r^0}\}}{r^0}.
$$
Coordinatewise $T_j=\theta_j+c_{ij}T_i+(Y_i)_j$ identifies $z^0$ with the forced vector defining $\rho_i(T_i,Y_i)$. With $\tau_i=qr^0/N$, the right side equals $(q/N)a(T_i;\tau_i)$, proving (b). Ties belong to the first case. If $R=0$, the second case must hold and both sides vanish. For $N=1$, $r^0=1$, $\tau_i=q$, and both sides are exactly $\mathbf1\{p(|T_i|)\le q\}$.

#### Step 4: Borel structure and exogenous expectation

For every $q\in(0,1)$ define $t_k=qk/N$ and $u_k=p^{-1}(t_k)>0$; none of the small-level auxiliary notation is required. For the forced vector the rank-$k$ qualification event is
$$
1+\sum_{j\ne i}\mathbf1\{|\theta_j+c_{ij}x+y_j|\ge u_k\}\ge k.
$$
The finitely many inequalities are Borel in $(x,y)$, so their maximal qualifying index $\rho_i$ and the grid-valued $\tau_i$ are Borel. The map $(x,y)\mapsto a(x;\tau_i(x,y))$ is Borel and between zero and $N/q$. In particular $y\mapsto\tau_i(0,y)$ is Borel. Because $T_i\sim N(0,1)$, symmetry and continuity give $\mathbb P(p(|T_i|)\le t_k)=2\overline\Phi(u_k)=t_k$. For any Borel grid-valued $g$, independence from step 2 gives
$$
\mathbb E[a(T_i;g(Y_i))\mid Y_i]
=\sum_{k=1}^N\mathbf1\{g(Y_i)=t_k\}\frac{\mathbb P(p(|T_i|)\le t_k)}{t_k}=1.
$$
Integrability follows from the bound already stated. Taking expectations proves (c) and its exogenous special case.

#### Step 5: FDR decomposition

The finite sum of the pointwise identities in step 3 is the FDP. Taking expectations yields
$$
\operatorname{FDR}
=\frac qN\sum_{i\in I_0}\mathbb E a(T_i;\tau_i(T_i,Y_i))
=\frac{q|I_0|}{N}+\frac qN\sum_{i\in I_0}\Delta_i.
$$
Every expectation is finite by step 4 and nonnegative, giving $\Delta_i\ge-1$. Since the false-rejection count lies between zero and $R$, the FDP lies in $[0,1]$, proving $\sum_{i\in I_0}(q/N)(1+\Delta_i)\le1$. If there are no true nulls all sums and the FDP vanish. This proves (d).

#### Step 6: branch formula

Assign either sign at zero, which has probability zero. For every Borel $B\subseteq[0,\infty)$, the standard normal density gives
$$
\mathbb P(\operatorname{sgn}(T_i)=\pm1,\ |T_i|\in B)=\int_B\phi(s)\,ds
=\tfrac12\int_B2\phi(s)\,ds.
$$
Thus sign is uniform and independent of magnitude; step 2 makes their pair independent of $Y_i$. If $\mu_i$ denotes the probability law of $Y_i$, Tonelli applied to the nonnegative Borel integrand from step 4 gives
$$
1+\Delta_i
=\int\frac12\sum_{\sigma\in\{-1,1\}}\int_0^\infty
2\phi(s)a(\sigma s;\tau_i(\sigma s,y))\,ds\,\mu_i(dy)
=\mathbb E\left[\tfrac12\bigl(\Psi(f^+_{i,Y_i})+\Psi(f^-_{i,Y_i})\bigr)\right].
$$
The inner integral is a Borel function of $y$ by measurable integration, and it is at most $N/q$. Subtracting one gives the branch formula in (e).

#### Step 7: branch step structure

Fix $(i,y,\sigma)$ and a pair $(j,k)$, and put $d=\sigma c_{ij}$. If $d\ne0$, the strict inequality $|b_j+ds|<u_k$ is equivalent to
$$
\alpha<s<\beta,\qquad
\alpha=\min\{(-u_k-b_j)/d,(u_k-b_j)/d\},\quad
\beta=\max\{(-u_k-b_j)/d,(u_k-b_j)/d\}.
$$
Intersect this open interval with $[0,\infty)$. If $d=0$, the inactive set is the whole half-line when $|b_j|<u_k$ and empty otherwise. Thus each active indicator is constant except at at most two finite boundary locations. The union $E$ of boundaries over the $N(N-1)$ pairs has cardinality at most $2N(N-1)$. On every interval component of $[0,\infty)\setminus E$, every indicator, every qualifying-rank decision, and $f^\sigma_{i,y}$ are constant. Equality at a boundary makes the active indicator one; such a value need not equal its right limit, so no right-continuity of the original function is asserted. Assign each boundary its right-hand constant value to obtain a right-continuous grid-valued representative. The two functions differ only on the finite set $E$ (including zero if needed); Lebesgue integration against $2\phi(s)\,ds$ therefore gives identical $\Psi$. This proves all step-structure assertions in (e) directly, including zero loading; it uses no conclusion from source A4 or A2. For $N=1$ there are no pairs, and the threshold is the constant $q$.

#### Step 8: duplication, including zero rank

Let $M$ be any positive integer and repeat every entry of $z$ exactly $M$ times to form $z'$. Its count is $n_{z'}(t)=Mn_z(t)$ and its thresholds are $t'_k=qk/(MN)$. Write $r=\widehat k_q(z)$. When $r>0$, $Mr$ qualifies for $z'$ because $t'_{Mr}=t_r$ and $n_{z'}(t_r)\ge Mr$. When $r=0$, the automatic bound $\widehat k_q(z')\ge0=Mr$ replaces this qualification argument: zero is the sentinel in the maximum, not a positive qualifying rank. Conversely, if a positive duplicated rank $k>Mr$ qualifies, set $m=\lceil k/M\rceil$. Then $r<m\le N$, $t'_k\le t_m$, and
$$
n_z(t_m)\ge n_z(t'_k)=n_{z'}(t'_k)/M\ge k/M.
$$
Its integer value is at least $m$, contradicting maximality of $r$. Therefore the duplicated rank is exactly $Mr$, with equal thresholds. For $r>0$ each copy is rejected exactly when its original is; for $r=0$ both rejection sets are empty by definition. Null membership is also copied. Hence $V'=MV$ and $R'=MR$, giving equal FDP when $R>0$ and FDP zero in both dimensions otherwise.

Repeating Gaussian coordinates is a linear transformation of $T$ with repeated mean entries, positive semidefinite covariance, and unit diagonal, so it is an admissible possibly singular model. For a copied null $i'$, the pointwise contribution obeys
$$
\frac{\mathbf1\{i'\in\mathcal R'_q\}}{R'_q\vee1}
=\frac1M\frac{\mathbf1\{i\in\mathcal R_q\}}{R_q\vee1}.
$$
Indeed the numerator is zero on the zero-rejection event, and elsewhere $R'=MR$. Applying (b) in both dimensions and taking expectations yields
$$
\frac q{MN}(1+\Delta'_{i'})=\frac1M\frac qN(1+\Delta_i),
$$
so every copied excess equals the original. This proves (f).

## Provenance

Extracted verbatim from [the exogenous-pivotal blocks plan](../plans/plan_two_sided_exogenous_pivotal_blocks_20261105.md), Plan fixed notation and A1; Progress, Additional notation, P0, A0 and A1 (a)–(f). The branch regularity sentence in the original checklist is replaced by the explicit corrected version in Progress A1(e), copied above. No claim from the failed B4 step is used. The source proof and the extraction have not yet received independent verification. References to A2 and A4 in the copied text refer to the source plan sections.
