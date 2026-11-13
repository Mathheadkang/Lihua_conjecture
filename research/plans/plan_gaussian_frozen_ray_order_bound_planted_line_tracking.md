---
type: plan
title: >-
  Frozen-ray order bound via planted lines: scale-window change of measure,
  convexity along the planted line, and the spread-posterior remainder
status: failed
target_asset: gaussian_frozen_ray_order_bound
inspired_by:
  - idea_2bb31516b09b
  - idea_27baeafdd0f3
  - idea_6d87d51a889d
---

## Goal

Target: [asset](../assets/gaussian_frozen_ray_order_bound.md).

Prove $\mathbb E\min\{c,\Lambda(Z)\}\leq C_{\mathrm{FR}}\sqrt{\log c}$ for every $c\geq2$, uniformly in $n$, $\Sigma\in\mathcal C_n$ (singular allowed, either sign), and subprobability weights. The statement is not changed.

Idea. The heuristic of idea_2bb31516b09b (sup over $w$ is comparable to an average over a unit $w$-window, because $\partial_w^2\log L_w\geq-1$) loses a factor $\sqrt{\log c}$ when combined with Lehec's tail, because the window position $\hat w$ is random. This plan does not use Lehec's theorem. It uses the window only to change measure. The Cameron-Martin shift then turns $\mathbb E[\Lambda;\cdot]$ into an integral over planted lines $a\mapsto Z+a\Sigma_{\cdot i}$ of a tracking event $\{|\hat w-a|\leq1\}$. Along each planted line, $\log\Lambda$ is convex, and its slope is $\hat w$ times the posterior alignment $\alpha_i$ with the planted direction. So the tracking set is short (length $O(\sqrt{\log c})$) wherever the posterior is aligned. Only the spread-posterior (misaligned) part remains, and it is the single hard step (step 7). This keeps the common scale $w$ that idea_6d87d51a889d says must not be lost: $\hat w$ is the shared maximizer throughout.

## Notation

Write $|\omega|=\sum_i\omega_i$. If $|\omega|=0$ then $\Lambda\equiv0$ and there is nothing to prove, so assume $|\omega|\in(0,1]$. For $x\in\mathbb R^n$ and $a\geq0$, $L_a(x)=\sum_i\omega_ie^{ax_i-a^2/2}$. The posterior at scale $a$ is $p^{(a)}_j(x)=\omega_je^{ax_j}/\sum_k\omega_ke^{ax_k}$. Let $\hat w(x)$ be the largest maximizer of $a\mapsto L_a(x)$ on $[0,\infty)$, so $\Lambda(x)=L_{\hat w(x)}(x)$. Write $p_j(x)=p^{(\hat w(x))}_j(x)$ and $\alpha_i(x)=\sum_jp_j(x)\Sigma_{ji}\in[-1,1]$; this is the posterior alignment with direction $i$. Put $Z^{i,a}=Z+a\Sigma_{\cdot i}$, where $\Sigma_{\cdot i}$ is the $i$-th column. Let $h(x)=\min\{1,c/\Lambda(x)\}\mathbf 1\{\Lambda(x)>1\}$.

## Plan

1. [x] **Shift identity.** For every Borel $F\geq0$ on $\mathbb R^n$, $i\in[n]$ and $a\in\mathbb R$: $\mathbb E[e^{aZ_i-a^2/2}F(Z)]=\mathbb E[F(Z+a\Sigma_{\cdot i})]$. Proof: write $Z=AG$ with $AA^{\mathsf T}=\Sigma$ and $G\sim\mathcal N(0,I_n)$. Then $Z_i=\langle A^{\mathsf T}e_i,G\rangle$ with $|A^{\mathsf T}e_i|^2=\Sigma_{ii}=1$. The Cameron-Martin formula for $G$ with shift $aA^{\mathsf T}e_i$ moves $Z$ by $aAA^{\mathsf T}e_i=a\Sigma_{\cdot i}$. This works for singular $\Sigma$.
2. [x] **Scale profile.** For fixed $x$: (a) $L_a(x)=\sum_i\omega_ie^{x_i^2/2}e^{-(a-x_i)^2/2}\to0$ as $a\to\infty$, so maximizers exist, the set of maximizers is compact, and $\hat w$ is upper semicontinuous, hence Borel. (b) $g(a)=\log L_a(x)$ has $g''(a)=\operatorname{Var}_{p^{(a)}}(x_J)-1\geq-1$. (c) If $\Lambda(x)>1$ then $\hat w(x)>0$, because $L_0=|\omega|\leq1$. Then $g'(\hat w)=0$, so $g(a)\geq g(\hat w)-(a-\hat w)^2/2$ for all $a\geq0$. Hence $c_0\Lambda(x)\leq\int_{\hat w}^{\hat w+1}L_a(x)\,da\leq\int_{I(x)}L_a(x)\,da$, with $I(x)=[\hat w-1,\hat w+1]\cap[0,\infty)$ and $c_0=\int_0^1e^{-u^2/2}du>0.85$.
3. [x] **Planted-line reduction.** From $\min\{c,\Lambda\}\leq1+\Lambda h$, step 2(c), Tonelli and step 1 with $F(x)=\mathbf 1\{|\hat w(x)-a|\leq1\}h(x)$:
$$
\mathbb E\min\{c,\Lambda(Z)\}\leq1+c_0^{-1}\sum_i\omega_i\,\mathbb E\int_{T_i(Z)}\min\{1,c/\Lambda(Z^{i,a})\}\,da,
$$
where $T_i(z)=\{a\geq0:|\hat w(z+a\Sigma_{\cdot i})-a|\leq1,\ \Lambda(z+a\Sigma_{\cdot i})>1\}$ is the tracking set of the planted line. Check joint measurability of $(z,a)\mapsto\hat w(z+a\Sigma_{\cdot i})$ from step 2(a).
4. [x] **Convexity along a planted line.** For fixed $z,i$, the function $\varphi(a)=\log\Lambda(z+a\Sigma_{\cdot i})$ is finite and convex on $\mathbb R$: it is a supremum over $b$ of the log-sum-exp functions $a\mapsto\log L_b(z+a\Sigma_{\cdot i})$, which are convex in $a$. Moreover, with $x=z+a\Sigma_{\cdot i}$, for all $a'$:
$$
\varphi(a')\geq\log L_{\hat w(x)}(z+a'\Sigma_{\cdot i})\geq\varphi(a)+(a'-a)\,\hat w(x)\,\alpha_i(x),
$$
because the derivative of $t\mapsto\log L_{\hat w(x)}(z+t\Sigma_{\cdot i})$ at $t=a$ is $\hat w\sum_jp_j\Sigma_{ji}$. So $\hat w\alpha_i\leq\varphi'_+(a)$, and $\varphi'_+$ is nondecreasing.
5. [x] **Aligned tracking is short (pathwise).** Fix $\theta\in(0,1]$ and let $A^+_i(z)=\{a\in T_i(z):\alpha_i(z+a\Sigma_{\cdot i})\geq\theta\}$. Claim: $\int_{A^+_i(z)}\min\{1,ce^{-\varphi(a)}\}da\leq2+\theta^{-1}+\sqrt{8\log c/\theta}$ for every $z$.
   Proof. Put $A=A^+_i\cap[2,\infty)$. For $a\in A$, $\hat w\geq a-1\geq a/2$, so by step 4, $\varphi'_+(a)\geq\theta a/2\geq\theta$. Hence $\varphi$ is increasing after $a_0=\inf A$, with slope $\geq\theta$, and $\{a\geq a_0:\varphi(a)\geq\log c\}=[R,\infty)$.
   - On $A\cap[a_0,R)$, of measure $\ell$: choose $a_1\in A$ after which $A\cap[a_1,R)$ still has measure about $\ell/2$. Then $a_1\geq2+\ell/2$, so the slope is at least $\theta\ell/4$ on a stretch of length about $\ell/2$. Since $0<\varphi<\log c$ there, $\theta\ell^2/8\leq\log c$.
   - Beyond $R$: $\varphi(a)\geq\log c+\theta(a-R)$, so $\int_R^\infty ce^{-\varphi}\leq\theta^{-1}$.
6. [x] **Null-side form of the misaligned part.** Let $B_\theta=\sum_i\omega_i\mathbb E\int_{T_i(Z)\setminus A^+_i(Z)}\min\{1,c/\Lambda(Z^{i,a})\}da$. Apply step 1 backwards; the condition on $Z^{i,a}$ becomes the same condition on $Z$. This gives
$$
B_\theta=\mathbb E\Big[h(Z)\int_{I(Z)}\sum_{i:\alpha_i(Z)<\theta}\omega_ie^{aZ_i-a^2/2}\,da\Big].
$$
   Then bound $B_\theta\leq C\,\mathbb E[\min\{c,\Lambda\}\,\pi_\theta(Z)\mathbf 1\{\Lambda>1\}]$. Here $\pi_\theta$ is the posterior mass, maximized over $a\in I(Z)$, of $\{i:\alpha_i(Z)<\theta\}$. By Markov applied to $1-\alpha_J\geq0$ under $p$, this mass at $a=\hat w$ is at most $(1-Q)/(1-\theta)$, where $Q=p^{\mathsf T}\Sigma p$ is the posterior self-overlap. Record the exact constant, including the comparison of $p^{(a)}$ with $p$ over the window.
7. [ ] **Spread-posterior bound (main step).** Show $B_\theta\leq C(1+\sqrt{\log c})$ for one fixed $\theta$ (say $\theta=1/2$). Route:
   - (i) Layer $T_i\setminus A^+_i$ by dyadic alignment $\alpha_i\in[\beta,2\beta)$, $\beta=\theta2^{-k-1}$, plus the layer $\alpha_i\leq0$. Step 5's proof gives tracking length $O(1+\beta^{-1}+\sqrt{\log c/\beta})$ on layer $\beta$. Because $\varphi'_+$ is monotone, all layers along one line share the same budget $\varphi\leq\log c$; state and prove the shared form, i.e. the joint constraint on the layer lengths.
   - (ii) Show that tracking at alignment $\beta$ has probability $O(\sqrt\beta)$. Use the implicit-function formula at a strict maximum, $\partial_t\hat w(x+t\Sigma_{\cdot k})=(\alpha_k+\hat w\operatorname{Cov}_p(x_J,\Sigma_{Jk}))/\kappa$ with $\kappa=1-\operatorname{Var}_p(x_J)\in(0,1]$. Apply Gaussian one-dimensional anticoncentration of $\hat w(Z^{i,a})-a$ along the posterior-mean direction $\sum_jp_j\Sigma_{\cdot j}$. Average over the planted index: under the change of measure, $I$ given the data is distributed by the posterior, so the average of $\alpha_I$ is $Q$.
   - (iii) Sum the layers with the shared budget from (i), not layer by layer: a layer-by-layer sum loses a factor $\sqrt{\#\text{layers}}$.
   - The test case any argument must reproduce: directions $\sqrt q\,u+\sqrt{1-q}\,e_j$ with orthonormal $e_j\perp u$ and uniform tiny weights. There all tracking is misaligned ($\alpha\approx q$). Along each line the tracking set is empty or has length about $\sqrt{2\log c/q}$, with probability about $\sqrt q$, and the product is $\sqrt{\log c}$. Also check the orthogonal small-weight family: there the tracking set has length $O(1)$ below $\sqrt{2\log n}$ because $\hat w$ does not move with $a$.
8. [ ] **Combine.** Steps 3, 5, 7: $\mathbb E\min\{c,\Lambda\}\leq1+c_0^{-1}\big(2+\theta^{-1}+\sqrt{8\log c/\theta}+C(1+\sqrt{\log c})\big)\leq C_{\mathrm{FR}}\sqrt{\log c}$ for $c\geq2$, using $\sqrt{\log c}\geq\sqrt{\log2}$.

## Verification

Steps 1 to 6 are exact or elementary: Cameron-Martin, the scale semi-convexity $g''\geq-1$, Tonelli, convexity of log-sum-exp, and a measure-of-sublevel-set argument for a convex function. They hold for every $n$, every $\Sigma\in\mathcal C_n$ including singular $\Sigma$ and negative correlations, and every subprobability weight vector. Every constant ($c_0$, $\theta$, and those of step 5) is absolute. Step 3 bounds $\mathbb E\min\{c,\Lambda\}$ by $1$ plus the planted-line tracking integral. That integral splits into the aligned part (step 5, at most $2+\theta^{-1}+\sqrt{8\log c/\theta}$ pathwise, hence also after $\sum_i\omega_i\mathbb E$ since $|\omega|\leq1$) and the misaligned part $B_\theta$ (steps 6 and 7). Step 8 is then the exact statement, with $C_{\mathrm{FR}}$ independent of $n$, $\Sigma$, rank, weights, total mass and $c$.

All the difficulty is in step 7. If step 7 fails, the executed steps 1 to 6 still give the unconditional reduction $\mathbb E\min\{c,\Lambda\}\leq C(1+\sqrt{\log c})+C\,\mathbb E[\min\{c,\Lambda\}(1-Q)]$, which should be recorded. In words: the frozen-ray order bound holds up to the contribution of realizations where the posterior at the maximal scale is spread (self-overlap $Q$ bounded away from $1$). That is the precise residual for the next plan. Failure criterion for step 7: a family where the misaligned tracking integral exceeds $\sqrt{\log c}$ by an unbounded factor. Because of step 2(c) and the reverse window bound $\int_IL_a\leq2\Lambda$, the tracking integral is comparable to $\mathbb E\min\{c,\Lambda\}$ up to absolute constants, so such a family would also be a counterexample to the target. Check the multiscale and hierarchical families the falsification check left unexplored.

## Assumed definitions

- [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md) (approved): only the class $\mathcal C_n$ and the Gaussian law with possibly singular covariance.
- No unproved dependency is assumed. The approved Lehec tail results are not used; the window enters only as a change of measure.

## Failure

**Where it fails.** Step 7, the spread-posterior bound. Steps 1 to 6 are proved below. They give an unconditional reduction of the target to the misaligned part $B_\theta$. Route 7(i)-(iii) cannot bound $B_\theta$ as written, for two reasons.

- **7(ii) is false as stated.** Take $\Sigma=I_n$ and $\omega_i=1/n$. Then $\alpha_i(x)=p_i(x)$, which is typically of order $1/n$ in the high-temperature regime. Yet the tracking event at $a=\hat w(Z)$ happens with probability bounded below. A simulation with $200$ samples per $n$, a grid of $w$-step $0.005$ on $[0,8]$, and $i$ uniform gave the following. The fraction of samples with $\Lambda(Z)>1$, $\Lambda(Z^{i,a})>1$ and $|\hat w(Z^{i,a})-a|\le1$ at $a=\hat w(Z)$ was $0.63$, $0.72$, $0.75$ for $n=10^3,10^4,10^5$. The median of $\alpha_i(Z^{i,a})$ on that event was $3\cdot10^{-3}$, $6\cdot10^{-4}$, $1.4\cdot10^{-4}$. So tracking at alignment $\beta\to0$ has probability of order $1$, not $O(\sqrt\beta)$.
- **The layer lengths of 7(i) cannot be summed.** On a layer of alignment $\beta$, step 5's argument bounds the tracking length by $O(1+\beta^{-1}+\sqrt{\log c/\beta})$, which blows up as $\beta\to0$. In the orthogonal family the true length is $O(1)$. The reason is different: $\hat w$ does not move with $a$ ($\partial_a\hat w\approx0$). Convexity of $\varphi$ does not see this. Multiplying any bound of the form (i) by any true probability therefore diverges as $\beta\to0$.

The orthogonal family does not contradict the target: there $B_\theta=O(1)$. Nothing found here contradicts the target.

**What would be needed.** A bound on $B_\theta$ that uses the mobility of $\hat w$ along the planted line, not the alignment alone. At a nondegenerate maximum, the implicit-function formula gives $\partial_a\hat w(Z^{i,a})=(\alpha_i+\hat w\operatorname{Cov}_p(x_J,\Sigma_{Ji}))/\kappa$ with $\kappa=1-\operatorname{Var}_p(x_J)$. The tracking set is short, of length about $2/|1-\partial_a\hat w|$, unless $\partial_a\hat w\approx1$. Long tracking at small alignment happens, as in the $\sqrt q\,u+\sqrt{1-q}\,e_j$ family, only when $\partial_a\hat w\approx1$. One would need to show that this event has probability $O(\sqrt\beta)$ with length $O(\sqrt{\log c/\beta})$. One must also handle the degenerate maxima ($\kappa\to0$, where $\hat w$ jumps between local maxima), which the formula does not cover. A lemma of this kind, stated for $B_\theta$ directly, is the open step. A different reduction that avoids the window is recorded as an idea: an upcrossing (co-area) bound $\min\{c,\Lambda\}-1\le\int_0^\infty(\partial_wL_w)_+\mathbf 1\{1<L_w<c\}\,dw$, which is exact when $w\mapsto L_w$ is unimodal.

### Proved partial reduction (steps 1 to 6)

Throughout, $|\omega|\in(0,1]$. Indices with $\omega_i=0$ are dropped from all sums and posteriors. $\|x\|_\infty=\max_i|x_i|$.

**Step 1 (shift identity).** Let $A=\Sigma^{1/2}$ be the symmetric positive semidefinite square root, and let $G\sim\mathcal N(0,I_n)$. Then $AG\sim\mathcal N_n(0,\Sigma)$, so expectations of functionals of $Z$ may be computed with $Z=AG$. Put $v=Ae_i$. Then $Z_i=\langle v,G\rangle$ and $|v|^2=e_i^{\mathsf T}\Sigma e_i=1$. For Borel $\tilde F\geq0$ on $\mathbb R^n$, the change of variables $g\mapsto g+av$ in the standard Gaussian density, with $\phi_n(g-av)/\phi_n(g)=e^{a\langle v,g\rangle-a^2/2}$, gives $\mathbb E[e^{a\langle v,G\rangle-a^2/2}\tilde F(G)]=\mathbb E[\tilde F(G+av)]$. With $\tilde F=F\circ A$ and $A(G+av)=Z+aA^2e_i=Z+a\Sigma_{\cdot i}$, this is $\mathbb E[e^{aZ_i-a^2/2}F(Z)]=\mathbb E[F(Z^{i,a})]$. Singular $\Sigma$ needs no special care.

**Step 2 (scale profile).**
(a) For every $a\geq0$, $L_a(x)\leq|\omega|e^{a\|x\|_\infty-a^2/2}$. This is $<|\omega|=L_0(x)$ for $a>2\|x\|_\infty$. Hence every maximizer of the continuous function $a\mapsto L_a(x)$ on $[0,\infty)$ lies in $[0,2\|x\|_\infty]$. The maximizer set is compact and nonempty, and $\hat w(x)$, its largest element, is well defined. On $\{\|x\|_\infty<R\}$ we have $\Lambda(x)=\max_{a\in[0,2R]}L_a(x)$, a maximum over a compact set of a jointly continuous function, so $\Lambda$ is continuous. For $t\geq0$ let $g_t(x)=\sup_{a\geq t}L_a(x)$; it is lower semicontinuous as a supremum of continuous functions. We claim $\{\hat w\geq t\}=\{g_t-\Lambda\geq0\}$. If $\hat w\geq t$ then $g_t\geq\Lambda$. Conversely, if $g_t(x)\geq\Lambda(x)>0$, the supremum over $[t,\infty)$ is attained, because $L_a\to0$ as $a\to\infty$. The point where it is attained is a maximizer $\geq t$. Since $g_t-\Lambda$ is lower semicontinuous, $\{g_t-\Lambda\geq0\}=\bigcap_k\{g_t-\Lambda>-1/k\}$ is a $G_\delta$ set, so $\hat w$ is Borel. Consequently $(z,a)\mapsto\hat w(z+a\Sigma_{\cdot i})$ is jointly Borel. So is $p_j(x)=p^{(\hat w(x))}_j(x)$, a continuous function of $(x,\hat w(x))$, and so is $\alpha_i(x)$.
(b) $g(a)=\log L_a(x)=\log\sum_j\omega_je^{ax_j}-a^2/2$. Then $g'(a)=\mathbb E_{p^{(a)}}x_J-a$ and $g''(a)=\operatorname{Var}_{p^{(a)}}(x_J)-1\geq-1$.
(c) If $\Lambda(x)>1\geq|\omega|=L_0(x)$, then $\hat w>0$ is an interior maximizer, so $g'(\hat w)=0$. Taylor's formula with $g''\geq-1$ gives $g(a)\geq g(\hat w)-(a-\hat w)^2/2$, that is, $L_a(x)\geq\Lambda(x)e^{-(a-\hat w)^2/2}$. Integrating over $[\hat w,\hat w+1]\subset I(x)$ gives $c_0\Lambda(x)\leq\int_{I(x)}L_a(x)\,da$, with $c_0=\int_0^1e^{-u^2/2}du=\sqrt{2\pi}(\Phi(1)-\tfrac12)>0.85$. Conversely, $\int_{I(x)}L_a\,da\leq2\Lambda(x)$, since $|I(x)|\leq2$ and $L_a\leq\Lambda$.

**Step 3 (planted-line reduction).** If $\Lambda\leq1$ then $\min\{c,\Lambda\}\leq1$; if $\Lambda>1$ then $\Lambda h=\min\{c,\Lambda\}$. Hence $\min\{c,\Lambda\}\leq1+\Lambda h$. By step 2(c),
$$
\Lambda(Z)h(Z)\leq c_0^{-1}\int_0^\infty\mathbf 1\{|\hat w(Z)-a|\leq1\}h(Z)L_a(Z)\,da=c_0^{-1}\sum_i\omega_i\int_0^\infty e^{aZ_i-a^2/2}F_a(Z)\,da,
$$
where $F_a(x)=\mathbf 1\{|\hat w(x)-a|\leq1\}h(x)$. This is jointly Borel in $(x,a)$ by step 2(a), and $h$ is Borel because $\Lambda$ is continuous. Tonelli's theorem and step 1 give
$$
\mathbb E\min\{c,\Lambda(Z)\}\leq1+c_0^{-1}\sum_i\omega_i\int_0^\infty\mathbb E F_a(Z^{i,a})\,da=1+c_0^{-1}\sum_i\omega_i\,\mathbb E\int_{T_i(Z)}\min\{1,c/\Lambda(Z^{i,a})\}\,da .
$$

**Step 4 (convexity along a planted line).** Fix $z$ and $i$. For $b\geq0$, the function $\psi_b(a)=\log L_b(z+a\Sigma_{\cdot i})=\log\sum_j\omega_je^{bz_j+ab\Sigma_{ji}}-b^2/2$ is a log-sum-exp of affine functions of $a$, hence convex and $C^1$, with $\psi_b'(a)=b\sum_jp^{(b)}_j(z+a\Sigma_{\cdot i})\Sigma_{ji}$. The function $\varphi=\sup_b\psi_b$ is finite and convex. Fix $a$, put $x=z+a\Sigma_{\cdot i}$ and $b=\hat w(x)$. Then $\psi_b(a)=\varphi(a)$ and $\psi_b\leq\varphi$, so $\varphi(a')\geq\psi_b(a')\geq\varphi(a)+(a'-a)\hat w(x)\alpha_i(x)$ for all $a'$. Letting $a'\downarrow a$ gives $\varphi'_+(a)\geq\hat w(x)\alpha_i(x)$. The right derivative $\varphi'_+$ of a convex function is nondecreasing and right-continuous.

**Step 5 (aligned tracking is short, pathwise).** Fix $\theta\in(0,1]$, $z$ and $i$, and write $A=A^+_i(z)\cap[2,\infty)$. The part of $A_i^+(z)$ in $[0,2)$ contributes at most $2$. Let $a\in A$. Then $\hat w(z+a\Sigma_{\cdot i})\geq a-1\geq a/2$ and $\alpha_i\geq\theta$, so step 4 gives $\varphi'_+(a)\geq\theta a/2$. Also $\varphi(a)>0$, since $a\in T_i$. Assume $A\neq\emptyset$ and let $a_0=\inf A\geq2$. Choose $a_k\in A$ with $a_k\downarrow a_0$. Right-continuity gives $\varphi'_+(a_0)\geq\theta a_0/2\geq\theta$, and monotonicity gives $\varphi'_+\geq\theta$ on $[a_0,\infty)$. Let $R=\inf\{a\geq a_0:\varphi(a)\geq\log c\}$. Then $\varphi\geq\log c+\theta(a-R)$ for $a\geq R$, so $\int_{[R,\infty)}\min\{1,ce^{-\varphi}\}\,da\leq\int_R^\infty e^{-\theta(a-R)}da=\theta^{-1}$. Let $\ell=|A\cap[a_0,R)|$ and suppose $\ell>0$. Choose $a_1$ with $|A\cap[a_0,a_1)|=\ell/2$; then $a_1\geq a_0+\ell/2\geq2+\ell/2$. Let $a'=\inf(A\cap[a_1,R))$. By right-continuity along a sequence in $A$ decreasing to $a'$, $\varphi'_+(a')\geq\theta a'/2\geq\theta(2+\ell/2)/2\geq\theta\ell/4$, and $\varphi(a')\geq0$ by continuity. Since $A\cap[a_1,R)\subset[a',R)$, we have $R-a'\geq\ell/2$. Hence $\log c\geq\varphi(R)\geq\varphi(a')+\frac{\theta\ell}{4}\cdot\frac\ell2\geq\theta\ell^2/8$. Here $\varphi(R)=\log c$ by continuity when $R>a_0$; if $R=a_0$ then $\ell=0$. So $\ell\leq\sqrt{8\log c/\theta}$, and
$$
\int_{A^+_i(z)}\min\{1,ce^{-\varphi(a)}\}\,da\leq2+\theta^{-1}+\sqrt{8\log c/\theta}\qquad\text{for every }z .
$$
Since $|\omega|\leq1$, the aligned part of the bound in step 3 is at most $2+\theta^{-1}+\sqrt{8\log c/\theta}$.

**Step 6 (null-side form of the misaligned part).** Apply step 1 backwards with the jointly Borel function $F_a(x)=\mathbf 1\{|\hat w(x)-a|\leq1,\ \Lambda(x)>1,\ \alpha_i(x)<\theta\}\min\{1,c/\Lambda(x)\}$, and use Tonelli:
$$
B_\theta=\mathbb E\Big[h(Z)\int_{I(Z)}\sum_{i:\alpha_i(Z)<\theta}\omega_ie^{aZ_i-a^2/2}\,da\Big]
=\mathbb E\Big[h(Z)\int_{I(Z)}L_a(Z)\,p^{(a)}(S_\theta)\,da\Big],
$$
where $S_\theta=\{i:\alpha_i(Z)<\theta\}$. The posteriors $p^{(a)}$ and $p=p^{(\hat w)}$ are not uniformly comparable across the window, since $p^{(a)}_j/p_j\propto e^{(a-\hat w)x_j}$ with $x_j$ unbounded. So the window-averaged mass is used instead. Markov's inequality applied to $1-\alpha_J\geq0$ (recall $|\Sigma_{kj}|\leq1$) under $p^{(a)}$ gives
$$
p^{(a)}(S_\theta)\leq\frac{1-Q(a)}{1-\theta},\qquad Q(a)=\sum_jp^{(a)}_j\alpha_j(Z)=(p^{(a)})^{\mathsf T}\Sigma\,p\in[-1,1].
$$
Put $\bar Q=\int_IL_aQ(a)\,da/\int_IL_a\,da$, the $L$-weighted window average of the cross-overlap; then $1-\bar Q\geq0$. For $\theta\in(0,1)$, step 2(c) gives $h\int_IL_a\,da\leq2h\Lambda=2\min\{c,\Lambda\}\mathbf 1\{\Lambda>1\}$, and hence
$$
B_\theta\leq\frac{2}{1-\theta}\,\mathbb E\big[\min\{c,\Lambda(Z)\}\,(1-\bar Q(Z))\,\mathbf 1\{\Lambda(Z)>1\}\big].
$$
At $a=\hat w$, $Q(\hat w)=p^{\mathsf T}\Sigma p$ is the posterior self-overlap.

**Recorded reduction.** For every $c\geq2$, every $\theta\in(0,1)$, every $n$, every $\Sigma\in\mathcal C_n$ and every subprobability $\omega$,
$$
\mathbb E\min\{c,\Lambda(Z)\}\leq1+c_0^{-1}\Big(2+\theta^{-1}+\sqrt{8\log c/\theta}\Big)+c_0^{-1}B_\theta,
$$
with $B_\theta$ given exactly by the formula of step 6 and bounded by $\frac{2}{1-\theta}\mathbb E[\min\{c,\Lambda\}(1-\bar Q)\mathbf 1\{\Lambda>1\}]$. With $\theta=1/2$ the first part is at most $1+c_0^{-1}(4+4\sqrt{\log c})$. Thus the frozen-ray order bound holds up to the misaligned planted-line mass $B_{1/2}$. That mass is controlled by realizations where the window-averaged cross-overlap $\bar Q$ is bounded away from $1$. The target follows from any bound $B_{1/2}\leq C(1+\sqrt{\log c})$.
