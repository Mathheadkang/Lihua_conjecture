---
type: lemma
title: Baseline-subtracted pivotal identity for two-sided Gaussian BH
status: draft
source:
  kind: original
depends_on:
  - gaussian_bh_two_sided_exact_pivotal_identity
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_multifactor_representation
  - gaussian_one_common_factor_model
  - conditional_pvalue_distributions
tags:
  - gaussian
  - two_sided
  - baseline_subtracted
  - extracted_20261106
---

## Statement

**Fixed notation.**
- $p(u)=2\overline\Phi(u)$, $\phi$ standard normal density, $U=p^{-1}(q)$, $t_k=qk/N$, $u_k=p^{-1}(t_k)$ (so $u_k$ decreases in $k$, $u_N=U$), $J=\lceil\sqrt U\rceil$, $K=8\log U$, $L=K+\sqrt U$.
- $a(x;t)=\mathbf 1\{p(|x|)\le t\}/t$. For a true null $i$: $c_i=\Sigma_{-i,i}$, $Y_i=T_{-i}-\theta_{-i}-c_iT_i$, $\rho_i(x,y)$ is the largest qualifying BH rank of the vector with $0$ at $i$ and $p(|\theta_j+c_{ij}x+y_j|)$ at $j\ne i$, and $\tau_i=q\rho_i/N$.
- A *universal constant* $C$ does not depend on $q,N,\theta,\Sigma$, block data or loadings. Every $\eta(q)$ depends on $q$ only and tends to $0$.
- Class $\mathfrak B$ (independent one-factor blocks, $G\ge1$ arbitrary, $T_j=\theta_j+a_jZ_{g(j)}+\sqrt{1-a_j^2}\varepsilon_j$), $J_g$, $r_i=|a_i|$ and $\rho_r(u,z)=F^{(2)}_{r,z}(p(u))/p(u)$ are as in plan_two_sided_exogenous_pivotal_blocks_20261105, Part B. Recall $\rho_r$ is even in $z$ and $\int\phi(z)\rho_r(u,z)\,dz=1$ for every $u$.
- *Mates* of a null $i\in J_g$: the other members of $B_g$. *Background*: coordinates outside $B_g$.


**Class $\mathfrak B$.** A model in $\mathfrak B$ has a partition $[N]=B_1\sqcup\dots\sqcup B_G$ into nonempty blocks, with $G\ge1$ arbitrary. It has loadings $a\in[-1,1]^N$, means $\theta$, and
$$
T_j=\theta_j+a_jZ_{g(j)}+\sqrt{1-a_j^2}\,\varepsilon_j ,
$$
where $Z_1,\dots,Z_G,\varepsilon_1,\dots,\varepsilon_N$ are iid $N(0,1)$. The covariance is block diagonal with blocks $a_{B_g}a_{B_g}^{\mathsf T}+\operatorname{diag}(1-a_j^2)$; it is unit-diagonal and PSD, and singular when two loadings in a block have modulus one. $G=1$ is the approved [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md). Write $J_g=I_0\cap B_g$, $\pi_{0g}=|J_g|/N$, $G_0=\#\{g:J_g\ne\varnothing\}$, $r_i=|a_i|$ and $Z=(Z_1,\dots,Z_G)$. Let $\rho_r(u,z)=F^{(2)}_{r,z}(p(u))/p(u)$ with the kernels of the Lei tail-ratio lemma; $\rho_r$ is even in $z$.


Local kernel context from source Progress B1:

For $i\in J_g$, $P_i=p(|a_iZ_g+\sqrt{1-a_i^2}\,\varepsilon_i|)$. Since $\varepsilon_i\overset d=-\varepsilon_i$, its conditional CDF is $F^{(2)}_{r_i,Z_g}$, which depends on $Z$ only through $Z_g$; it is also even in $z_g$. The forced-zero rank $R_i=\widehat k_q(x^0)$ is a function of $(P_\ell)_{\ell\ne i}$, so it is conditionally independent of $P_i$ given $Z$.

Setting. $p(u)=2\overline\Phi(u)$, $t_k=qk/N$, $b\in[0,1]^N$, $\widehat k_q(b)=\max\{k\in\{0,\dots,N\}:\#\{j:b_j\le t_k\}\ge k\}$ ($\widehat k=0$ if none; $\max\emptyset=0$). Null $i$, $\theta_i=0$, so $T_i\sim N(0,1)$ and $P_i=p(|T_i|)$ is $U(0,1)$.

**(BSP-i), general $\Sigma$.** Movers $\mathcal M_i=\{j\ne i:c_{ij}\neq0\}$, $b^\flat=b^0$ with $b^\flat_j=1$ ($j\in\mathcal M_i$), $R^\flat_i=\widehat k_q(b^\flat)$, $\tau^\flat_i=qR^\flat_i/N$.
1. $b^0\le b^\flat$ so $R_i\ge R^\flat_i$ (BH2), and $R^\flat_i\ge1$ ($b^\flat_i=0$). **Monotonicity verified.**
2. For $j\notin\mathcal M_i\cup\{i\}$, $c_{ij}=0$ so $T_j-\theta_j=(Y_i)_j$: $b^\flat$ is a Borel function of $Y_i$ ($b^\flat_i=0$, $b^\flat_j=1$ on movers). Hence $R^\flat_i$ is $\sigma(Y_i)$-measurable, independent of $T_i$. **Independence verified.**
3. By (A1c), $\mathbb E\,a(T_i;\tau^\flat_i)=1$, so exactly $\Delta_i:=\mathbb E\,a(T_i;\tau_i)-1=\mathbb E[a(T_i;\tau_i)-a(T_i;\tau^\flat_i)]$. **Mean-one identity verified.**
4. Pointwise with $p=p(|T_i|)$, $\tau^\flat\le\tau$: $p\le\tau^\flat\Rightarrow a-a^\flat=1/\tau-1/\tau^\flat\le0$; $\tau^\flat<p\le\tau\Rightarrow 1/\tau$; $p>\tau\Rightarrow0$. So $\Delta_i\le\mathbb E[\mathbf 1\{\tau^\flat_i<p\le\tau_i\}/\tau_i]$.
Note on the extreme cases: if $\mathcal M_i=\emptyset$ then $b^\flat=b^0$, $\Delta_i=0$ exactly (e.g. $\Sigma=I$, each null: $\Delta_i=0$, $\operatorname{FDR}=q\pi_0$ exactly). For dense $\Sigma$ (all $c_{ij}\ne0$) $R^\flat_i=1$ and the identity is only $\Delta_i=\mathbb E\,a(T_i;\tau_i)-1$.


**(BSP-ii), block form.** In $\mathfrak B$ take $i\in J_g$ with $a_i\ne0$; $\mathcal M_i=\{j\in B_g\setminus\{i\}:a_j\ne0\}$. The vector $b^\flat$ consists of the background block-$g$ members with $a=0$, all other blocks, and the $1$-entries of the movers, plus one $0$; as a multiset it is the same for every $i\in J_g$ with $a_i\ne0$, so $R^\flat_i=:R^{(g)}$ and it is independent of $(Z_g,\varepsilon_j)_{j\in B_g}$. Given $Z=z$ the $T_j$ are independent, $R_i$ is a function of $(T_j)_{j\ne i}$ and $P_i=p(|rz+s\varepsilon_i|)$ ($r=|a_i|$, $s=\sqrt{1-r^2}$, using the evenness of $p(|\cdot|)$ to take $a_i=r>0$), so $\mathbb E[a(T_i;\tau_i)\mid Z,R_i]=F_{r,Z}(p(u_{R_i}))/p(u_{R_i})=\rho_r(u_{R_i},Z)$. And $\mathbb E[\rho_r(u_k,Z)]=\mathbb P(p(|X|)\le p(u_k))/p(u_k)=1$ for $X=rZ+s\varepsilon\sim N(0,1)$, so $\mathbb E[\rho_r(u_{R^{(g)}},Z)]=\mathbb E_{R^{(g)}}\mathbb E[\rho_r(u_{R^{(g)}},Z)\mid R^{(g)}]=1$ by independence of $R^{(g)}$ and $Z_g$. Thus $\Delta_i=\mathbb E[\rho_r(u_{R_i},Z_g)-\rho_r(u_{R^{(g)}},Z_g)]$, $R_i\ge R^{(g)}$; and $\Delta_i=0$ whenever $R_i=R^{(g)}$ a.s. (null alone, or all mates carrying $a_j=0$). For $r_i=0$: $\rho_0\equiv1$, $\Delta_i=0$.


**(BSP-iii), two-copy form.** With $R_i=R(Z;\xi)$, $Z'$ an independent copy: $\mathbb E[\rho_r(u_{R(Z';\xi)},Z)]=\mathbb E_{Z',\xi}\int\phi\rho_r(u_{R(Z';\xi)},\cdot)=1$. Hence $\Delta_i=\mathbb E[\rho_Z(u(Z))-\rho_Z(u(Z'))]$ ($u(\cdot)=u_{R(\cdot;\xi)}$); exchanging $(Z,Z')$ and averaging, $=\frac12\mathbb E[(\rho_Z-\rho_{Z'})(u(Z))-(\rho_Z-\rho_{Z'})(u(Z'))]$. This is an identity.


## Proof

gap: In source Progress Step 3 (BSP-ii), the asserted independence of $R^{(g)}$ from $(Z_g,\varepsilon_j)_{j\in B_g}$ is not established when the block retains a member with $a_j=0$: its p-value is a function of $\varepsilon_j$ and is retained in $b^\flat$. The source assertion is copied unchanged below; no repair has been inserted.

### Step 3 (BSP): complete proof, re-verified line by line

Setting. $p(u)=2\overline\Phi(u)$, $t_k=qk/N$, $b\in[0,1]^N$, $\widehat k_q(b)=\max\{k\in\{0,\dots,N\}:\#\{j:b_j\le t_k\}\ge k\}$ ($\widehat k=0$ if none; $\max\emptyset=0$). Null $i$, $\theta_i=0$, so $T_i\sim N(0,1)$ and $P_i=p(|T_i|)$ is $U(0,1)$.

**(BH0) forced-zero identity (all ties, $R=0$).** Let $b^0$ be the p-value vector with $b^0_i=0$ and $R_i=\widehat k_q(b^0)$; $R_i\ge1$ since $b^0_i=0\le t_1$ gives $\#\{j:b^0_j\le t_1\}\ge1$. Let $b$ be the actual vector ($b_i=P_i$), $R=\widehat k_q(b)$. Claim: $\{i\ \text{rejected}\}=\{P_i\le t_{R_i}\}$ and on it $R=R_i$. Proof. Let $c(k),c^0(k)$ be the counts at level $t_k$ for $b,b^0$; $c\le c^0$ pointwise (as $b\ge b^0$) and $c=c^0$ at every $k$ with $t_k\ge P_i$, while $c(k)=c^0(k)-1$ when $t_k<P_i$. (a) If $P_i\le t_{R_i}$: $c(R_i)=c^0(R_i)\ge R_i$ so $R\ge R_i$; for $k>R_i$, $c(k)\le c^0(k)<k$, so $R=R_i$, and $P_i\le t_R$ means $i$ is rejected (BH rejects exactly $\{j:b_j\le t_R\}$ if $R\ge1$). (b) If $i$ is rejected then $R\ge1$, $P_i\le t_R$; $c^0(R)\ge c(R)\ge R$ so $R_i\ge R$; if $R_i>R$ then $t_{R_i}>t_R\ge P_i$ so $c(R_i)=c^0(R_i)\ge R_i$, giving $R\ge R_i$, a contradiction; so $R_i=R$ and $P_i\le t_{R_i}$. Hence pointwise
$$\frac{\mathbf 1\{i\in\mathcal R\}}{R\vee1}=\frac{\mathbf 1\{P_i\le t_{R_i}\}}{R_i}=\frac qN\,a(T_i;\tau_i),\quad a(x;t)=\frac{\mathbf 1\{p(|x|)\le t\}}t,\ \tau_i=\frac{qR_i}N .$$
On $\{R=0\}$ both sides are $0$ (if $P_i\le t_{R_i}$ then $R=R_i\ge1$ by (a)).

**(BH2) monotonicity.** If $b\le b'$ entrywise then $\#\{j:b_j\le t\}\ge\#\{j:b'_j\le t\}$ for each $t$, so $\widehat k_q(b)\ge\widehat k_q(b')$. Ties are irrelevant (weak inequalities everywhere).

**(A1c) exogenous thresholds.** $Y_i:=T_{-i}-\theta_{-i}-c_iT_i$, $c_i=\Sigma_{-i,i}$. $(T_i,Y_i)$ is jointly Gaussian (linear image of $T$; zero variance allowed) with $\operatorname{Cov}(Y_i,T_i)=c_i-c_i\operatorname{Var}T_i=0$, hence $T_i\perp Y_i$ also for singular $\Sigma$ (a Gaussian vector with a zero cross-covariance block splits; degenerate components are constants). So for every Borel $g$ with values in $\{t_1,\dots,t_N\}$: $\mathbb E\,a(T_i;g(Y_i))=\mathbb E\big[\mathbb P(P_i\le g(Y_i)\mid Y_i)/g(Y_i)\big]=1$ since $\mathbb P(P_i\le t)=t$ for $t\in(0,1)$ (here $t_N=q<1$).

**(BSP-i), general $\Sigma$.** Movers $\mathcal M_i=\{j\ne i:c_{ij}\neq0\}$, $b^\flat=b^0$ with $b^\flat_j=1$ ($j\in\mathcal M_i$), $R^\flat_i=\widehat k_q(b^\flat)$, $\tau^\flat_i=qR^\flat_i/N$.
1. $b^0\le b^\flat$ so $R_i\ge R^\flat_i$ (BH2), and $R^\flat_i\ge1$ ($b^\flat_i=0$). **Monotonicity verified.**
2. For $j\notin\mathcal M_i\cup\{i\}$, $c_{ij}=0$ so $T_j-\theta_j=(Y_i)_j$: $b^\flat$ is a Borel function of $Y_i$ ($b^\flat_i=0$, $b^\flat_j=1$ on movers). Hence $R^\flat_i$ is $\sigma(Y_i)$-measurable, independent of $T_i$. **Independence verified.**
3. By (A1c), $\mathbb E\,a(T_i;\tau^\flat_i)=1$, so exactly $\Delta_i:=\mathbb E\,a(T_i;\tau_i)-1=\mathbb E[a(T_i;\tau_i)-a(T_i;\tau^\flat_i)]$. **Mean-one identity verified.**
4. Pointwise with $p=p(|T_i|)$, $\tau^\flat\le\tau$: $p\le\tau^\flat\Rightarrow a-a^\flat=1/\tau-1/\tau^\flat\le0$; $\tau^\flat<p\le\tau\Rightarrow 1/\tau$; $p>\tau\Rightarrow0$. So $\Delta_i\le\mathbb E[\mathbf 1\{\tau^\flat_i<p\le\tau_i\}/\tau_i]$.
Note on the extreme cases: if $\mathcal M_i=\emptyset$ then $b^\flat=b^0$, $\Delta_i=0$ exactly (e.g. $\Sigma=I$, each null: $\Delta_i=0$, $\operatorname{FDR}=q\pi_0$ exactly). For dense $\Sigma$ (all $c_{ij}\ne0$) $R^\flat_i=1$ and the identity is only $\Delta_i=\mathbb E\,a(T_i;\tau_i)-1$.

**(BSP-ii), block form.** In $\mathfrak B$ take $i\in J_g$ with $a_i\ne0$; $\mathcal M_i=\{j\in B_g\setminus\{i\}:a_j\ne0\}$. The vector $b^\flat$ consists of the background block-$g$ members with $a=0$, all other blocks, and the $1$-entries of the movers, plus one $0$; as a multiset it is the same for every $i\in J_g$ with $a_i\ne0$, so $R^\flat_i=:R^{(g)}$ and it is independent of $(Z_g,\varepsilon_j)_{j\in B_g}$. Given $Z=z$ the $T_j$ are independent, $R_i$ is a function of $(T_j)_{j\ne i}$ and $P_i=p(|rz+s\varepsilon_i|)$ ($r=|a_i|$, $s=\sqrt{1-r^2}$, using the evenness of $p(|\cdot|)$ to take $a_i=r>0$), so $\mathbb E[a(T_i;\tau_i)\mid Z,R_i]=F_{r,Z}(p(u_{R_i}))/p(u_{R_i})=\rho_r(u_{R_i},Z)$. And $\mathbb E[\rho_r(u_k,Z)]=\mathbb P(p(|X|)\le p(u_k))/p(u_k)=1$ for $X=rZ+s\varepsilon\sim N(0,1)$, so $\mathbb E[\rho_r(u_{R^{(g)}},Z)]=\mathbb E_{R^{(g)}}\mathbb E[\rho_r(u_{R^{(g)}},Z)\mid R^{(g)}]=1$ by independence of $R^{(g)}$ and $Z_g$. Thus $\Delta_i=\mathbb E[\rho_r(u_{R_i},Z_g)-\rho_r(u_{R^{(g)}},Z_g)]$, $R_i\ge R^{(g)}$; and $\Delta_i=0$ whenever $R_i=R^{(g)}$ a.s. (null alone, or all mates carrying $a_j=0$). For $r_i=0$: $\rho_0\equiv1$, $\Delta_i=0$.

**(BSP-iii), two-copy form.** With $R_i=R(Z;\xi)$, $Z'$ an independent copy: $\mathbb E[\rho_r(u_{R(Z';\xi)},Z)]=\mathbb E_{Z',\xi}\int\phi\rho_r(u_{R(Z';\xi)},\cdot)=1$. Hence $\Delta_i=\mathbb E[\rho_Z(u(Z))-\rho_Z(u(Z'))]$ ($u(\cdot)=u_{R(\cdot;\xi)}$); exchanging $(Z,Z')$ and averaging, $=\frac12\mathbb E[(\rho_Z-\rho_{Z'})(u(Z))-(\rho_Z-\rho_{Z'})(u(Z'))]$. This is an identity.


## Provenance

Extracted verbatim from [the baseline-subtracted pivotal probe plan](../plans/plan_two_sided_baseline_subtracted_pivotal_probe_20261105.md), Progress Step 3 (BSP), setting, BH0, BH2, A1c, BSP-i, BSP-ii and BSP-iii. The statement reproduces the actual Progress version, including its intermediate assertions, rather than the earlier checklist formulation. Local fixed notation is from that plan; the full block-class paragraph is copied from [the exogenous-pivotal blocks plan](../plans/plan_two_sided_exogenous_pivotal_blocks_20261105.md), Part B. The numerical re-check is excluded from the proof. Neither the source claim nor this extraction has received independent verification.
