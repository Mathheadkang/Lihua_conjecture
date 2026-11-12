---
title: Coordinate-carrier blocking for many-block frozen backgrounds, two-sided entropy truncation, and the exogenous-pivotal route to the sharp two-sided bound
type: plan
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
inspired_by:
  - idea_3370404c0baa
  - idea_5684036b1ecf
  - idea_a4ba452bf4a7
  - idea_3be77b4166bb
  - idea_0d2e69e0ba3b
  - idea_0610115f8682
adapts:
  - lei2026_two_sided_common_factor_upper
  - lei2026_conditional_fdp_bound
  - lei2026_integrated_conditional_tail_ratios
---

## Goal

Target: [Sharp uniform upper-bound target for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_sharp_upper.md).

**The only conclusion.** For every $\varepsilon>0$ there is $q_\varepsilon\in(0,1)$ such that the following holds for every $q\in(0,q_\varepsilon)$, every finite $N$, every $\theta\in\mathbb R^N$ and every unit-diagonal positive-semidefinite $\Sigma$. Here $\Sigma$ may be singular, and $N,\theta,\Sigma$ may depend on $q$. Ordinary BH with the largest qualifying rank, applied to $p_i=2\overline\Phi(|T_i|)$ with true nulls $\{\theta_i=0\}$, satisfies
$$
\operatorname{FDR}\le\Big(\frac1{2\sqrt\pi}+\varepsilon\Big)q\sqrt{\log(1/q)} .
$$
Block classes, bounded block numbers, the multiplicity class and fixed-$q$ families are gates and tests only.

### Mechanism chosen, and why

The skeleton is that of plan_two_sided_exogenous_pivotal_blocks_20261105. It has three parts:
- the exact identity $\operatorname{FDR}=q\pi_0+(q/N)\sum_i\Delta_i$ (proved there, re-included here);
- a gate on independent one-factor blocks $\mathfrak B$;
- a global pivotality step for arbitrary $\Sigma$.

That plan stopped at B4, the per-null bound with a frozen background coming from the other blocks. This plan replaces B4 by a different decomposition, in four parts.

1. **Reduction of B4 to a single background inequality (H-KEY).** For a null $i$ in block $g$, every block $\mathfrak B$-model is a factor model with factor $\zeta=Z_g$ along the null's line and orthogonal factors $x=(Z_h)_{h\ne g}$. The approved sibling theorem twosided_kfactor_sharp_upper (path in `## Adapted from`) splits the other coordinates into three classes:
   - A: movers along the null's line;
   - L: rigid, nearly unit-variance coordinates;
   - H: coordinates with a large loading on an orthogonal factor.

   Its Steps 4–7 and 10 reduce the per-null tracking length to one inequality about H-points. In $\mathfrak B$ the H class is exactly the background coordinates with $|a_\ell|>r/6$. Steps 4–7 are fiberwise and do not depend on the number of factors. **Only their H-step (Step 8, the direction count) depends on the number of factors, and it fails for many background blocks.** The new KEY is that H-step, proved uniformly in the number of blocks (H-KEY, step 2).
2. **Coordinate-carrier blocking.** Block structure gives two facts that a random direction on a high-dimensional sphere loses.
   - Every H-atom lies on a coordinate axis $e_h$.
   - Every H-atom has zero loading on $\zeta$, so its conditional count does not depend on $\zeta$.

   Hence one H-point blocks tracking at height $t+\Delta_q$ on **both** signs, along its dominant carrier's own coordinate. The shift is exactly aligned: $\vartheta=1$, with no direction count. The two-sided structure enters through this sign-free blocking and through Lei's reflected exclusion for the A-class.

   Two regimes are then proved gates:
   - few heavy carriers, via Rademacher directions on the block coordinates, for which no direction is bad;
   - light (small) blocks, via Bernstein concentration over independent blocks plus monotone-likelihood-ratio rigidity of unit-variance means ([Unit-variance backgrounds cannot hug the BH line over a tilt range (MLR rigidity)](../ideas/idea_a4ba452bf4a7.md)).

   **The remaining KEY core is the regime of many heavy carriers whose identity varies with $x$.** Two independent projects reached this obstruction; see the sibling note below.
3. **Two-sided entropy truncation.** This adapts the approved sibling theorem onesided_direction_entropy_upper. Each null block is truncated at its own level $U_g=p^{-1}(qw_g)$, using a two-sided shell lemma (proved below). This replaces the $G_0q$ tail of the old B5 by $2q\sum_gw_g\log(1/w_g)\le2q(\log G_0+1/e)$, so the bound is sharp whenever $\log G_0=o(\sqrt{\log(1/q)})$. The joint-competition KEY (B6′) is then needed only for $\log G_0\gtrsim\sqrt{\log(1/q)}$, that is, exponentially many null blocks.
4. **Error budget.** Every intermediate bound carries an error $\eta(q)\,qU$ with $\eta(q)\to0$ depending on $q$ only, which is all the target needs. The old plan's $C\sqrt U$ requirement is dropped.

**Alternatives considered and not adopted.**
- *Sign-pairing for a fixed background* (idea_3370404c0baa item 2). Not adopted; see the tests below. A version averaged over the background, "one sign per height on average", is exactly H-KEY.
- *Background anti-hugging* (cost of the hug set tends to zero). This is stronger than needed. H-KEY needs only H-density at most $1/2$ per sign. Anti-hugging is kept only as an optional route, step 2a(ii).
- *Deficit-line Lemma 4.5* (idea_5684036b1ecf). Not adopted: the contradiction needs the deficit to decay over the shift distance, and only "$\ell-D$ nonincreasing" is known. Block-pivotal crossings are covered instead by the sibling A/L-fiber lemmas (step 3), which need only that the background count is nonnegative.

### Heuristics tested at planning (results, not proofs)

- **idea_3370404c0baa item 1 (envelope reduction): correct, not used.** The likelihood ratio of $|ry+s\varepsilon|$ against $|N(0,1)|$ is unimodal in $|x|$. Indeed $\frac d{dx}\log\mathrm{LR}=x(1-1/s^2)+c\tanh(cx)$ is concave on $[0,\infty)$ and vanishes at $0$. Then $\rho'=\lambda(\rho-\mathrm{LR})$ gives unimodality of $u\mapsto\rho_r(u,z)$. Inserting the background-alone rank as a lower bound reproduces the supremum form and its factor-two loss.
- **Item 2 (sign-splitting with a frozen $B$): the stated justification is incomplete. It is not refuted.**
  - Pairing $z$ with $-z$ at the same $|z|$ gives no contradiction even with no background. At $-x$ the reflected class lies beyond $v_++2|\alpha|x$, deeper than the crossing, so the only constraint is $|A_-|\le3p(v_-)/q$, which is consistent.
  - Lei's useful pairing ($z_1$ against $z_2,-z_3$ beyond $z_1+B_q$) contradicts the crossing conditions only when the comparison function decays over the shift. With a frozen background the comparison function is the deficit $D$, which can be flat.
  - Flat $D$ is harmless for a different reason. The crossing is then an order statistic of points moving at speed at most $1$, while tracking needs speed $1/r>5/3$.
  - No admissible counterexample was found.
- **Item 3, the sandwich: correct.** The claim "a deterministic hugging background is realizable by LLN over a range" is **false** for any range of tilt length $\gg\eta/U$, by MLR rigidity of unit-variance mixtures ([MLR rigidity](../ideas/idea_a4ba452bf4a7.md)). Numerically, the hug length satisfies $u_b-u_a\le1.5\,\eta u_b/U^2$ over 900 random mixtures. Realized counts can still return to the line with probability of order one (sibling counterexample below), but only inside an interval of tilt length $O(1/U)$.
- **Item 4 (one-sided sup form): not relevant** to this two-sided target; not used.

### Sibling-project results (researcher-authorized). Approved there, **not** approved here.

The files are under `/Users/xiaosheng/Desktop/Research/Lihua_conjecture_claude/BH_FDR_Claude_Independent/research/assets/`.
- **twosided_kfactor_sharp_upper.md.** For every fixed $K$, in two-sided $K$-factor models, $\operatorname{FDR}\le q\pi_0\{u_q/(2\sqrt{2\pi})+C_Ku_q^{3/4}\}+C_Kq$. Steps 1–7, 9 and 10 of its proof are reproduced here in $\mathfrak B$-form (steps 2b, 3, 4 below). Its Step 8 is replaced.
- **twosided_kfactor_growing_sharp_upper.md.** The bound $\operatorname{FDR}\le q\pi_0\{u_q/(2\sqrt{2\pi})+C[(K+1)\log u_q+K^{1/4}u_q^{3/4}]\}+Cq$ with absolute $C$. It is used only as the model for the few-carrier gate (step 2b). Our version replaces its random-sphere direction count by Rademacher directions on block coordinates.
- **onesided_direction_entropy_upper.md.** $\operatorname{FDR}\le q\pi_0u/\sqrt{2\pi}+Cq(1+\sum_gw_g\log(1/w_g))$ in one-sided factor models. Its Steps 2–6 (group truncation, group cap, coupling shell, assembly) are adapted to the two-sided case in step 9. The two-sided shell lemma is proved there.
- **cx_block_extreme_window_lemma_r1_s2_critical_iid_background.md (approved counterexample).**
  - What it shows: a near-critical i.i.d. background has a realized count that performs a near-driftless walk, so per-cell return probabilities are of order one.
  - Consistency check: no step here uses a per-cell probability or a per-level anti-concentration bound. The background enters only through Gaussian averages over $x$ of the tracking set, weighted by the null's own factor $\zeta$, as in the sibling Step 10. Its i.i.d. background has loading $0$, so it is L-class, and the L-fiber lemma (step 3(b)) confines tracking within tilt distance $2K_q+101$ in every fiber; its random returns are absorbed by Lei's factor-two good event. Test T9 re-checks this numerically.
- **block_carrier_excess_lemma.md (draft there) and onesided_block_factor_sharp_upper.md (parked there).** Not used. Their stated obstruction is anti-concentration in finitely many extreme factor coordinates across arbitrarily many mixed-sign blocks. It is the same as our KEY core 2d (many heavy carriers) and our B6′ (exponentially many null blocks). Our attack on 2d differs from theirs:
  - it bounds a two-sided per-null tracking length, not a pooled one-sided level sum over carriers;
  - it uses deterministic blocking along the carrier's own coordinate, not a per-cell window or return probability.

**Library.** Searches for `anti-concentration`, `Kolmogorov Rogozin concentration function`, `monotone likelihood ratio tail ratio`, `Benjamini Hochberg level`, `Poisson binomial Bernstein`, `Gaussian BH two-sided` and `Littlewood Offord` returned no results. No library statement is cited.

## Plan

**Fixed notation.**
- $p(u)=2\overline\Phi(u)$; $\phi$ is the standard normal density; $\lambda=\phi/\overline\Phi$.
- For $0<q\le q_0\le2\overline\Phi(1)$: $U=p^{-1}(q)$, $t_k=qk/N$, $u_k=p^{-1}(t_k)$, $J=\lceil\sqrt U\rceil$, $K=K_q=8\log U$, $L=L_q=K+\sqrt U$, $\Delta_q=2K+1$.
- A *universal constant* $C$ is independent of $q,N,\theta,\Sigma$, the number of blocks, block sizes and loadings. Every $\eta(q)$ is a function of $q$ alone with $\eta(q)\to0$.
- Class $\mathfrak B$, $J_g$, $G_0$, $r_i=|a_i|$ and $\rho_r$ are as in plan_two_sided_exogenous_pivotal_blocks_20261105 (its `## Plan`, Part B).
- **Factor form for a null.** Fix $i\in J_g$ with $r=r_i\in(0,3/5]$. Put $\zeta=\operatorname{sgn}(a_i)Z_g$ and $x=(Z_h)_{h\ne g}\in\mathbb R^{G-1}$ with law $\gamma$.
  - For $\ell\ne i$ the atom $(\theta_\ell,\alpha_\ell,c_\ell,s_\ell)$ is:
    - $(\theta_\ell,\operatorname{sgn}(a_i)a_\ell,0,\sqrt{1-a_\ell^2})$ if $\ell\in B_g$;
    - $(\theta_\ell,0,a_\ell e_{g(\ell)},\sqrt{1-a_\ell^2})$ if $\ell\notin B_g$.
  - $\Pi_i=N^{-1}\sum_{\ell\ne i}\delta_{\text{atom}}$, $Y_z=\theta+\alpha\zeta+\langle c,x\rangle+s\varepsilon$ and $G_z(w)=\int\mathbb P(|Y_z|\ge w)\,d\Pi_i$ for $z=(\zeta,x)$.
- **Classes.** Put $b=r/U$ and $\tau=r/6$.
  - A: $|\alpha|\ge b$. These are block-$g$ members only.
  - L: $|\alpha|<b$ and $\alpha^2+|c|^2\le\tau^2$. These are block-$g$ members with small loading, and background coordinates with $|a_\ell|\le\tau$.
  - H: $|\alpha|<b$ and $\alpha^2+|c|^2>\tau^2$. These are exactly the background coordinates with $|a_\ell|>\tau$; they have $\alpha=0$ and $c=a_\ell e_h$.

  Write $G=G^A+G^L+G^H$. **$G^H_z$ does not depend on $\zeta$.**
- **Admissibility and types** (Lei's good event $A_{i,z}$ of (278), with constants $1/2$ and $3$).
  - Weights $w_{i,k}(z)=\mathbb P(R_i=k,A_{i,z}\mid Z=z)$ for $k>J$, and $\mathcal C_z=\{u_k:w_{i,k}(z)>0\}$, which satisfies (212).
  - $\mathcal W(z)=\{w\in\mathcal C_z:||\zeta|-rw|\le K\}$. A *tracking point* is a $z$ with $L\le|\zeta|\le U$ and $\mathcal W(z)\ne\varnothing$.
  - Types A, L, H: some $w\in\mathcal W(z)$ has $G^{\bullet}_z(w)\ge p(w)/(6q)$.
  - $t_A(x)$ and $t_L(x)$ are the infima of $|\zeta|$ over A-, respectively L-points in the fiber; $P_t=\{x:t_A(x)\ge t\}$; $I=[\max(L,rU-K),U]$.
  - $H^\sigma_t=\{x\in P_t:(\sigma t,x)\text{ is an H-point}\}$, $h^\sigma(t)=\gamma(H^\sigma_t)$, and $v_H(z)$ is the largest H-witness.
  - All of this is exactly the sibling notation (twosided_kfactor_sharp_upper, Steps 3–5), with $K=1+(G-1)$ factors.
- **Carriers.** For an H-point $z_1$ with witness $v_1=v_H(z_1)$ and a background block $h$, put
  $$
  m_h(z_1)=N^{-1}\sum_{\ell\in B_h,\ |a_\ell|>\tau}\mathbb P(|Y^{(\ell)}_{z_1}|\ge v_1),
  $$
  so $\sum_hm_h(z_1)=G^H_{z_1}(v_1)\ge p(v_1)/(6q)$, and $m_h$ depends on $z_1$ only through $x_h$.
  - For a witness level $v$ put $v^+=v+C_1v/U^2$, with $C_1$ the constant of the MLR lemma in 2c.
  - Block $h$ is *$\kappa$-light for $v$* if $|\{\ell\in B_h:|a_\ell|>\tau\}|\le\kappa\,Np(v^+)/q$, and *heavy for $v$* otherwise.
  - Fix $\kappa=\kappa_{q,r}:=(\log(U/r))^{-2}$. This depends on the null's loading $r$, as the classes already do through $\tau=r/6$.
  - $z_1$ is *light-dominated* if the blocks that are light for $v_1$ carry at least half of $G^H_{z_1}(v_1)$, and *heavy-dominated* otherwise.

### Part I — Replacement of B4 (execute first)

1. [x] **(D1, mandatory diagnostic; evidence only, not a proof step.)** Run tests T9–T12 before step 2. Use $q\in\{10^{-4},10^{-8},10^{-16}\}$, $r\in\{0.1,0.3,0.5\}$, Monte Carlo over $x$, and exact admissible sets from the mean counts. Report:
   - $\mathbb E_\gamma|T(X)|/((1-r)U)$;
   - the per-sign H-densities $\int_Ih^\sigma/\int_I\gamma(P_t)$;
   - for T11, the H-density restricted to heavy-dominated points.

   If some family has $\int_Ih^\sigma\ge(\frac12+c)\int_I\gamma(P_t)$ for one sign, with $c\ge0.1$ at all three $q$ and no decreasing trend, then:
   - record it as an H-KEY counterexample candidate (an obstruction to the route, not to the target);
   - try to prove the lower bound analytically along $q\downarrow0$;
   - if that succeeds, H-KEY is false: stop under the stop rule.

   Short local runs only, with at most seven workers; heavier runs go to the configured remote server.

2. [ ] **(H-KEY, KEY.)** There are $q_0>0$ and $\eta_H(q)\to0$ such that for every $q\le q_0$, every model in $\mathfrak B$, and every $i\in I_0$ with $r_i\in(0,3/5]$,
   $$
   \sum_{\sigma=\pm1}\int_Ih^\sigma(t)\,dt\le\int_I\gamma(P_t)\,dt+\eta_H(q)\,U,
   $$
   uniformly in $G$, block sizes, loadings, means and $N$. The sibling proves this with $\eta_H$ depending on $K=G$: Steps 8–10 give $\eta_K(1/2)U+2C'_q\phi(0)U+\Delta_q$ per sign. **H-KEY is the many-block version.** Sub-steps, in execution order:

   - 2a. [x] **(TR, routine-new, deterministic) Coordinate-carrier blocking, both signs.** Let $z_1=(\sigma t_1,x_1)$ be an H-point with $v_1=v_H(z_1)$. Let $h$ be a background block with $m_h(z_1)\ge\kappa\,G^H_{z_1}(v_1)$ for some $\kappa\in(0,1]$. Let $\varsigma\in\{\pm1\}$ maximize the oriented mass
     $$
     m^\varsigma_h=N^{-1}\sum_{\ell\in B_h,|a_\ell|>\tau}\mathbb P\big(|Y^{(\ell)}_{z_1}|\ge v_1,\ \varsigma\operatorname{sgn}(Y^{(\ell)}_{z_1})\operatorname{sgn}(a_\ell)\ge0\big)\ \Big(\ge\tfrac12m_h\Big).
     $$
     Then for every $\delta\ge C'(\kappa):=6\log(37/\kappa)/\sqrt U$, neither $(t_1+\Delta_q,\,x_1+\varsigma\delta e_h)$ nor $(-(t_1+\Delta_q),\,x_1+\varsigma\delta e_h)$ is a tracking point, provided $t_1+\Delta_q\le U$.

     *Proof to write out.*
     - Oriented atoms satisfy $|Y_{z'}|\ge v_1+\tau\delta\ge w:=v_1+\log(37/\kappa)/v_1$, using $\alpha=0$ and $rv_1\ge t_1-K\ge\sqrt U$. So $G_{z'}(w)\ge\kappa p(v_1)/(12q)$ at both signs of $z'$.
     - A witness $u'$ at height $t_1+\Delta_q$ has $ru'\ge rv_1+1$, so $u'>w$, and (212) gives $G_{z'}(w)\le3p(w)/q\le\frac3{37}\kappa\,p(v_1)/q$ by Lei (230).
     - This is the sibling Step 8 with $\vartheta=1$ and no direction count.

     (ii) *Optional (anti-hugging form).* Along $e_h$ with $x_{-h}$ frozen, the hug-extent staircase argument holds: on an $x_h$-interval of length $\Lambda/2$, the set of points whose hug extent is at least $\Lambda$ and whose carrier is $h$ has Lebesgue measure at most $Ct_0(1+U/(r\Lambda))$, with $t_0=C\log(1/\kappa)/U$. It may be used instead of the $(t,t+\Delta)$ pairing.

   - 2d. [ ] **(CU, KEY core) Many heavy carriers.** For heavy-dominated H-points, prove the blocking inequality
     $$
     (1-\eta(q))\,h^\sigma_{\rm hv}(t)+h^\sigma_{\rm hv}(t+\Delta_q)\le\gamma(P_t)+\eta(q)\quad\text{for all }t\in I,\ t+\Delta_q\le U,
     $$
     uniformly in the number of heavy blocks. Here $h^\sigma_{\rm hv}(t)=\gamma\{x\in P_t:(\sigma t,x)\text{ is a heavy-dominated H-point}\}$.

     What is known at planning:
     - 2a gives the per-carrier statement: for each $h$, the set $A^h_t$ of heavy-dominated H-points whose dominant heavy carrier is $h$ is separated from $T'_{t+\Delta_q}$ along every $e_h$-line, in the sense of the sibling Step 9 hypothesis.
     - Summing the per-$h$ inequalities fails. Any union argument must use model structure, for two reasons.
       - (a) With point-dependent directions the abstract implication is false: a Nikodym set of full measure has, through each of its points, a line meeting it only there.
       - (b) With coordinate directions the trivial overlap bound is $2dC'\phi(0)$, where $d$ is the number of active carriers.
     - Candidate structure, not checked:
       - each block's upper-tail part is nondecreasing and its lower-tail part nonincreasing in its own factor;
       - blocks are independent;
       - H-mass is $\zeta$-free;
       - the line is steep, $p(w+d)\le e^{-wd}p(w)$.

       Together these should force each $A^h_t$ to sit in an $e_h$-boundary layer of a single *monotone* set, whose Gaussian coordinate boundary is $O(1)$ by the Bernstein bound of 2c.

     Execution must prove CU or stop. Do not prove only the few-carrier case 2b and present it as CU.

   - 2b. [ ] **(Few-carrier gate, routine; reproduces sibling Steps 8–10 with Rademacher directions.)** Let $S$ be a fixed set of $d$ background blocks containing all heavy carriers that occur at heavy-dominated H-points. For $\xi\in\{\pm1\}^S$ put $\omega_\xi=d^{-1/2}\sum_{h\in S}\xi_he_h$.
     - Every H-atom in $S$ has $|\langle c,\omega_\xi\rangle|\ge\tau d^{-1/2}$. For every $z_1$ and $\xi$, $m_+(\xi)+m_-(\xi)$ equals the $S$-mass, so no direction is bad.
     - Heavy-dominated means the $S$-mass is at least $G^H/2$. So the better orientation carries at least $G^H/4$, which is the case $\kappa=1/2$ of 2a with the shift reduced by the factor $|\langle c,\omega_\xi\rangle|/|a_\ell|=d^{-1/2}$.
     - The sibling Steps 9–10 then give the inequality of 2d with $\eta=0$ and the additive term $2C'_d\phi(0)$, where $C'_d=6\sqrt d\,\log 74/\sqrt U$.
     - Hence $\int_Ih^\sigma_{\rm hv}\le\frac12\int_I\gamma(P_t)+C\sqrt{dU}+\Delta_q$.

     This proves CU whenever $d\le D_q:=U/(\log U)^2$. It is a gate only.

   - 2c. [ ] **(Light-domination, routine.)** There is $C$ such that, outside an event $\mathcal F$ in $x$ with $\gamma(\mathcal F)\le CU^{-2}$, all light-dominated H-points, over all fibers in $\mathcal F^c$ and both signs, have heights in one deterministic interval of length at most $2K+C$. Consequently $\sum_\sigma\int_Ih^\sigma_{\rm lt}\le4K+C+CU^{-1}$.

     Route:
     - Use Bernstein's inequality over independent blocks, for the H-atoms of the blocks that are light for $v$, at the levels $v$ and $v^+$. Take $v$ on a grid of $[U,(U+K)/r]$ with local spacing $\epsilon_0/v$, so that $p$ changes by a factor of at most $e^{2\epsilon_0}$ between neighbours. The grid has at most $CU^2/r^2$ points.
     - Each summand is at most $\kappa Np(v^+)/q$. So the relative error is at most $\frac1{24}$ at both levels, except with probability $e^{-c/\kappa}$ per grid point. Since $\kappa=(\log(U/r))^{-2}$, the union over the grid is at most $CU^{-2}$, uniformly in $r$.
     - Monotonicity of counts in $v$ covers the levels between grid points.
     - The light part's mean is a unit-variance mixture (each $a_\ell Z_h+s_\ell\varepsilon\sim N(0,1)$). Prove MLR rigidity:
       - (i) $\partial_u\log L_\theta(u)\ge c_1\log L_\theta(u)/u$ for $u\ge1$, where $L_\theta(u)=\mathbb P(|\theta+\varepsilon|\ge u)/p(u)$;
       - (ii) consequently, a mixture whose ratio to the line is at least $1/13$ at $v$ exceeds $4$ at $v^+=v+C_1v/U^2$.
     - Then the cutoff argument of the sibling Step 7(b) applies in every fiber of $\mathcal F^c$ at once, because the light part is $x$-free up to the error. Let $v_1$ be the witness of the shallowest light-dominated H-point. Then no fiber has a witness deeper than $v_1^+$, and $r(v_1^+-v_1)\le2C_1/U$.

     Uniformity in $r$ comes from $\kappa=(\log(U/r))^{-2}$ together with the grid count $CU^2/r^2$. Check it explicitly.

   - 2e. [ ] **(Assembly of H-KEY, routine given 2a–2d.)** H-points are light- or heavy-dominated. Integrate 2d as in the sibling Step 10(ii) to get $\int_Ih^\sigma_{\rm hv}\le\frac12\int_I\gamma(P_t)+\eta U$, and add 2c.

3. [ ] **(Fiber lemmas in $\mathfrak B$, routine; reproduce sibling Steps 5–7, adapting Lei Lemmas 4.5 and 4.6.)**
   - (a) A-fiber lemma: for every $x$ and every $t>t_A(x)+B_q$, at most one of $(\pm t,x)$ is a tracking point of any type, where $B_q=\frac{2K+2r^2}{1-r^2/U}+4\sqrt U$.
   - (b) L-fiber lemma: if $T^L(x)\ne\varnothing$, then every tracking point in the fiber has $|\zeta|\le t_L(x)+2K+101$.
   - (c) Measurability, as in the sibling Step 5.

   Check:
   - A-atoms are block-$g$ members with $c=0$, so $Y_{z_2}=Y_{z_1}+\alpha\sigma_1(t-t_1)$ in the fiber.
   - L-atoms include background coordinates with $|a_\ell|\le\tau$. In the fiber their mean is $\theta+a_\ell x_h$ and their variance is at least $1-\tau^2$, as the sibling's adjusted log-convexity requires.
   - The upper bound (212) is used only for the total $G$. The background count is nonnegative, which is the only property of the frozen background used here.
   - Replace the sibling's $K_q=\sqrt{8\log u}$ by $K=8\log U$ and check every largeness condition. Only $e^{-K^2/2}\le U^{-4}$, $K\le U/4$ and $\Delta_q=O(\log U)$ are used.

4. [ ] **(KB in $\mathfrak B$, routine given 2 and 3; sibling Step 10, pointwise count.)** For every model in $\mathfrak B$ and every $i$ with $r_i\in(0,3/5]$,
   $$
   \mathbb E_\gamma|T(X)|\le(1-r)U+\eta_H(q)U+C\sqrt U,\qquad T(x)=\{\zeta:(\zeta,x)\text{ tracking}\}.
   $$

5. [ ] **(B4″, per-null central bound, routine given 4 and Part II; sibling Steps 3, 4 and 11 together with Lei (205)–(206) and B4-a.)** For every model in $\mathfrak B$ and every $i\in I_0$,
   $$
   C_i(q):=\mathbb E\Big[\sum_{k=1}^N\rho_{r_i}(u_k,Z_{g(i)})\,\mathbb P(R_i=k\mid Z)\,\mathbf 1\{|Z_{g(i)}|\le U\}\Big]\le\frac U{2\sqrt{2\pi}}+\eta_4(q)U .
   $$
   It covers $k\le J$ (B2), the bad event (B3), $r_i\in\{0\}\cup(3/5,1]$ (B4-a), and $0<r_i\le3/5$ (step 4 with (205)–(206) and $(1-r)/\sqrt{1-r^2}\le1$).

### Part II — Proved steps re-included from plan_two_sided_exogenous_pivotal_blocks_20261105 (re-check against its `## Progress`)

6. [ ] **(Re-check, routine.)** Each statement below is re-verified from that plan's `## Progress` and copied into the final proof.
   - **P0.** (BH1) If $\widehat k\ge1$ then $R_q=n_x(t_{\widehat k})=\widehat k$. (BH2) $x\le x'$ entrywise implies $\widehat k_q(x)\ge\widehat k_q(x')$, with $N$ fixed.
   - **A0.** If $I_0=\varnothing$ then $\operatorname{FDR}=0$. If $N=1$ then $\operatorname{FDR}\le q$. For $q\le2\overline\Phi(1)$, $U^2\le2\log(2/q)$, hence $qU/(2\sqrt{2\pi})\le\frac{1+o(1)}{2\sqrt\pi}q\sqrt{\log(1/q)}$.
   - **A1 (G1).** Items (a)–(f) of that plan's step 2, which hold for every admissible $(N,\theta,\Sigma)$. In particular
     $$
     \mathbf 1\{i\in\mathcal R_q\}/(R_q\vee1)=(q/N)\,a(T_i;\tau_i(T_i,Y_i))
     $$
     pointwise, $\mathbb E\,a(T_i;g(Y_i))=1$ for Borel $g$, and $\operatorname{FDR}=q\pi_0+(q/N)\sum_{i\in I_0}\Delta_i$ exactly. Correction (e): $f^\pm_{i,y}$ is piecewise constant with at most $2N(N-1)$ jumps and agrees with a right-continuous step function off a finite set.
   - **A2.** (i) The exact branch formula $\Psi(f)=\sum_k[\min\{f_k,p(s_k)\}-p(s_{k+1})]_+/f_k$. The telescoping identity $\Psi(f)-1=\sum_k\big[\min\{p_k,f_k\}/f_k-\min\{p_k,f_{k-1}\}/f_{k-1}\big]$. (ii) If $f$ is nondecreasing then $\Psi(f)\le1$. (iii) The jump bound.
   - **A4 (i)–(iii).** The reflected-floor and subset-floor lemmas, as stated in that plan's step 4.
   - **B1.** In $\mathfrak B$, $\frac qN(1+\Delta_i)=\frac qN\mathbb E\sum_k\rho_{r_i}(u_k,Z_g)\mathbb P(R_i=k\mid Z)$, and $\sum_g\mathrm{FDR}_g(Z)=\mathbb E[\mathrm{FDP}\mid Z]\le1$.
   - **B2.** $\frac qN\sum_{i\in I_0}\mathbb E\sum_{k\le J}\rho\,\mathbb P(R_i=k\mid Z)\le\pi_0qJ$.
   - **B3.** $\mathbb P(A^c_{i,Z}\mid Z)\le\delta_J=3e^{-(\log2-1/2)J}/(1-e^{-(\log2-1/2)})$ and $C_q:=\sup_r\int_{-U}^U\phi\sup_{u\ge U}\rho_r\le\frac12+U/\sqrt{2\pi}$. Hence the bad-event part is at most $C\pi_0q$.
   - **B4-a.** For $r_i\in[3/5,1)$ the good-event central part is at most $\frac12+U/(2\sqrt{2\pi})$. For $r_i=1$ it is $0$; for $r_i=0$ it is at most $1$.
   - **Lei Lemma 4.4.** (205) and (206), recorded as B4-c there and not yet rechecked line by line. Re-check them here from pp. 64–65 of `lei2026_gaussian_bh`.

### Part III — Rest of gate G2

7. [ ] **(Two-sided shell lemma, routine.)** For $r\in[0,1]$, $u'>0$ and $y\in\mathbb R$: $\rho_r(u',y)\le2/p(|y|)$. Hence, for $U\le U'$,
   $$
   \int_{U<|y|\le U'}\phi(y)\sup_{u'\ge U}\rho_r(u',y)\,dy\le2\log\frac{p(U)}{p(U')} .
   $$
   Proof to write out.
   - Take $y\ge0$. First, $\mathbb P(|ry+s\varepsilon|\ge u')\le2\,\mathbb P(ry+s\varepsilon\ge u')$.
   - Second, $\overline\Phi(y)\,\mathbb P(ry+s\varepsilon\ge u')\le\mathbb P(r\zeta+s\varepsilon>u')=\overline\Phi(u')$, by the coupling of the sibling Lemma 6′.
   - So $p(y)\,\mathbb P(|ry+s\varepsilon|\ge u')\le2p(u')$. Then integrate $\lambda$.
   - The case $r=1$ is direct.

8. [ ] **(Group cap, routine; sibling entropy Steps 2–3.)** In $\mathfrak B$, let $J'_g$ be the loaded nulls of block $g$, $w_g=|J'_g|/N$, and $U_g=p^{-1}(qw_g)\ge U$. Then pointwise
   $$
   \sum_{i\in J'_g}X_i\le\mathbf 1\{|Z_g|>U_g\}+\sum_{i\in J'_g}X_i\mathbf 1\{|Z_g|\le U_g\},
   $$
   with $\mathbb P(|Z_g|>U_g)=qw_g$. No union bound over blocks is used.

9. [ ] **(B5-ent, routine given 5, 7 and 8.)** For every model in $\mathfrak B$ and $q\le q_0$,
   $$
   \operatorname{FDR}\le q\pi_0+q\pi_0\Big(\frac U{2\sqrt{2\pi}}+\eta_4(q)U\Big)+2q\sum_gw_g\log\frac1{w_g}\le q\pi_0\Big(1+\frac U{2\sqrt{2\pi}}+\eta_4U\Big)+2q\Big(\log G_0+\frac1e\Big).
   $$
   - Unloaded nulls contribute at most $q/N$ each, by exact uniformity.
   - For a loaded null, the part on $\{|Z_g|\le U_g\}$ is at most $(q/N)[C_i(q)+2\log(1/w_g)]$, by B1, step 5 and step 7.
   - This is sharp whenever $\log G_0=o(\sqrt{\log(1/q)})$. It supersedes the old B5. Record it as a separate draft asset candidate; it is not the target.

10. [ ] **(B6′, KEY; actual-FDR statement.)** There are $q_0$ and $\eta_6(q)\to0$ such that every model in $\mathfrak B$ satisfies
    $$
    \operatorname{FDR}\le(1+\eta_6(q))\frac{qU}{2\sqrt{2\pi}}+Cq .
    $$
    By step 9 it suffices to treat $\sum_gw_g\log(1/w_g)\ge\eta U$: exponentially many null blocks, whose factor maximum is of order $\sqrt{2\log G_0}\gg U$.
    - In this regime the nulls in blocks with $|Z_g|>U$ must be controlled jointly. The shell cost $2\log(1/w_g)$ is then of order $U$ per null.
    - Carry over the old plan's B6 notes (a)–(d): no $G_0q$ or $\pi_0$ factor in the error; the T6 warning that central and tail parts must be treated jointly; the tracked-set joint measure suggestion; the refutation standard.
    - This is the two-sided form of the sibling's parked obstruction. A violation is a **refutation candidate** for the target and must meet the project's refutation standard.

11. [ ] **(G2, routine from 9 and 10.)** For $q\le q_0$ and every model in $\mathfrak B$, $\operatorname{FDR}\le(1+\eta_{G2}(q))qU/(2\sqrt{2\pi})+Cq$.

### Part IV — Arbitrary covariance (unchanged in substance from the failed plan's Part C; restated with $o(U)$ errors)

12. [ ] **(C0, routine.)** Reductions.
    - (a) The FDR is continuous along $(1-\eta)\Sigma+\eta I$ as $\eta\downarrow0$, so positive-definite $\Sigma$ suffice, with constants independent of $\eta$.
    - (b) Latent form $T=\theta+VW$ with unit rows $v_j$. For null $i$, $c_i=(Vv_i)_{-i}$ and $Y_i=(VP_{v_i^\perp}W)_{-i}$.

13. [ ] **(C1, routine.)**
    - (a) Private-noise decompositions satisfy $s^2\le1-R_i^2$, which vanishes under duplication (obstruction (1) of idea_0d2e69e0ba3b).
    - (b) The pathwise pivotal form $\operatorname{FDR}-q\pi_0\le\mathbb E[V^{\rm piv}/(R\vee1)]\le\operatorname{FDR}$, with $V^{\rm piv}=\sum_{i\in\mathcal R\cap I_0}\kappa_i$ as defined in the old plan's step 14.

14. [ ] **(C2, KEY.)** Multiplicity gate. For every model in $\mathfrak B$ and multiplicities $n\in\{1,2,\dots\}^N$, the model that repeats coordinate $j$ exactly $n_j$ times satisfies G2, with possibly larger universal constants and another $\eta(q)\to0$.
    - Uniform multiplicities follow from A1(f).
    - Test T2 first.
    - Note: copies share private noise, so the class split by factor loadings must treat heavy multiplicities as weighted, conditionally deterministic coordinates. Those are H- or L-atoms of the multiplied model.

15. [ ] **(C3 = G3, KEY.)** Global pivotality. For all admissible $(N,\theta,\Sigma)$ and $q\le q_0$,
    $$
    \frac qN\sum_{i\in I_0}\Delta_i\le\mathfrak S(q)+\eta_3(q)qU+C_3q,\qquad\mathfrak S(q)=\sup_{\mathfrak B^{\rm mult}}(\operatorname{FDR}-q\pi_0).
    $$
    The direct form $(q/N)\sum_i\Delta_i\le(1+\eta)qU/(2\sqrt{2\pi})+Cq-q\pi_0$ also completes the plan.
    - The mandatory properties (R1)–(R5) of the old plan's step 16 apply verbatim. Here (R2) means "no supremum over admissible thresholds given an over-revealing $\sigma$-field", and (R3) means "no covariance certificate, LP or transport ledger".
    - Also: **(R6)** no per-cell probability or per-level anti-concentration bound against an arbitrary background (the sibling counterexample).
    - Route: C3.1 writes steps 2–5 as line functionals of $\frac12\sum_\sigma(\Psi(f^\sigma_{i,y})-1)$, listing the block-specific inputs:
      - (F1) concentration given the line position;
      - (F2) $c_{ij}=a_ia_j$;
      - (F3) independence across blocks;
      - (F4) coordinate alignment of H-atoms with $\alpha=0$ (steps 2a–2d).

      Output one candidate line inequality $L^*$ that passes T1–T12. C3.2 proves $L^*$ for arbitrary $\Sigma$.

16. [ ] **(C4, routine.)** Assembly, as in Verification.

**Test families** (exact finite models; numerics are evidence only).
- T1–T8: as defined in plan_two_sided_exogenous_pivotal_blocks_20261105 (its `## Plan`, test list). T1 is the Lei two-sided lower construction, which every bound must match. T3 is the single-null staircase. T6 is $\lceil q^{-K}\rceil$ T1-type blocks. T7 is the fixed-$q$ common-gate family. T8 has a loading-one staircase background block.
- **T9 (sibling counterexample, two-sided).**
  - Block $g$: one null with loading $r$ and $\lfloor10\sqrt b\rfloor$ alternatives with loading $1$ and mean $1$.
  - Background: $M$ i.i.d. $N(\vartheta,1)$ coordinates with $\vartheta=\kappa U/\sqrt b$, scaled so that the mean count at rank $b$ is $b-\sqrt b$, plus far-negative fillers.
  - Expected: no H-points; tracking confined by the L-fiber lemma; per-null cost at most $U/(2\sqrt{2\pi})+O(K)$.
- **T10 (one heavy carrier).** T8 with mirror (both-sign) and one-sided staircases tuned to hug at relative level $1-\eta/2$ for $Z_2\approx0$. This is covered by the sibling with $K=2$; it checks steps 2a and 2b.
- **T11 (many heavy carriers; the CU stress test).** Take $d$ background blocks, $d\in\{U,U^2,e^{U}\}$ as far as computable.
  - Each is a loading-one staircase scaled to carry the whole BH line on its own level window when its factor is near $w^*$, with windows overlapping.
  - The dominant carrier is then the block with the extreme factor, and its identity varies with $x$.
  - Compare the H-density per sign with $1/2$.
- **T12 (light blocks).** Many small staircase blocks (LLN regime), plus a rigid unit-variance part with a compensating heavy block. This checks steps 2c and 2a.

**Stop rule (failure condition).**
- Execute the steps in the listed order. Within step 2: 2a, then 2d, then 2b, 2c, 2e.
- A routine step found false is a planning error. Record it with its counterexample, every hypothesis checked, and stop.
- **Execution stops at the first KEY step (2d, i.e. H-KEY; 10; 14; 15) whose displayed inequality is not proved with universal constants and an $\eta(q)\to0$ depending on $q$ only.** On stopping:
  1. Set this plan to `failed`.
  2. Under `## Failure`, state the exact inequality not proved. Name the parameter that breaks uniformity: number of heavy carriers, their factor coordinates, block sizes, loadings, $\theta$, $N$, $G$ or $G_0$.
  3. Record any admissible model violating the inequality, with every hypothesis checked: finite $N$, unit-diagonal PSD $\Sigma$, nulls exactly $\theta_i=0$, largest-rank BH, the $q$-range used. State whether the violation is asymptotic or only at fixed $q$.
     - Violations of H-KEY, KB or B4″ are obstructions to this route, not statements about the FDR.
     - Violations of B6′, G2, C2 or the direct form of C3 concern actual FDR. They are reported only as **refutation candidates** under the project's standard, never as proved.
  4. Keep all completed steps as Progress and leave the target asset untouched.
- **A failed plan is not a falsification** of the target or the conjecture.
- Prohibited repairs:
  - adding $\pi_0$, $G_0$, $\log N$, $\log G$ or $d$ factors to error terms;
  - restricting the class after the fact, for example to $d\le D_q$ carriers;
  - enlarging the leading constant;
  - letting $q_0$ depend on $N$, $G$ or $\Sigma$;
  - restating an unproved inequality (CU, B6′, C3) as an assumption.

  A weakened statement, such as the gates of 2b and 9, may be recorded only as a separate idea or draft asset.

## Progress

Execution of 2026-11-05 (third attempt; the two earlier attempts left no record). Steps are written here in execution order as they are established; a box in `## Plan` is ticked only for a step whose complete argument appears below. Notation is that of `## Plan` (Fixed notation). Throughout, $p(w)=2\overline\Phi(w)$ and the elementary tail inequality
$$
p(v+\delta)\le e^{-v\delta}p(v)\qquad(v\ge0,\ \delta\ge0)\tag{M2}
$$
is used; it follows from $\phi(s+\delta)=\phi(s)e^{-s\delta-\delta^2/2}\le\phi(s)e^{-v\delta}$ for $s\ge v$, integrated over $s\ge v$. This is Lei's (230).

### Step 2a (coordinate-carrier blocking, both signs): proved, with one explicit proviso

**Statement proved.** Let $U\ge4$. Let $z_1=(\sigma t_1,x_1)$ be an H-point with H-witness $v_1=v_H(z_1)$, let $h\ne g$ be a background block, and let $\kappa\in(0,1]$ satisfy $m_h(z_1)\ge\kappa\,G^H_{z_1}(v_1)$ and
$$
r\log(37/\kappa)<U .\tag{2a.0}
$$
Let $\varsigma\in\{\pm1\}$ maximize $m^\varsigma_h$ (defined in `## Plan`, 2a). Then for every $\delta\ge C'(\kappa)=6\log(37/\kappa)/\sqrt U$ and both $\sigma'\in\{\pm1\}$, the point $z'=(\sigma'(t_1+\Delta_q),\,x_1+\varsigma\delta e_h)$ is not a tracking point (of any type).

*On (2a.0).* It holds for $\kappa=\kappa_{q,r}=(\log(U/r))^{-2}$ and for every $\kappa\ge1/2$, uniformly in $r\in(0,3/5]$, as soon as $U\ge4$. For $\kappa\ge1/2$: $r\log(37/\kappa)\le\frac35\log74<2.6<U$. For $\kappa_{q,r}$: $f(r)=r\log37+2r\log\log(U/r)$ has $f'(r)=\log37+2\log\log(U/r)-2/\log(U/r)>0$ on $(0,3/5]$ because $\log(U/r)\ge\log(5U/3)\ge1.89$ there; so $f(r)\le f(3/5)=\frac35\log37+\frac65\log\log(5U/3)$, which is $<2.95$ at $U=4$ and grows slower than $U$ (derivative of $U-f(3/5)$ is $1-\frac{6}{5U\log(5U/3)}>0$). The plan's two uses of 2a (2b with $\kappa=1/2$, 2d/2c with $\kappa_{q,r}$) are therefore covered without any dependence on $G$, block sizes, $N$ or $\theta$.

**Proof.** (i) *Orientation.* For an H-atom $\ell\in B_h$ (so $|a_\ell|>\tau=r/6$, $\alpha_\ell=0$, $c_\ell=a_\ell e_h$), $Y^{(\ell)}_z=\theta_\ell+a_\ell x_h+s_\ell\varepsilon_\ell$ does not involve $\zeta$. The two events $E_\pm=\{|Y^{(\ell)}_{z_1}|\ge v_1,\ \pm\operatorname{sgn}(Y^{(\ell)}_{z_1})\operatorname{sgn}(a_\ell)\ge0\}$ cover $\{|Y^{(\ell)}_{z_1}|\ge v_1\}$, so $m^+_h+m^-_h\ge m_h$ and the maximizing orientation has $m^\varsigma_h\ge m_h/2\ge\kappa G^H_{z_1}(v_1)/2\ge\kappa p(v_1)/(12q)$, the last step by the definition of the H-witness, $G^H_{z_1}(v_1)\ge p(v_1)/(6q)$.

(ii) *Deterministic gain along $e_h$, at both signs.* Fix $\ell$ and a noise value $\varepsilon_\ell$ in $E_\varsigma$. Since $|Y^{(\ell)}_{z_1}|\ge v_1\ge U>0$, $\operatorname{sgn}(Y^{(\ell)}_{z_1})=\varsigma\operatorname{sgn}(a_\ell)\ne0$. At $z'$ (either sign $\sigma'$) the same noise gives $Y^{(\ell)}_{z'}=Y^{(\ell)}_{z_1}+\varsigma\delta a_\ell$, and the increment has the sign of $Y^{(\ell)}_{z_1}$, so
$$
|Y^{(\ell)}_{z'}|=|Y^{(\ell)}_{z_1}|+|a_\ell|\delta\ge v_1+\tau\delta\ge v_1+\frac{r\log(37/\kappa)}{\sqrt U}\ge v_1+\frac{\log(37/\kappa)}{v_1}=:w ,
$$
where $\tau C'(\kappa)=r\log(37/\kappa)/\sqrt U$ and, since $v_1\in\mathcal W(z_1)$ and $z_1$ is a tracking point, $rv_1\ge|\zeta_1|-K=t_1-K\ge L-K=\sqrt U$. Hence $\{|Y^{(\ell)}_{z'}|\ge w\}\supseteq E_\varsigma$ for every oriented H-atom of block $h$, and
$$
G_{z'}(w)\ge G^H_{z'}(w)\ge N^{-1}\sum_{\ell\in B_h,\ |a_\ell|>\tau}\mathbb P(E_\varsigma)=m^\varsigma_h\ge\frac{\kappa\,p(v_1)}{12q}\qquad\text{for both }\sigma'.\tag{2a.1}
$$

(iii) *Any witness at height $t_1+\Delta_q$ lies above $w$.* Suppose $z'$ is a tracking point with witness $u'\in\mathcal W(z')\subseteq\mathcal C_{z'}$. Then $|t_1+\Delta_q-ru'|\le K$ gives $ru'\ge t_1+\Delta_q-K=t_1+K+1$, while $rv_1\le t_1+K$; so $u'\ge v_1+1/r$. By (2a.0) and $v_1\ge U$, $\log(37/\kappa)/v_1\le\log(37/\kappa)/U<1/r$, hence $U\le v_1<w<u'$.

(iv) *Contradiction with (212).* Since $u'\in\mathcal C_{z'}$ and $U\le w<u'$, (212) gives $G_{z'}(w)\le3p(w)/q$. By (M2) with $v=v_1$ and $\delta=\log(37/\kappa)/v_1$, $p(w)\le e^{-\log(37/\kappa)}p(v_1)=\frac{\kappa}{37}p(v_1)$. Thus $G_{z'}(w)\le\frac{3\kappa}{37}\frac{p(v_1)}q<\frac{\kappa}{12}\frac{p(v_1)}q$, because $3\cdot12=36<37$. This contradicts (2a.1). So $z'$ is not a tracking point. (If $t_1+\Delta_q>U$ the conclusion is trivial, since tracking points have $|\zeta|\le U$.) $\square$

*What was used.* Only: the factor form of block models (H-atoms are $\zeta$-free with $c_\ell=a_\ell e_h$), the definitions of tracking point, $\mathcal W$, H-witness, the bound (212) satisfied by the true admissible set $\mathcal C_{z'}$, and (M2). No constant depends on $G$, block sizes, loadings, $\theta$ or $N$. This is the sibling Step 8 (twosided_kfactor_sharp_upper, same folder as in `## Adapted from`) with the random direction $\omega$ replaced by the carrier's own axis $e_h$, so $\vartheta=1$ and no direction count enters; the sibling's event "$\varsigma\operatorname{sgn}(Y)\langle c,\omega\rangle\ge\vartheta|c|$" becomes "$\varsigma\operatorname{sgn}(Y)\operatorname{sgn}(a_\ell)\ge0$", and its $|c|\ge r/7$ becomes $|a_\ell|>\tau=r/6$.

### Step 1 (D1 diagnostic): run; evidence only

*Deviation forced by the constants.* With the plan's $K=8\log U$ and $L=K+\sqrt U$ one has $L>U$ for all three prescribed levels ($U\approx3.9,5.7,8.3$ at $q=10^{-4},10^{-8},10^{-16}$), so the tracking region $[L,U]$ and $I$ are empty and every diagnostic quantity is $0$. The runs therefore use a reduced tilt window $K\in\{0.5,1\}$ and $I=[rU-K,U]$, which mimics the asymptotic regime $K/U\to0$; the $K$-dependence of the results (below) measures the window inflation $2K/|I|$. Everything is computed from **mean counts** (loading-one atoms are deterministic given $Z$): the admissible set is the outer set of (212), $\{w\ge U:G_x(w)\ge p(w)/(2q),\ G_x(v')\le3p(v')/q\ \forall v'\in[U,w)\}$, on a level grid with step $0.25$ in $\log p$ from $U$ to $(U+K)/r$; types use $G^\bullet\ge p(w)/(6q)$; $t$ runs over a $60$-point grid of $I$; $x$ is Monte Carlo ($150$–$300$ samples). The null's block is the null alone in T10–T12, so $\gamma(P_t)=1$ and $h^+=h^-$. Reported: per-sign H-density $\int_Ih^\sigma/\int_I\gamma(P_t)$; the plan's threshold for a counterexample candidate is $\ge0.6$.

- **T11 (direct).** $d\in\{U,U^2,e^U\}$ identical loading-one blocks with the mean-count staircase $n_h(s)=\#\{\ell\in B_h:\theta_\ell\ge s\}=c\,Np(s+w^*)/q$ on $s\in[w_a-w^*,(U+K)/r-w^*]$, $w^*=\overline\Phi^{-1}(1/d)+\text{off}$, scale $c\in\{1,0.3,0.1\}$, off $\in\{-1,\dots,2\}$, and $w_a=\max(U,p^{-1}(q/(cd)))$ so that the blocks fit into $N$ coordinates. Maximum over $(c,\text{off})$ of the per-sign H-density, $K=0.5$: $q=10^{-8}$: $0.19$–$0.43$ ($r=0.1,0.3,0.5$); $q=10^{-16}$: $0.13$–$0.30$. With $K=1$ the values rise by about $0.17$ at $q=10^{-8}$ (window inflation). Decreasing in $q$. No candidate.
- **T11-EV (extreme-value form, the CU stress test).** Same blocks with $d=1/\overline\Phi(w^*)$ for $w^*/U\in\{0.5,\dots,1.5\}$, that is $d=e^{11}$ to $e^{81}$: only the top $200$ factors are sampled, exactly in law through $x_{(j)}=\overline\Phi^{-1}(E_j/d)$ with $E_j$ the arrival times of a unit Poisson process, and the remaining blocks enter through their mean count. $q=10^{-16}$, $K=0.5$: per-sign density $0.29$–$0.44$ ($r=0.5$), $0.30$–$0.37$ ($r=0.3$); within $I$, $h(t)$ reaches $0.9$–$1.0$ on one quartile (the free level at the staircase bottom $w_a$, where no shallower level constrains) and is $\le0.4$ elsewhere. No candidate for H-KEY.
- **T10 (one heavy carrier).** $d=1$, $w^*=0$, scale $1-\eta/2$, one-sided and mirrored staircases, $q=10^{-8}$: $0.20$–$0.45$, with $h=1$ on the bottom quartile only (the level $U$ has no shallower competitor).
- **T12 (light blocks).** $400$ blocks with loading $0.9$ carrying $(1-\eta)$ of the quantile staircase plus one heavy loading-one block at scale $\eta=0.2$: density $0.24$–$0.34$, every H-point light-dominated, all heights in the bottom quartile, as 2c predicts.
- **T9.** Has no H-atoms (loading $0$ background), so $h\equiv0$ by construction; it tests only the fiber lemmas of step 3, which were not reached.

**Pointwise test of the 2d display (added).** In T11-EV with $r=0.5$, $K=0.5$, $\Delta_q=2K+1$, $c=1$, the maximum over $t$ of $h(t)+h(t+\Delta_q)$ (the left side of 2d with $\eta=0$; right side $\gamma(P_t)+\eta=1+\eta$):

| $q$ | $w^*/U$ | $w_a$ | constants $(1/2,3)$ | $(0.7,1.3)$ | $(0.9,1.1)$ |
|---|---|---|---|---|---|
| $10^{-16}$ | $0.6$ | $9.93$ | $1.167=0.91+0.26$ | $0.887$ | $0.813$ |
| $10^{-16}$ | $0.75$ | $10.62$ | $1.293=0.98+0.32$ | $0.957$ | $0.870$ |
| $10^{-16}$ | $0.9$ | $11.41$ | $1.340=1.00+0.34$ | $1.030$ | $0.967$ |
| $10^{-30}$ | $0.6$ | $13.64$ | $1.183=0.92+0.26$ | $0.903$ | $0.820$ |
| $10^{-30}$ | $0.75$ | $14.60$ | $1.333=0.99+0.35$ | $0.993$ | $0.900$ |
| $10^{-30}$ | $0.9$ | $15.69$ | $1.353=1.00+0.35$ | $1.043$ | $0.980$ |

The first term is the free level near $w_a$ (height $t\approx rw_a$), the second is frozen-regime hugging by the extreme block at level $\approx(t+\Delta_q)/r$. The excess over $1$ does not decrease from $U=8.3$ to $U=11.5$. With the admissibility constants sharpened to $1\pm\epsilon$ the sums drop to $0.81$–$1.04$ (above $1$ only at $(0.7,1.3)$, $w^*/U=0.9$, by $0.03$–$0.04$; at $(0.9,1.1)$ always below $1$, and there the maximum is attained where $h(t)=0$, that is, it is a single free-level band, not a double witness). Interpretation in `## Failure`.

## Failure

Execution stopped at the KEY step 2d (the core of H-KEY, step 2), under the stop rule. Steps 2b, 2c, 2e, 3–16 were not attempted because they come after 2d in the plan's order.

**Inequality not proved.** For heavy-dominated H-points,
$$
(1-\eta(q))\,h^\sigma_{\rm hv}(t)+h^\sigma_{\rm hv}(t+\Delta_q)\le\gamma(P_t)+\eta(q)\qquad(t\in I,\ t+\Delta_q\le U),
$$
with $\eta(q)\to0$ depending on $q$ only and uniformly in the number of heavy carriers.

**Parameter that breaks uniformity.** The number $d$ of heavy background blocks when the identity of the dominant carrier varies with $x$. Two separate facts, both uniform in everything except $d$:

1. *The (212)-only route cannot work.* Every handle the plan gives on the true admissible set $\mathcal C_z$ is the outer condition (212) with Lei's constants $1/2$ and $3$ (step 2a uses nothing else, and the sibling Steps 9–10 use nothing else). For the sets defined by (212) itself the display is false: in the extreme-value family of the D1 table (identical loading-one staircase blocks, $d=1/\overline\Phi(w^*)$, the null alone in its block, so $\gamma(P_t)=1$) the left side with $\eta=0$ reaches $1.17$–$1.34$ at $q=10^{-16}$ and $1.18$–$1.35$ at $q=10^{-30}$, with no decrease in $U$. Mechanism, checked by hand against the numbers: the extreme block's factor $x_{(1)}$ has density $\approx e^{-1}\sqrt{2\log d}$ near $w^*$, and its count ratio at level $v$ is $\approx e^{v(x_{(1)}-w^*)}$; the (212) window $[1/2,3]$ then admits deep witnesses on a set of $x$ of measure $\approx e^{-1}\log6\cdot w^*/v$ (observed $0.26$–$0.35$ at $v\approx(t+\Delta_q)/r$), while at the staircase bottom $w_a$ (forced by realizability $c\,d\,p(w_a)\le q$) no shallower level constrains and $h\approx1$ on a band of width $2K$ around $t=rw_a$. So an argument that only uses (212) proves a false statement for these sets, hence cannot prove the display.
2. *No union mechanism over carriers.* 2a gives, for each carrier $h$, separation of $A^h_t$ from $T'_{t+\Delta_q}$ along $e_h$, and the sibling's one-dimensional lemma gives $\gamma(A^h_t)+\gamma(T'_{t+\Delta_q})\le\gamma(P_t)+2C'\phi(0)$ for each $h$ separately; the sum over $h$ carries the factor $d$. The plan's candidate structure, "each $A^h_t$ sits in an $e_h$-boundary layer of one monotone set whose Gaussian coordinate boundary is $O(1)$", is false as stated: $M=\{x:\max_hx_h\ge c\}$ is monotone, and the union over $h$ of its $e_h$-boundary layers of width $\delta$ is $\{c\le\max_hx_h<c+\delta\}$, of Gaussian measure $\approx e^{-1}\delta\sqrt{2\log d}$, unbounded in $d$; for $\delta=C'(\kappa)\asymp\log\log U/\sqrt U$ this exceeds $1$ as soon as $\log d\gtrsim U/(\log\log U)^2$, which block models allow ($d\le N$ is the only constraint).

**Configuration (route obstruction only).** $\mathfrak B$-model: block $g=\{i\}$ with $a_i=r=1/2$, $\theta_i=0$; $d=1/\overline\Phi(w^*)$ background blocks of loading one (unit-diagonal PSD, singular inside blocks, allowed) whose members have means $\theta_\ell=u-w^*\ne0$ for $u$ on the quantile staircase of $[w_a,(U+K)/r]$ (mean-count profile $n(s)=Np(s+w^*)/q$; a finite $N$ realizes it to any precision, and loading-one counts given $Z$ are deterministic, so mean counts are exact counts); BH with the largest qualifying rank (the derivation of (212) assumes exactly this); $q\in\{10^{-16},10^{-30}\}$, $K=0.5$. The violation is of the **(212)-outer form** of the display, in the mean-count evaluation, and is asymptotic in the sense that it does not decrease from $U=8.3$ to $U=11.5$ and the mechanism is $U$-free. It is **not** a violation of the display for the true sets: for this deterministic background the true $\mathcal C_z$ is the single BH rank (the shallowest up-crossing), the deep witnesses disappear, and the sum is about $0.9$; the sharpened constants in the table show the same. It says nothing about the FDR: H-KEY, KB and B4″ are per-null tracking bounds of this route. **No refutation candidate.** The integrated H-densities of all families stay below $0.45$ per sign at $K=0.5$, so H-KEY itself (the integrated statement) is numerically plausible; it is simply not provable by the plan's pointwise mechanism.

**Established before the stop (kept in `## Progress`).** (M2); step 2a in full, with the explicit proviso (2a.0) that the plan's two uses satisfy; the D1 diagnostics with the pointwise table.

**What a proof would need.** (i) Replace Lei's constants in the good event by $1\pm\epsilon(q)$ for ranks $k>J$ (the rank lemma gives $\mathbb P(\mathcal A^c)\le\sum_{k>J}2e^{-c\epsilon^2k}$, harmless for $\epsilon=U^{-1/8}$, $J=\lceil\sqrt U\rceil$, with B3 redone); the table shows this reduces the extreme-value sums from $1.17$–$1.35$ to $0.81$–$1.04$, and at $(0.9,1.1)$ no double witness remains. (ii) Prove a "no double witness" bound, $\gamma\{x\in P_t:(\sigma t,x)\text{ H-point},\ (\sigma(t+\Delta_q),x)\text{ tracking}\}\le\eta(q)$, which gives the display directly through $\gamma(A)+\gamma(T')=\gamma(A\cup T')+\gamma(A\cap T')$ and needs no union over carriers. Heuristically it holds in the frozen extreme-value regime with error $O(\epsilon)$ (the total ratio at $w_1$ must lie in $[1-\epsilon,1+\epsilon]$, a window of Gumbel length $O(\epsilon)$ for the extreme factor) and in the self-averaging regime by the MLR rigidity of the $x$-averaged unit-variance mixture; the mixed regime, non-identical blocks and the A/L share of the total are open. This is recorded as a separate idea (idea_c270c9b9e4f3), not as a repair of this plan. A failed plan is not a falsification of the target.

## Verification

How the steps give the target, and what a fresh referee checks, in order.

1. **Part II (step 6).** Check each listed statement against the `## Progress` section of plan_two_sided_exogenous_pivotal_blocks_20261105. That section has complete proofs of P0, A0, A1, A2, A4, B1, B2, B3 and B4-a. Check Lei Lemma 4.4 separately against `lei2026_gaussian_bh` pp. 64–65. No other source is needed.
2. **Step 2a.** Check the two inequalities: $|Y_{z'}|\ge w$ for oriented H-atoms at both signs, using $\alpha=0$ and $rv_1\ge\sqrt U$; and $u'>w$ for any witness at height $t_1+\Delta_q$. Then check $3p(w)/q<\kappa p(v_1)/(12q)$ from $p(v+d)\le e^{-vd}p(v)$.
3. **Step 2d (KEY).** Check that the inequality holds for every heavy-dominated H-point configuration, with constants independent of the number of blocks. Reject any proof that:
   - sums the per-carrier inequalities of 2a over $h$ with error proportional to the number of carriers;
   - uses a per-cell return probability or a per-level anti-concentration bound against an arbitrary background, which is false by the sibling counterexample;
   - treats a frozen deterministic background as arbitrary when it in fact needs the unit-variance mean structure.
4. **Steps 2b, 2c, 2e.** For 2b, check that the Rademacher family has no bad directions and that the sibling Steps 9–10 integrate as stated. For 2c, check the Bernstein bound over blocks, the level grid spaced $O(1)$ in tilt (hence uniform in $r$), and the MLR lemma.
5. **Steps 3–5.** Compare with the sibling Steps 5–7, 10 and 11. Check the class assignment in $\mathfrak B$, and that only nonnegativity of the background count is used besides (212). Then:
   - KB gives, by (205)–(206) and $(1-r)/\sqrt{1-r^2}\le1$, a central bound of $U/(2\sqrt{2\pi})+o(U)$ per null with $0<r\le3/5$;
   - B2, B3 and B4-a cover the remaining pieces, so $C_i(q)\le U/(2\sqrt{2\pi})+\eta_4U$.
6. **Steps 7–9.** Check the shell lemma's coupling, the identity $\mathbb P(|Z_g|>U_g)=qw_g$, and the sum
   $$
   \operatorname{FDR}\le q(\pi_0-W)+\sum_g\big[qw_g+qw_g(C_*+2\log(1/w_g))\big],\qquad W=\sum_gw_g\le\pi_0,
   $$
   with $C_*=\sup_iC_i(q)$.
7. **Steps 10–11.** B6′ gives G2 for all $G_0$.
8. **Part IV.** C2 extends G2 to $\mathfrak B^{\rm mult}$, so $\mathfrak S(q)\le(1+\eta)qU/(2\sqrt{2\pi})+Cq$. C3 and A1(d) then give
   $$
   \operatorname{FDR}=q\pi_0+\frac qN\sum_i\Delta_i\le q\pi_0+(1+\eta)\frac{qU}{2\sqrt{2\pi}}+Cq+\eta_3qU+C_3q\le(1+\eta')\frac{qU}{2\sqrt{2\pi}}+C'q .
   $$
   (Here $q\pi_0\le q$.)
9. **A0.** It gives $qU/(2\sqrt{2\pi})\le\frac{1+o(1)}{2\sqrt\pi}q\sqrt{\log(1/q)}$ and $C'q=o(q\sqrt{\log(1/q)})$. Hence, for every $\varepsilon>0$, $\operatorname{FDR}\le(1/(2\sqrt\pi)+\varepsilon)q\sqrt{\log(1/q)}$ for all $q<q_\varepsilon$, uniformly in $N,\theta,\Sigma$. This is the unchanged target and the only conclusion.
10. **Uniformity audit.** At every step confirm that no constant depends on:
    - $N$, $G$, $G_0$, $d$, block sizes, loadings or $\theta$;
    - $r$, outside the explicit $r$-dependence of $\rho_r$.

    Confirm also that every $\eta(q)$ is a function of $q$ alone.

## Assumed definitions

- All definitions used are approved:
  - gaussian_multiple_testing_model;
  - gaussian_test_pvalues;
  - benjamini_hochberg_step_up;
  - false_discovery_rate;
  - gaussian_worst_case_bh_fdr;
  - gaussian_one_common_factor_model, used to describe $\mathfrak B$ with $G=1$.
- No draft asset and no unproved statement is assumed. The draft asset lei2026_two_sided_common_factor_upper is not cited: its source lemmas are re-proved (step 3 and Part II). The draft lei2026_two_sided_fdr_lower is used only as test T1.
- The sibling results are approved only in the sibling project. Every step that uses them reproduces their proofs (steps 2b, 3, 4, 5, 7, 8, 9).

## Adapted from

- **lei2026_two_sided_common_factor_upper** (source: `lei2026_gaussian_bh`, Section 4.2.2, pp. 62–82).
  - Kept as stated: Lemma 4.3 (B3), Lemma 4.4 (Part II), the rank lemma 4.8 and the good event (278) (B3).
  - Lemma 4.5 becomes step 3(a). The lower bound is used at one point only, and the upper bounds come from (212) for the total count, so the background needs only to be nonnegative.
  - Lemma 4.6 becomes step 3(b), adapted to L-atoms with variance in $[1-\tau^2,1]$, including background coordinates.
  - Lemma 4.7 is replaced by steps 4–5: the H class, absent from Lei's one-factor model, is new.
- **lei2026_conditional_fdp_bound** and **lei2026_integrated_conditional_tail_ratios.** Re-proved in B1 and B3 (Part II), exactly as in the failed plan.
- **Sibling twosided_kfactor_sharp_upper** (`/Users/xiaosheng/Desktop/Research/Lihua_conjecture_claude/BH_FDR_Claude_Independent/research/assets/twosided_kfactor_sharp_upper.md`).
  - Hypotheses that transfer: $\mathfrak B$ is a $G$-factor model with $b_\ell=a_\ell e_{g(\ell)}$, unit diagonal, two-sided nulls with $\theta_i=0$.
  - Steps 1–7, 9 and 10 are reproduced; $K_q$ becomes $8\log U$ (step 3).
  - Step 2 (the $\chi^2_K$ shell) is replaced by the entropy truncation (steps 7–9).
  - Step 8 (blocking with a random direction on $S^{K-2}$, direction count $a_K\vartheta$) is replaced by coordinate blocking (2a), Rademacher directions (2b), light-block rigidity (2c) and the KEY core (2d).
- **Sibling twosided_kfactor_growing_sharp_upper** (same folder). Used only as a cross-check of the constants in 2b, through its Step 8 "free window" form.
- **Sibling onesided_direction_entropy_upper** (same folder). Steps 2–6 (group levels $U_g$, group cap, coupling shell, assembly) are adapted to two-sided p-values. Lemma 6′ becomes the two-sided shell lemma of step 7, with constant $2$. The per-null central bound comes from step 5, not from the one-sided Lemma 5.

## Difference from failed plans

- **plan_two_sided_exogenous_pivotal_blocks_20261105.**
  - That plan's B4 asked for a per-$z_{-g}$ exclusion with the frozen background as an arbitrary deficit; the supremum form of that exclusion is false (its B4-b).
  - Here the background enters only through Gaussian averages over its factors $x$, split into L-atoms (rigid in every fiber) and H-atoms (coordinate-aligned and $\zeta$-free).
  - The new KEY is the H-step for many blocks (2d), with exact coordinate blocking on both signs (2a) and two proved gates (2b, 2c).
  - Its B5 is replaced by the entropy truncation (step 9), so the joint B6′ is needed only for exponentially many null blocks.
  - The error budget is $o(U)$.
- **plan_two_sided_fixed_label_blocks_20261104.** No covariance or nuclear-norm certificate. All bounds use actual BH ranks and conditional tail ratios.
- **plan_two_sided_null_noise_folded_completion_20261104.** No null-noise interpolation and no SDP relaxation over correlation matrices. T7 is a test only.
- **plan_two_sided_reflection_paired_stein_capacity_20261104.** No LP or Stein-capacity certificate. Reflection enters only through Lei's A-class exclusion and the sign-free H-blocking.
- **plan_two_sided_signed_face_budget_20261104.** No signed face formula and no rank-tail differences. Concentration is dimension-free (Lei 4.8, and Bernstein over blocks).
- **plan_two_sided_rotation_pooled_arc_transport_20261104.** No Gaussian rotation and no transport ledger. The "shift" in 2a is a deterministic exclusion along one factor coordinate, not a coupling of rank layers.
- **plan_two_sided_signed_forest_rank_cells_20261104.** No cluster expansion. No error proportional to $|J|/N$ times a growing factor, as T3 and (R4) require.

**Sibling project (not a failed plan here).**
- Its one-sided block route failed at a per-cell window lemma, which is refuted, and at a pooled carrier level-sum (draft, unproved).
- Our KEY step 2d differs:
  - it is a two-sided per-null blocking inequality in Gaussian measure over the background factors;
  - it uses exact coordinate alignment and the $\zeta$-independence of H-mass, which block it on both signs;
  - it needs neither a return probability nor a pooled level sum.
- Its approved two-sided $K$-factor and entropy results are reused, with proofs reproduced, as steps 2b, 3–5 and 7–9.
