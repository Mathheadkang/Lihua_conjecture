---
title: Exogenous-pivotal identity, independent one-factor blocks, and a line-form global pivotality inequality for two-sided BH
type: plan
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
inspired_by:
  - idea_3be77b4166bb
  - idea_0d2e69e0ba3b
  - idea_4a0615ac99ad
  - idea_0610115f8682
adapts:
  - lei2026_two_sided_common_factor_upper
  - lei2026_conditional_fdp_bound
  - lei2026_integrated_conditional_tail_ratios
---

## Goal

Target: [Sharp uniform upper-bound target for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_sharp_upper.md).

Prove the unchanged statement: for every $\varepsilon>0$ there is $q_\varepsilon\in(0,1)$ such that for every $q\in(0,q_\varepsilon)$, every finite $N$, every $\theta\in\mathbb R^N$ and every unit-diagonal positive-semidefinite $\Sigma$ (singular allowed; $N,\theta,\Sigma$ may depend on $q$), ordinary BH with the largest qualifying rank applied to $p_i=2\overline\Phi(|T_i|)$, with true nulls $\theta_i=0$, satisfies $\operatorname{FDR}\le(1/(2\sqrt\pi)+\varepsilon)\,q\sqrt{\log(1/q)}$. The block class, bounded block numbers, multiplicity class and fixed-$q$ families below are gates and test cases only; none of them is the conclusion.

The route is the exogenous–pivotal decomposition of [Exogenous-pivotal decomposition: only threshold moves caused by the null's own correlation line can inflate the FDR](../ideas/idea_3be77b4166bb.md), not tried by earlier plans. Part A proves its exact two-sided form (gate G1). Part B bounds the pivotal term on independent one-factor blocks by adapting the proof of [Lei sharp two-sided BH upper bound with one common factor](../assets/lei2026_two_sided_common_factor_upper.md) (gate G2). Part C states and attacks the open global step (gate G3).

**Two-sided version used.** The idea writes its exogenous term with the one-sided tail $\overline\Phi(\cdot-\theta_i)$ and an inequality. Here every true null has $\theta_i=0$, so $T_i\sim N(0,1)$ and $2\overline\Phi(|T_i|)$ is exactly uniform. The exogenous term is therefore exactly $1$ and $\operatorname{FDR}=q\pi_0+(q/N)\sum_i\Delta_i$ holds with *equality* (A1). The forced-zero threshold depends on the null's line position only through $|\theta_j+c_{ij}x+y_j|$, and $\Delta_i$ is the average of the two branches $x\gtrless0$ (A1(e)). The idea's monotonicity remark "$\Delta_i\le0$ for purely positively correlated movers" has no direct two-sided analogue, since a positive shift lowers $|\theta_j+y_j+cx|$ when $\theta_j+y_j$ and $c$ have opposite signs. The two-sided replacement is A2(ii): $\Delta_i\le0$ whenever both branch thresholds are nondecreasing in $|x|$. The constant $1/(2\sqrt\pi)$ enters as $qU/(2\sqrt{2\pi})$ with $U=p^{-1}(q)$ (A0).

**Obstructions respected** (from [Two obstructions to conditional tail-ratio routes](../ideas/idea_0d2e69e0ba3b.md)).
- (1) No step for general $\Sigma$ conditions on $\sigma(T_{-i})$ or on a factor representation that gives the null private noise. C1(a) proves that such a decomposition always has private variance at most the leave-one-out residual variance, which vanishes under duplication. Part B's conditional mechanism is used only inside the block class.
- (2) No step replaces the actual BH threshold by a supremum of conditional tail ratios over admissible thresholds when the conditioning reveals more than the threshold uses. In particular, B4 records that the supremum form of Lei's Lemma 4.7 fails once a frozen background is added.
- The isotropic family of [Isotropic weak-loading many-factor nulls do not beat the one-factor constant](../ideas/idea_4a0615ac99ad.md) is used only as numerical test T5.

**Sources.** Native library searches for `Gaussian BH two-sided`, `one-factor Gaussian BH FDR`, `exogenous pivotal`, `leave-one-out forced zero BH`, `Benjamini Hochberg dependence upper bound`, `conditional tail ratio factor`, `PRDS`, `one factor blocks` and `Poisson binomial concentration` returned no results. The pack has no Library analogues section, and no library statement is cited. Additional native reads were needed. The three ideas above define the route, its obstructions and test T5. [Along a Gaussian ray, two-sided deactivations have a reflected strong-mean rejection witness](../ideas/idea_0610115f8682.md) supplies the deterministic fact rederived in A4. Lei's Section 4.2.2 (paper `lei2026_gaussian_bh`, pp. 62–86) is the proof being adapted in Part B. The approved [Lei conditional leave-one-out FDP bound](../assets/lei2026_conditional_fdp_bound.md) and [Lei integrated conditional Gaussian tail-ratio bounds](../assets/lei2026_integrated_conditional_tail_ratios.md) are not in the target's `depends_on`. Their arguments are therefore reproved where used (B1, B3), not cited. The draft [Lei finite Gaussian lower bound for two-sided BH](../assets/lei2026_two_sided_fdr_lower.md) is used only as test T1, and the failure section of plan_two_sided_signed_forest_rank_cells_20261104 supplies test T3.

## Plan

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

### Part A — exact identity and one-dimensional lemmas (gate G1; all routine)

1. [x] **(A0, routine) Scale and trivial cases.** If $I_0=\varnothing$ then $\operatorname{FDR}=0$; if $N=1$ then $\operatorname{FDR}\le q$. For $q\le2\overline\Phi(1)$, the Mills bound $\overline\Phi(U)\le\phi(U)/U$ gives $U^2\le2\log(2/q)$. Hence
   $$
   \frac{qU}{2\sqrt{2\pi}}\le\frac{1}{2\sqrt\pi}\,q\sqrt{\log(2/q)}=\frac{1+o(1)}{2\sqrt\pi}\,q\sqrt{\log(1/q)} .
   $$

2. [x] **(A1 = G1, routine) Exact two-sided exogenous–pivotal identity.** For every $q\in(0,1)$, every admissible $(N,\theta,\Sigma)$ and every $i\in I_0=I_0^{(2)}(\theta)$:
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
     Each $f^\pm_{i,y}$ is a right-continuous step function with finitely many jumps, since each equation $|\theta_j+c_{ij}x+y_j|=u_k$ has at most two roots. Measurability in $y$ holds because there are finitely many polyhedral cells.
   - (f) Duplication invariance. Repeating every coordinate $M$ times maps $\widehat k\mapsto M\widehat k$, keeps the threshold $q\widehat k/N$, keeps the FDP, and keeps every $\Delta_i$; for duplicated copies it follows from per-null expectations.

3. [x] **(A2, routine) Exact branch formula, monotone lemma and jump bound.** Let $f$ be a right-continuous step function on $[0,\infty)$ with jumps $0<s_1<\dots<s_n$, values $f_0,\dots,f_n\in\{t_1,\dots,t_N\}$, and $s_0=0$, $s_{n+1}=\infty$.
   - (i) Exactly,
     $$
     \Psi(f)=\sum_{k=0}^n\frac{[\min\{f_k,p(s_k)\}-p(s_{k+1})]_+}{f_k}.
     $$
   - (ii) If $f$ is nondecreasing, then $\Psi(f)\le1$. Hence, if for a.e. $y$ both $f^\pm_{i,y}$ are nondecreasing, then $\Delta_i\le0$.
   - (iii) Jump bound:
     $$
     \Psi(f)-1\le\sum_{k:\,f_k<f_{k-1},\ p(s_k)\le f_{k-1}}\min\{p(s_k),f_k\}\Big(\frac1{f_k}-\frac1{f_{k-1}}\Big)\le\sum_{k:\,f_k<f_{k-1},\ p(s_k)\le f_{k-1}}\Big(1-\frac{f_k}{f_{k-1}}\Big).
     $$
     Only downward jumps at which the null was already rejected can contribute positively. A planning check over $2\cdot10^5$ random step configurations found a largest excess of $3.8\cdot10^{-16}$ (rounding). That is corroboration, not proof: prove (iii) by induction on $n$ from (i).

4. [x] **(A4, routine) Reflected-floor and subset-floor lemmas along a null line.** Fix $i$, $y$, a branch $\sigma\in\{\pm1\}$ and a level $k$. For $j\ne i$ put $b_j=\theta_j+y_j$ and $c=c_{ij}$.
   - (i) $\{s\ge0:|b_j+\sigma cs|<u_k\}$ is an interval. Thus $j$ deactivates at level $k$ at most once on branch $\sigma$, and only if $|b_j|\ge u_k$ and $\sigma cb_j<0$.
   - (ii) In that case $|b_j-\sigma cs|\ge|b_j|$ for all $s\ge0$. So $j$ is active on branch $-\sigma$ at every level $k'$ with $u_{k'}\le|b_j|$, for every $s\ge0$.
   - (iii) BH rank is nonincreasing in each p-value with the denominator $N$ fixed. Hence for every $S\subseteq[N]\setminus\{i\}$, $\tau_i(x,y)\ge(q/N)\,\widehat k_q(\pi_S)$, where $\pi_S$ keeps the entries on $S$ and sets the others to $1$. If $D$ is the set of coordinates that deactivate on branch $\sigma$, then for all $s\ge0$
     $$
     \tau_i(-\sigma s,y)\ge\frac qN\,\widehat k_q\big((p(|b_j|))_{j\in D},1,\dots,1\big).
     $$
     This is the two-sided half-factor mechanism: the threshold ranges tracked on the two branches are separated by these floors.

5. [ ] **(A5, routine diagnostics, evidence only) Exact checks of A1–A4** on the following cases:
   - $N=1$;
   - $\Sigma=I$, where every $c_i=0$ and $\Delta_i=0$;
   - one null and one alternative with $N=2$, against the closed form $H=q/2+\tfrac12J_{uu}-J_{vu}$ recorded in plan_two_sided_null_noise_folded_completion_20261104;
   - uniform duplication (A1(f));
   - test T3 below, where $\Delta_1\ge3U^2/8-1$ is consistent with A1 because $\pi_0=1/N$;
   - test T7 at a fixed $q$, where $(q/N)\sum_i\Delta_i=H_{N,1}(\lambda)-q/2$ is positive for large $N$.

   Short local runs only (at most seven workers); anything heavier goes to the configured remote server in a new task directory.

### Part B — independent one-factor blocks (gate G2)

**Class $\mathfrak B$.** A model in $\mathfrak B$ has a partition $[N]=B_1\sqcup\dots\sqcup B_G$ into nonempty blocks, with $G\ge1$ arbitrary. It has loadings $a\in[-1,1]^N$, means $\theta$, and
$$
T_j=\theta_j+a_jZ_{g(j)}+\sqrt{1-a_j^2}\,\varepsilon_j ,
$$
where $Z_1,\dots,Z_G,\varepsilon_1,\dots,\varepsilon_N$ are iid $N(0,1)$. The covariance is block diagonal with blocks $a_{B_g}a_{B_g}^{\mathsf T}+\operatorname{diag}(1-a_j^2)$; it is unit-diagonal and PSD, and singular when two loadings in a block have modulus one. $G=1$ is the approved [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md). Write $J_g=I_0\cap B_g$, $\pi_{0g}=|J_g|/N$, $G_0=\#\{g:J_g\ne\varnothing\}$, $r_i=|a_i|$ and $Z=(Z_1,\dots,Z_G)$. Let $\rho_r(u,z)=F^{(2)}_{r,z}(p(u))/p(u)$ with the kernels of the Lei tail-ratio lemma; $\rho_r$ is even in $z$.

6. [x] **(B1, routine; adapts Lei Lemma 4.1 and (273)) Multi-block conditional identity.** Given $Z$, all coordinates are independent, and $P_i$ is independent of the forced-zero rank $R_i$. Hence, for $i\in J_g$,
   $$
   \frac qN(1+\Delta_i)=\frac qN\,\mathbb E\sum_{k=1}^N\rho_{r_i}(u_k,Z_g)\,\mathbb P(R_i=k\mid Z).
   $$
   The block share $\mathrm{FDR}_g(z):=(q/N)\sum_{i\in J_g}\sum_k\rho_{r_i}(u_k,z_g)\mathbb P(R_i=k\mid Z=z)$ satisfies $\sum_g\mathrm{FDR}_g(Z)=\mathbb E[\mathrm{FDP}\mid Z]\le1$ almost surely. This is A1(b) plus conditional independence; no external citation.

7. [x] **(B2, routine; as Lei (275)) Small ranks.** Since $\int\rho_r(u,z)\phi(z)\,dz=1$ for each fixed $u$, on the whole line,
   $$
   \frac qN\sum_{i\in I_0}\mathbb E\sum_{k\le J_q}\rho_{r_i}(u_k,Z_{g(i)})\mathbb P(R_i=k\mid Z)\le\pi_0qJ_q .
   $$

8. [x] **(B3, routine; as Lei Lemma 4.8 and (279)–(282)) Bad events on each null's own central region.** Let $A_{i,z}$ be Lei's good event (278), built from $N_{i,j}=\sum_{\ell\ne i}\mathbf 1\{P_\ell\le t_j\}$ and $\mu_{i,j}(z)=\mathbb E[N_{i,j}\mid Z=z]$. These counts are Poisson-binomial given the full vector $Z$. Then
   $$
   \frac qN\sum_{i\in I_0}\mathbb E\Big[\sum_{k>J_q}\rho_{r_i}(u_k,Z_{g(i)})\mathbb P(R_i=k,A^c_{i,Z}\mid Z)\,\mathbf 1\{|Z_{g(i)}|\le U\}\Big]\le C\pi_0q .
   $$
   This uses Lemma 4.8's uniformity in the number of Bernoulli variables, and the bound $\int_{-U}^U\phi\sup_{u\ge U}\rho_r\le\tfrac{1-q}2+U/\sqrt{2\pi}$, rederived as in the approved Lei tail-ratio lemma.

9. [ ] **(B4, KEY; adapts Lei Lemmas 4.4–4.7 and (280), changed) Per-null good-event bound with a frozen background.** There are universal $C,q_0$ such that, for every model in $\mathfrak B$ and every $i\in I_0$ with $g=g(i)$,
   $$
   \mathbb E\Big[\sum_{k>J_q}\rho_{r_i}(u_k,Z_g)\,\mathbb P(R_i=k,A_{i,Z}\mid Z)\,\mathbf 1\{|Z_g|\le U\}\Big]\le\frac{U}{2\sqrt{2\pi}}+C\sqrt U .
   $$
   **What changes.** In the slice $z_g\mapsto(z_g,z_{-g})$, the mean of the other counts is $G_{i,z}(u)=\int\mathbb P(|\vartheta+\alpha z_g+\sqrt{1-\alpha^2}\varepsilon|\ge u)\,d\Pi_{i,g}+B_{z_{-g}}(u)$. Here $\Pi_{i,g}=N^{-1}\sum_{\ell\in B_g\setminus\{i\}}\delta_{(\theta_\ell,a_\ell)}$, and $B(u)=N^{-1}\sum_{\ell\notin B_g}\mathbb P(|\theta_\ell+a_\ell z_{g(\ell)}+\sqrt{1-a_\ell^2}\varepsilon|\ge u)$ is nonincreasing in $u$ and independent of $z_g$. The background $B$ is *not* of Lei's $\Pi$ form: its residual variances are $1-a_\ell^2<1$, and it has point masses when $|a_\ell|=1$.

   **Planning observation (to be rechecked in execution, not used as a result).** The abstract supremum form of Lemma 4.7, with its factor-two crossing conditions (262) and an arbitrary nonincreasing $z$-independent $B$, is false. Take $B(u)=p(u)/(2q)$ on $[U,\infty)$ and a small null-only $\Pi$. Then every grid level is admissible for every $z$. Unit weights at the tilt-matched level give about $(1-r)U/(\sqrt{2\pi}\sqrt{1-r^2})$, which is the factor-two loss of Theorem 4.2(a).

   **Required approach.** B4 must use structure beyond (262). Take one of two routes.
   - (i) Sharpened crossing conditions on the good event: $\mu_{i,k}\ge(1-\epsilon_k)(k-1)$ and $\mu_{i,j}\le(1+\epsilon_j)j$ for $j>k$, with $\epsilon_k\le C(k^{-1}\log k)^{1/2}$ from Bernstein's inequality. The bad-event cost then becomes $O(\pi_0q\sqrt U)$, which is still acceptable. Then do reflected-floor accounting (A4) on the block's own deactivated movers: the block must supply the line deficit $(1-\epsilon_k)k/N-B(u_k)$. A separate estimate is needed for *background-pivotal* crossings, where the deficit is at most $\epsilon_kk/N$ (heuristic (iv) of the route idea).
   - (ii) Average over $Z_{-g}$ before any range bound.

   Test T8 must be passed by whichever argument is used.

10. [ ] **(B5, routine given B4) Fallback theorem: boundedly many null-carrying blocks.** Since $\sum_g\mathrm{FDR}_g(Z)\mathbf 1\{|Z_g|>U\}\le\mathbf 1\{\max_{g:J_g\ne\varnothing}|Z_g|>U\}$, B1–B4 give, uniformly over $\mathfrak B$,
    $$
    \operatorname{FDR}\le\pi_0q\Big(\frac{U}{2\sqrt{2\pi}}+C\sqrt U\Big)+Cq+G_0q .
    $$
    This gives the sharp constant whenever $G_0=o(\sqrt{\log(1/q)})$. It is a genuinely broader class than one factor. Record it as a separate draft asset candidate; it is not the target.

11. [ ] **(B6, KEY, new) Joint competition inequality for arbitrary $G_0$.** There are universal $C,q_0$ such that, for every model in $\mathfrak B$,
    $$
    \sum_{g=1}^G\mathbb E\,\mathrm{FDR}^{>J}_g(Z)\le\Big(1+\frac C{\sqrt U}\Big)\frac{qU}{2\sqrt{2\pi}}+Cq,\qquad
    \mathrm{FDR}^{>J}_g(z)=\frac qN\sum_{i\in J_g}\sum_{k>J_q}\rho_{r_i}(u_k,z_g)\,\mathbb P(R_i=k\mid Z=z).
    $$
    The bound covers the whole line in every $z_g$, with good and bad events together, uniformly in $G$, $G_0$, block sizes, loadings and means.

    Notes.
    - (a) The leading term has no factor $\pi_0$, and only an absolute $Cq$ is allowed. The per-block tail cost $G_0q$ of B5 must disappear.
    - (b) B6 cannot be obtained by adding B4's per-block central bounds to a tail estimate. In test T6, a heuristic leader-tracking calculation shows that this sum can exceed the target by a constant factor greater than one near $K=1$, while the heuristic actual excess stays below the target. Central and tail regions must be treated jointly.
    - (c) Suggested mechanism. For each block, take the whole-line tracked set $S_g(z_{-g})\subseteq\mathbb R$: the set of $z_g$ at which the selected crossing is tilt-matched, $||z_g|-r_iu|\le K_q$. Lemma 4.4 (206), extended to $|z|>U$, gives $\phi(z)\rho_r\le(1+CK_q/U)/(2\sqrt{2\pi}\sqrt{1-r^2})$ there; off the tracked sets, Gaussian off-tilt decay applies. Then prove the joint measure bound
      $$
      \sum_g\sum_{i\in J_g}\frac1N\,\frac{\mathbb E\,|S_{g,r_i}(Z_{-g})|}{\sqrt{1-r_i^2}}\le U+C\sqrt U .
      $$
      Its inputs are the reflected floors (A4) and the cap $\sum_gq\pi_{0g}\rho_g\le1+o(1)$, which is forced by the crossing conditions at all larger thresholds because the nulls are part of $G_{i,z}$. With one small block of null fraction $\pi$, the bound reduces to $\pi\sqrt{2\log(2/(q\pi))}\le U$, which holds for $\pi\le1$.
    - (d) B6 and G2 are statements about actual FDR. A rigorous violation would be a refutation candidate for the target itself, and must meet the project's refutation standard: an exact finite model, largest-rank BH, finite transfer and an independent check.

12. [ ] **(G2, conclusion of Part B; routine from B2 and B6.)** There are universal $C,q_0$ such that, for $q\le q_0$ and every model in $\mathfrak B$,
    $$
    \operatorname{FDR}\le\Big(1+\frac C{\sqrt U}\Big)\frac{qU}{2\sqrt{2\pi}}+Cq ,
    $$
    equivalently, by A1(d), $(q/N)\sum_{i\in I_0}\Delta_i\le(1+C/\sqrt U)\,qU/(2\sqrt{2\pi})+Cq-q\pi_0$.

### Part C — arbitrary covariance (gate G3; the open step)

13. [ ] **(C0, routine) Reductions.**
    - (a) For each fixed finite model, $\operatorname{FDR}(N,\theta,(1-\eta)\Sigma+\eta I)\to\operatorname{FDR}(N,\theta,\Sigma)$ as $\eta\downarrow0$. The FDP is bounded and continuous off the null set $\{|T_j|=u_k$ for some $j,k\}$, every $T_j$ is non-degenerate, and the means and null set are unchanged. So it suffices to treat positive-definite $\Sigma$, with all constants independent of $\eta$.
    - (b) Latent form $T=\theta+VW$, with rows $v_j$ unit vectors in $\mathbb R^d$ and $W\sim N(0,I_d)$. For null $i$, $c_i=(Vv_i)_{-i}$, $Y_i=(VP_{v_i^\perp}W)_{-i}$, and the line of null $i$ is the $W$-direction $v_i$.

14. [ ] **(C1, routine) Why Part B's mechanism cannot transfer, and the pathwise pivotal form.**
    - (a) Suppose $T_i=rS+s\varepsilon$, with $S$ measurable with respect to $\sigma(T_{-i})$ and $\varepsilon\sim N(0,1)$ independent of $\sigma(T_{-i},S)$. Then $s^2=1-R_i^2$, where $R_i^2$ is the squared multiple correlation of $T_i$ with $T_{-i}$. Similarly, $\Sigma=AA^{\mathsf T}+D^2$ with $D$ diagonal forces $D_{ii}^2\le1-R_i^2$. Under duplication of $i$ both vanish, and Part B's conditional route then bounds the FDR by itself. This is obstruction (1); Part C therefore averages over the null's own line (A1(e)).
    - (b) Pathwise pivotal form. Put $\tau=qR/N$, $\tau_i^{\mathrm{ex}}=\tau_i(0,Y_i)$, $\kappa_i=\big(1-(\tau/\tau_i^{\mathrm{ex}})\mathbf 1\{p_i\le\tau_i^{\mathrm{ex}}\}\big)_+\in[0,1]$, and $V^{\mathrm{piv}}=\sum_{i\in\mathcal R\cap I_0}\kappa_i\le V$. Then
      $$
      \operatorname{FDR}-q\pi_0\le\mathbb E\big[V^{\mathrm{piv}}/(R\vee1)\big]\le\operatorname{FDR}.
      $$
      This follows from A1(c),(d) and $(q/N)(a_i-a_i^{\mathrm{ex}})_+=\kappa_i\mathbf 1\{i\in\mathcal R\}/R$. It keeps the cap $V^{\mathrm{piv}}\le R$ in a single realization.

15. [ ] **(C2, KEY) Multiplicity gate $\mathfrak B^{\mathrm{mult}}$ (duplication robustness).** For every model in $\mathfrak B$ and multiplicities $n\in\{1,2,\dots\}^N$, the model obtained by repeating coordinate $j$ exactly $n_j$ times satisfies the G2 bound, with possibly larger universal constants. That model has dimension $\sum_jn_j$, duplicated rows and columns of $\Sigma$, and the same means. Uniform multiplicities are trivial by A1(f); non-uniform ones are the content.

    This is the smallest class where Lei's conditional independence of $P_i$ and $R_i$ given $Z$ fails, since copies share private noise, and where obstruction (1) lives. A hybrid proof is conceivable:
    - given $Z$, distinct base coordinates are independent;
    - the null's own copies are self-movers along its line, whose effect is in the favourable monotone direction (A2(ii));
    - heavy multiplicities break unit-weight Poisson-binomial concentration and must be treated as weighted, conditionally deterministic coordinates.

    Before proving, test T2 with null multiplicity $M\in\{2,\lceil\sqrt N\rceil,N/2\}$ and alternatives of multiplicity one.

16. [ ] **(C3 = G3, KEY, open) Global pivotality inequality.** For all admissible $(N,\theta,\Sigma)$ and $q\le q_0$,
    $$
    \frac qN\sum_{i\in I_0}\Delta_i(N,\theta,\Sigma)\le\mathfrak S(q)+\eta_3(q)\,qU+C_3q,\qquad
    \mathfrak S(q):=\sup_{\mathfrak M\in\mathfrak B^{\mathrm{mult}}}\big(\operatorname{FDR}(\mathfrak M)-q\pi_0(\mathfrak M)\big).
    $$
    C2 bounds $\mathfrak S(q)$, so C3 and C2 give the target. Proving the direct form $(q/N)\sum_i\Delta_i\le(1+\eta)qU/(2\sqrt{2\pi})+Cq$ for all models also completes the plan; by A1 that form is the target itself.

    **Mandatory properties of any proof.** A violation means the step is not proved.
    - (R1) Duplication-robust: no conditioning on $\sigma(T_{-i})$ or on a factor representation with private null noise; the argument must also apply to $\mathfrak B^{\mathrm{mult}}$ and T2.
    - (R2) Threshold-relevant only: no supremum of conditional tail ratios over admissible thresholds given a larger $\sigma$-field. T4 must not lose its heuristic factor of about $1.29$.
    - (R3) None of the failed tools: no covariance or nuclear-norm certificate, no SDP or completion relaxation over correlation matrices, no per-cell or per-face coefficient budget, no LP, and no transport ledger.
    - (R4) No absolute error proportional to $|I_0|/N$ times a growing factor; T3 must pass.
    - (R5) Uniform in $N,\theta,\Sigma$.

    **Route, in order.**
    - **C3.1 (key).** Rewrite the good-event arguments of B4, B6 and C2 as inequalities about the line functionals $\tfrac12\sum_\sigma(\Psi(f^\sigma_{i,y})-1)$, averaged over the law of $Y_i$. List explicitly the only block-specific inputs used:
      - (F1) concentration of the other counts given the null's line position;
      - (F2) the scalar-factor slope structure $c_{ij}=a_ia_j$;
      - (F3) independence across blocks.

      Output, before any attempt at C3.2: one written candidate line inequality $L^*$ whose hypotheses make sense for every $\Sigma$ and which implies the direct form. $L^*$ must first pass the numerical kill tests T1–T8.
    - **C3.2 (key, open).** Prove $L^*$ for arbitrary $\Sigma$ by replacing each input:
      - (F1′) exact deterministic line counts given $Y_i$, with Gaussian averaging over $Y_i$;
      - (F2′) the affine-path transport of Lemma 4.5 for arbitrary slopes $c_{ij}\in[-1,1]$, combined with A4;
      - (F3′) aggregation across nulls through the single-realization cap of C1(b).

17. [ ] **(C4, routine) Assembly.** This is the argument in Verification.

**Test families** (exact finite models; numerical evaluation is evidence only):
- T1: the Lei two-sided lower construction of [Lei finite Gaussian lower bound for two-sided BH](../assets/lei2026_two_sided_fdr_lower.md). Every candidate bound must be asymptotically tight here, not violated.
- T2: T1 with all coordinates duplicated (exact invariance), and with only nulls repeated $M$ times.
- T3: the single-null staircase of plan_two_sided_signed_forest_rank_cells_20261104, (F1)–(F2): $q=2\overline\Phi(U)$, $N=\lceil q/\overline\Phi(2U)\rceil$, $T_1=Z$, $T_{j+1}=Z-2t_j$. Here $(q/N)\Delta_1\ge(q/N)(3U^2/8-1)$.
- T4: the two-level factor family of idea_0d2e69e0ba3b(2).
- T5: the isotropic many-factor family of idea_4a0615ac99ad.
- T6: $G=\lceil q^{-K}\rceil$ iid T1-type blocks of $N/G$ coordinates each, for $K\in\{1/4,9/16,1,2\}$.
- T7: the fixed-$q$ common-gate family ($b=1$) of plan_two_sided_null_noise_folded_completion_20261104, Section 5. It lies in $\mathfrak B$ with $G=1$, and its finite-$q$ gain is not a violation.
- T8: $G=2$. Block 1 is a T1-type block with small null loading. Block 2 is a loading-one staircase $T_j=\theta_j+Z_2$, tuned so that for $Z_2$ in a window its counts lie within a factor $1-\delta$ of the BH line over a long threshold range.

**Stop rule (failure condition).**
- Execute the steps in the listed order. A routine step found false is a planning error: record it with its counterexample and stop.
- At the first KEY step (B4, B6, C2, C3.1 or C3.2) whose displayed inequality is not proved in full, execution stops. "In full" means every constant universal and every $o(1)$ a function of $q$ alone.
- On stopping:
  1. Set this plan to `failed`.
  2. Under `## Failure`, record the exact inequality that fails or remains unproved, and the precise estimate in the attempted argument that is not uniform, naming which of $N$, $G$, block sizes, loadings, $\theta$ or $\Sigma$ it depends on.
  3. Record any explicit admissible model violating that inequality, with every hypothesis checked: finite $N$, unit diagonal, PSD, nulls exactly $\theta_i=0$, ordinary largest-rank BH, the $q$-range used. State whether the violation is asymptotic in $q$ or only at fixed $q$; a finite-$q$ excess does not violate an asymptotic statement.
  4. Keep all completed steps as Progress, and leave the target asset untouched.
- Examples. B4 fails if no argument controls the frozen background uniformly, in particular if T8 gives a model in $\mathfrak B$ with the left side of B4 at least $(1+c)U/(2\sqrt{2\pi})$ for a fixed $c>0$ along $q\downarrow0$. C3.1 fails if no candidate $L^*$ passes T1–T8.
- A failed or refuted key proposition is an obstruction to this route only. **A failed plan is not a falsification** of the target or of the conjecture. A violation of B6, G2, C2 or the direct form of C3 would concern actual FDR; it is reported as a refutation candidate under the project's standard, never as proved.
- Prohibited repairs:
  - adding a $\pi_0$, $G_0$, $\log N$ or $\log G$ factor to an error term;
  - restricting the model class after the fact;
  - enlarging the leading constant;
  - letting $q_0$ depend on $N$, $G$ or $\Sigma$;
  - restating an unproved inequality as an assumption.

  A weakened statement may be recorded only as a separate idea.

## Verification

A fresh referee should check the following, in order.

1. **A1.**
   - (a) uses only joint Gaussianity and $\Sigma_{ii}=1$, singular case included.
   - (b) is deterministic, with non-strict inequalities, ties, $R=0$, and the largest qualifying rank.
   - (c) uses exact uniformity of $2\overline\Phi(|T_i|)$ for $\theta_i=0$ and independence of $Y_i$.
   - (d) is an equality.
   - (e) has finitely many jumps per line and measurable cells.
   - For (f), check $\widehat k\mapsto M\widehat k$ directly from the order statistics.
2. **A2 and A4.** Prove A2(iii) from the exact formula (i). The A4 floors use the same denominator $N$ and monotonicity of $\widehat k_q$ in each coordinate.
3. **Part B uniformity.**
   - B1 needs conditional independence given the whole vector $Z$; check that each null's kernel depends only on its own block factor.
   - B2 integrates over the whole line.
   - In B3, Lemma 4.8's constants are free of the number of Bernoulli variables, and $\delta_JC_q\le C(1+U)e^{-c\sqrt U}$, or $O(\sqrt U)$ under the sharpened conditions of B4(i).
   - In B4, every use of Lemmas 4.4–4.6 lies on its stated range ($0\le r\le3/5$, $|z|\le U$, or the stated extension). The background enters only through $z_g$-independence, and no supremum over admissible crossings is taken where a background can make all levels admissible.
   - In B6, no constant depends on $G$, $G_0$ or block sizes. The error is at most $Cq\sqrt U$ plus an absolute $Cq$, never $G_0q$.
   - G2 follows from B2 and B6, since $\operatorname{FDR}=\sum_g\mathbb E\,\mathrm{FDR}_g(Z)$.
4. **Part C.** C0's continuity argument fixes the finite model before $\eta\downarrow0$. C1(a) is a conditional-variance identity. C2 and C3 satisfy (R1)–(R5); the referee checks each requirement and reruns T1–T8 on $L^*$.
5. **Assembly.** By A1(d), and by C3 with C2 (or the direct form of C3), for $q\le q_0$ and every admissible model,
   $$
   \operatorname{FDR}\le q+\Big(1+\eta(q)\Big)\frac{qU}{2\sqrt{2\pi}}+Cq,\qquad \eta(q)=\frac C{\sqrt U}+2\sqrt{2\pi}\,\eta_3(q).
   $$
   By A0,
   $$
   \frac{\operatorname{FDR}}{q\sqrt{\log(1/q)}}\le\frac{1+\eta(q)}{2\sqrt\pi}\sqrt{1+\frac{\log2}{\log(1/q)}}+\frac{1+C}{\sqrt{\log(1/q)}} .
   $$
   The right side depends on $q$ alone and tends to $1/(2\sqrt\pi)$. For each $\varepsilon>0$, choose $q_\varepsilon\le q_0$ making it at most $1/(2\sqrt\pi)+\varepsilon$. This is exactly the target, uniform over all $N$, $\theta$ and $\Sigma$, including singular $\Sigma$ (C0(a)) and $q$-dependent models.
6. **Scope.** No step takes a fixed latent dimension, a single factor beyond the gate classes, a spherical population, or $N\to\infty$ before $q\downarrow0$.

## Assumed definitions

- Approved definitions used: [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md), [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md), and [conditional p-value distributions and independence](../definitions/conditional_pvalue_distributions.md).
- The classes $\mathfrak B$ and $\mathfrak B^{\mathrm{mult}}$, and the functionals $\Psi$, $\Delta_i$ and $\kappa_i$, are defined inside this plan. They are not new definition nodes; if B5 is extracted later, its class needs a draft definition node.
- No unproved draft result is assumed as a black box. The draft [Lei sharp two-sided BH upper bound with one common factor](../assets/lei2026_two_sided_common_factor_upper.md) is adapted and rechecked step by step (Adapted from), not cited.

## Adapted from

- **lei2026_two_sided_common_factor_upper** (draft; proof in paper `lei2026_gaussian_bh`: Theorem 4.2 on p. 60, proof of (b) on pp. 62–86).
  - **Hypotheses that transfer to $\mathfrak B$.** Conditional independence of all coordinates given the factor vector $Z$. Explicit Gaussian conditional kernels for each null that depend only on its block factor. The uniformity of Lemma 4.8 in the number and success probabilities of Bernoulli variables. The uniformity of Lemma 4.4 for $0\le r\le3/5$ and $|z|\le u_q$ (p. 64).
  - **Hypotheses that do not transfer.** The $\Pi$ form (211) of the slice mean count, because a frozen background from the other blocks appears. The single tail event $A_q=\{|Z|>u_q\}$ costing $q$ (p. 83), because there are $G_0$ such events.
  - **Step map.**
    - Lemma 4.1 and (273) correspond to B1 (vector factor; otherwise as in Lei).
    - (275) corresponds to B2, unchanged.
    - Lemma 4.8 (p. 83) and (279)–(282) correspond to B3, restricted to each null's own $|Z_{g(i)}|\le U$.
    - Lemmas 4.4–4.7 (pp. 64–82; range bound (215) on p. 66; integral bound (262) on p. 80) and (280) correspond to B4, changed by the background, the sharpened crossing conditions and the background-pivotal regime.
    - Lei's "first term at most $q$" (p. 83) is replaced by B5 (cost $G_0q$) and by the new joint estimate B6.
  - Part C adapts nothing from Lei except, in C3.2, the affine-path transport idea of Lemma 4.5, to be reproved for arbitrary slopes.
- **lei2026_conditional_fdp_bound** (approved). Its hypothesis, conditional independence given $Z$, holds for $\mathfrak B$ with the vector $Z$. Its proof is reproduced inside B1 through A1(b); it fails for $\mathfrak B^{\mathrm{mult}}$, which is the reason for C2.
- **lei2026_integrated_conditional_tail_ratios** (approved). Its kernels $F^{(2)}_{r,z}$ and its two-sided integrated bound on $|z|\le u_q$, which is zero at $r=1$, are rederived as in its proof for the constant $C_q$ in B3. Nothing else changes.

## Difference from failed plans

- **plan_two_sided_fixed_label_blocks_20261104.** That plan used a nuclear-norm completion certificate along an independent-null path and stopped at the dimension-uniform negative-part bound (Pr28). Here there is no covariance dual, path or certificate. Every quantity is an expectation under the actual law; the exact identity A1 has no remainder; and "blocks" are a model class, not fixed label blocks of a dual matrix.
- **plan_two_sided_null_noise_folded_completion_20261104.** That plan's diagonal relaxation (D2) over all correlation matrices was refuted by the common-gate family. Here there is no null-noise interpolation and no relaxation over correlation matrices; the common-gate family is test T7 inside $\mathfrak B$, with $G=1$, as a finite-$q$ check.
- **plan_two_sided_reflection_paired_stein_capacity_20261104.** That plan stopped at uniform feasibility of a frozen $N=2$ linear program. Here there is no LP certificate. Reflection enters only through the deterministic floor lemma A4, inside range bounds that keep the actual alternative distributions, the largest rank and the favourable cancellations, as that failure report requests.
- **plan_two_sided_rotation_pooled_arc_transport_20261104.** That plan failed because its unmatched term was controlled only by the FDR itself, which is circular. Here there is no transport ledger. Every bound in Parts B and C must be by a quantity other than the FDR (Verification item 3), and C1(a) identifies exactly when a conditional route turns circular.
- **plan_two_sided_signed_face_budget_20261104.** That plan's signed face kernels and reciprocal-rank telescoping lost the harmonic factor $H_N$. Here there are no face kernels. Small ranks are cut at $J_q=\lceil\sqrt U\rceil$, and larger ranks are controlled by conditional concentration and Lei-type range bounds; A2(iii) is a one-line tool, not a budget.
- **plan_two_sided_signed_forest_rank_cells_20261104.** That plan's per-null budget proportional to $|J|/N$ was refuted by the staircase. Here no per-null $\Delta_i$ is bounded individually; the staircase's $\Delta_1\gtrsim3U^2/8$ is allowed and is test T3. The error terms are an absolute $Cq$; B6 and C3 forbid null-fraction-proportional errors with growing factors (R4).

## Progress

Execution of 2026-11-05. Checklist items A0, A1, A2, A4, B1, B2 and B3 are established below with complete arguments. A5 was run in part (evidence only). Execution stopped at the key step B4; see `## Failure`. Nothing here is cited from failed plans or from draft assets. The approved Lei lemmas are reproved where used, as the plan requires.

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

### A2 (established)

**(i)** Put $p_k=p(s_k)$ and $p_{n+1}=0$. Since $f_k\le q<1=p(0)$ and $p$ is continuous and strictly decreasing,
$$
\{s\in[s_k,s_{k+1}):p(s)\le f_k\}=[\max(s_k,p^{-1}(f_k)),s_{k+1}) .
$$
Integrating $2\phi=-p'$ over this set gives (i).

**Telescoping identity.** Since $p_{k+1}\le p_k$, we have $[\min(f_k,p_k)-p_{k+1}]_+=\min(f_k,p_k)-\min(f_k,p_{k+1})$. Regroup the sum in (i), using $\min(f_0,p_0)/f_0=1$ and $\min(f_n,p_{n+1})=0$:
$$
\Psi(f)-1=\sum_{k=1}^nJ_k,\qquad J_k=\frac{\min\{p_k,f_k\}}{f_k}-\frac{\min\{p_k,f_{k-1}\}}{f_{k-1}} .
$$

**(ii) and (iii).** The map $f\mapsto\min\{p,f\}/f=\min\{p/f,1\}$ is nonincreasing. There are three cases.
- If $f_k\ge f_{k-1}$, then $J_k\le0$.
- If $f_k<f_{k-1}<p_k$, then both minima equal $1$, so $J_k=0$.
- If $f_k<f_{k-1}$ and $p_k\le f_{k-1}$, then
$$
J_k=\frac{\min\{p_k,f_k\}}{f_k}-\frac{p_k}{f_{k-1}}\le\min\{p_k,f_k\}\Big(\frac1{f_k}-\frac1{f_{k-1}}\Big)\le1-\frac{f_k}{f_{k-1}} .
$$

This is (iii). If $f$ is nondecreasing, every $J_k\le0$, which gives (ii); the statement about $\Delta_i$ then follows from A1(e). The telescoping identity replaces the induction suggested in the plan.

### A4 (established)

Fix $i$, $y$, $\sigma$ and $k$.

**(i)** The set $\{s\ge0:|b_j+\sigma cs|<u_k\}$ is the preimage of $(-u_k,u_k)$ under an affine map, intersected with $[0,\infty)$, so it is an interval. Coordinate $j$ is active exactly off this interval, so a deactivation as $s$ increases happens at most once. It requires activity at $s=0$, that is $|b_j|\ge u_k$. If $\sigma cb_j\ge0$, then $|b_j+\sigma cs|=|b_j|+|c|s\ge u_k$ for all $s\ge0$. So a deactivation also requires $\sigma cb_j<0$.

**(ii)** If $\sigma cb_j\le0$, then $b_j$ and $-\sigma c$ have the same sign (or $c=0$). Hence $|b_j-\sigma cs|=|b_j|+|c|s\ge|b_j|$. So $p(|b_j-\sigma cs|)\le p(|b_j|)\le t_{k'}$ whenever $u_{k'}\le|b_j|$.

**(iii)** The vector defining $\rho_i(x,y)$ is entrywise at most $\pi_S$: on $S$ the entries are equal, and elsewhere $\pi_S$ is $1$. By BH2, $\tau_i(x,y)\ge(q/N)\,\widehat k_q(\pi_S)$. For the coordinates $j\in D$, (ii) gives $p(|b_j-\sigma c_{ij}s|)\le p(|b_j|)$ for all $s\ge0$. Hence the vector at $x=-\sigma s$ is entrywise at most $((p(|b_j|))_{j\in D},1,\dots,1)$, and BH2 gives the floor.

### A5 (partly run; evidence only; box left unticked)

**Analytic cases.**
- $\Sigma=I$: every $c_i=0$, so $\tau_i(x,y)$ does not depend on $x$, and $\Delta_i=0$ by A1(c).
- $N=1$: $\tau\equiv q$ and $\Delta_1=0$.
- Uniform duplication: covered by A1(f).

**Numerical check 1 (A2).** 2000 random step functions were drawn with $q=0.05$ and $N=40$: $n\in\{0,\dots,5\}$ jumps uniform on $[0,3.5]$, and values uniform on the grid $\{t_k\}$.
- Largest difference between the telescoped identity and (i): $4.4\cdot10^{-16}$.
- Largest value of $\Psi-1-(\text{jump bound (iii)})$: $3.3\cdot10^{-16}$, which is rounding.
- For 200 of the cases, (i) was compared with a Monte Carlo average of $\mathbf 1\{p(s)\le f(s)\}/f(s)$ over $4\cdot10^5$ draws $s=|N(0,1)|$. The largest $|z|$-score was $1.84$.

**Numerical check 2 (A1(b),(d),(e)).** Three random models with $N=3$ were drawn with seed 20261105:
- $\Sigma$ is the correlation matrix of $AA^{\mathsf T}+0.05\,\mathrm{diag}(\mathrm{Unif})$ with $A\in\mathbb R^{3\times2}$ standard Gaussian;
- $\theta=(0,0,\vartheta)$ with $\vartheta\sim\mathrm{Unif}[2,4]$;
- $q=0.2$.

Two estimates of the FDR were compared.
- Direct Monte Carlo of the FDP over $4\cdot10^5$ draws, with largest-rank BH.
- The identity $q\pi_0+(q/N)\sum_i\Delta_i$, where each $\Delta_i$ uses $6000$ draws of $Y_i\sim N(0,\Sigma_{-i,-i}-c_ic_i^{\mathsf T})$. For each $Y_i$ and branch, all roots $s>0$ of $|b_j+\sigma c_{ij}s|=u_k$ are listed, the forced-zero rank is evaluated at the midpoints, and (i) is applied.

| model | direct Monte Carlo FDR | identity estimate | $(\Delta_1,\Delta_2)$ |
|---|---|---|---|
| 1 | $0.12143\pm0.00044$ | $0.12095$ | $(-0.090,-0.096)$ |
| 2 | $0.13549\pm0.00044$ | $0.13528$ | $(0.008,0.021)$ |
| 3 | $0.12076\pm0.00044$ | $0.12017$ | $(-0.095,-0.103)$ |

The identity estimate has its own Monte Carlo error of comparable size. The core of the branch evaluation is:

```python
p = lambda u: 2*norm.sf(u)
def psi_exact(jumps, vals):            # A2(i), right-continuous version
    s = np.concatenate([[0.0], jumps, [np.inf]]); tot = 0.0
    for k, f in enumerate(vals):
        nxt = 0.0 if np.isinf(s[k+1]) else p(s[k+1])
        tot += max(min(f, p(s[k])) - nxt, 0.0)/f
    return tot
# branch sigma, given y: b = theta[-i] + y, cc = sigma*Sigma[-i, i]
# roots = sorted{(±u_k - b_j)/cc_j > 0}; vals = q*bh_rank(vector with 0 at i,
#   p(|b + cc*s|) elsewhere)/N at the midpoints between consecutive roots
# Delta_i = mean over y of (psi(+)+psi(-))/2 - 1
```

**Not run:** the $N=2$ closed form of plan_two_sided_null_noise_folded_completion_20261104, and tests T3 and T7. Their parameters are defined in other plans outside this stage's pack.

### B1 (established)

Given $Z$, the coordinates $T_j=\theta_j+a_jZ_{g(j)}+\sqrt{1-a_j^2}\,\varepsilon_j$ are functions of the independent $\varepsilon_j$, so they are conditionally independent.

For $i\in J_g$, $P_i=p(|a_iZ_g+\sqrt{1-a_i^2}\,\varepsilon_i|)$. Since $\varepsilon_i\overset d=-\varepsilon_i$, its conditional CDF is $F^{(2)}_{r_i,Z_g}$, which depends on $Z$ only through $Z_g$; it is also even in $z_g$. The forced-zero rank $R_i=\widehat k_q(x^0)$ is a function of $(P_\ell)_{\ell\ne i}$, so it is conditionally independent of $P_i$ given $Z$.

By A1(b),
$$
\mathbb E\Big[\frac{\mathbf 1\{i\in\mathcal R\}}{R\vee1}\,\Big|\,Z\Big]=\sum_k\mathbb P(R_i=k\mid Z)\frac{F^{(2)}_{r_i,Z_g}(t_k)}{k}=\frac qN\sum_k\rho_{r_i}(u_k,Z_g)\,\mathbb P(R_i=k\mid Z),
$$
because $t_k=p(u_k)$ and $1/k=(q/N)/t_k$. Take expectations and use A1(d) to get the display of B1. Summing over $i\in J_g$ and over $g$ gives $\sum_g\mathrm{FDR}_g(Z)=\mathbb E[\mathrm{FDP}\mid Z]\le1$. At $|a_i|=1$ the kernel is a $0/1$ function, and nothing changes.

### B2 (established)

For fixed $u$, let $X=rZ+\sqrt{1-r^2}\,\varepsilon\sim N(0,1)$. Then
$$
\int\rho_r(u,z)\phi(z)\,dz=\frac{\mathbb P(p(|X|)\le p(u))}{p(u)}=1 .
$$
Using $\mathbb P(R_i=k\mid Z)\le1$, $\rho\ge0$ and $Z_{g(i)}\sim N(0,1)$, the left side of B2 is at most
$$
\frac qN\sum_{i\in I_0}\sum_{k\le\min(J_q,N)}1\le\pi_0qJ_q .
$$

### B3 (established)

The event $A_{i,z}$ is Lei's (278): with $J=J_q$, set $B^+_{i,j}=\{N_{i,j}\ge j-1,\ \mu_{i,j}(z)<j/2\}$ and $B^-_{i,j}=\{N_{i,j}\le j-2,\ \mu_{i,j}(z)>2j\}$, and let $A_{i,z}=\bigcap_{j=J}^N(B^+_{i,j}\cup B^-_{i,j})^c$. For $q<2\overline\Phi(1)$ we have $U>1$, so $J\ge2$.

**Lemma 4.8, reproved.** Let $N_j$ be Poisson-binomial with mean $\mu_j$; the $N_j$ may be nested in $j$.
- *Upper tail.* For $a>\mu$, Chernoff gives $\mathbb P(N\ge a)\le e^{-\mu}(e\mu/a)^a$, using $\mathbb Ee^{\lambda N}\le e^{\mu(e^\lambda-1)}$ with $\lambda=\log(a/\mu)$. The bound is increasing in $\mu\in(0,a)$. Take $a=j-1$, $\mu<j/2$, $j\ge2$, and use $(j-1)\log\frac j{j-1}\le1$. Then
$$
\mathbb P(B^+_j)\le\exp\Big(-\frac j2+(j-1)(1-\log2)+1\Big)=2e^{-(\log2-1/2)j} .
$$
If $\mu=0$, then $N=0$ almost surely, and $B^+_j$ is null for $j\ge2$.
- *Lower tail.* If $\mu>2j$, then $\mathbb P(N\le j-2)\le\mathbb P(N\le\mu/2)\le e^{-\mu/8}\le e^{-j/4}$.

Put $c_0=\log2-1/2$. Summing over $j\ge J$,
$$
\mathbb P\Big(\bigcup_{j\ge J}(B^+_j\cup B^-_j)\Big)\le\delta_J:=\frac{3e^{-c_0J}}{1-e^{-c_0}} .
$$
This bound is uniform in the number of Bernoulli variables and their success probabilities.

In $\mathfrak B$, the indicators $\mathbf 1\{P_\ell\le t_j\}$ for $\ell\ne i$ are conditionally independent given the full vector $Z$ (B1). So $\mathbb P(A^c_{i,Z}\mid Z)\le\delta_J$ almost surely.

**Tail-ratio integral, rederived.** For $r<1$ put $s=\sqrt{1-r^2}$. The joint density identity $\phi(z)\phi((x-rz)/s)=\phi(x)\phi((z-rx)/s)$ gives, for $v\ge U$,
$$
\phi(z)\,\overline\Phi\Big(\frac{v-rz}s\Big)=\int_v^\infty\phi(x)\frac1s\phi\Big(\frac{z-rx}s\Big)dx\le\frac1s\phi\Big(\frac{(rU-z)_+}s\Big)\overline\Phi(v).
$$
The inequality holds because $rx-z\ge rU-z\ge0$ for $x\ge v\ge U$ when $z\le rU$, and trivially when $z>rU$. Applying it to both tails,
$$
\phi(z)\sup_{v\ge U}\rho_r(v,z)\le\frac1{2s}\Big[\phi\Big(\frac{(rU-z)_+}s\Big)+\phi\Big(\frac{(rU+z)_+}s\Big)\Big].
$$
Integrating over $[-U,U]$ gives
$$
\int_{-U}^U\phi\,\sup_{v\ge U}\rho_r\le\Phi(U/\gamma_r)-\frac12+\frac{\gamma_rU}{\sqrt{2\pi}}\le\frac12+\frac{\gamma_rU}{\sqrt{2\pi}},\qquad \gamma_r=\sqrt{\frac{1-r}{1+r}} .
$$
At $r=1$, $\rho_1(v,z)=\mathbf 1\{|z|\ge v\}/p(v)$ vanishes on $|z|<U\le v$, so the integral is $0$. Since $\gamma_r\le1$, $C_q:=\sup_r\int_{-U}^U\phi\sup_{v\ge U}\rho_r\le\frac12+U/\sqrt{2\pi}$. This is slightly weaker than the plan's $(1-q)/2+U/\sqrt{2\pi}$ and is all that is needed.

**Conclusion.** For $k>J$ we have $u_k\ge U$, so
$$
\sum_{k>J}\rho_{r_i}(u_k,Z_g)\,\mathbb P(R_i=k,A^c_{i,Z}\mid Z)\le\delta_J\sup_{u\ge U}\rho_{r_i}(u,Z_g).
$$
Taking expectations on $\{|Z_g|\le U\}$ and summing over $i\in I_0$, the left side of B3 is at most
$$
\pi_0q\,\delta_J\,C_q\le\pi_0q\cdot\frac{3e^{-c_0\sqrt U}}{1-e^{-c_0}}\Big(\frac12+\frac U{\sqrt{2\pi}}\Big)\le C\pi_0q,
$$
with a universal $C$.

### B4: what was proved before the stop (partial; B4 itself is not established)

**(B4-a) Proved: the loadings $r_i\in\{0\}\cup[3/5,1]$.** Since $\sum_k\mathbb P(R_i=k,A_{i,Z}\mid Z)\le1$ and $u_k\ge U$, the left side of B4 is at most $\int_{-U}^U\phi\,\sup_{u\ge U}\rho_{r_i}$.
- For $3/5\le r<1$, this is at most $\frac12+\gamma_rU/\sqrt{2\pi}\le\frac12+U/(2\sqrt{2\pi})$, because $\gamma_r$ is decreasing and $\gamma_{3/5}=1/2$. The integral is rederived in B3.
- For $r=1$ it is $0$.
- For $r=0$, $\rho_0\equiv1$, and the left side is at most $1$.

So B4 holds with $C=1$ for these loadings, with no use of the background.

**(B4-b) Rechecked: the planning observation (the supremum form of Lemma 4.7 fails with a frozen background).** Fix $0<r<3/5$, and suppose every grid level satisfies Lei's crossing conditions (262) at every $z_g$. This happens when the slice count is $G(u_k)=\lceil k/2\rceil/N$.
- *Realisation at one background value.* Take $G=2$. Block 1 contains only the null $i$, with loading $r$. Block 2 has loading-one coordinates $T_\ell=\theta_\ell+Z_2$, with $|\theta_\ell|=u_{2m-1}$ for $m=1,\dots,\lceil N/2\rceil$, padded by block-2 coordinates with $\theta_\ell=0$. At $z_2=0$ the padding is inactive, and $\#\{\ell:|\theta_\ell|\ge u_k\}=\lceil k/2\rceil$.
- *Lower bound.* Take the weight at the level nearest to $u=|z_g|/r$, for $|z_g|\in[rU,U]$. Then $u-r|z_g|=us^2$. The Mills bounds $\overline\Phi(x)\ge\frac{x}{1+x^2}\phi(x)$ and $\overline\Phi(u)\le\phi(u)/u$, together with $\phi(ru)\phi(su)/\phi(u)=1/\sqrt{2\pi}$, give
$$
\phi(z_g)\rho_r(u,z_g)\ge\frac1{2s\sqrt{2\pi}}\Big(1-\frac1{U^2s^2}\Big).
$$
For large $N$ the grid is dense in $[U,U/r+1]$ and $\rho_r$ is continuous. So the supremum-form integral is at least $(1-o(1))\gamma_rU/\sqrt{2\pi}$. This exceeds $U/(2\sqrt{2\pi})+C\sqrt U$ for small $q$, because $\gamma_r>1/2$.
- *Numbers.* The integral $\int_{-U}^U\phi\sup_{u\ge U}\rho_r$ was computed with mpmath (40 digits; supremum over a 401-point $u$-grid on $[U,\max(|z|/r,U)+3]$; trapezoid rule on 801 points of $z$). Its ratio to $U/(2\sqrt{2\pi})$ was:

| $q$ | $r=0.1$ | $r=0.3$ |
|---|---|---|
| $10^{-4}$ | $2.34$ | $2.07$ |
| $10^{-8}$ | $2.20$ | $1.89$ |
| $10^{-16}$ | $2.10$ | $1.76$ |
| $10^{-32}$ | $2.02$ | $1.67$ |

  The limits are $2\gamma_{0.1}=1.81$ and $2\gamma_{0.3}=1.47$ up to the additive $1/2$. The ratio tends to $2\gamma_r$, which is Theorem 4.2(a)'s factor-two loss.
- *Scope.* This refutes only the abstract supremum lemma. In this configuration the *actual* weights $\mathbb P(R_i=k,A_{i,z}\mid Z=z)$ vanish on the range, because a crossing needs $N_{i,k}\ge k-1$ while the count is about $k/2$. So it is not a model violating B4.

**(B4-c) Carried over from Lei, not rechecked line by line.** For $0<r<3/5$, the pieces $|z_g|<L_q$ (Lemma 4.4 (205), cost $CL_q$) and the off-tilt piece $\bigl||z_g|-ru\bigr|>K_q$ (cost $O(U^{-3})$) involve only the null's own kernel. They hold for $\mathfrak B$ unchanged.

## Failure

Execution stopped at the first key step, **B4**, under the plan's stop rule. The target asset is untouched. A failed plan is not a falsification of the target or of the conjecture, and no refutation candidate arose.

### 1. The inequality that is not proved

B4, for null loadings $0<r_i<3/5$: for every model in $\mathfrak B$ and every $i\in J_g$,
$$
\mathbb E\Big[\sum_{k>J_q}\rho_{r_i}(u_k,Z_g)\,\mathbb P(R_i=k,A_{i,Z}\mid Z)\,\mathbf 1\{|Z_g|\le U\}\Big]\le\frac{U}{2\sqrt{2\pi}}+C\sqrt U .
$$
For $r_i\in\{0\}\cup[3/5,1]$ it is proved (Progress, B4-a). Within the attempted argument, the missing estimate is the replacement of Lei's length bound (269): the total tilt-matched length must be at most $(1-r)U+C\sqrt U$ once a frozen background is present.

### 2. The attempted argument (route (i)) and where it stops

**Step 1, sharpened good event (sketch, believed routine).** Define $A'_{i,z}$ by $\mu_{i,k}\ge(1-\epsilon_k)(k-1)$ on $\{N_{i,k}\ge k-1\}$ and $\mu_{i,j}\le(1+\epsilon_j)j$ on $\{N_{i,j}\le j-2\}$, for all $j\ge J$, with $\epsilon_k=4\sqrt{\log k/k}$. Bernstein's inequality bounds each level's failure probability by $2k^{-2}$. Hence $\mathbb P((A'_{i,z})^c\mid Z=z)\le4/J$. As in B3, the cost is at most $(4/J)\,C_q\le C\sqrt U$ per null. So it suffices to bound the B4 left side with $A_{i,Z}\cap A'_{i,Z}$ in place of $A_{i,Z}$.

**Step 2, decomposition.** Write $\mu_{i,j}(z)/N=G^{\mathrm{blk}}_{i,z_g}(u_j)+B_{z_{-g}}(u_j)$, where
- $G^{\mathrm{blk}}$ is the slice count of the block's own measure $\Pi_{i,g}$, nulls included;
- $B$ is the background from the other blocks.

Pieces with $|z_g|<L_q$, or with $\bigl||z_g|-ru_k\bigr|>K_q$, are handled by Lemma 4.4 and do not involve the background (Progress, B4-c). For a tilt-matched crossing at level $k$, fix $\eta\in(0,1/4]$ and split into two cases.
- **Block-pivotal:** $G^{\mathrm{blk}}(u_k)\ge\eta\,p(u_k)/q$. The block measure then satisfies Lei's (212) with lower constant $\eta$ in place of $1/2$. The upper bound $G^{\mathrm{blk}}(v)\le G(v)\le3p(v)/q$ is inherited because $B\ge0$. So Lemmas 4.5 and 4.6 should apply to $\Pi_{i,g}$ with $\eta$-dependent constants. This was not rechecked against pp. 66–80.
- **Background-pivotal:** $G^{\mathrm{blk}}(u_k)<\eta\,p(u_k)/q$. On $A'$ this forces
$$
B_{z_{-g}}(u_k)\ge(1-\epsilon_k-\eta)\frac{p(u_k)}q-\frac1N,\qquad B_{z_{-g}}(u_j)\le(1+\epsilon_j)\frac{p(u_j)}q\quad(j>k).
$$

**Step 3, the unproved estimate.** The proof needs
$$
\mathcal E^{\mathrm{bg}}_i:=\mathbb E\Big[\mathbf 1\{L_q\le|Z_g|\le U\}\sum_{k>J_q}\rho_{r}(u_k,Z_g)\,\mathbb P\big(R_i=k,\ A_{i,Z}\cap A'_{i,Z},\ \mathcal P^{\mathrm{bg}}_k\mid Z\big)\Big]\le C\sqrt U ,
$$
where
$$
\mathcal P^{\mathrm{bg}}_k=\Big\{G^{\mathrm{blk}}_{i,Z_g}(u_k)<\eta\,\frac{p(u_k)}q,\ \bigl||Z_g|-ru_k\bigr|\le K_q\Big\}.
$$
It also needs the block-pivotal length bound to stay at $(1-r)U+C\sqrt U$. I could prove neither form of the background estimate.
- **Per fixed $z_{-g}$.** The set of levels satisfying the two background conditions does not depend on $z_g$. It can contain every level in $[U,U/r]$: take the deterministic staircase of B4-b, rescaled to the counts $\lceil(1-\eta/2)k\rceil$. Then the block needs to supply only an $\eta/2$ fraction. Lemma 4.5's exclusion (219)–(223) compares the block's count at shifted levels with the line $p(v)/q$. Here the comparison function is the deficit $D(v)=p(v)/q-B(v)$, plus the slack $\epsilon_jp(v)/q$. The only constraint on $D$ is that $p/q-D$ is nonincreasing, and the slack can exceed $D$. So the block's available upper bound $D+\epsilon_jp/q$ is not comparable with its lower bound at the crossing, and no exclusion follows. B4-b shows that the abstract admissible-set version of this step is false.
- **Averaged over $Z_{-g}$ (route (ii)).** This fails at the first step. After averaging, the weights $\mathbb E_{Z_{-g}}\mathbb P(R_i=k,A\mid Z)$ at a given $z_g$ draw their support from different backgrounds. No single slice count $G$ satisfies (262) for them, so Lemma 4.7 cannot be invoked. A direct averaged bound would need an anti-concentration estimate: how often, in $Z_{-g}$ and in the background's private noise, the background count process stays within relative $\eta+\epsilon_k$ of the BH line at the levels tilt-matched to $z_g$. I have no such estimate uniform over the model class.

### 3. Which parameter breaks uniformity, and how

- **Background loadings $|a_\ell|\to1$, $\ell\notin B_g$.** These coordinates have no private noise. Given $Z_{-g}$ their counts are deterministic, so Poisson-binomial concentration gives no smoothing. Their staircase can be placed on the BH line to any precision.
- **Background means $\theta_\ell$.** They set where the staircase sits.
- **The number of background blocks $G$.** The background can be assembled from many independent staircases, and no argument here controls their joint configuration.

Per $z_{-g}$, the quantity that is not uniformly bounded is the measure of $z_g$ tilt-matched to background-pivotal levels. It can reach $2(1-r)U-O(L_q)$ in the admissible-set form (B4-b), twice what is allowed. No uniform bound was found on the $Z_{-g}$-probability of such configurations under actual BH.

### 4. Models

No admissible model violating B4 is known, and test T8 was not run. The B4-b configuration violates only the abstract supremum lemma, at the single factor value $z_2=0$. That model is admissible: finite $N$; block-diagonal unit-diagonal PSD $\Sigma$, singular because block 2 contains pairs with loading one; the null $i$ has $\theta_i=0$; largest-rank BH; any $q\le q_0$. But $\{Z_2=0\}$ is a null event, and the actual weights vanish there, so it says nothing about the FDR.

Heuristic evidence that B4 may be true (not proofs):
- For one loading-one staircase block, the window in $z_h$ where the background stays within relative $\delta$ of the line at level $u$ has width $O(\delta/u)$. That suggests an excess of $O(\delta)\ll\sqrt U$.
- Block counts are nondecreasing in the level. So a crossing that is strictly below the line at all larger thresholds cannot follow the tilt over an interval when the movers are same-sign loading-one coordinates and the deficit is flat. The required deficit would have to be both nondecreasing and decreasing in $u$.

### 5. What was established before the stop (all under `## Progress`)

- **G1 = A1 (proved).** The identity $\operatorname{FDR}=q\pi_0+(q/N)\sum_{i\in I_0}\Delta_i$ holds exactly, together with the pointwise identity (b), the exogenous unbiasedness (c), the branch form (e) and duplication invariance (f). One detail is corrected: $f^\pm_{i,y}$ is piecewise constant and equals a right-continuous step function off a finite set.
- **A0, A2, A4 (proved).** A2 adds the exact identity $\Psi(f)-1=\sum_k\bigl[\min\{p_k,f_k\}/f_k-\min\{p_k,f_{k-1}\}/f_{k-1}\bigr]$.
- **B1, B2, B3 (proved for $\mathfrak B$).** In B3, $C_q\le\frac12+U/\sqrt{2\pi}$, and $\delta_J=3e^{-(\log2-1/2)J}/(1-e^{-(\log 2-1/2)})$.
- **B4-a (proved).** B4 holds with $C=1$ when $r_i\in\{0\}\cup[3/5,1]$.
- **B4-b (rechecked, with proof sketch and numbers).** The supremum form of Lemma 4.7 is false with a frozen background.
- **A5 (partial numerical evidence).**
- **Not attempted:** B5–B6, G2 and C0–C4. B5 depends on B4.

### 6. What a new plan would need

1. **A deficit form of Lemma 4.5.** Replace the line by $D=p/q-B$, use only that $p/q-D$ is nonincreasing, and obtain an exclusion for block-pivotal crossings with explicit dependence on $\eta$.
2. **A background estimate.** Either an anti-concentration lemma, uniform over the other blocks, giving $\mathcal E^{\mathrm{bg}}_i\le C\sqrt U$; or a coupling showing that, in the background-pivotal regime, the realised rank agrees with a $Z_g$-independent rank except on an event of small tilt-weighted probability.

Weakening B4, for example by restricting background loadings away from one, is a separate idea and not a repair.
