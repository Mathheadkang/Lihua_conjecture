---
id: plan_gaussian_bh_angular_cluster_partial_entropy_bound_direct_hazard
type: plan
title: >-
  Deterministic per-null BH bound with unit loadings, hazard inequality and
  explicit off-strip constants for the partial angular-cluster entropy bound
status: succeeded
target_asset: gaussian_bh_angular_cluster_partial_entropy_bound
inspired_by:
  - idea_83da76e88e04
  - idea_d09ce0db2d38
adapts:
  - gaussian_bh_angular_cluster_entropy_bound
proof_digest: 78a73394d08314f9e440069f2df68e6f45c1bb98e70c74b2fffb4ea5c90c4b4c
statement_digest: 736750aaadb60109c2ce46215b308676bc7a0cd9e89173948fa97978fa8123b1
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_multifactor_representation: e3a61244f476941be96780294a5d26af63dd415aa7462c2662601bf6aeb086fe
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 78a73394d08314f9e440069f2df68e6f45c1bb98e70c74b2fffb4ea5c90c4b4c
---

## Goal

Target: [asset](../assets/gaussian_bh_angular_cluster_partial_entropy_bound.md)

Prove parts (a) and (b) exactly as stated, with the explicit choices
$$
q_1=\overline\Phi(3),\qquad \kappa'=\kappa\sqrt{2(C+1)},\qquad A_1(\kappa,C)=1+A^*(\kappa'),
$$
where $K_0(k)=k\Phi(k)+\phi(k)$, $K_1(k)=\tfrac12\bigl((k^2+1)\Phi(k)+k\phi(k)\bigr)$ and $A^*(k)=2(k+1)K_0(k)+4K_1(k)$ (the constant of the approved [angular-cluster entropy bound](../assets/gaussian_bh_angular_cluster_entropy_bound.md)). These depend only on $\kappa$ and $C$, and $q_1\in(0,1/2)$.

The route is self-contained: with unit loadings every null p-value is a function of $Z$, so the leave-one-out step and the Lei tail-ratio lemma are replaced by a one-line deterministic bound, and the only borrowed ingredients are the hazard inequality and the off-strip integral of the approved proof (Steps 5-7 there), re-proved here. No dependency is cited as a black box, so `depends_on` stays empty.

## Plan

1. [x] **Elementary Gaussian facts.** (i) Hazard inequality: $\phi(y)\le(y+1)\overline\Phi(y)$ for $y\ge0$, proved as in Step 5 of the approved proof (Gordon's bound $\overline\Phi(y)<\phi(y)/y$, Mills ratio monotone, $g(y)=(y+1)\overline\Phi(y)-\phi(y)$ unimodal with $g(0)>0$, $g(\infty)=0$). (ii) Chernoff: $\overline\Phi(t)\le e^{-t^2/2}$ for $t\ge0$ (from $\mathbb P(N\ge t)\le e^{-t^2+t^2/2}$). (iii) $K_0(k)=\int_0^\infty\Phi(k-s)\,ds$ and $K_1(k)=\int_0^\infty s\Phi(k-s)\,ds$ with the closed forms above, both nonnegative and nondecreasing, so $A^*$ is finite, nonnegative and nondecreasing on $[0,\infty)$ (as in Steps 6-7 of the approved proof).

2. [x] **Level facts for $q\le q_1$.** Then $u\ge3$. (i) From 1(i), $q=\overline\Phi(u)\ge\phi(u)/(u+1)$, so $\log(1/q)\le u^2/2+\log(\sqrt{2\pi}(u+1))\le u^2$; the last step holds at $u=3$ ($4.5\ge\log(4\sqrt{2\pi})\approx2.31$) and the difference has derivative $u-1/(u+1)>0$. (ii) $q\pi_G\in(0,q]$, so $b_G=\overline\Phi^{-1}(q\pi_G)$ is well defined, $b_G\ge u>0$, and $\overline\Phi(b_G)=q\pi_G$ by continuity and strict monotonicity of $\overline\Phi$. (iii) From 1(ii) with $t=\sqrt{2\log(1/(q\pi_G))}$, $\overline\Phi(t)\le q\pi_G$, so $b_G\le t$; with $\pi_G\ge q^C$, $\log(1/(q\pi_G))\le(C+1)\log(1/q)\le(C+1)u^2$, hence $b_G\le\sqrt{2(C+1)}\,u$. This is the only use of $\pi_G\ge q^C$.

3. [x] **Angular geometry.** For $i\in G$ put $X_i=w_i^{\mathsf T}Z$, $\rho_i=w_i^{\mathsf T}v$, $\sigma_i=\sqrt{1-\rho_i^2}$. Since $\|w_i-v\|^2=2-2\rho_i\le\kappa^2/u^2\le1/9$: $\rho_i\in[1/2,1]$ (Cauchy-Schwarz for $\rho_i\le1$); $\sigma_i^2=(1-\rho_i)(1+\rho_i)\le2(1-\rho_i)=\|w_i-v\|^2$, so $\sigma_i\le\kappa/u\le1/3$; and $(1-\rho_i)/\sigma_i\le\sigma_i$ when $\rho_i<1$ (equivalent to $1\le(1+\rho_i)^2$). If $\rho_i<1$, $Y_G-\rho_iX_i$ is a linear function of $Z$ uncorrelated with $X_i$, hence independent of $X_i$, with law $\mathcal N(0,\sigma_i^2)$. If $\rho_i=1$ then $w_i=v$ and $Y_G=X_i$.

4. [x] **Deterministic per-null bound.** For $i\in I_0$, pointwise on every outcome,
$$
\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}\le\frac qm\,\frac{\mathbf1\{X_i\ge u\}}{\overline\Phi(X_i)}.
$$
Proof: if $\widehat k_q=0$ the left side is $0$. Otherwise $p_{(1)},\ldots,p_{(\widehat k_q)}\le q\widehat k_q/m$, so $R\ge\widehat k_q\ge1$. If $i\in\mathcal R_q$ then $p_i\le q\widehat k_q/m$; since $\theta_i\le0$ and $\overline\Phi$ is decreasing, $\overline\Phi(X_i)\le\overline\Phi(\theta_i+X_i)=p_i\le q\widehat k_q/m\le q$, hence $X_i\ge u$ and $1/R\le1/\widehat k_q\le q/(m\overline\Phi(X_i))$. Summing over $i\in G$: $V_G/(R\vee1)\le\frac qm\sum_{i\in G}\mathbf1\{X_i\ge u\}/\overline\Phi(X_i)$. Here $R$, $V_G$ refer to the unmodified procedure on all $m$ coordinates; nothing about other coordinates is used.

5. [x] **Part (a), upper off-strip term.** $V_G\le R$ on $\{R\ge1\}$ and $V_G=0$ otherwise, so $V_G/(R\vee1)\le1$ and the second term is at most $\mathbb P(Y_G>b_G)=\overline\Phi(b_G)=q\pi_G$, since $Y_G\sim\mathcal N(0,1)$ ($v$ unit).

6. [x] **Part (a), lower off-strip term.** By step 4 and Tonelli, the first term is at most $\frac qm\sum_{i\in G}E_i$ with $E_i=\mathbb E[\mathbf1\{X_i\ge u,\,Y_G\le u\}/\overline\Phi(X_i)]$. If $\rho_i=1$, the event is $\{X_i=u\}$, a null set, so $E_i=0$. If $\rho_i<1$, by step 3 and Fubini, with $x=u+t$,
$$
E_i=\int_u^\infty\frac{\phi(x)}{\overline\Phi(x)}\Phi\!\Bigl(\frac{u-\rho_ix}{\sigma_i}\Bigr)dx\le\int_0^\infty(u+1+t)\,\Phi\!\Bigl(\kappa-\frac t{2\sigma_i}\Bigr)dt,
$$
using 1(i), $u(1-\rho_i)/\sigma_i\le u\sigma_i\le\kappa$ and $\rho_it/\sigma_i\ge t/(2\sigma_i)$. Substituting $t=2\sigma_is$ gives $2\sigma_i(u+1)K_0(\kappa)+4\sigma_i^2K_1(\kappa)\le2(\kappa+1)K_0(\kappa)+4K_1(\kappa)=A^*(\kappa)$, since $\sigma_i(u+1)\le\kappa(1+1/u)\le\kappa+1$ and $\sigma_i^2\le1$. Hence the first term is at most $q\pi_GA^*(\kappa)$.

7. [x] **Part (b).** By step 4, the strip term is at most $\frac qm\sum_{i\in G}S_i$, $S_i=\mathbb E[\mathbf1\{X_i\ge u,\,u<Y_G\le b_G\}/\overline\Phi(X_i)]$. Split by $X_i\le b_G$ and $X_i>b_G$. On $\{u\le X_i\le b_G\}$ drop the $Y_G$ condition: contribution $\le\int_u^{b_G}\phi/\overline\Phi=\log(\overline\Phi(u)/\overline\Phi(b_G))=\log(1/\pi_G)$ by step 2(ii). On $\{X_i>b_G\}$ keep only $Y_G\le b_G$: zero if $\rho_i=1$; otherwise, as in Steps 4 and 6 of the approved proof with $\beta=b_G$, the contribution is at most $\int_0^\infty(b_G+1+t)\Phi(\kappa'-t/(2\sigma_i))\,dt$, because $b_G(1-\rho_i)/\sigma_i\le b_G\sigma_i\le b_G\kappa/u\le\kappa'$ by steps 2(iii) and 3; this equals $2\sigma_i(b_G+1)K_0(\kappa')+4\sigma_i^2K_1(\kappa')\le A^*(\kappa')$ using $\sigma_ib_G\le\kappa'$, $\sigma_i\le1$. So $S_i\le\log(1/\pi_G)+A^*(\kappa')$ and the strip term is at most $q\pi_G(\log(1/\pi_G)+A^*(\kappa'))$.

8. [x] **Constants.** Since $C\ge1$, $\kappa'\ge\kappa$, so $A^*(\kappa)\le A^*(\kappa')$ by 1(iii). Steps 5-6 give (a) $\le q\pi_G(1+A^*(\kappa))\le A_1q\pi_G$; step 7 gives (b) $\le q\pi_G(\log(1/\pi_G)+A^*(\kappa'))\le A_1q\pi_G(1+\log(1/\pi_G))$, as $\log(1/\pi_G)\ge0$ and $A_1\ge1$.

## Verification

Steps 4-6 and 8 prove (a), steps 4, 7 and 8 prove (b), for every $0<q\le q_1=\overline\Phi(3)$, every $m,d,\theta,w_1,\ldots,w_m$ and every angular cluster $(G,v)$ at scale $\kappa\in(0,1]$ with $\pi_G\ge q^C$. The constants $A_1=1+A^*(\kappa\sqrt{2(C+1)})$ and $q_1$ involve only $\kappa$ and $C$: steps 4-7 never use $m$, $d$, $\theta$ beyond $\theta_i\le0$ on $G$, the loadings outside $G$, or other clusters. Singular covariance is allowed since only the laws of the scalar projections $X_i$, $Y_G$, $Y_G-\rho_iX_i$ of $Z$ are used. Ties and $R=0$ are handled pointwise in step 4. The case $\rho_i=1$ (including $w_i=v$) is treated separately in steps 6-7, so no division by $\sigma_i=0$ occurs. All integrands are nonnegative, so Tonelli/Fubini apply even though $\mathbb E[\mathbf1\{X_i\ge u\}/\overline\Phi(X_i)]=\infty$; the bounded integrals arise only after inserting the $Y_G$ indicator.

## Assumed definitions

All definitions used (gaussian_multiple_testing_model, gaussian_multifactor_representation, gaussian_test_pvalues, benjamini_hochberg_step_up, false_discovery_rate) are approved. No unproved dependency is assumed.

## Adapted from

- **gaussian_bh_angular_cluster_entropy_bound** (approved). Transferred: the hazard inequality (its Step 5), the off-strip integral and the closed forms of $K_0,K_1$ with monotonicity of $A^*$ (its Steps 6-7), and the region split by the null's own projection versus the cluster projection (its Step 4). Its hypotheses $\rho_i\ge\frac12$ and $\beta\sqrt{1-\rho_i^2}\le\kappa'$ hold here by step 3 and step 2(iii), with $\beta=b_G$, $r_i=1$, $\gamma_i=0$. Changes: (1) its Step 2 leave-one-out reduction (which uses the Lei conditional FDP bound) is replaced by the deterministic bound of step 4, valid because unit loadings make $p_i$ a function of $Z$; (2) its Step 3 (Lei integrated tail-ratio lemma for the region $Y_i\le u$) is not needed, because the bound of step 4 vanishes for $X_i<u$; (3) the new lower off-strip estimate of step 6 (event $X_i\ge u$, $Y_G\le u$) is the same integral with level $u$ in place of $\beta$ and closeness $u\sigma_i\le\kappa$, which removes the $\log$ term and the $\frac12$ constant; (4) its cluster-level bound $\overline\Phi(\beta)$ on $\{W>\beta\}$ becomes the separate second term of (a). Hence none of the results cited by the adapted proof is needed here.

## Outcome

Succeeded. The complete proof is under `## Proof` in [the target asset](../assets/gaussian_bh_angular_cluster_partial_entropy_bound.md) (statement unchanged, status draft), with $q_1=\overline\Phi(3)$, $\kappa'=\kappa\sqrt{2(C+1)}$ and $A_1=1+A^*(\kappa')$. Every step of the plan went through as written; the hazard inequality, the closed forms of $K_0,K_1$ and the off-strip integral are re-proved inside the proof. Nothing is assumed beyond the approved definitions, and `depends_on` stays empty. The pathwise bound $\mathbf 1\{i\in\mathcal R_q\}/(R\vee1)\le(q/m)\mathbf 1\{X_i\ge u\}/\overline\Phi(X_i)$ has infinite expectation by itself. It is integrated only on $\{Y_G\le u\}$, on the bounded strip $\{u\le X_i\le b_G\}$, and on $\{X_i>b_G,\,Y_G\le b_G\}$, where the integrals are finite.

## Verdict

confirmed

Checked step by step against the statement (unit loadings, one-sided p-values, $G\subseteq I_0$, $\|w_i-v\|\le\kappa/u$, $\pi_G\ge q^C$, $0<q\le q_1$).

- Step 1: the hazard inequality $\phi(y)\le(y+1)\overline\Phi(y)$ on $y\ge0$ is correct ($\mu'=y\mu-1$, $g'=\phi(\mu-1)$, $g(0)>0$, $g\to0$). Chernoff is correct. The closed forms $K_0=\int_0^\infty\Phi(k-s)\,ds=k\Phi(k)+\phi(k)$ and $K_1=\int_0^\infty s\,\Phi(k-s)\,ds=\tfrac12((k^2+1)\Phi+k\phi)$ check out by differentiation together with the limits at $-\infty$. Monotonicity of $A^*$ is correct.
- Step 2: $u\ge3$; $\log(1/q)\le u^2$ ($f(3)\approx2.19>0$, $f'>0$); $b_G\le\sqrt{2(C+1)}\,u$ via $\overline\Phi(t)\le q\pi_G$. All correct.
- Step 3: $\rho_i\ge17/18$, $\sigma_i\le\|w_i-v\|\le\kappa/u$, and $(1-\rho_i)/\sigma_i\le\sigma_i$ (which is equivalent to $(1+\rho_i)^2\ge1$). $E_i'=Y_G-\rho_iX_i$ is independent of $X_i$ with variance $1-\rho_i^2$, so formula (1) is right. The case $\rho_i=1$ is handled separately, so there is no division by zero.
- Step 4: the pathwise bound (2) is correct. $R\ge\widehat k$ holds with ties. For a composite null, $\theta_i\le0$ gives $\overline\Phi(X_i)\le p_i\le q\widehat k/m\le q$, hence $X_i\ge u$ and $1/(R\vee1)\le q/(m\overline\Phi(X_i))$. Nothing about coordinates outside $G$ is used.
- Coverage and finiteness: (3) is integrated only against $\{Y_G\le u\}$ (Step 6), the bounded strip $\{u\le X_i\le b_G\}$, and $\{X_i>b_G, Y_G\le b_G\}$ (Step 7). Together these cover $\{X_i\ge u\}\cap\{Y_G\le b_G\}$, which is exactly what (a)'s lower term and (b) need. The upper term $\{Y_G>b_G\}$ is bounded separately by $V_G/(R\vee1)\le1$ and $\mathbb P(Y_G>b_G)=q\pi_G$, so (2) is never used there.
  - In Step 6, the shift $x=u+t$ gives the argument $u(1-\rho_i)/\sigma_i-\rho_it/\sigma_i\le\kappa-t/(2\sigma_i)$, using $u\sigma_i\le\kappa$ and $\rho_i\ge1/2$. The hazard factor is at most $u+1+t$. Substituting $t=2\sigma_is$ gives $2\sigma_i(u+1)K_0(\kappa)+4\sigma_i^2K_1(\kappa)\le A^*(\kappa)$, using $\sigma_i(u+1)\le\kappa+\kappa/u\le\kappa+1$.
  - Step 7 is the same argument with $b_G\sigma_i\le\kappa'$ and $\sigma_i(b_G+1)\le\kappa'+1$. The strip integral equals exactly $\log(1/\pi_G)$.
- Step 8: $\kappa'\ge\kappa$ because $C\ge1$, and $A^*$ is nondecreasing. So (a) $\le q\pi_G(1+A^*(\kappa))\le A_1q\pi_G$ and (b) $\le q\pi_G(\log(1/\pi_G)+A^*(\kappa'))\le A_1q\pi_G(1+\log(1/\pi_G))$. The constants $q_1=\overline\Phi(3)\in(0,1/2)$ and $A_1=1+A^*(\kappa\sqrt{2(C+1)})$ depend only on $\kappa$ and $C$. Singular covariance is harmless, since only the laws of the scalar projections of $Z$ are used.

Small notational gap, closed here: Step 3 defines $X_i=w_i^{\mathsf T}Z$ only for $i\in G$, but Step 4 uses it for all $i\in I_0$. The same definition, $X_i=T_i-\theta_i$, applies.
